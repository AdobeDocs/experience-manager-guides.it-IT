---
title: Modifiche al framework di estensione per Editor 2.0
description: Scopri le modifiche apportate al framework dell’estensione per Editor 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 2ba8eadcb30faca01170cb13ae2da6fdf7da19c8
workflow-type: tm+mt
source-wordcount: '2003'
ht-degree: 3%

---

# Modifiche al framework di estensione per Editor 2.0 (nuovo editor)

Questo documento descrive tutte le API aggiunte a `guides.editor` (e `guides`) come parte del framework di estensione per il nuovo editor (editor basato su ProseMirror). Queste API consentono alle estensioni esterne di interagire con l’editor senza dover intervenire direttamente sui DOM o senza alcuna conoscenza dell’implementazione interna.

## Panoramica

L&#39;oggetto `guides` globale è il punto di ingresso per tutte le integrazioni di estensioni:

```js
guides.editor    // Editor interaction APIs
guides.util      // Utility libraries (lodash, async)
guides.ready(cb) // Lifecycle hook fires when the editor is fully loaded
```

Tutte le API `guides.editor` possono essere richiamate dai controller delle estensioni, dai gestori delle barre degli strumenti e dalla logica di dialogo.

## Ciclo di vita

`guides.ready(callback)`: registra un callback da eseguire una volta completato il caricamento del gestore di visualizzazione della pagina. Utilizzalo prima di registrare i plug-in o di eseguire qualsiasi configurazione dell’editor.

**Firma:**

```ts
guides.ready(callback: () => void): void
```

**Esempio:**

```js
guides.ready(() => {
  // Safe to access guides.editor APIs here
  guides.editor.registerPlugin(createMyPlugin);
});
```

## Proprietà dello stato dell’editor

- `guides.editor.filePath`: restituisce il percorso del documento attualmente attivo.

  **Tipo:** `string | undefined`

  **Esempio: lettura percorso file per una chiamata API metadati:**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath) {
  tcx.api.getMetadata(filePath).subscribe((metadata) => {
    // use metadata...
    });
  }
  ```

  **Esempio: logica condizionale basata sulla posizione del file**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath?.endsWith(".ditamap")) {
    // ditamap-specific handling
  }
  ```

- `guides.editor.version`: restituisce la stringa della versione dell&#39;editor attualmente caricato.

  | Valore | Editor |
  |---------|------------------------------------|
  | `1.0.0` | CKEditor legacy (`xml_author_view`) |
  | `2.0.0` | Nuovo editor (basato su ProseMirror) |

  **Tipo:** `string`

  **Esempio:**

  ```js
  if (guides.editor.version  === '1.0.0') {
    // CKEditor specific logic 
  }
  ```

- `guides.editor.appState(keyName)`: legge un valore dal modello dell&#39;applicazione in base al nome della chiave.

  **Firma:**

  ```ts
  guides.editor.appState(keyName: string): unknown
  ```

  **Esempio:**

  ```js
  const editorMode = guides.editor.appState('editorMode');
  ```

## Interazione con l’editor

- `guides.editor.focus()`: imposta lo stato attivo sull&#39;editor attivo. Chiama prima di eseguire i comandi che richiedono che l’editor abbia lo stato attivo.

  **Firma:**

  ```ts
  guides.editor.focus(): boolean
  ```

  **Esempio: attivazione prima dell&#39;inserimento del contenuto**

  ```js
  guides.editor.focus();
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  // ...proceed with wrap or insert
  ```

- `guides.editor.canInsertXmlElement(tagName, insertAfter?)`: controlla se un determinato elemento XML può essere inserito nella posizione corrente del cursore.

  **Firma:**

  ```ts
  guides.editor.canInsertXmlElement(tagName: string, insertAfter?: boolean): boolean
  ```

  **Esempio: guardia prima di inserire`<xref>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("xref");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "xref is not allowed here");
  }
  ```

  **Esempio: guardia prima di inserire `<sup>` /`<sub>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("sup");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "superscript is not allowed here");
  }
  ```

- `guides.editor.selectCurrentBlockElement()`: seleziona l&#39;elemento a livello di blocco corrente nell&#39;editor.

  **Firma:**

  ```ts
  guides.editor.selectCurrentBlockElement(): boolean
  ```

  **Esempio:**

  ```js
  guides.editor.selectCurrentBlockElement();
  ```

- `guides.editor.getValidElementNamesForInsertion(args)`: restituisce un elenco di nomi di elementi XML validi che possono essere inseriti nella posizione corrente.

  **Firma:**

  ```ts
  guides.editor.getValidElementNamesForInsertion(args: {
    insertMode?: 'after' | 'before' | 'rename',
    strict: boolean
  }): string[] | false
  ```

  **Esempio:**

  ```js
  const validElements = guides.editor.getValidElementNamesForInsertion({
    insertMode: 'after',
    strict: true
  });
  ```

