---
title: Personalizza barra degli strumenti
description: Scopri come personalizzare la barra degli strumenti
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/jSw3gKCCrJYRO6sPgWNnZCT8RzKtMFRYLytHZyX4mGk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1003
ht-degree: 0%

---

# Personalizza barra degli strumenti {#id172FB00L0V6}

Per impostazione predefinita, l&#39;Editor Web viene fornito con le funzioni editoriali più comuni richieste da qualsiasi editor DITA. Nell’editor sono disponibili funzioni quali l’inserimento di elementi di tipo elenco \(numerato o puntato\), riferimenti incrociati, riferimenti a contenuti, tabelle, paragrafi e formattazione di caratteri. Oltre a questi elementi di base, è possibile personalizzare l&#39;Editor Web per inserire elementi utilizzati nell&#39;ambiente di authoring.

>[!NOTE]
>
> Durante la migrazione dalla vecchia interfaccia alla nuova interfaccia utente di AEM Guides (applicabile dalle versioni 2502 e 5.0 di AEM Guides), gli aggiornamenti a `ui_config` devono essere convertiti in configurazioni dell&#39;interfaccia utente più flessibili e modulari. Questo framework consente di adottare le modifiche direttamente nell’editor_toolbar e in altri widget di destinazione, a seconda delle necessità. Per ulteriori dettagli, visualizzare [Panoramica della configurazione dell&#39;interfaccia utente di conversione](https://experienceleague.adobe.com/it/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

Esistono due modi per personalizzare la barra degli strumenti dell’editor web:

- Aggiungere una nuova funzionalità alla barra degli strumenti
- Rimuovi eventuali funzionalità esistenti dalla barra degli strumenti


## Aggiungere una feature nella barra degli strumenti

L&#39;aggiunta di una funzionalità all&#39;editor Web comporta due attività principali: l&#39;aggiunta di un&#39;icona per la funzionalità nel file *ui\_config.json* e l&#39;aggiunta della funzionalità in background in JavaScript.

Per aggiungere una funzionalità alla barra degli strumenti dell&#39;editor Web, effettuare le operazioni riportate di seguito.

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti e fai clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto
1. Fai clic sull&#39;icona **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.
1. Nel file `ui_config.json`, aggiungere la definizione della nuova funzionalità nella sezione delle barre degli strumenti. Salva il file e caricalo.

   In genere, è possibile creare un nuovo gruppo di pulsanti della barra degli strumenti e aggiungervi uno o più pulsanti. In alternativa, è possibile aggiungere un nuovo pulsante della barra degli strumenti all&#39;interno di un gruppo di barre degli strumenti esistente. Per creare un nuovo gruppo di barre degli strumenti sono necessari i seguenti dettagli:

   **tipo**: specificare `blockGroup` come valore `type`. Questo valore indica che si sta creando un gruppo di blocchi contenente uno o più gruppi di barre degli strumenti.

   **extraclass**: nome della classe o delle classi separate da spazio.

   **elementi**: specifica la definizione di tutti i gruppi nella barra degli strumenti. Ogni gruppo può contenere una o più icone della barra degli strumenti. Per definire le icone all&#39;interno di un gruppo di barre degli strumenti, è necessario definire nuovamente l&#39;attributo `type` all&#39;interno di `items` e impostarne il valore su `buttonGroup`. Specificare uno o più nomi di classe nella proprietà `extraclass`. Specificare il nome della funzionalità nella proprietà `label`. Il frammento seguente del file `ui_config.json` mostra la definizione per il blocco della barra degli strumenti principale, seguito dalla definizione `buttonGroup`:

   ```
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

   **tipo**: specificare `button` come valore `type`. Questo valore indica che si sta aggiungendo un pulsante della barra degli strumenti.

   **icon**: specificare il nome dell&#39;icona Coral che si desidera utilizzare nella barra degli strumenti.

   **variante**: specificare `quiet` come valore `variant`.

   **title**: specifica la descrizione comando per l&#39;icona.

   **al clic**: specificare il nome del comando definito per la funzionalità nel file JavaScript. Se il comando richiede parametri di input, specificare il nome del comando come:

   ```Javascript
   "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
   ```

   **mostra o nascondi**: se si sta definendo la proprietà `show`, specificare le modalità di visualizzazione dell&#39;icona. I valori possibili sono - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(visualizza in tutte le modalità\) o `false` \(nascondi in tutte le modalità\).

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


## Rimuovere una feature dalla barra degli strumenti

Talvolta è possibile non assegnare tutte le funzionalità attualmente disponibili nell&#39;editor Web, in tal caso è possibile rimuovere la funzionalità indesiderata dalla barra degli strumenti dell&#39;editor Web.

Per rimuovere qualsiasi feature indesiderata dalla barra degli strumenti, effettuate le seguenti operazioni:

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto
1. Fai clic sull&#39;icona **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.

   Il file `ui_config.json` è suddiviso in tre sezioni:

   1. **barre degli strumenti**: questa sezione contiene la definizione di tutte le funzionalità disponibili nella barra degli strumenti dell&#39;editor, ad esempio Inserisci/Rimuovi elenco numerato, \(file\) Chiudi, Salva, Commenti e altro ancora.

   1. **scelte rapide**: questa sezione contiene la definizione delle scelte rapide da tastiera assegnate a una particolare funzione nell&#39;editor.

   1. **modelli**: questa sezione contiene la struttura predefinita degli elementi DITA che è possibile utilizzare nel documento. Per impostazione predefinita, la sezione modelli contiene le definizioni dei modelli per gli elementi paragrafo, tabella semplice, tabella e corpo. Puoi creare una definizione di modello per qualsiasi elemento aggiungendo una struttura XML valida per l’elemento desiderato. Ad esempio, se si desidera aggiungere un elemento `p` con ogni nuovo elemento `li` in un elenco, è possibile aggiungere il codice seguente alla fine della sezione dei modelli per ottenere questo risultato:

   ```css
   "li": "<li><p></p></li>"
   ```

1. Dalla sezione delle barre degli strumenti, rimuovere la voce della caratteristica che non si desidera esporre agli utenti.

1. Salva il file *ui\_config.json* e ricarica l&#39;editor Web.


**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
