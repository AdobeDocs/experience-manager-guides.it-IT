---
title: Migrazione delle modifiche al framework dell’estensione per Editor 2.0
description: Scopri la migrazione al framework di estensione per Editor 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 75954eab3ac1738705fe2a7280973af39b9214df
workflow-type: tm+mt
source-wordcount: '1904'
ht-degree: 0%

---


# Migrazione del framework dell’estensione all’Editor 2.0 (nuovo Editor)

Questa guida aiuta gli autori delle estensioni a comprendere cosa c&#39;è da fare per spostare le personalizzazioni dal **vecchio editor** al **nuovo editor** in AEM Guides, in modo che possano pianificare la transizione senza problemi e con il minimo disagio.

>[!IMPORTANT]
> 
> Se disponi di un’estensione AEM Guides (Old Editor) esistente, che include voci di menu di scelta rapida personalizzate, pulsanti della barra degli strumenti, finestre di dialogo, logica degli attributi o dei metadati o stile del contenuto, questa guida ti aiuta a mantenerla funzionante con il nuovo editor.

## Panoramica

- **La registrazione non cambia**: continua a utilizzare `window.extension` / `tcx.extension.register`.
- **L&#39;area di lavoro dell&#39;editor è una nuova superficie.** Le voci del menu di scelta rapida devono dichiarare il nuovo ID widget
  `markup_editor_menu`; il comportamento nell&#39;editor deve interrompere il tocco del DOM.