- `guides.editor.updateAttributeByXpath(args)`: aggiorna un attributo XML specifico in un nodo identificato dal relativo XPath. Delega al metodo `updateAttributeByXpath` dell&#39;editor attivo.

  **Firma:**

  ```ts
  guides.editor.updateAttributeByXpath(args: UpdateXpathArgs): any
  ```

## Esecuzione del comando

- `guides.editor.runCommand(commandName, ...args)`: esegue un comando denominato nel nuovo editor. Restituisce `true` se il comando è riuscito, `false` in caso contrario.

  **Firma:**

  ```ts
  guides.editor.runCommand(commandName: string, ...args: any[]): boolean
  ```

  **Comandi disponibili**

  >[!NOTE]
  >
  > Stabilità: i comandi elencati di seguito fanno parte dell&#39;interfaccia pubblica. I nomi, le firme e il comportamento osservabile sono considerati stabili e vengono mantenuti per compatibilità. Comandi aggiuntivi possono essere presenti all’interno dell’editor; tuttavia, si tratta di comandi interni, non sono destinati all’uso esterno e possono essere modificati o rimossi senza preavviso.

  | Categoria | Comando | Argomenti | Descrizione |
  |---|---|---|---|
  | Generale | `undo` | _(nessuno)_ | Annulla l&#39;ultima modifica del documento |
  | Generale | `redo` | _(nessuno)_ | Ripete l&#39;ultima modifica annullata |
  | Selezione | `select` | `from: number, to?: number` | Seleziona l&#39;intervallo da `from` a `to` (o solo `from` se `to` viene omesso) |
  | Selezione | `cursor` | `pos: number` | Sposta il cursore su `pos` |
  | Selezione | `selectNodesFromXpaths` | `xpaths: Array<{path: Array<{name: string, count: number}>}>` | Seleziona i nodi identificati dalle posizioni XPath |
  | Formattazione | `toggleBold` | _(nessuno)_ | Attiva o disattiva il grassetto nella selezione corrente |
  | Formattazione | `toggleItalic` | _(nessuno)_ | Attiva o disattiva la formattazione corsivo per la selezione corrente |
  | Formattazione | `toggleUnderline` | _(nessuno)_ | Attiva/disattiva la formattazione della sottolineatura per la selezione corrente |
  | Formattazione | `toggleFormatting` | `markType: string, allowEmptySelection?: boolean` | Attiva/disattiva un elemento di formattazione (ad esempio `'b'`, `'i'`, `'sup'`, `'sub'`) sulla selezione |
  | Inserimento | `insertText` | `text: string` | Inserisce testo normale in corrispondenza del cursore |
  | Inserimento | `insertXml` | `xml: string, position?: number, options?: InsertXmlOptions` | Inserisce XML non elaborato in corrispondenza del cursore o della posizione specificata |
  | Inserimento | `insertXmlAfterElement` | `elementName: string, xmlString: string` | Inserisce XML immediatamente dopo il predecessore più vicino corrispondente a `elementName` |
  | Inserimento | `replaceSelectionWithXml` | `xmlString: string` | Sostituisce la selezione corrente con l&#39;XML specificato |
  | Operazioni sui nodi | `surroundWithElement` | `tagName: string, attrs?: Record<string,unknown>, replaceTextWithEmptyNode?: boolean` | Dispone la selezione corrente con l&#39;elemento specificato |
  | Operazioni sui nodi | `wrapNode` | `type: string, target?: number, attrs?: Record<string, unknown>` | Racchiude il nodo in `target` (o nel nodo corrente) in un elemento di `type` |
  | Operazioni sui nodi | `renameNode` | `newNodeName: string` | Rinomina l&#39;elemento del nodo corrente |
  | Operazioni sui nodi | `unwrapNode` | _(nessuno)_ | Rimuove l&#39;elemento wrapper del nodo corrente mantenendo il relativo contenuto |
  | Eliminare | `deleteSelection` | _(nessuno)_ | Elimina il contenuto attualmente selezionato |
  | Eliminare | `deleteNode` | _(nessuno)_ | Elimina l&#39;intero nodo corrente |
  | Attributi | `setNodeXmlAttributes` | `position: number, attrs: Record<string, unknown>` | Imposta più attributi XML sul nodo in `position` |
  | Attributi | `setNodeXmlAttribute` | `position: number, attrName: string, value: string` | Imposta un singolo attributo XML sul nodo in `position` |
  | Elenchi | `toggleList` | `listName: 'ol' \| 'ul'` | Consente di alternare tra un elenco del tipo specificato e un paragrafo |
  | Tabelle | `addRowAfter` | `count?: number` | Aggiunge `count` righe sotto la riga corrente (impostazione predefinita 1) |
  | Tabelle | `addColumnAfter` | `count?: number` | Aggiunge `count` colonne a destra della colonna corrente (impostazione predefinita 1) |
  | Tabelle | `deleteRow` | _(nessuno)_ | Elimina la riga corrente |
  | Tabelle | `deleteColumn` | _(nessuno)_ | Elimina la colonna corrente |
  | Tabelle | `mergeCells` | _(nessuno)_ | Unisce le celle attualmente selezionate |
  | Appunti | `copy` | _(nessuno)_ | Copia la selezione corrente negli Appunti |
  | Appunti | `cut` | _(nessuno)_ | Taglia la selezione corrente negli Appunti |
  | Trova e sostituisci | `setSearchQuery` | `query: string, options?: { caseSensitive?: boolean, regex?: boolean }` | Imposta la query di ricerca attiva |
  | Trova e sostituisci | `findNext` | _(nessuno)_ | Passa alla ricerca successiva |
  | Trova e sostituisci | `replaceAll` | `replacement?: string` | Sostituisce ogni corrispondenza della query di ricerca corrente con `replacement` |

   - **Esempio: impostare più attributi in un nodo**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttributes",
       rootRange.from,
       { createdDate: "2024-01-01", author: "Jane Doe" }
     );
     ```

   - **Esempio: impostare un singolo attributo su un nodo**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttribute",
       range.from,
       "placeholdertext",
       "Chapter 3 — Safety Requirements"
     );
     ```

   - **Esempio: racchiudere la selezione con un elemento e impostare gli attributi**

     ```js
     const didWrap = guides.editor.runCommand(
       "surroundWithElement",
       "ph",
       { outputclass: "highlight" },
       true   // replace text content with empty node
     );
     ```

   - **Esempio: esegui il wrapping della selezione in `<sup>` (attiva/disattiva apice)**

     ```js
     const didWrap = guides.editor.runCommand('surroundWithElement', 'sup');
     if (!didWrap) {
       tcx.util.showAlert("warning", "superscript is not allowed here");
     }
     ```

   - **Esempio: rimuovi a capo il nodo corrente (disattiva apice)**

     ```js
     const didUnwrap = guides.editor.runCommand('unwrapNode');
     ```

   - **Esempio: inserire XML in corrispondenza del cursore con punto di inserimento all&#39;interno di**

     ```js
     guides.editor.runCommand(
       'insertXml',
       '<sup></sup>',
       undefined,
       { setCursorInContent: true, focusEditor: true, selectInsertedXml: false }
     );
     ```

