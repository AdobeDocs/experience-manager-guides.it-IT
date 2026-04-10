---
title: Personalizza barra degli strumenti
description: Scopri come personalizzare la barra degli strumenti
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 5057f9935982d4b13c245453f15a93f48679f16b
workflow-type: tm+mt
source-wordcount: '1717'
ht-degree: 0%

---

# Personalizza barra degli strumenti {#id172FB00L0V6}

Per impostazione predefinita, l&#39;Editor Web viene fornito con le funzioni editoriali più comuni richieste da qualsiasi editor DITA. Nell’editor sono disponibili funzioni quali l’inserimento di elementi di tipo elenco \(numerato o puntato\), riferimenti incrociati, riferimenti a contenuti, tabelle, paragrafi e formattazione di caratteri. Oltre a questi elementi di base, è possibile personalizzare l&#39;Editor Web per inserire elementi utilizzati nell&#39;ambiente di authoring.

>[!NOTE]
>
> Durante la migrazione dalla vecchia interfaccia alla nuova interfaccia utente di AEM Guides (applicabile dalle versioni 2502 e 5.0 di AEM Guides), gli aggiornamenti a `ui_config` devono essere convertiti in configurazioni dell&#39;interfaccia utente più flessibili e modulari. Questo framework consente di adottare le modifiche direttamente nell’editor_toolbar e in altri widget di destinazione, a seconda delle necessità. Per ulteriori dettagli, visualizzare [Panoramica della configurazione dell&#39;interfaccia utente di conversione](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

Esistono due modi per personalizzare la barra degli strumenti dell’editor web:

- Aggiungere una nuova funzionalità alla barra degli strumenti

- Rimuovi eventuali funzionalità esistenti dalla barra degli strumenti


## Aggiungere una feature nella barra degli strumenti

L&#39;aggiunta di una funzionalità all&#39;editor Web comporta due attività principali: l&#39;aggiunta di un&#39;icona per la funzionalità nel file *ui\_config.json* e l&#39;aggiunta della funzionalità in background in JavaScript.

Le seguenti schede forniscono istruzioni in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti e fai clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto
1. Fai clic sull&#39;icona **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.
1. Nel file `ui_config.json`, aggiungere la definizione della nuova funzionalità nella sezione delle barre degli strumenti. Salva il file e caricalo.

   In genere, è possibile creare un nuovo gruppo di pulsanti della barra degli strumenti e aggiungervi uno o più pulsanti. In alternativa, è possibile aggiungere un nuovo pulsante della barra degli strumenti all&#39;interno di un gruppo di barre degli strumenti esistente. Per creare un nuovo gruppo di barre degli strumenti sono necessari i seguenti dettagli:

   **tipo**:   Specificare `blockGroup` come valore `type`. Questo valore indica che si sta creando un gruppo di blocchi contenente uno o più gruppi di barre degli strumenti.

   **extraclass**:   Nome della classe o delle classi separate da spazio.

   **elementi**:   Specificate la definizione di tutti i gruppi nella barra degli strumenti. Ogni gruppo può contenere una o più icone della barra degli strumenti. Per definire le icone all&#39;interno di un gruppo di barre degli strumenti, è necessario definire nuovamente l&#39;attributo `type` all&#39;interno di `items` e impostarne il valore su `buttonGroup`. Specificare uno o più nomi di classe nella proprietà `extraclass`. Specificare il nome della funzionalità nella proprietà `label`. Il frammento seguente del file `ui_config.json` mostra la definizione per il blocco della barra degli strumenti principale, seguito dalla definizione `buttonGroup`:

       &quot;
       &quot;toolbar&quot;: &lbrace;
       &quot;type&quot;: &quot;blockGroup&quot;,
       &quot;extraclass&quot;:
       &quot;operazioni barra degli strumenti&quot;,
       &quot;elementi&quot;: &lbrack;
       &lbrace;
       &quot;type&quot;: &quot;buttonGroup&quot;,
       &quot;extraclass&quot;: &quot;left-controls&quot;,
       &quot;label&quot;: &quot;Left Controls&quot;,
       &quot;elementi&quot;: &lbrack;
       &quot;
   
   Nell&#39;insieme `items` è necessario specificare la definizione di una o più icone della barra degli strumenti.

   Per aggiungere un&#39;icona a forma di barra degli strumenti, è necessario definire le seguenti proprietà:

   **tipo**:   Specificare `button` come valore `type`. Questo valore indica che si sta aggiungendo un pulsante della barra degli strumenti.

   **icona**:   Specificate il nome dell&#39;icona Coral da utilizzare nella barra degli strumenti.

   **variante**:   Specificare `quiet` come valore `variant`.

   **titolo**:   Specifica la descrizione comando per l’icona.

   **al clic**:   Specificate il nome del comando definito per la feature nel file JavaScript. Se il comando richiede parametri di input, specificare il nome del comando come:

       &quot;Javascript
       &quot;al clic&quot;: {&quot;name&quot;: &quot;AUTHOR_INSERT_ELEMENT&quot;, &quot;args&quot;: &quot;simpletable&quot;}
       &quot;
   
   **mostra o nascondi**:   Se si sta definendo la proprietà `show`, specificare le modalità di visualizzazione dell&#39;icona. I valori possibili sono - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(visualizza in tutte le modalità\) o `false` \(nascondi in tutte le modalità\).

   Al posto di `show`, puoi anche definire la proprietà `hide`. I valori possibili sono gli stessi della proprietà `show` con l&#39;unica differenza che l&#39;icona non viene visualizzata per la modalità specificata.

   L’esempio seguente mostra il numero di versione di AEM Guides quando l’utente fa clic sull’icona Mostra versione nella barra degli strumenti.

   Aggiungi il codice seguente a un file JavaScript:

   ```Javascript
   $(document).ready(setTimeout(function() {
                           fmxml.commandHandler.subscribe({
                           key: 'user.alert',
                           next: function() {
                           alert("AEM Guides version x.x")
                           }
                           })
                           }, 1000))
   ```

   Aggiungi la funzionalità nel file *ui\_config.json* come:

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Crea una cartella *clientlib* e aggiungi il tuo JavaScript in questa cartella.

