---
title: Mappatura dei componenti per AEM Sites
description: Scopri come eseguire la mappatura dei componenti per AEM Sites
feature: Installation
role: Admin
level: Experienced
exl-id: f59e3ad5-bf9c-468d-aab7-144c8c2335ac
source-git-commit: beb1ca15fdfb0e7ea30e6e685ac67a2a398cc064
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---

# Mappatura dei componenti per AEM Sites

L’articolo tratta i vari aspetti della mappatura dei componenti per i siti AEM (utilizzando la mappatura dei componenti compositi).

## Regole di mappatura dei componenti

Utilizza un array JSON di regole (il tuo `componentmapping.json`) per convertire HTML in componenti. Usa regole il più possibile semplici, esplicite e specifiche.

### Eseguire il targeting dell’elemento HTML e della relativa classe

- Scrivere il nome del tag HTML in `name`.
- Includere la classe CSS applicata all&#39;elemento in `class`, se la classe esiste.
Esempio:

  ```html
  <div class ="sample-class">
  <p> Sample html element </p>
  </div>
  ```

  ```json
  {
  "name": "div",
  "class": "sample-class",
  "resourceType": "guides-components/components/table",
  "attributeMap": []
  }
  ```

Durante la definizione degli elementi di cui sopra, assicurati quanto segue:

- `name` può essere un elenco separato da virgole (ad esempio, `"h1, h2"`).
- `class` deve essere presente nell&#39;elemento (tutte le classi elencate devono corrispondere).
- `resourceType` indica che si intende utilizzare il componente `table`. Il pacchetto `guides-components` è un OOTB fornito dalle guide. Se necessario, è possibile utilizzare anche altri pacchetti di componenti, ad esempio `core/wcm/`.

### Utilizza attributeMap per salvare le proprietà sul nodo JCR

Aggiungere voci a `attributeMap` per impostare le proprietà nel nodo di output. Ogni voce produce `attrs[to] = value`.
Pattern comuni:

```json
// copy an attribute
{ "attribute": "src", "to": "image-src" }
// read content or tag name
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "text" }
{ "from": "name",       "to": "type" }  // the tag name, e.g., "h2"
// constant value
{ "value": true, "to": "textIsRich" }
```

Di seguito è riportato un esempio da HTML a JSON per un elemento immagine.

```html
<img src="/content/dam/aemg-docs/tragopan.svg" class="cmp-image__image" itemprop="contentUrl" data-cmp-hook-image="image" alt="">
```

```json
{
    "name": "img",
    "resourceType": "core/wcm/components/image/v2/image",
    "attributeMap": [
      {
        "from": "src",
        "to": "fileReference"
      },
      {
        "value": ["fileReference"],
        "to": "path-attributes"
      }
    ]
  }
```

### Normalizzare i percorsi tramite una voce dedicata

Per normalizzare (rendere assoluti) i valori, dichiarare quali chiavi di attributo devono essere normalizzate utilizzando:

```json
{
  "value": ["text"],
  "to": "path-attributes"
}
```

Assicurati di occuparti dei seguenti punti importanti:

- Inserire l&#39;elenco dei nomi di proprietà che si desidera normalizzare in `value` (ad esempio, `["text"]` o `["href", "src"]`).
- Durante la creazione del componente finale, il sistema normalizzerà tutti i valori trovati sotto tali nomi di proprietà.


### Estrarre i valori HTML prima di suddividerli in componenti

Utilizzare `from` per specificare come leggere un valore dall&#39;elemento prima che il documento venga suddiviso in componenti separati:

- `"textContent"`: testo normale dell&#39;elemento
- `"outerHTML"`: l&#39;elemento e il relativo markup interno
- `"innerHTML"`: solo markup interno dell&#39;elemento
- Qualsiasi altra stringa: trattata come nome di attributo (ad esempio, `"src"`, `"href"`)


Esempi:

```json
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "snippet" }
{ "from": "src",        "to": "image#src" }
```

### Esempio end-to-end minimo in componentmapping.json

```json
[
  {
    "name": "h1, h2",
    "class": "topic-title",
    "resourceType": "core/wcm/components/title/v2/title",
    "attributeMap": [
      { "from": "textContent", "to": "text" },
      { "from": "name",        "to": "type" }
    ]
  },
  {
    "name": "img",
    "class": "hero",
    "resourceType": "weretail/components/content/heroimage",
    "attributeMap": [
      { "from": "src", "to": "image#src" },
      { "value": ["image#src"], "to": "path-attributes" }
    ]
  },
  {
    "name": "#element",
    "resourceType": "core/wcm/components/text/v2/text",
    "attributeMap": [
      { "from": "outerHTML", "to": "text" },
      { "value": true,        "to": "textIsRich" }
    ]
  }
]
```