- **Interrompere la lettura/scrittura del DOM**: sostituire l&#39;accesso DOM `tcx.curEditor.*` con
  API `guides.editor`: [leggi con `runUtil(...)`](#migrate-reads-dom-runutil), [scrivi con `runCommand(...)`](#migrate-writes-dom-mutation-runcommand), [stile con decorazioni](#migrate-rendering-only-logic-dom-paint-decorations) ed [esegui azioni globali (salva) tramite eventi app](#migrate-global-actions-savefocus-app-events).
- **I menu della shell dell&#39;app (repository, visualizzatore di mappe, file/cartella) sono invariati**: vengono comunque eseguiti
il framework legacy.
- **Entrambi gli editor coesistono**: entrambi i tipi di destinazione devono essere impostati su array. Quando si caricano **Registra** plug-in in modo incondizionato; cancella solo *runtime* azioni di `guides.editor.version` (che rimane `1.0.0` finché un file non viene aperto, visualizza [Rileva l&#39;editor e avvia in modo sicuro](#detect-the-Editor-and-bootstrap-safely)).


## Perché il cambiamento?

| Criteri | Editor CKE legacy | Nuovo MarkupEditor |
|---|---|---|
| Source della verità | DOM | Documento ProseMirror |
| Selezione | `getSelection()` in un documento radice | Selezione ProseMirror (posizioni/intervalli) |
| Per modificare il contenuto | Mutate attributi/classi DOM | Inviare un comando (transazione) |
| Rendering | DOM è permanente | DOM è un rendering temporaneo in un DOM ombra, ricostruito in qualsiasi momento |
| Attribuzione stile | CSS Page o clientlib | CSS ha inserito DOM shadow tramite il plug-in di registro. Consulta [Hello world: a CSS-only highlight plugin](#hello-world-a-css-only-highlight-plugin) per utilizzare le classi esistenti e aggiungere CSS e [Migrare la logica di solo rendering](#migrate-rendering-only-logic-dom-paint-decorations) per aggiungere una nuova classe e aggiungere stili. |

Qualsiasi estensione che muta il DOM o qualsiasi modifica DOM non viene mantenuta, ma viene eliminata al prossimo rendering. La migrazione è fondamentalmente *passare da DOM-first a model-first*.

## Rilevare l&#39;editor e l&#39;avvio in modo sicuro

L&#39;oggetto `guides` globale è il punto di ingresso per tutte le nuove integrazioni:

```js
guides.editor    // editor interaction APIs
guides.util      // bundled utility libs (lodash, async)
guides.ready(cb) // fires once at app load (view system ready) — before any file is open
```

`guides.editor.version` segnala l&#39;**editor attualmente aperto**, quindi è significativo solo una volta
file effettivamente aperto:

| `guides.editor.version` | Significato |
|---|---|
| `2.0.0` | È aperto un file MarkupEditor (ProseMirror) |
| `1.0.0` | Un file CKEditor legacy è aperto o nessun file è ancora aperto |

>[!IMPORTANT]
>
> Quando si verifica l&#39;evento `guides.ready`, nessun file è stato ancora aperto, quindi `version` segnalerà come `1.0.0` indipendentemente dal fatto che MarkupEditor sia abilitato o meno. Non utilizzare `version` per determinare se i plug-in ottengono *registrazione* (visualizzazione [Registrazione plug-in e controllo runtime](#plugin-registration-and-runtime-gating)). Utilizzalo solo per diramare il comportamento *runtime* e valutarlo nel punto di esecuzione (ad esempio, all&#39;interno di un gestore di menu), dove un file è sicuramente aperto.

### Registrazione del plug-in e verifica runtime

- **Registrazione** (`registerPlugin`, installazione una tantum): eseguilo **incondizionatamente** in `guides.ready`. È un innocuo no-op sull&#39;editor legacy: l&#39;editor legacy non legge mai il registro del plug-in e la fabbrica viene eseguita solo quando un MarkupEditor viene effettivamente costruito. **non** genera.

- **Chiamate runtime** (`runCommand`, `runUtil`, `addDecoration`, ...): il gate per versione esiste e non è uguale a &quot;1.0.0&quot; al momento della chiamata. Non viene attivato l&#39;editor legacy (viene restituito in modo sicuro `false`/`undefined`), ma il controllo evita avvisi di no-op e consente di mantenere un fallback legacy.

```js
guides.ready(() => {
  // Always register — inert on legacy, applied only when a MarkupEditor opens.
  guides.editor.registerPlugin(createMyPlugin);
});

function onMenuClick() {
  if (guides.editor.version && guides.editor.version !== "1.0.0") {
    guides.editor.runCommand('surroundWithElement', 'sup'); // MarkupEditor path
  } else {
    // legacy path (or no-op)
  }
}
```

Passa una **factory** `() => ({ plugin, css })` — a `registerPlugin`, mai un&#39;istanza del plug-in costruita. Una non funzione è l’unico input che rifiuta (genera su entrambi gli editor). Non memorizzare nella cache l&#39;istanza dell&#39;editor; chiamare `guides.editor.*` ogni volta.

### Hello world: un plug-in di evidenziazione solo CSS

L&#39;estensione utile più piccola invia a **only CSS** un plug-in ProseMirror senza funzionalità e stili. Questo
evidenzia ogni elemento `<note>` con uno sfondo giallo all&#39;interno dell&#39;editor:

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no behavior — CSS only
    css: `[data-xml-element="note"] { background: #fff3cd; outline: 1px solid #ffe08a; }`
  }));
});
```

- Ogni elemento viene riprodotto come `data-xml-element="<tag>"`, in modo che sia possibile eseguire il targeting di qualsiasi elemento DITA in questo modo
(`note`, `codeblock`, `section`, `table`, ...).
- CSS **must** da inviare tramite registerPlugin: l&#39;editor risiede in un DOM shadow, pertanto non è possibile utilizzare CSS page/clientlib
raggiungilo.
- Aprire un argomento DITA contenente un `<note>` per vederlo applicato. La registrazione è incondizionata (§2.1),
questo è sicuro anche se `version` è ancora `1.0.0` alle `guides.ready`.


## Inventario dell’estensione (elenco di controllo grep)

```bash
# DOM-first reads that will break
grep -rnE "rootDocument|rootElement|getSelection\(|selectedHtml|selectedText|\.xmlDoc|\.ancestors\b" src