1. Aggiorna la proprietà Categories della cartella *clientlib* assegnandole il valore di *apps.fmdita.xml\_editor.page\_overrides*.

1. Salva il file *ui\_config.json* e ricarica l&#39;editor Web.

>[!TAB On-Premise]

1. Accedi ad AEM e apri la modalità CRXDE Lite.

1. Passare al file di configurazione predefinito disponibile nella posizione seguente:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Creare una copia del file di configurazione predefinito nella posizione seguente:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Passare al file `ui_config.json` nel nodo `apps` e aprirlo per la modifica.

1. Nel file `ui_config.json`, aggiungere la definizione della nuova funzionalità nella sezione delle barre degli strumenti. In genere, è possibile creare un nuovo gruppo di pulsanti della barra degli strumenti e aggiungervi uno o più pulsanti. In alternativa, è possibile aggiungere un nuovo pulsante della barra degli strumenti all&#39;interno di un gruppo di barre degli strumenti esistente. Per creare un nuovo gruppo di barre degli strumenti sono necessari i seguenti dettagli:

   - **type:**&#x200B;Specificare `blockGroup` come valore `type`. Questo valore indica che si sta creando un gruppo di blocchi contenente uno o più gruppi di barre degli strumenti.

   - **extraclass:** Nome della classe o delle classi separate da spazio.

   - **elementi:** Specificare la definizione di tutti i gruppi nella barra degli strumenti. Ogni gruppo può contenere una o più icone della barra degli strumenti. Per definire le icone all&#39;interno di un gruppo di barre degli strumenti, è necessario definire nuovamente l&#39;attributo `type` all&#39;interno di `items` e impostarne il valore su `buttonGroup`. Specificare uno o più nomi di classe nella proprietà `extraclass`. Specificare il nome della funzionalità nella proprietà `label`. Il frammento seguente del file `ui_config.json` mostra la definizione per il blocco della barra degli strumenti principale, seguito dalla definizione `buttonGroup`:

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

     Nell&#39;insieme `items` è necessario specificare la definizione di una o più icone della barra degli strumenti.
Per aggiungere un&#39;icona a forma di barra degli strumenti, è necessario definire le seguenti proprietà:

   - **tipo:** Specificare `button` come valore `type`. Questo valore indica che si sta aggiungendo un pulsante della barra degli strumenti.

   - **icona:** Specificare il nome dell&#39;icona Coral che si desidera utilizzare nella barra degli strumenti.

   - **variante:** Specificare `quiet` come valore `variant`.

   - **titolo:** Specificare la descrizione comando per l&#39;icona.

   - **al clic del mouse:** Specificare il nome del comando definito per la funzionalità nel file JavaScript. Se il comando richiede parametri di input, specificare il nome del comando come:

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **mostra o nascondi:** Se stai definendo la proprietà `show`, specifica le modalità di visualizzazione dell&#39;icona. I valori possibili sono - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(visualizza in tutte le modalità\) o `false` \(nascondi in tutte le modalità\).

   Al posto di `show`, puoi anche definire la proprietà `hide`. I valori possibili sono gli stessi della proprietà `show` con l&#39;unica differenza che l&#39;icona non viene visualizzata per la modalità specificata.