Definisci l&#39;elemento e la classe di destinazione, utilizza `attributeMap` per impostare le proprietà del nodo, aggiungi una voce `path-attributes` per normalizzare i percorsi e scegli il `from` destro per i valori che desideri estrarre. `heroimage` utilizzato in precedenza è un componente in un sito `we-retail`.

**Nota**: è importante discutere il testo RTF predefinito e identificare gli elementi per i quali viene utilizzato.

## Creare un componente personalizzato

Scopri come creare un componente tabella personalizzato che visualizzi le immagini all’interno delle celle. Questo approccio garantisce un design pulito e riutilizzabile per i contenuti dinamici. Copre ciò che verrà creato, il motivo per cui è efficace, i prerequisiti chiave, il design di alto livello e altro ancora.

### Cosa verrà creato

Componente tabella personalizzato che accetta il contenuto della tabella HTML e sostituisce ogni `<img>` al suo interno con l’output del componente Immagine core di AEM. Questo consente di riutilizzare le funzioni dell’immagine core (immagini reattive, gestione delle opzioni Alt, accessibilità) mantenendo al contempo il controllo completo sul markup della tabella.
Utilizzando questo approccio, puoi creare altri componenti personalizzati per il sito web di AEM (utilizzando la mappatura dei componenti compositi).

### Perché questo approccio

- **Riutilizza**: sfrutta il comportamento maturo dell&#39;immagine core invece di implementarla nuovamente.
- **Coerenza**: le immagini nella tabella si comportano come le immagini in altre parti del sito.
- **Lato server**: le immagini vengono sottoposte a rendering sul server per migliorare le prestazioni, l&#39;ottimizzazione SEO e l&#39;accessibilità.

### Prerequisiti

- AEM SDK in esecuzione e questo progetto è stato estratto.
- Componenti core installati nell’istanza AEM.
- Maven disponibile per la generazione e la distribuzione.

### Design di alto livello

- Nella finestra di dialogo del componente, Autore fornisce HTML per la tabella.
- Un modello Sling analizza che HTML, trova `<img>` tag e, per ogni immagine, chiama un servizio che esegue il rendering del componente immagine core lato server.
- Il modello scambia l&#39;originale `<img>` con l&#39;immagine core acquisita di HTML e passa il HTML completato ad HTL per l&#39;output.

La tabella viene generata una sola volta e contiene già il markup Immagine core. Non è necessaria alcuna manipolazione DOM lato client.

### Struttura delle cartelle e file chiave (in questo archivio)

- Componente HTL e clientlibs: `ui.apps/src/main/content/jcr_root/apps/guides-components/components/table/`
   - `table.html` (renderer HTL)
   - `_cq_editConfig.xml` (aggiorna listener)
   - `clientlibs/` con `css.txt`, `js.txt`, `css/table.css`, `js/table.js`
- Modello Sling: `core/src/main/java/com/adobe/guides/aem/components/core/models/TableModel.java`
- Servizio di rendering immagini: `core/src/main/java/com/adobe/guides/aem/components/core/services/ImageComponentRenderer.java`

### Passaggi di implementazione

**Definire il componente Tabella (nodo componente)**

Crea il componente in `apps/guides-components/components/table`. Se non ne hai già uno, aggiungi un minimo di `.content.xml` come di seguito per registrarlo nel pannello laterale.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
          jcr:primaryType="cq:Component"
          jcr:title="Table"
          componentGroup="Guides - Custom"/>
```

Indica ad AEM che si tratta di un componente disponibile per gli autori per l’aggiunta alle pagine.

**Esegui rendering con HTL e includi stili**

Utilizza un modello Sling e genera il HTML elaborato. Includi la categoria clientlib per CSS/JS.

```html
<sly data-sly-use.model="com.adobe.guides.aem.components.core.models.TableModel"
     data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html">
</sly>
<sly data-sly-call="${clientLib.css @ categories='guides-components.table'}"></sly>
<sly data-sly-test="${wcmmode.edit && !model.hasContent}">
  <div class="cq-placeholder" data-emptytext="${component.title}"></div>
</sly>
<div data-sly-test="${model.hasContent}"
     class="gu-table-wrapper ${model.enableResponsive ? 'gu-table--responsive' : ''} gu-table--style-${model.tableStyle}"
     id="${model.componentId}">
  ${model.processedTableHtml @ context='unsafe'}