# DOM/legacy writes that will break
grep -rnE "updateAttributes\(|setAttribute\(|classList\.|\.saveFile\(|resetDirty\(|validateRangeForInsertion\(" src

# The editor handle itself
grep -rn "tcx.curEditor" src

# Context-menu targeting + page CSS
grep -rnE "contextMenuWidget|dita_editor_menu|author_outline_element" src
grep -rn "dita_content_overrides" .
```

Ogni hit è un elemento di migrazione. Classifica ciascuno come: *superficie del menu di scelta rapida*, *stato letto*, *contenuto
write*, *azione globale*, *solo rendering* o *CSS*.


## Comune per entrambi i redattori

I seguenti comportamenti e strutture si applicano in modo identico a entrambi i Editor:

- **Registrazione:** `window.extension[id] = config` e/o `tcx.extension.register(id, config)` il
evento `tcx-loaded`.
- **Forma oggetto di configurazione:** `{ id, contextMenuWidget, view: { items }, controller }`.
- **I menu contestuali della shell app** mantengono gli ID widget esistenti e il comportamento legacy:

  | Superficie | ID widget (non modificato) |
  |---|---|
  | Pannello archivio (file/cartella) | `repository_panel` / `file_options` / `folder_options` |
  | Visualizzatore mappa | `ditamap_viewer` / `map_view_options` |
  | Pannelli linea di base/predefiniti | `baseline_panel_menu` / `preset_item_menu` |

  Per gli elementi destinati a queste superfici non è necessario **alcun cambiamento** per il nuovo editor, non spostarli in
  `markup_editor_menu`.

## Riferimento di sostituzione API

| Legacy (`tcx.curEditor…` / DOM) | Nuovo MarkupEditor |
|---|---|
| `tcx.curEditor.filePath` | `guides.editor.filePath` |
| `getSelection()` / `selectedHtml` / `selectedText` | `runUtil('getSelectedXml' / 'getSelectedPlainText' / 'hasSelection')` |
| `rootDocument.querySelector(tag)` | `runUtil('findPositionRange' / 'findPositionRanges', tag)` |
| elemento `.getAttribute` / `xmlDoc.attributes` | `runUtil('getAttributeAtPosition', pos, name)` / `getSerializableAttributes(xpath)` |
| id radice (`querySelector('[concept]').id`) | `runUtil('getAttributeAtPosition', 0, 'id')` |
| `editor.ancestors` | `runUtil('getAncestorsDetails' / 'getAncestorXpaths')` |
| `editor.updateAttributes(attrs, root)` | `runCommand('setNodeXmlAttributes', 0, attrs)` |
| imposta attributo sull&#39;elemento | `runCommand('setNodeXmlAttribute', pos, name, value)` |
| racchiudi/inserisci/rimuovi selezione | `runCommand('surroundWithElement' / 'insertXml' / 'unwrapNode', …)` |
| `canInsertXmlElement` / `validateRangeForInsertion` | `canRunCommand(name, …)` / `canInsertXmlElement(tag)` |
| `editor.focus()` | `guides.editor.focus()` |
| `tcx.curEditor.saveFile()` | `tcx.eventHandler.next(KEYS.AUTHOR_SAVE_KEY)` |
| `setAttribute` / `classList` per lo stile | `addDecoration` / `batchDecorations` / `registerPlugin` |
| CSS page/clientlib per contenuti dell’editor | `registerPlugin({ css })` (DOM shadow) |
| `contextMenuWidget: 'dita_editor_menu'` | `['dita_editor_menu', 'markup_editor_menu']` |


## Eseguire la migrazione delle voci del menu di scelta rapida (area di lavoro dell’editor)

Applicabile solo ai menu di destinazione dell&#39;**editor** (`dita_editor_menu`,
`author_outline_element`), ovvero il menu di scelta rapida o il menu di scelta rapida all&#39;interno della superficie di modifica.

### Come viene indirizzato nel nuovo editor

```
window.extension[id]  ─►  filtered by contextMenuWidget == 'markup_editor_menu'
                      ─►  view.items rendered in the canvas menu
   (click) ───────────►  fires an extension event:
                          • eventid is a known global key  → run as a built-in editor command
                          • otherwise                       → your controller[eventid]() runs