1. Crea una cartella *clientlib* e aggiungi il tuo JavaScript in questa cartella.

1. Aggiorna la proprietà Categories della cartella *clientlib* assegnandole il valore di *apps.fmdita.xml\_editor.page\_overrides*.

1. Salva il file *ui\_config.json* e ricarica l&#39;editor Web.


**Esempi di codice JavaScript**

Questa sezione fornisce due esempi di codice JavaScript utili per iniziare ad aggiungere funzionalità personalizzate. L’esempio seguente mostra il numero di versione di AEM Guides quando un utente fa clic sull’icona Mostra versione nella barra degli strumenti.

Aggiungi il codice seguente a un file JavaScript:

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

>[!ENDTABS]


## Rimuovere una feature dalla barra degli strumenti

Talvolta è possibile non assegnare tutte le funzionalità attualmente disponibili nell&#39;editor Web, in tal caso è possibile rimuovere la funzionalità indesiderata dalla barra degli strumenti dell&#39;editor Web.

Le schede seguenti forniscono istruzioni per rimuovere eventuali funzioni indesiderate dalla barra degli strumenti in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto
1. Fai clic sull&#39;icona **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.

   Il file `ui_config.json` è suddiviso in tre sezioni:

   1. **barre degli strumenti**:   Questa sezione contiene la definizione di tutte le funzioni disponibili nella barra degli strumenti dell’editor, ad esempio Inserisci/Rimuovi elenco numerato, \(file\) Chiudi, Salva, Commenti e altro ancora.

   1. **collegamenti**:   Questa sezione contiene la definizione delle scelte rapide da tastiera assegnate a una particolare funzione nell’editor.

   1. **modelli**:   Questa sezione contiene la struttura predefinita degli elementi DITA che è possibile utilizzare nel documento. Per impostazione predefinita, la sezione modelli contiene le definizioni dei modelli per gli elementi paragrafo, tabella semplice, tabella e corpo. Puoi creare una definizione di modello per qualsiasi elemento aggiungendo una struttura XML valida per l’elemento desiderato. Ad esempio, se si desidera aggiungere un elemento `p` con ogni nuovo elemento `li` in un elenco, è possibile aggiungere il codice seguente alla fine della sezione dei modelli per ottenere questo risultato:

   ```css
   "li": "<li><p></p></li>"
   ```

1. Dalla sezione delle barre degli strumenti, rimuovere la voce della caratteristica che non si desidera esporre agli utenti.

1. Salva il file *ui\_config.json* e ricarica l&#39;editor Web.

>[!TAB On-Premise]

1. Accedi ad AEM e apri la modalità CRXDE Lite.

1. Passa al file di configurazione predefinito disponibile nella posizione seguente:.

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Creare una copia del file di configurazione predefinito nella posizione seguente:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Passare al file `ui_config.json` nel nodo `apps` e aprirlo per la modifica.
Il file `ui_config.json` è suddiviso in tre sezioni:

- **barre degli strumenti:**   Questa sezione contiene la definizione di tutte le funzioni disponibili nella barra degli strumenti dell’editor, ad esempio Inserisci/Rimuovi elenco numerato, \(file\) Chiudi, Salva, Commenti e altro ancora.

- **collegamenti:**   Questa sezione contiene la definizione delle scelte rapide da tastiera assegnate a una particolare funzione nell’editor.

- **modelli:**   Questa sezione contiene la struttura predefinita degli elementi DITA che è possibile utilizzare nel documento. Per impostazione predefinita, la sezione modelli contiene le definizioni dei modelli per gli elementi paragrafo, tabella semplice, tabella e corpo. Puoi creare una definizione di modello per qualsiasi elemento aggiungendo una struttura XML valida per l’elemento desiderato. Ad esempio, se si desidera aggiungere un elemento `p` con ogni nuovo elemento `li` in un elenco, è possibile aggiungere il codice seguente alla fine della sezione dei modelli per ottenere questo risultato:

```HTML
"li": "<li><p></p></li>"
```

1. Dalla sezione delle barre degli strumenti, rimuovere la voce della caratteristica che non si desidera esporre agli utenti.

1. Salvare il file `*ui\_config.json*` e ricaricare l&#39;editor Web.

>[!ENDTABS]