</div>
```

Il modello restituisce HTML completo con l’immagine core già renderizzata, quindi HTL lo stampa e basta.

**Aggiungi il modello Sling per elaborare HTML ed eseguire il rendering dell&#39;immagine core**

Il modello legge i campi della finestra di dialogo, analizza la tabella HTML, trova ogni `<img>` e lo sostituisce con Core Image HTML tramite un servizio.

Di seguito sono riportate alcune delle conoscenze importanti per `TableModel`:

- Legge `tableHtml`, `enableResponsive`, `tableStyle` dalle proprietà della risorsa.
- Utilizza Jsoup per analizzare e modificare HTML in modo sicuro.
- Chiama `ImageComponentRenderer` per eseguire il rendering dell&#39;immagine core e acquisire HTML.
- Mantiene le classi e lo stile CSS dall&#39;originale `<img>`.
- Normalizza i percorsi DAM (rimuove `/jcr:content/renditions/*`).

```java
@Model(adaptables = {Resource.class, SlingHttpServletRequest.class},
       defaultInjectionStrategy = DefaultInjectionStrategy.OPTIONAL)
public class TableModel {
  @ValueMapValue private String tableHtml;
  @ValueMapValue private boolean enableResponsive;
  @ValueMapValue private String tableStyle;
  @OSGiService private ImageComponentRenderer imageRenderer;
  // ...
  @PostConstruct
  protected void init() {
    // parse HTML, for each <img> build image props (fileReference, alt, title)
    // call imageRenderer.renderImageComponent(...)
    // replace <img> with returned Core Image HTML
  }
  public String getProcessedTableHtml() { /* return final HTML */ }
}
```

Questo centralizza la logica sul server e riutilizza il comportamento Immagine core.

**Esegui rendering dell&#39;immagine di base tramite un servizio (server-side include)**

`ImageComponentRenderer` esegue il rendering del componente immagine core e acquisisce l&#39;output. It

- invia a capo una risorsa che forza `core/wcm/components/image/v2/image`.
- utilizza `RequestDispatcher#include` per il rendering.
- acquisisce la risposta come stringa.

```java
@Component(service = ImageComponentRenderer.class)
public class ImageComponentRenderer {
  private static final String IMAGE_RESOURCE_TYPE = "core/wcm/components/image/v2/image";
  public String renderImageComponent(Resource base, Map<String,Object> props,
                                     SlingHttpServletRequest req, SlingHttpServletResponse resp) {
    // create wrapped resource with IMAGE_RESOURCE_TYPE and props
    // dispatcher.include(...) with a response wrapper to capture HTML
    // return captured HTML
  }
}
```

Questo ti consente di **rilasciare l&#39;immagine principale** ovunque ti serva, non solo come componente secondario.

**Librerie client**

Crea una libreria client per piccoli stili o JS futuri. L&#39;HTL riportato sopra carica la categoria `guides-components.table`.

```java
clientlibs/css.txt
  #base=css
  table.css
clientlibs/js.txt
  #base=js
  table.js
  
```

In questo modo gli stili e gli script sono sempre modulari e individuabili.

**Campi finestra di dialogo (input autore)**

Aggiungi una finestra di dialogo con almeno le seguenti proprietà:

- **Tabella HTML**: `./tableHtml` (area di testo); HTML della tabella.
- **Abilita responsive**: `./enableResponsive` (casella di controllo); attiva una classe di wrapper responsive.
- **Stile tabella**: `./tableStyle` (selezione); applica una classe di modificatori di stile.

Questi mappano 1:1 alle proprietà del modello Sling e controllano il rendering.

**Consenti il componente nei modelli**

Nell&#39;Editor modelli, modifica il criterio Contenitore di layout > Componenti consentiti > abilita il componente Tabella in **Guide - Personalizzato**.

Gli autori non possono aggiungere componenti finché i criteri non lo consentono.

## Suggerimenti per l’authoring

- Incolla un HTML valido per la tabella. Il modello bonifica e regola gli URL dell’immagine.
- Utilizza i percorsi delle risorse DAM per le immagini; le rappresentazioni vengono normalizzate nel percorso della risorsa originale.
- Se possibile, inserisci testo alternativo nel HTML; in caso contrario, le immagini sono contrassegnate come decorative.

## Vincoli

- Il servizio forza l’immagine core v2. Per cambiare versione, aggiornare `IMAGE_RESOURCE_TYPE`.
- Per il rendering sintetico, il modello sostituisce gli URL `.coreimg.` generati dall&#39;immagine core con percorsi DAM diretti e rimuove `srcset` per evitare URL interrotti.
- Tutto il rendering viene eseguito una volta sul server; JavaScript è facoltativo.

## Riferimento rapido (implementazione)

- HTML: `ui.apps/.../components/table/table.html`
- Clientlibs: `ui.apps/.../components/table/clientlibs/`
- Modello: `core/.../models/TableModel.java`
- Servizio: `core/.../services/ImageComponentRenderer.java`

Questo modello mostra come comporre un componente personalizzato con un componente core lato server, mantenendo il markup durante il riutilizzo della logica core.