```

### Aggiungi il nuovo ID widget (l’array mantiene il funzionamento legacy)

```js
// BEFORE
contextMenuWidget: 'dita_editor_menu',
// AFTER
contextMenuWidget: ['dita_editor_menu', 'markup_editor_menu'],
```

### Mantieni la forma prevista

- Gli elementi utilizzabili risiedono in `view.items` con `data.eventid`.
- Ogni nome di metodo `controller` **corrisponde** esattamente ai relativi `eventid`.

```js
view: {
  items: [{
    displayName: 'Edit Cross Reference',
    icon: 'link',
    data: { eventid: 'editCrossReference' },
    target: { key: 'displayName', value: 'Cut', viewState: 'prepend' }
  }]
},
controller: {
  editCrossReference() { /* runs on click */ }
}
```

### Ancoraggio di nuovo `target`

Il nuovo menu risolve `target` in base alle voci di menu dell&#39;editor di markup.

- `target.key`: `displayName | id | icon | eventid`
- `target.viewState`: `append | prepend | replace`
- Ancoraggio a un elemento nativo stabile come **`Cut`**.
- Se l&#39;ancoraggio non si risolve, l&#39;elemento viene comunque visualizzato ma si trova nella posizione predefinita
(non è un errore, correggi l’ancoraggio).

### Scegliere il ciclo per articolo

```js
data: { eventid: 'AUTHOR_CUT' }          // built-in command → routed natively, no controller needed
data: { eventid: 'editCrossReference' }  // custom → runs controller.editCrossReference()
```

Aggiungi `readOnly: true` a un elemento che deve rimanere abilitato in contenuto di sola lettura.

### Riscrivi il corpo del gestore

I gestori di solito leggono la selezione e modificano un nodo, migrano quelli dal DOM.

## Esegui migrazione letture (DOM: `runUtil`)

```js
// BEFORE — DOM selection / queries
const { editor } = tcx.curEditor;
const html = editor.selectedHtml;
const topicId = editor.rootDocument.querySelector('[data-tcx-tag="concept"]').id;

// AFTER — read from the document model
const selectedXml = guides.editor.runUtil('getSelectedXml');
const hasSel      = !!guides.editor.runUtil('hasSelection'); // check if selection is empty
const topicId     = guides.editor.runUtil('getAttributeAtPosition', 0, 'id'); // root = position 0
```

Trovare un nodo per tag, trovare una corrispondenza per ID e leggere un attributo XML:

```js
let value = '';
for (const range of (guides.editor.runUtil('findPositionRanges', 'xref') || [])) {
  const id = guides.editor.runUtil('getAttributeAtPosition', range.from, 'id');
  if (String(id) !== String(targetId)) continue;
  value = guides.editor.runUtil('getAttributeAtPosition', range.from, 'placeholdertext') || '';
  break;
}
```

**Utilità di lettura:** `getTextPos`, `getNodePosition`, `getSelectedXml`, `getSelectedPlainText`,
`hasSelection`, `getAncestorsNames`, `getAncestorsDetails`, `getAncestorXpaths`,
`findPositionRange`, `findPositionRanges`, `getAttributeAtPosition`, `getSerializableAttributes`. Fare riferimento all&#39;[appendice](#appendix-a-more-exposed-utils-examples).


## Migra scritture (mutazione DOM: `runCommand`)

```js
// BEFORE
const root = editor.rootElement.findOne('[data-tcx-tag="concept"]');
editor.updateAttributes({ docOwner: 'Jane' }, root);

