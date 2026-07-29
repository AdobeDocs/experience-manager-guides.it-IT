---
title: Completa l'attività di revisione come revisore
description: Scopri come contrassegnare un’attività come completata come revisore in AEM Guides.
feature: Reviewing
role: User
exl-id: 99b64fb5-c509-41cf-b091-ba78b90db481
TQID: https://experienceleague.adobe.com/Ttty7SNmwHvrs-Ma5SN0JqjQRR3Y6yM-W-ozgQ3Vcyg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: eb30be6342a50ba52e8afd8b4a31148b3ad9c340
workflow-type: tm+mt
source-wordcount: 854
ht-degree: 0%

---

# Completa l&#39;attività di revisione come revisore

In qualità di revisore, puoi contrassegnare un’attività di revisione come completata dopo aver rivisto tutto il contenuto e aver richiesto una notifica all’autore. In questa fase è inoltre possibile lasciare eventuali commenti finali.

Per completare un&#39;attività di revisione, effettuare le seguenti operazioni:

1. Aprire l&#39;attività di revisione assegnata all&#39;utente.
2. Seleziona **Contrassegna come completato** dall&#39;alto come mostrato di seguito:

   ![](images/review-task-mark-as-done.png){width="350"}

   Viene visualizzata la finestra di dialogo **Attività completata**.
3. Nella finestra di dialogo **Completa attività**, aggiungi i commenti finali per l&#39;autore e seleziona **Completa**.

   >[!NOTE]
   >
   > I commenti a livello di attività fungono da riepilogo o commenti finali e sono distinti dai commenti a livello di testo aggiunti durante la revisione dell&#39;argomento. In questa finestra di dialogo è possibile delineare azioni di follow-up, ad esempio richiedere all’autore di rispondere a commenti specifici e inviare nuovamente l’attività per la revisione, oppure indicare che la revisione è completa.

   Ad esempio, in qualità di Revisore, puoi aggiungere un commento come azione di follow-up per l’Autore:

   ![](images/complete-task-dialog-followup.png){width="350"}

   Oppure, aggiungi un commento per indicare il completamento dell’attività come mostrato di seguito:

   ![](images/complete-task-dialog.png){width="350"}


L&#39;attività è stata contrassegnata come completata e il relativo stato è ora impostato su **Completata**. Non sono consentite ulteriori azioni dopo che l’attività è contrassegnata come completata. Viene inviata una notifica all’Autore o all’iniziatore dell’attività di revisione per attirare la loro attenzione immediata. Per ulteriori dettagli su come attivare le notifiche di revisione, visualizzare [Informazioni sulle notifiche di revisione](./review-understanding-review-notifications.md).

![](images/task-completed-status.png){width="350"}

In base al feedback, se l&#39;autore o l&#39;iniziatore dell&#39;attività decide di [chiudere l&#39;attività di revisione](./review-close-review-task.md), lo stato dell&#39;attività nell&#39;interfaccia utente di revisione viene modificato in **Chiuso**.

![](images/review-status-closed-review-ui.png){width="350"}

>[!NOTE]
>
> La sincronizzazione delle attività tra l’interfaccia utente di revisione e la casella in entrata di AEM è disponibile ed è abilitata per impostazione predefinita. Quando un revisore contrassegna un&#39;attività di revisione come **Completa** nell&#39;interfaccia utente Revisione, l&#39;attività corrispondente viene automaticamente completata e rimossa dalla casella in entrata di AEM del revisore. Analogamente, il completamento di un’attività dalla casella in entrata di AEM la contrassegna automaticamente come completata nell’interfaccia utente di revisione.
>
> L’autore o l’iniziatore dell’attività può comunque rivedere il feedback e riassegnare l’attività se è necessaria un’ulteriore revisione. Quando un’attività viene riassegnata, viene generata una nuova notifica Casella in entrata AEM per il revisore, che consente di rivedere nuovamente l’attività.
>
> Se si desidera utilizzare il comportamento precedente, in cui le attività di revisione completate rimangono nella casella in entrata di AEM del revisore fino a quando l&#39;autore o l&#39;iniziatore dell&#39;attività non esamina il feedback e chiude l&#39;attività di revisione, contattare il team Customer Success per disabilitare la sincronizzazione delle attività.