- `guides.editor.canRunCommand(commandName, ...args)`: verifica se è attualmente possibile eseguire un comando denominato senza eseguirlo effettivamente.

  **Firma:**

  ```ts
  guides.editor.canRunCommand(commandName: string, ...args: any[]): boolean
  ```

  **Esempio:**

  ```js
  if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
    guides.editor.runCommand('surroundWithElement', 'sup');
  }
  ```

## Funzioni utility

- `guides.editor.runUtil(utilName, ...args)`: richiama un&#39;utilità denominata dal Registro di sistema dell&#39;utilità del nuovo editor. Restituisce il risultato dell&#39;utilità o `undefined` se l&#39;utilità non viene trovata.

  **Firma:**

  ```ts
  guides.editor.runUtil(utilName: string, ...args: any[]): any
  ```

  **Utilità disponibili**

  >[!NOTE]
  >
  > Stabilità: le utility elencate di seguito fanno parte dell’interfaccia pubblica. I nomi, le firme e il comportamento osservabile sono considerati stabili e vengono mantenuti per compatibilità. Comandi aggiuntivi possono essere presenti all’interno dell’editor; tuttavia, si tratta di comandi interni, non sono destinati all’uso esterno e possono essere modificati o rimossi senza preavviso.


  | Categoria | Utilità | Argomenti | Restituisce | Descrizione |
  |---|---|---|---|---|
  | Posizione | `getTextPos` | _(nessuno)_ | `{ start: number, end: number }` | Posizioni iniziale e finale della selezione corrente nel documento ProseMirror |
  | Posizione | `getNodePosition` | `position?: number` | `number` | Posizione del documento del nodo attualmente selezionato/attivato |
  | Posizione | `mapToXpath` | `position: number` | `XPathPosition` | Mappa una posizione ProseMirror a un descrittore XPath |
  | Posizione | `inverseMap` | `xpath: XPathPosition \| number` | `number` | Esegue il mapping di un descrittore XPath (o posizione numerica) su una posizione ProseMirror |
  | Documento | `getNodeTree` | _(nessuno)_ | `NodeTree \| null` | Rappresentazione ad albero del documento, adatta al rendering della struttura |
  | Documento | `getAncestorsNames` | `position?: number` | `string[]` | Nomi tag XML dei nodi predecessori in `position` |
  | Documento | `getAncestorsDetails` | `position?: number` | `{ currNode: string, ancestors: Array<{tagName: string}>, previousSibling?: string, nextSibling?: string } \| undefined` | Nodo corrente, elementi precedenti e elementi di pari livello a `position` |
  | Documento | `getAncestorXpaths` | `includeId?: boolean` | `AncestorXpathItem[]` | Stringhe XPath per tutti i nodi predecessori |
  | Documento | `getPreviousSibling` | `position?: number` | `string \| undefined` | Nome del tag dell&#39;eventuale elemento di pari livello precedente |
  | Documento | `getNextSibling` | `position?: number` | `string \| undefined` | Nome del tag dell&#39;eventuale pari livello successivo |
  | Documento | `getTagName` | `position?: number` | `string \| null` | Nome tag dell&#39;elemento in corrispondenza di `position` (o cursore) |
  | Ricerca elemento | `findPositionRange` | `tagName: string` | `{ from: number, to: number } \| undefined` | Intervallo del primo elemento con il tag specificato |
  | Ricerca elemento | `findPositionRanges` | `tagName: string` | `Array<{ from: number, to: number }>` | Tutti gli intervalli per gli elementi corrispondenti a `tagName` |
  | Attributi | `getAttributeAtPosition` | `position: number, attrName: string` | `unknown` | Legge un valore di attributo XML dal nodo in `position` |
  | Attributi | `getSerializableAttributes` | `xpath: string` | `Record<string, unknown>` | Tutti gli attributi XML serializzabili per il nodo in `xpath` |
  | Serializzazione | `serialize` | _(nessuno)_ | `string` | Serializza l&#39;intero documento in formato XML |
  | Serializzazione | `serializeToText` | _(nessuno)_ | `string` | Serializza l&#39;intero documento in testo normale |
  | Serializzazione | `getRangeXml` | `xpaths: AncestorXpathItem[]` | `string` | Restituisce il codice XML per un intervallo definito da XPath |
  | Selezione | `getSelectedXml` | _(nessuno)_ | `string` | Contenuto attualmente selezionato come stringa XML |
  | Selezione | `getSelectedText` | _(nessuno)_ | `string` | Testo selezionato senza markup |
  | Selezione | `hasSelection` | _(nessuno)_ | `boolean` | `true` se è presente una selezione di testo/nodo attiva |
  | Selezione | `isSelectionEditable` | _(nessuno)_ | `boolean` | Se la selezione corrente si trova all&#39;interno di contenuto modificabile |
  | Selezione | `isPositionEditable` | `position: number` | `boolean` | Indica se `position` si trova all&#39;interno di contenuto modificabile |
  | Inserimento | `canInsert` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `boolean` | Indica se `name` può essere inserito in `position` (o cursore) |
  | Inserimento | `getInsertPosition` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `number \| null` | Posizione di inserimento valida per `name` o `null` se non inseribile |
  | Inserimento | `getNodeXml` | `nodeName: string, nodeContent?: string` | `string \| null` | Modello XML per un tipo di nodo |
  | Racchiudi/Rinomina | `getValidWrapNodeElementNames` | _(nessuno)_ | `string[]` | Nomi di elementi che possono racchiudere la selezione corrente |
  | Racchiudi/Rinomina | `getValidRenameNodeElementNames` | _(nessuno)_ | `string[]` | Nomi di elementi in cui il nodo corrente può essere rinominato |
  | Tabelle | `getTableInfo` | `position?: number` | `{ rows: number, cols: number, header: number }` | Dimensioni della tabella corrente |
  | Visualizzazione tag | `isTagViewActive` | _(nessuno)_ | `boolean` | Indica se il rendering della visualizzazione tag è attivo |

  **Esempio: posizione del cursore e nomi precedenti**

  ```js
  const textPos = guides.editor.runUtil("getTextPos");
  const ancestorNames = guides.editor.runUtil(
    "getAncestorsNames",
    typeof textPos === "number" ? textPos : undefined
  );
  ```

  **Esempio: trovare tutti gli elementi `<xref>` e leggerne gli attributi**

  ```js
  const xrefRanges = guides.editor.runUtil("findPositionRanges", "xref") || [];
  xrefRanges.forEach((range) => {
    const id = guides.editor.runUtil("getAttributeAtPosition", range.from, "id");
    const placeholderText = guides.editor.runUtil(
      "getAttributeAtPosition",
      range.from,
      "placeholdertext"
    );
  });
  ```

  **Esempio: trovare l&#39;intervallo di elementi radice e leggerne gli attributi**

  ```js
  const rootRange = guides.editor.runUtil("findPositionRange", "concept"); // or "topic"
  if (rootRange) {
    const createdDate = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "createdDate"
    );
    const author = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "author"
    );
  }
  ```

  **Esempio: controllare la selezione e convalidare il contesto predecessore prima di un&#39;operazione**

  ```js
  const ancestorsDetails = guides.editor.runUtil('getAncestorsDetails');
  const selectedText = guides.editor.runUtil('getSelectedPlainText');
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  
  const firstAncestor = ancestorsDetails?.currNode || ancestorsDetails?.ancestors?.[0]?.tagName;
  if (firstAncestor === 'ph') {
    tcx.util.showAlert("warning", "Operation is not allowed inside this element type.");
    return;
  }
  ```

  **Esempio: ottenere gli ID degli elementi dai XPaths precedenti**

  ```js
  const ancestorItems = guides.editor.runUtil('getAncestorXpaths', true);
  for (const item of ancestorItems) {
    const attrs = guides.editor.runUtil('getSerializableAttributes', item.xpath);
    if (attrs?.id) { /* use element ID */ }
  }
  ```

