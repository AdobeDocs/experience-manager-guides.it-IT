---
title: Personalizza barra degli strumenti
description: Scopri come personalizzare la barra degli strumenti
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---

# Personalizza barra degli strumenti {#id172FB00L0V6}

Per impostazione predefinita, l&#39;Editor Web viene fornito con le funzioni editoriali più comuni richieste da qualsiasi editor DITA. Nell’editor sono disponibili funzioni quali l’inserimento di elementi di tipo elenco \(numerato o puntato\), riferimenti incrociati, riferimenti a contenuti, tabelle, paragrafi e formattazione di caratteri. Oltre a questi elementi di base, è possibile personalizzare l&#39;Editor Web per inserire elementi utilizzati nell&#39;ambiente di authoring.

Esistono due modi per personalizzare la barra degli strumenti dell’editor web:

- Aggiungere una nuova funzionalità alla barra degli strumenti

- Rimuovi eventuali funzionalità esistenti dalla barra degli strumenti


## Aggiungere una feature nella barra degli strumenti

L’aggiunta di una funzionalità all’editor web comporta due attività principali: l’aggiunta di un’icona per la funzione nel *ui\_config.json* e aggiungendo la funzionalità di background in JavaScript.

Per aggiungere una funzionalità alla barra degli strumenti dell&#39;editor Web, effettuare le operazioni riportate di seguito.

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul pulsante **Profilo globale** affiancare.
1. Seleziona la **Configurazione editor XML** e fai clic su **Modifica** icona in alto
1. Fai clic su **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.
1. In `ui_config.json` aggiungere la definizione della nuova feature nella sezione barre degli strumenti. Salva il file e caricalo.

   In genere, è possibile creare un nuovo gruppo di pulsanti della barra degli strumenti e aggiungervi uno o più pulsanti. In alternativa, è possibile aggiungere un nuovo pulsante della barra degli strumenti all&#39;interno di un gruppo di barre degli strumenti esistente. Per creare un nuovo gruppo di barre degli strumenti sono necessari i seguenti dettagli:

   **tipo**: specifica `blockGroup` come `type` valore. Questo valore indica che si sta creando un gruppo di blocchi contenente uno o più gruppi di barre degli strumenti.

   **extraclass**: nome della classe o delle classi separate da spazio.

   **elementi**: specifica la definizione di tutti i gruppi nella barra degli strumenti. Ogni gruppo può contenere una o più icone della barra degli strumenti. Per definire le icone all&#39;interno di un gruppo di barre degli strumenti, è necessario definire nuovamente `type` all&#39;interno del `items`e impostarne il valore su `buttonGroup`. Specifica uno o più nomi di classe in `extraclass` proprietà. Specificate il nome della feature nella `label` proprietà. Lo snippet seguente proveniente da `ui_config.json` file mostra la definizione del blocco della barra degli strumenti principale, seguito da `buttonGroup` definizione:

       &quot;
       &quot;toolbar&quot;: {
       &quot;type&quot;: &quot;blockGroup&quot;,
       &quot;extraclass&quot;:
       &quot;operazioni sulla barra degli strumenti&quot;,
       &quot;items&quot;: [
       {
       &quot;type&quot;: &quot;buttonGroup&quot;,
       &quot;extraclass&quot;: &quot;left-controls&quot;,
       &quot;label&quot;: &quot;Left Controls&quot;,
       &quot;items&quot;: [
       &quot;
   
   All&#39;interno del `items` raccolta, è necessario specificare la definizione per una o più icone della barra degli strumenti.

   Per aggiungere un&#39;icona a forma di barra degli strumenti, è necessario definire le seguenti proprietà:

   **tipo**: specifica `button` come `type` valore. Questo valore indica che si sta aggiungendo un pulsante della barra degli strumenti.

   **icona**: specifica il nome dell’icona Coral da utilizzare nella barra degli strumenti.

   **variante**: specifica `quiet` come `variant` valore.

   **titolo**: specifica la descrizione comando per l’icona.

   **on-click**: specifica il nome del comando definito per la funzione nel file JavaScript. Se il comando richiede parametri di input, specificare il nome del comando come:

       &quot;Javascript
       &quot;al clic&quot;: {&quot;name&quot;: &quot;AUTHOR_INSERT_ELEMENT&quot;, &quot;args&quot;: &quot;simpletable&quot;}
       &quot;
   
   **mostrare o nascondere**: se definisci il `show` , quindi specificare le modalità di visualizzazione dell&#39;icona. I valori possibili sono - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(visualizza in tutte le modalità\), oppure `false` \(nascondi in tutte le modalità\).

   In sostituzione di `show`, puoi anche definire `hide` proprietà. I valori possibili sono gli stessi di `show` con l’unica differenza che l’icona non viene visualizzata per la modalità specificata.

   L’esempio seguente mostra il numero di versione delle guide AEM quando l’utente fa clic sull’icona Mostra versione nella barra degli strumenti.

   Aggiungi il seguente codice a un file JavaScript:

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

   Aggiungi la funzione nella sezione *ui\_config.json* file come:

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Creare un *clientlib* e aggiungi il tuo JavaScript a questa cartella.

1. Aggiornare la proprietà Categories del *clientlib* assegnandogli il valore di *apps.fmdita.xml\_editor.page\_overrides*.

1. Salva il *ui\_config.json* e ricaricare l&#39;editor Web.


## Rimuovere una feature dalla barra degli strumenti

Talvolta è possibile non assegnare tutte le funzionalità attualmente disponibili nell&#39;editor Web, in tal caso è possibile rimuovere la funzionalità indesiderata dalla barra degli strumenti dell&#39;editor Web.

Per rimuovere qualsiasi feature indesiderata dalla barra degli strumenti, effettuate le seguenti operazioni:

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul pulsante **Profilo globale** affiancare.
1. Seleziona la **Configurazione editor XML** e fai clic su **Modifica** icona in alto
1. Fai clic su **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.

   Il `ui_config.json` Il file è suddiviso in tre sezioni:

   1. **barre degli strumenti**: questa sezione contiene la definizione di tutte le funzioni disponibili nella barra degli strumenti dell’editor, ad esempio Inserisci/Rimuovi elenco numerato, \(file\) Chiudi, Salva, Commenti e altro ancora.

   1. **scelte rapide**: questa sezione contiene la definizione delle scelte rapide da tastiera assegnate a una particolare funzione nell’editor.

   1. **modelli**: questa sezione contiene la struttura predefinita degli elementi DITA che è possibile utilizzare nel documento. Per impostazione predefinita, la sezione modelli contiene le definizioni dei modelli per gli elementi paragrafo, tabella semplice, tabella e corpo. Puoi creare una definizione di modello per qualsiasi elemento aggiungendo una struttura XML valida per l’elemento desiderato. Ad esempio, se desideri aggiungere una `p` con ogni nuovo elemento `li` in un elenco, puoi aggiungere il seguente codice alla fine della sezione modelli per ottenere questo risultato:

   ```css
   "li": "<li><p></p></li>"
   ```

1. Dalla sezione delle barre degli strumenti, rimuovere la voce della caratteristica che non si desidera esporre agli utenti.

1. Salva il *ui\_config.json* e ricaricare l&#39;editor Web.


**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