// AFTER — update the model; persists across rerenders
guides.editor.runCommand('setNodeXmlAttributes', 0, { docOwner: 'Jane' });
```

```js
// Set one attribute at a found position
guides.editor.runCommand('setNodeXmlAttribute', pos, 'placeholdertext', text);

// Wrap / insert / unwrap
guides.editor.runCommand('surroundWithElement', 'sup');
guides.editor.runCommand('insertXml', '<sup></sup>', undefined, { setCursorInContent: true });
guides.editor.runCommand('unwrapNode');
```

**Prerequisito**

```js
guides.editor.focus();
if (!guides.editor.canInsertXmlElement('xref')) {
  return tcx.util.showAlert('warning', 'xref is not allowed here'); 
}
if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
  guides.editor.runCommand('surroundWithElement', 'sup');
}
```

**Comandi:** `setNodeXmlAttributes`, `setNodeXmlAttribute`, `surroundWithElement`, `insertXml`,
`unwrapNode`. Fare riferimento all&#39;[appendice](#appendix-b-more-exposed-commands-examples).

## Migrare azioni globali (salvare/concentrare: eventi delle app)

```js
// BEFORE
tcx.curEditor?.saveFile?.();
// AFTER
tcx.eventHandler.next(tcx.eventHandler.KEYS.AUTHOR_SAVE_KEY);
```

`resetDirty(...)` e `tcx.curEditor.html` non hanno un equivalente MarkupEditor, quindi eliminali; salvataggio
attraverso l’evento gestisce lo stato dirty a livello centrale. Utilizza `guides.editor.focus()` per mettere a fuoco.


## Migrare la logica di solo rendering (pittura DOM: decorazioni)

Tutto ciò che ha aggiunto classi CSS, attributi `data-*` o &quot;testo visualizzato&quot; modificando il DOM deve
diventa una **decorazione** o svanisce sul rendering. Di seguito sono riportati alcuni semplici casi dichiarativi:

```js
guides.editor.addDecoration('important-sections', 'section', {
  class: 'section-important',
  computeAttributes: (node, ctx) => ({ 'data-number-label': String(ctx.index + 1) }),
  filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
});

guides.editor.batchDecorations([
  { action: 'remove', id: 'legacy-numbering' },
  { action: 'add', id: 'division-numbering', selector: 'conbody', options: { class: 'division-numbering' } }
]);

guides.editor.removeDecoration('important-sections');
guides.editor.clearDecorations();
guides.editor.getDecorations();
```

Casi complessi (stato personalizzato, stato interrotto tramite meta transazione, testo widget): registrazione di una
Plug-in ProseMirror una volta, utilizzando le librerie esposte:

```js
const createXrefPlugin = () => {
  const { Plugin, PluginKey } = guides.editor.prosemirror.state;
  const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  return {
    plugin: new Plugin({ key: new PluginKey('xrefDisplay'), props: { decorations(state) { /* … */ } } }),
    css: `.xref-broken { text-decoration: underline wavy red; }`
  };
};