## API di decorazione

L’API Decoration fornisce un’alternativa di livello superiore alla scrittura di plug-in ProseMirror completi per le personalizzazioni visive più comuni. Anziché gestire `Plugin`, `PluginKey` e `DecorationSet` manualmente, si descrivono *cosa* decorare e *come* e lo stato di ProseMirror viene gestito internamente dal responsabile centrale delle decorazioni dell&#39;editor.

Le decorazioni sono identificate da una stringa `id` e possono quindi essere aggiornate o rimosse in modo indipendente in qualsiasi momento.

>[!NOTE]
>
> **Solo nuovo editor** Queste API non sono operazioni nell&#39;editor legacy (`version === '1.0.0'`).

- `guides.editor.addDecoration(id, selector, options)`: aggiunge o sostituisce una regola di decorazione. Tutti i nodi corrispondenti a `selector` nel documento corrente verranno decorati in base a `options`. La decorazione viene riapplicata automaticamente a ogni modifica del documento.

  **Firma:**

  ```ts
  guides.editor.addDecoration(
    id: string,
    selector: string,
    options: DecorationOptions
  ): boolean
  ```

  **`DecorationOptions`campi:**

  | Campo | Tipo | Descrizione |
  |---|---|---|
  | `class` | `string` | Nome classe CSS aggiunto ai nodi corrispondenti |
  | `computeAttributes` | `(node, context) => Record<string, string>` | La funzione restituisce `data-*` dinamico o altri attributi HTML per nodo |
  | `filter` | `(node) => boolean` | Predicato facoltativo - decorati solo i nodi in cui restituisce `true` |

  L&#39;oggetto `context` passato a `computeAttributes` include:
   - `index` — Posizione basata su 0 del nodo tra i pari livello corrispondenti al selettore

  **Esempio: aggiungi una classe CSS a tutti i `<section>` elementi**

  ```js
  guides.editor.addDecoration('highlight-sections', 'section', {
    class: 'my-section-highlight'
  });
  ```

  **Esempio: aggiungere un attributo `data-number-label` calcolato a ogni sezione**

  ```js
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

  **Esempio: decorare solo le sezioni con `importance="high"` attributo**

  ```js
  guides.editor.addDecoration('important-sections', 'section', {
    class: 'section-important',
    filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
  });
  ```

  **Esempio: combinare classe e attributi calcolati**

  ```js
  guides.editor.addDecoration('numbering-mode', 'conbody', {
    class: 'legacy-numbering'
  });
  
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