## Visualizza commenti a livello di attività

Tutti i commenti a livello di attività vengono visualizzati nella finestra di dialogo **Commenti attività**, disponibile in modalità di sola lettura. Quando completate un&#39;attività di revisione con un commento finale, il vostro input viene registrato in questa finestra di dialogo per riferimento futuro.

Per accedere ai commenti a livello di attività dall&#39;interfaccia utente Revisione, passa al pannello a sinistra e seleziona l&#39;icona **Commenti attività**.

![](images/task-comments-icon.png){width="350"}

La finestra di dialogo **Commenti attività** è visualizzata a destra.

![](images/task-comments-reviewer.png){width="350"}

I commenti all&#39;interno della finestra di dialogo vengono visualizzati in ordine cronologico, con i commenti recenti visualizzati per primi e i commenti meno recenti visualizzati per ultimi. Questo ordine ti aiuta a seguire la conversazione come progrediva nel tempo.

La finestra di dialogo **Commenti attività** è accessibile a tutti gli utenti coinvolti nell&#39;attività di revisione, inclusi l&#39;autore o l&#39;iniziatore dell&#39;attività di revisione e altri revisori. Di conseguenza, i commenti di altri revisori (se coinvolti) potrebbero essere visualizzati anche nella finestra di dialogo Commenti attività. Ciò consente di garantire una comunicazione chiara e tracciabile durante l’intero processo di revisione.

Dopo aver esaminato il feedback a livello di attività, l’Autore può richiedere un riesame o chiudere l’attività di revisione. In entrambi i casi, tutti i commenti acquisiti durante il processo di revisione rimangono disponibili come riferimento nella finestra di dialogo **Commenti attività**.

## Delegare un&#39;attività di revisione a un altro revisore

>[!IMPORTANT]
>
> Questa funzione è attivata per impostazione predefinita. Se preferisci non utilizzare questa funzione nel tuo ambiente, contatta il team Customer Success.

In qualità di Revisore, a volte può essere utile che un altro utente esprima il proprio giudizio su una revisione prima che torni all’Autore. Ad esempio, se parte del contenuto non rientra tra le tue competenze o desideri un secondo parere prima di contrassegnare l&#39;attività come **Completa**. Anziché eseguire il routing tramite un amministratore di progetto, è possibile consigliare un revisore direttamente dall&#39;attività di revisione utilizzando l&#39;opzione **Delega**.

La selezione di **Delegato** non completa l&#39;attività di revisione per tuo conto. Invia il consiglio all&#39;autore (iniziatore dell&#39;attività), che decide se aggiungere il revisore consigliato all&#39;attività.

Per delegare un&#39;attività di revisione, effettuare le operazioni riportate di seguito.

1. Aprire l&#39;attività di revisione assegnata all&#39;utente.
2. Dopo aver rivisto il contenuto, seleziona **Delega**, accanto a **Contrassegna come completato**.

   ![](./images/review-delegate-option.png){width="350"}

3. Viene visualizzata la finestra di dialogo **Consiglia revisore**. Seleziona un utente dall’elenco a discesa da consigliare come revisore per questa attività.

   ![](./images/recommend-reviewer-dialog.png){width="350"}

4. *(Facoltativo)* Aggiungi un commento per l&#39;Autore, per il contesto.
5. Seleziona **Delega**.

All&#39;autore viene inviata una notifica che indica che è stato richiesto di aggiungere un revisore all&#39;attività. Per informazioni dettagliate sulla risposta dell&#39;autore a questa richiesta, visualizzare [Richiedere un riesame o chiudere un&#39;attività di revisione come autore](./review-close-review-task.md).

