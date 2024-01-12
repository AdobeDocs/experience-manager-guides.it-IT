---
title: Personalizza barra degli strumenti
description: Scopri come personalizzare la barra degli strumenti
exl-id: 14a82c7e-5c07-43a8-bd9e-b221d80f6d05
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---

# Personalizza barra degli strumenti {#id172FB00L0V6}

Per impostazione predefinita, l&#39;Editor Web viene fornito con le funzioni editoriali più comuni richieste da qualsiasi editor DITA. Nell’editor sono disponibili funzioni quali l’inserimento di elementi di tipo elenco \(numerato o puntato\), riferimenti incrociati, riferimenti a contenuti, tabelle, paragrafi e formattazione di caratteri. Oltre a questi elementi di base, è possibile personalizzare l&#39;Editor Web per inserire elementi utilizzati nell&#39;ambiente di authoring.

Esistono due modi per personalizzare la barra degli strumenti dell’editor web:

- Aggiungere una nuova funzionalità alla barra degli strumenti

- Rimuovi eventuali funzionalità esistenti dalla barra degli strumenti


## Aggiungere una feature nella barra degli strumenti

L’aggiunta di una funzionalità all’editor web comporta due attività principali: l’aggiunta di un’icona per la funzione nel *ui\_config.json* e aggiungendo la funzionalità di background in JavaScript.

**Aggiungi un’icona nella barra degli strumenti**

Per aggiungere una funzionalità alla barra degli strumenti dell&#39;editor Web, effettuare le operazioni riportate di seguito.

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passare al file di configurazione predefinito disponibile nella posizione seguente:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Creare una copia del file di configurazione predefinito nella posizione seguente:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accedi a e apri il `ui_config.json` file in `apps` per la modifica.

1. In `ui_config.json` aggiungere la definizione della nuova feature nella sezione barre degli strumenti. In genere, è possibile creare un nuovo gruppo di pulsanti della barra degli strumenti e aggiungervi uno o più pulsanti. In alternativa, è possibile aggiungere un nuovo pulsante della barra degli strumenti all&#39;interno di un gruppo di barre degli strumenti esistente. Per creare un nuovo gruppo di barre degli strumenti sono necessari i seguenti dettagli:

   - **type:**Specify `blockGroup` come `type` valore. Questo valore indica che si sta creando un gruppo di blocchi contenente uno o più gruppi di barre degli strumenti.

   - **extraclass:** Nome della classe o delle classi separate da spazio.

   - **elementi:** Specificate la definizione di tutti i gruppi nella barra degli strumenti. Ogni gruppo può contenere una o più icone della barra degli strumenti. Per definire le icone all&#39;interno di un gruppo di barre degli strumenti, è necessario definire nuovamente `type` all&#39;interno del `items`e impostarne il valore su `buttonGroup`. Specifica uno o più nomi di classe in `extraclass` proprietà. Specificate il nome della feature nella `label` proprietà. Lo snippet seguente proveniente da `ui_config.json` file mostra la definizione del blocco della barra degli strumenti principale, seguito da `buttonGroup` definizione:

     ```json
     "toolbar": {    
       "type": "blockGroup",    
       "extraclass": 
       "toolbar operations",    
         "items": [      
           {        
             "type": "buttonGroup",        
             "extraclass": "left-controls",        
             "label": "Left Controls",        
             "items": [
     ```

     All&#39;interno del `items` raccolta, è necessario specificare la definizione per una o più icone della barra degli strumenti.
Per aggiungere un&#39;icona a forma di barra degli strumenti, è necessario definire le seguenti proprietà:

   - **tipo:** Specifica `button` come `type` valore. Questo valore indica che si sta aggiungendo un pulsante della barra degli strumenti.

   - **icona:** Specificate il nome dell&#39;icona Coral da utilizzare nella barra degli strumenti.

   - **variante:** Specifica `quiet` come `variant` valore.

   - **titolo:** Specifica la descrizione comando per l’icona.

   - **clic:** Specifica il nome del comando definito per la funzione nel file JavaScript. Se il comando richiede parametri di input, specificare il nome del comando come:

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **mostra o nascondi:** Se si sta definendo `show` , quindi specificare le modalità di visualizzazione dell&#39;icona. I valori possibili sono - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(visualizza in tutte le modalità\), oppure `false` \(nascondi in tutte le modalità\).

   In sostituzione di `show`, puoi anche definire `hide` proprietà. I valori possibili sono gli stessi di `show` con l’unica differenza che l’icona non viene visualizzata per la modalità specificata.

1. Creare un *clientlib* e aggiungi il tuo JavaScript a questa cartella.