- `guides.editor.removeDecoration(id)`: rimuove una decorazione aggiunta in precedenza in base al relativo ID.

  **Firma:**

  ```ts
  guides.editor.removeDecoration(id: string): boolean
  ```

  **Esempio:**

  ```js
  guides.editor.removeDecoration('section-numbers');
  ```

- `guides.editor.batchDecorations(changes)`: applica più modifiche di aggiunta/rimozione di elementi decorativi in un&#39;unica spedizione ProseMirror. Utilizza questa opzione per attivare o disattivare più decorazioni contemporaneamente per evitare che vengano eseguiti più rendering.

  **Firma:**

  ```ts
  guides.editor.batchDecorations(changes: DecorationBatchChange[]): boolean
  
  type DecorationBatchChange =
    | { action: 'add', id: string, selector: string, options: DecorationOptions }
    | { action: 'remove', id: string }
  ```

  **Esempio: passaggio atomico tra due modalità di numerazione**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'legacy-numbering' },
    {
      action: 'add',
      id: 'division-numbering',
      selector: 'conbody',
      options: { class: 'division-numbering' }
    }
  ]);
  ```

  **Esempio: cancellare una decorazione e aggiungerne due nuove**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'old-highlights' },
    {
      action: 'add',
      id: 'section-labels',
      selector: 'section',
      options: {
        computeAttributes: (node, ctx) => ({ 'data-section-index': String(ctx.index) })
      }
    },
    {
      action: 'add',
      id: 'note-style',
      selector: 'note',
      options: { class: 'styled-note' }
    }
  ]);
  ```