guides.ready(() => guides.editor.registerPlugin(createXrefPlugin));
```

Registra i plug-in al caricamento dell’app (una volta), non all’interno di finestre di dialogo o più volte, il registro di sistema non viene deduplicato. `registerPlugin` accetta solo una **funzione factory**, non un&#39;istanza del plug-in.
`guides.editor.prosemirror` espone: `state`, `model`, `view`, `transform`, `commands`, `keymap`,
`history`, `tables`, `dropcursor`, `collab`, `markdown`.


## Migra CSS (page clientlib → shadow DOM)

MarkupEditor esegue il rendering all&#39;interno di un **DOM shadow**; gli stili CSS clientlib a livello di pagina e AEM non lo raggiungono.

```js
guides.editor.registerPlugin(() => ({
  plugin: new guides.editor.prosemirror.state.Plugin({}),   // no-op, CSS only
  css: `[data-xml-element="codeblock"] { font-family: monospace; background: #f5f5f5; }`
}));
```

La categoria clientlib dei contenuti legacy (`apps.guides.xml_editor.dita_content_overrides`) è ancora
applica lo stile solo all&#39;editor legacy, mantienilo se supporti entrambi, ma saprai che è inerte in MarkupEditor.

## Accesso a Live EditorView (plug-in `view` prop): tratteggio di escape DOM

Decorazioni e comandi sono l&#39;approccio preferito. Tuttavia, alcuni effetti non possono essere implementati come decorazioni. In questi casi, utilizzare la proprietà del plug-in `view` per accedere alla versione live di `EditorView` e operare su `editorView.dom`. Questo è l’unico modo supportato per interagire direttamente con l’editor DOM renderizzato.

```js
const createMyPlugin = () => {
  const { Plugin } = guides.editor.prosemirror.state;
  return {
    plugin: new Plugin({
      view(editorView) {
        const root = editorView.dom;          // the shadow-DOM editor node
        const apply = () => { /* re-color / rewrite target nodes in `root` */ };
        apply();
        return {
          update(view, prevState): apply,                       // re-apply after every rerender
          destroy() { /* remove any listeners/observers */ },
        };
      },
    }),
    css: `/* ... */`,
  };
};