1. Aggiornare la proprietà Categories del *clientlib* assegnandogli il valore di *apps.fmdita.xml\_editor.page\_overrides*.

1. Salva il *ui\_config.json* e ricaricare l&#39;editor Web.


**Esempi di codice JavaScript**

Questa sezione fornisce due esempi di codice JavaScript utili per iniziare ad aggiungere funzionalità personalizzate. L’esempio seguente mostra il numero di versione delle guide AEM quando un utente fa clic sull’icona Mostra versione nella barra degli strumenti.

Aggiungi il seguente codice a un file JavaScript:

```JavaScript
/**
* This file contains an example to show AEM Guides version 
* number when a user clicks on the Show Version icon in the toolbar. 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  window.addEventListener('DOMContentLoaded', function () {
    fmxml.ready(function () {
      fmxml.eventHandler.subscribe({
        key: 'user.alert',
        next: function next() {
          alert("AEM Guides version x.x");
        }
      });
    });
  });
})(window);
```

Aggiungi la funzione nel file ui\_config.json come:

```json
 {
      "type": "button",
      "icon": "alert",
      "title": "About AEM Guides",
      "variant": "quiet",

  "show": "true",
      "on-click": "user.alert"
  } 
```

Nell&#39;esempio seguente viene illustrato come modificare lo stato di un documento di un file attivo in &quot;In-Review&quot;.

```JavaScript
/**
* This file contains an example to set the document state of an active *open documen to "In-Review". 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  //Wait for the page has been completely loaded 

  window.addEventListener('DOMContentLoaded', function () {

    //Wait for the xml editor to start
    fmxml.ready(function () {

      //Subscribe to 'user.docstate.to.in-review' event
      fmxml.eventHandler.subscribe({
        key: 'user.docstate.to.in-review',
        next: function next() {
          var docstate = "In-Review"; // New docstate name
          var filePath = fmxml.curEditor.filePath; 
// Get the file path of active open file
          if (filePath) {
            //Call API to change the doc state
            $.ajax({
              type: 'POST',
              url: '/bin/fmdita/states',
              data: {
                paths: filePath,
                operation: "setdocstates",
                docstate: docstate
              }
            }).fail(function (xhr, textStatus, errorThrown) {
              console.error("Cannot update docstate to " + docstate);
            }).success(function (data) {
              console.log('docstate updated to ' + docstate);
            });
          }
        }
      });
    });
  });
})(window);
```

Aggiungi la funzione nel file ui\_config.json come:

```json
 {
      "type": "button",
      "icon": "actions",
      "title": "Change document state to In-Review",
      "variant": "quiet",
      "show": "true",
      "on-click": "user.docstate.to.in-review"
    } 
```

## Rimuovere una feature dalla barra degli strumenti

Talvolta è possibile non assegnare tutte le funzionalità attualmente disponibili nell&#39;editor Web, in tal caso è possibile rimuovere la funzionalità indesiderata dalla barra degli strumenti dell&#39;editor Web.

Per rimuovere qualsiasi feature indesiderata dalla barra degli strumenti, effettuate le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passa al file di configurazione predefinito disponibile nella posizione seguente:.

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Creare una copia del file di configurazione predefinito nella posizione seguente:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accedi a e apri il `ui_config.json` file in `apps` per la modifica.
Il `ui_config.json` Il file è suddiviso in tre sezioni:

- **barre degli strumenti:**   Questa sezione contiene la definizione di tutte le funzioni disponibili nella barra degli strumenti dell’editor, ad esempio Inserisci/Rimuovi elenco numerato, \(file\) Chiudi, Salva, Commenti e altro ancora.

- **collegamenti:**   Questa sezione contiene la definizione delle scelte rapide da tastiera assegnate a una particolare funzione nell’editor.

- **modelli:**   Questa sezione contiene la struttura predefinita degli elementi DITA che è possibile utilizzare nel documento. Per impostazione predefinita, la sezione modelli contiene le definizioni dei modelli per gli elementi paragrafo, tabella semplice, tabella e corpo. Puoi creare una definizione di modello per qualsiasi elemento aggiungendo una struttura XML valida per l’elemento desiderato. Ad esempio, se desideri aggiungere una `p` con ogni nuovo elemento `li` in un elenco, puoi aggiungere il seguente codice alla fine della sezione modelli per ottenere questo risultato:

```HTML
"li": "<li><p></p></li>"
```

1. Dalla sezione delle barre degli strumenti, rimuovere la voce della caratteristica che non si desidera esporre agli utenti.

1. Salva il *ui\_config.json* e ricaricare l&#39;editor Web.


**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