- `guides.editor.clearDecorations()`: rimuove tutte le decorazioni attive gestite dal gestore delle decorazioni.

  **Firma:**

  ```ts
  guides.editor.clearDecorations(): boolean
  ```

  **Esempio:**

  ```js
  guides.editor.clearDecorations();
  ```

- `guides.editor.getDecorations()`: restituisce gli ID di tutte le decorazioni attualmente attive.

  **Firma:**

  ```ts
  guides.editor.getDecorations(): string[]
  ```

  **Esempio:**

  ```js
  const active = guides.editor.getDecorations();
  console.log('Active decorations:', active);
  // e.g. ['section-numbers', 'numbering-mode', 'note-style']
  ```


### Confronto tra Decoration API e `registerPlugin`

| Scenario | Utilizza |
|---|---|
| Applicare una classe CSS o gli attributi `data-*` agli elementi corrispondenti | `addDecoration` |
| Attiva o aggiorna lo stile in base allo stato di runtime (metadati, azione utente) | `addDecoration` / `removeDecoration` / `batchDecorations` |
| Logica complessa del plug-in: stato personalizzato, associazioni chiave, decorazioni widget, gestori eventi | `registerPlugin` |
| Inserimento di CSS nel DOM shadow | `registerPlugin` con campo `css` |


## Registrazione del plug-in ProseMirror

- `guides.editor.registerPlugin(factory)`: registra una factory del plug-in ProseMirror da includere in ogni istanza del nuovo editor. Sono accettate solo le funzioni di fabbrica, le istanze di plug-in diretto vengono rifiutate. La factory viene chiamata una volta per ogni istanza dell’editor, garantendo lo stato del plug-in isolato.

  **Firma:**

  ```ts
  guides.editor.registerPlugin(factory: () => PluginConfig): void
  
  interface PluginConfig {
    plugin: ProseMirrorPlugin | ProseMirrorPlugin[]
    css?: string  // Injected into editor's shadow DOM
  }
  ```

  **Esempio: registrare i plug-in quando l&#39;editor è pronto**

  ```js
  guides.ready(() => {
    guides.editor.registerPlugin(createNumberingPlugin);
    guides.editor.registerPlugin(createXrefPlugin);
  });
  ```

  **Esempio: fabbrica in linea con CSS**

  ```js
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({
      key: new guides.editor.prosemirror.state.PluginKey("myPlugin"),
      props: {
        decorations(state) {
          // return DecorationSet...
        }
      }
    }),
    css: `.my-decoration { background: yellow; }`
  }));
  ```

  >[!NOTE]
  >
  > Il CSS passato tramite `css` viene inserito nel DOM shadow dell&#39;editor. I fogli di stile a livello di pagina standard non sono applicabili all’interno dell’editor.

## Librerie ProseMirror

- `guides.editor.prosemirror`: espone i pacchetti ProseMirror direttamente per l&#39;utilizzo nello sviluppo di plug-in. Questo evita la necessità di raggruppare ProseMirror separatamente nel codice dell’estensione.

  | Proprietà | Pacchetto |
  |---|---|
  | `state` | `prosemirror-state` |
  | `model` | `prosemirror-model` |
  | `view` | `prosemirror-view` |
  | `transform` | `prosemirror-transform` |
  | `commands` | `prosemirror-commands` |
  | `keymap` | `prosemirror-keymap` |
  | `history` | `prosemirror-history` |
  | `tables` | `prosemirror-tables` |
  | `dropcursor` | `prosemirror-dropcursor` |
  | `markdown` | `prosemirror-markdown` |

  **Esempio: creare un plug-in di decorazione del nodo**

  ```js
  const myPluginKey = new guides.editor.prosemirror.state.PluginKey("myPlugin");
  
  const createMyPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: myPluginKey,
        state: {
          init() { return { enabled: true }; },
          apply(tr, value) {
            const meta = tr.getMeta(myPluginKey);
            return meta ? { ...value, ...meta } : value;
          }
        },
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name === "section") {
                decorations.push(
                  Decoration.node(pos, pos + node.nodeSize, { class: "my-section" })
                );
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.my-section { border-left: 3px solid #ccc; padding-left: 8px; }`
    };
  };
  ```

  **Esempio: creare un plug-in di decorazione widget (testo di visualizzazione in linea)**

  ```js
  const xrefPluginKey = new guides.editor.prosemirror.state.PluginKey("xrefDisplay");
  
  const createXrefPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: xrefPluginKey,
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name.includes("xref")) {
                const display = node.attrs?.xmlAttrs?.placeholdertext;
                if (display) {
                  decorations.push(
                    Decoration.widget(pos + 1, () => {
                      const el = document.createElement("span");
                      el.textContent = `[${display}]`;
                      el.setAttribute("contenteditable", "false");
                      return el;
                    }, { key: `xref-${pos}` })
                  );
                }
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.xref-display-text { color: #0074d9; pointer-events: none; }`
    };
  };
  ```

## Inserimento di CSS nell’editor

L&#39;editor DITA delle guide carica gli stili di contenuto in modalità di authoring da una libreria client con categoria `apps.guides.dita_editor.content`. La libreria client ha una dichiarazione `embed` che richiama automaticamente qualsiasi libreria client registrata nella categoria:

```
apps.guides.xml_editor.dita_content_overrides
```

Per inserire CSS personalizzati nell’area del contenuto dell’editor, crea un nodo clientlib di AEM con questa categoria. Non è necessario alcun cablaggio aggiuntivo; Guides lo seleziona automaticamente al caricamento della pagina dell&#39;editor.

**struttura nodo clientlib di AEM (`/apps/my-extension/clientlibs/editor-content-overrides/.content.xml`)**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:cq="http://www.day.com/jcr/cq/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
    jcr:primaryType="cq:ClientLibraryFolder"
    categories="[apps.guides.xml_editor.dita_content_overrides]"/>
```