guides.ready(() => guides.editor.registerPlugin(createMyPlugin));
```

**Guardrail**:

- Esci solo dal tratteggio, utilizza decorazioni per classi, etichette e stili.
- `editorView.dom` è l&#39;unico handle supportato;
- Riapplica da `update()` in modo che la modifica sopravviva ai rendering; pulizia in `destroy()`.

## Ciclo di vita registrazione plug-in

`registerPlugin` in `guides.ready` registra la fabbrica una sola volta. La fabbrica stessa funziona di nuovo
ogni volta che un file viene aperto, ogni file MarkupEditor aperto lo richiama per generare il file
istanza del plug-in.

## Problemi comuni

- Dove il codice DOM si rivolge ai nodi e a `Range`, MarkupEditor si rivolge a **posizioni**, interi semplici che si indicizzano nel documento (`0` = inizio del documento, ovvero la radice). Un `range` è `{ from, to }`, due posizioni che delimitano un&#39;estensione, non un DOM `Range`. Le posizioni cambiano quando il documento cambia, quindi non memorizzarne una nella cache durante una modifica.
- **L&#39;elemento non viene visualizzato nel menu Nuovo editor**: `contextMenuWidget` è mancante
  `markup_editor_menu` oppure la configurazione è stata registrata *dopo* l&#39;editor è stato aperto (la configurazione è letta
  once at editor construction register at app load).
- **L&#39;elemento viene visualizzato in una posizione errata**: l&#39;ancoraggio `target` non viene risolto. Ancoraggio a un elemento che
esiste nel nuovo menu (ad esempio `Cut`).
- **Modifica &quot;works&quot; quindi scompare**: il DOM è stato modificato. Utilizza un comando (scrittura) o una decorazione
(stile).
- **CSS non ha alcun effetto**: è a livello di pagina; l&#39;editor si trova in un DOM shadow. Usa `registerPlugin({ css })`.
- **Le guardie non sicure lanciano**: modelli come `if (!tcx.curEditor && !tcx.curEditor.editor)` valutano
  `.editor` su un oggetto falsy. Controlla le funzionalità di `guides.editor`:
  `if (!guides?.editor) return;`.
- **Tentativo di migrazione dei menu della shell dell&#39;app**: i menu dell&#39;archivio/mappa/file non sono nell&#39;area di lavoro dell&#39;editor;
lasciali sui loro widget id legacy.

## Elenco di controllo per la verifica

- Le voci del menu di scelta rapida vengono visualizzate in **entrambi** i menu legacy e MarkupEditor.
- Gli elementi vengono sbarcati nella posizione prevista.
- `eventid` personalizzato esegue `controller[eventid]`; le chiavi globali attivano il comando incorporato.
- Le letture dello stato restituiscono i valori corretti dopo la digitazione o il rendering (modello, non DOM obsoleto).
- Le scritture del contenuto *persistono dopo il salvataggio e la riapertura*.
- Le decorazioni sopravvivono a un rendering.
- Il CSS Shadow-DOM viene applicato in modo visibile all’interno dell’editor.
- Salvare gli incendi tramite `AUTHOR_SAVE_KEY` e cancellare lo stato dirty.
- `readOnly` elementi si comportano correttamente nel contenuto bloccato.
- Anteprima o affiancamento; il lavoro DOM intenzionale di sola lettura viene lasciato invariato.
- `grep -rn "tcx.curEditor" src` è pulito (o solo il resto intenzionale documentato).
- Plug-in registrati esattamente una volta, in `guides.ready`.


## Sequenza di rollout consigliata

1. **Bootstrap**: esegui il wrapping dell&#39;installazione in `guides.ready`; registra i plug-in in modo incondizionato e aggiungi il controllo `version` solo per *runtime* azioni (per i dettagli, visualizza [Plugin Registration and Runtime Gating](#plugin-registration-and-runtime-gating)).
2. **Superficie del menu di scelta rapida**: aggiungere `markup_editor_menu`, correggere `target` ancoraggi. Vengono ora visualizzati gli elementi.
3. **Letture**: esegui la migrazione delle letture di selezione/attributo in `runUtil`.
4. **Scritture**: esegui la migrazione delle mutazioni in `runCommand`; salva in eventi app.
5. **Rendering**: sposta lo stile DOM nelle decorazioni / `registerPlugin`; sposta CSS nel DOM shadow.
6. **Completa**: correggi le protezioni non sicure, rimuovi l&#39;handle dell&#39;editor, verifica in entrambi gli editor.

Eseguire la migrazione di una superficie alla volta e mantenere attivi i percorsi legacy (array + verifica della versione) in modo da
la build a estensione singola viene eseguita su entrambi gli editor durante la transizione.

## Appendice A: Utenti più esposti (esempi)

Trovare le utilità seguenti da utilizzare tramite `runUtil`.

| Util | Parametri restituiti → | Effetto |
|---|---|---|
| `getTextPos` | `(): { start, end }` | Limiti dei nodi di testo selezionati correnti |
| `getValidElementNames` | `(ancestorLevel?): ElementName[]` | Nomi di elementi che potrebbero essere legalmente inseriti/racchiusi nella selezione corrente. |
| `getValidElementNamesBefore` | `(): ElementName[]` | Nomi di elementi validi immediatamente prima della selezione corrente. |
| `getSelectedText` | `(): string` | Testo non elaborato selezionato. |
| `getSerializableAttributes` | `(): { [key]: string }` | Mappa di attributi XML per il nodo corrente, in base al nome dell&#39;attributo. |
| `getTagName` | `(): string \| null` | Nome tag del nodo corrente. |
| `hasSelection` | `(): boolean` | Indica se è attualmente selezionato un contenuto. |
| `isSelectionEditable` | `(): boolean` | Indica se è possibile modificare la selezione corrente. |
| `getAncestorPos` | `(name): number \| undefined` | Posizione del predecessore più vicino con il nome elemento specificato, dalla selezione corrente. |
| `getValidWrapNodeElementNames` | `(): ElementName[]` | Nomi di elemento validi per `wrapNode` nella selezione corrente. |
| `getValidRenameNodeElementNames` | `(): ElementName[]` | Nomi di elementi a cui il nodo corrente poteva essere legalmente rinominato. |
| `getValidSurroundElementNames` | `(): ElementName[]` | Nomi di elemento validi per `surroundWithElement` nella selezione corrente. |
| `serialize` | `(doc?): string` | Serializza un documento ProseMirror (o l&#39;intero documento) in XML. |
| `getSelectedXml` | `(range?): string` | XML per la selezione corrente o un intervallo `{ from, to }` esplicito. |
| `getRangeXml` | `(xpaths): string` | XML per uno o più intervalli xpath-object (vedere l&#39;avvertimento xpath di §8: questo è il modulo oggetto, non il modulo stringa). |
| `mapToXpath` | `(position, doc?): XPathPosition` | Converte una posizione in xpath in forma di oggetto. |
| `inverseMap` | `(xpath \| position, doc?): number` | Converte nuovamente un xpath (o posizione) in forma di oggetto in una posizione. |
| `getAncestorsDetails` | `(): { ancestors, previousSibling, nextSibling, currNode } \| undefined` | Catena predecessore più elementi di pari livello immediati per il nodo corrente. |
| `getAncestorsNames` | `(): ElementName[]` | Catena predecessore solo come nomi di elementi, per il nodo corrente. |
| `getPreviousSibling` | `(): ElementName \| undefined` | Nome dell&#39;elemento di pari livello precedente. |
| `getNextSibling` | `(): ElementName \| undefined` | Nome dell&#39;elemento di pari livello successivo. |
| `getAncestorXpaths` | `(includeNodeAtPosition?): { tag, xpath }[]` | Catena predecessore come `{tag, xpath}` coppie — xpath in forma di oggetto, non il formato stringa `updateAttributeByXpath` (§8). |
| `getSelectedPlainText` | `(range?): string` | Testo normale della selezione corrente o di un intervallo esplicito. |
| `getDecorations` | `(): string[]` | ID di tutte le decorazioni attualmente applicate. |
| `getResolvedDitaDocumentTitle` | `(props?): string` | Risoluzione del titolo visualizzato del documento DITA. `props`: `doc` per eseguire il targeting di un documento specifico, `allowedPrefixElements` per consentire elementi titolo-prefisso. |

## Appendice B: Altri comandi esposti (esempi)

I comandi seguenti sono esempi aggiuntivi di ciò che è esposto tramite `guides.editor.runCommand(name, ...args)`.
Controllare prima qualsiasi comando con `guides.editor.canRunCommand(name, ...args)` se potrebbe non essere applicabile nel contesto corrente.

| Comando | Parametri | Effetto |
|---|---|---|
| `focusEditor` | `()` | Attiva l’editor. |
| `unwrapNode` | `()` | Rimuove l&#39;elemento di ritorno a capo nella selezione corrente, mantenendo i relativi elementi figlio. |
| `surroundWithElement` | `(elementName, attrs?, groupInline?)` | Dispone la selezione corrente in un nuovo elemento in linea/blocco. `attrs`: mapping di attributi XML da impostare sul nuovo elemento di wrapping. |
| `insertXml` | `(xml)` | Inserisce un frammento XML in corrispondenza del cursore. |
| `replaceSelectionWithXml` | `(xml)` | Sostituisce la selezione corrente con XML. |
| `insertText` | `(text)` | Inserisce testo normale in corrispondenza del cursore. |
| `selectNodesFromXpaths` | `(xpaths)` | Seleziona uno o più nodi in base agli xpath in forma di oggetto. |
| `delete` | `()` | Elimina la selezione corrente. |
| `undo` / `redo` | `()` | Annulla/Ripristina standard. |
| `removeDecoration` | `(id)` | Rimuove una singola decorazione per ID. |
| `clearDecorations` | `()` | Rimuove tutte le decorazioni nel file aperto corrente. |
| `setFileReadOnly` | `(readOnly: boolean)` | Attiva la modalità di sola lettura per il file. |
| `generateUniqueId` | `()` | Genera e assegna un attributo ID univoco al nodo corrente. |