Inserisci il file CSS (`css.txt` + il file `.css`) in questa cartella. Verrà incorporato automaticamente nel foglio di stile di contenuto dell’editor.

**Esempio: sostituire gli stili di titolo delle sezioni in modalità di creazione**

```css
/* /apps/my-extension/clientlibs/editor-content-overrides/css/content.css */

/* Increase section title font size in author mode */
.section > title {
  font-size: 1.4em;
  font-weight: bold;
  color: #333;
}

/* Highlight note blocks */
.note {
  border-left: 4px solid #0074d9;
  padding-left: 12px;
  background: #f0f7ff;
}
```

>[!NOTE]
>
>Questo CSS esegue il targeting solo della superficie di authoring legacy basata su CKEditor. Non ha alcun effetto all&#39;interno del nuovo editor (ProseMirror), che utilizza un DOM ombra.


### Nuovo editor: `css` in `registerPlugin`

Il nuovo editor esegue il rendering all&#39;interno di un **DOM shadow**, che lo isola da tutti gli stili a livello di pagina, incluso AEM `clientlibs`. Per inserire CSS nella superficie di authoring del nuovo editor, passa una stringa `css` come parte di `PluginConfig` restituita dalla tua factory del plug-in.

Il file CSS viene inserito come tag `<style>` direttamente all&#39;interno della radice shadow dell&#39;editor ogni volta che viene creata un&#39;istanza dell&#39;editor.

**Esempio: inserire gli stili accanto a un plug-in di decorazione**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: createMyPlugin(), // your ProseMirror plugin
    css: `
      /* Styles scoped to the New Editor shadow DOM */
      .section > .title-node {
        font-size: 1.4em;
        font-weight: bold;
        color: #333;
      }

      .note-node {
        border-left: 4px solid #0074d9;
        padding-left: 12px;
        background: #f0f7ff;
      }
    `
  }));
});
```

**Esempio: plug-in solo CSS (nessuna logica di decorazione)**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no-op plugin
    css: `
      /* Custom author-mode typography */
      [data-xml-element="codeblock"] {
        font-family: monospace;
        background: #f5f5f5;
        padding: 8px;
        border-radius: 4px;
      }
    `
  }));
});
```

>[!NOTE]
>
> Questo CSS si applica solo all’interno del DOM shadow del nuovo editor. Non ha alcun effetto sul resto della pagina o sull’editor legacy.


## Estensioni del menu di scelta rapida (`contextMenuWidget`)

Le estensioni possono aggiungere elementi al menu di scelta rapida dell&#39;editor facendo clic con il pulsante destro del mouse o dichiarando un campo `contextMenuWidget` nella configurazione dell&#39;estensione. Questo comunica al framework quale menu dell’editor eseguire il targeting.

### ID widget

| ID widget | Editor |
|---|---|
| `dita_editor_menu` | Superficie di authoring CKEditor legacy (menu di scelta rapida breadcrumb + elemento) |
| `markup_editor_menu` | Menu di scelta rapida Nuovo editor (ProseMirror) breadcrumb ed elemento |

Entrambi i widget vengono montati sulla pagina contemporaneamente. Il framework corrisponde ogni estensione al menu corretto basato su questo campo.

> Le estensioni possono inoltre eseguire il targeting di entrambi gli editor passando un array: `contextMenuWidget: ["dita_editor_menu", "markup_editor_menu"]`

### Editor legacy: `dita_editor_menu`

Utilizzalo per le estensioni che dovrebbero essere visualizzate nel menu di scelta rapida legacy di CKEditor.

```js
const myContextMenuExtension = {
  id: "dita_author_view_menu",
  contextMenuWidget: "dita_editor_menu",
  view: {
    items: [
      {
        displayName: "My Custom Action",
        data: { eventid: "myCustomAction" },
        icon: "textSpaceAfter",
        target: {
          key: "displayName",
          value: "Wrap Element",   // insert after this existing menu item
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    myCustomAction() {
      console.log("Custom action triggered");
    },
  },
};
```

### Nuovo editor: `markup_editor_menu`

Utilizzalo per le estensioni che dovrebbero essere visualizzate nel menu di scelta rapida Nuovo editor (breadcrumb e clic con il pulsante destro del mouse sugli elementi). Il controller riceve eventi tramite `handleExtensionEvent`, che indirizza i gestori locali al controller `markup_editor_menu` e invia eventi globali tramite il gestore eventi dell&#39;app.

```js
const myMarkupContextMenu = {
  id: "dita_author_view_menu",
  contextMenuWidget: "markup_editor_menu",
  view: {
    items: [
      {
        displayName: "Edit Cross Reference",
        data: { eventid: "editCrossReference" },
        icon: "link",
        target: {
          key: "displayName",
          value: "Cut",
          viewState: "prepend",
        },
      },
      {
        displayName: "Remove Cross Reference",
        data: { eventid: "removeCrossReference" },
        icon: "deleteOutline",
        target: {
          key: "displayName",
          value: "Edit Cross Reference",
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    editCrossReference() {
      // Use guides.editor APIs to read context
      const ancestorXpaths = guides.editor.runUtil("getAncestorXpaths", true);
      // open dialog or take action...
    },
    removeCrossReference() {
      guides.editor.runCommand("unwrapNode");
    },
  },
};
```

## Librerie di utilità

- Libreria dell&#39;utilità lodash `guides.util.lodash`:The, stessa istanza inclusa nell&#39;editor.

  ```js
  const uniqueIds = guides.util.lodash.uniq(ids);
  ```

- `guides.util.async`: libreria di utilità asincrona per l&#39;utilizzo dell&#39;estensione.

  ```js
  guides.util.async.parallel([task1, task2], callback);
  ```

## Riferimento API completo

| API | Descrizione |
|---|---|
| `filePath` | Ottieni il percorso file del documento attivo |
| `version` | Ottieni la stringa della versione dell’editor caricata |
| `appState(key)` | Leggi un valore dal modello dell’applicazione |
| `focus()` | Attiva l&#39;editor attivo |
| `canInsertXmlElement(tag, insertAfter?)` | Controlla se è possibile inserire un elemento in corrispondenza del cursore |
| `selectCurrentBlockElement()` | Seleziona l’elemento del blocco corrente |
| `getValidElementNamesForInsertion(args)` | Elenca nomi di elementi validi per l&#39;inserimento |
| `updateAttributeByXpath(args)` | Aggiornare un attributo con XPath |
| `runCommand(name, ...args)` | Esegui un comando dell’editor denominato |
| `canRunCommand(name, ...args)` | Verifica se un comando può essere eseguito |
| `runUtil(name, ...args)` | Richiama un&#39;utilità di editor denominata |
| `addDecoration(id, selector, options)` | Aggiungere o sostituire una regola di decorazione denominata sugli elementi corrispondenti |
| `removeDecoration(id)` | Rimuovere una regola di decorazione per ID |
| `batchDecorations(changes)` | Applicazione di più modifiche di aggiunta/rimozione di elementi decorativi in un&#39;unica spedizione |
| `clearDecorations()` | Rimuovi tutte le regole di decorazione attive |
| `getDecorations()` | Ottieni ID di tutte le decorazioni attualmente attive |
| `registerPlugin(factory)` | Registra una fabbrica di plug-in ProseMirror (anche il meccanismo per l&#39;iniezione CSS DOM ombra) |
| `prosemirror.state` | Pacchetto `prosemirror-state` |
| `prosemirror.model` | Pacchetto `prosemirror-model` |
| `prosemirror.view` | Pacchetto `prosemirror-view` |
| `prosemirror.transform` | Pacchetto `prosemirror-transform` |
| `prosemirror.commands` | Pacchetto `prosemirror-commands` |
| `prosemirror.keymap` | Pacchetto `prosemirror-keymap` |
| `prosemirror.history` | Pacchetto `prosemirror-history` |
| `prosemirror.tables` | Pacchetto `prosemirror-tables` |
| `prosemirror.dropcursor` | Pacchetto `prosemirror-dropcursor` |
| `prosemirror.collab` | Pacchetto `prosemirror-collab` |
| `prosemirror.markdown` | Pacchetto `prosemirror-markdown` |
