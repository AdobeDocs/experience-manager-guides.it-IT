---
title: Generazione di output
description: Gestisci il processo di generazione dell’output in AEM Sites, PDF, HTML5, EPUB, personalizzato e JSON tramite plug-in DITA-OT, pubblicazione di PDF nativi e FMPS in AEM Guides.
feature: Publishing
role: User
exl-id: 11bb3604-f45c-4df7-be74-588dbf8594af
TQID: 'https://experienceleague.adobe.com/hfJ-UrLwhOp0IFxw3vRpCgFU8eWkZCConfPlQfwL9V8'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
    internal-label: Native PDF publishing
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 43e3af5a6d753e6124acf1d56e99497f6b9c4cd9
workflow-type: tm+mt
source-wordcount: '1296'
ht-degree: 0%
---
# Gestisci processo di generazione output

Adobe Experience Manager Guides consente di monitorare e gestire le attività di generazione output per le mappe DITA. È possibile visualizzare lo stato delle attività di generazione dell&#39;output, annullare le attività in corso e rimuovere le voci obsolete dalla cronologia di generazione dell&#39;output.

Dopo aver avviato un&#39;operazione di generazione output per una mappa o rigenerato gli argomenti selezionati, Experience Manager Guides invia l&#39;operazione alla coda di generazione output. Lo stato dell&#39;attività viene aggiornato con l&#39;avanzamento del processo di generazione dell&#39;output.

Puoi visualizzare e gestire le attività di generazione output utilizzando la scheda **Cronologia output** nell&#39;editor o la scheda **OUTPUT** nell&#39;interfaccia utente di Assets.


## Visualizza e gestisci le attività di generazione output dall’editor

Puoi visualizzare e gestire le attività di generazione dell&#39;output direttamente dalla scheda **Cronologia output** nella console Mappa.

Apri la mappa DITA nella console Mappa e genera l’output utilizzando uno qualsiasi dei predefiniti di output disponibili in Experience Manager Guides. Passa alla scheda **Cronologia output** per visualizzare lo stato dell&#39;attività di generazione output e altri dettagli, come illustrato di seguito:

![](images/output-history-editor-view.png)

Per ogni attività di generazione dell&#39;output, è possibile visualizzare le informazioni seguenti:

1. **Predefinito:** Nome del predefinito di output utilizzato per generare l&#39;output.
1. **Tipo di predefinito:** Tipo di predefinito di output utilizzato per la generazione dell&#39;output.
1. **Stato:** Stato corrente dell&#39;attività di generazione dell&#39;output, ad esempio In attesa, In esecuzione, Completato, Non riuscito, Post-pubblicazione o Annullato.
1. **Generato il:** Data e ora di generazione dell&#39;output.
1. **Durata:** tempo impiegato per generare l&#39;output.
1. **Generato da:** Nome dell&#39;utente che ha avviato l&#39;attività di generazione output.

>[!NOTE]
>
> Se un&#39;attività di generazione output è attualmente in corso, l&#39;etichetta **Esecuzione** nella colonna **Stato** indica che l&#39;attività è in fase di elaborazione. Utilizza **Aggiorna** per visualizzare lo stato più recente delle attività di generazione output.

È inoltre possibile annullare un&#39;attività di generazione output in corso. Per annullare un&#39;attività in corso, passa il cursore sulla riga attività e seleziona **Annulla generazione**.

![](images/cancel-generation-editor.png)

Una volta annullata l&#39;attività, l&#39;etichetta **Annullato** viene visualizzata nella colonna **Stato**.

Per le attività di generazione output completate, passa il cursore sulla riga dell&#39;attività per accedere alle azioni seguenti, a seconda dello stato dell&#39;attività:

![](images/output-history-editor-actions.png)

- **Apri output:** Visualizza l&#39;output generato in una nuova scheda.
- **Visualizza registri:** Accedi ai registri di generazione dell&#39;output per esaminare i dettagli di pubblicazione e risolvere eventuali errori o avvisi.
- **Elimina cronologia output:** Rimuovere l&#39;attività selezionata dalla cronologia di generazione dell&#39;output senza eliminare l&#39;output generato.

Per lavorare con la cronologia di generazione dell&#39;output, è inoltre possibile utilizzare le seguenti opzioni:

- **Ricerca:** Utilizzare il campo di ricerca per trovare attività di generazione output specifiche nella cronologia.
- **Scarica CSV:** Seleziona **Scarica CSV** per scaricare la cronologia di generazione dell&#39;output in formato CSV.
- **Ridimensiona colonna:** Selezionare il menu a discesa accanto al nome di una colonna e selezionare **Ridimensiona colonna** per regolare la larghezza della colonna.
- **Filtro**: applica filtri in base al tipo di predefinito di output, allo stato dell&#39;attività e all&#39;intervallo di date e ore per limitare la cronologia di generazione dell&#39;output.

  ![](./images/output-history-filters.png)

Inoltre, le icone colorate indicano lo stato di ciascuna attività: verde per le attività riuscite, arancione per le attività completate con messaggi e rosso per le attività non riuscite. Ciò consente di identificare rapidamente le attività che richiedono attenzione.

## Visualizzare e gestire le attività di generazione degli output dall’interfaccia utente di Assets

Utilizzando Assets AI, puoi eseguire le seguenti azioni sull’output generato:

- [Visualizza lo stato dell&#39;attività di generazione output](#view-the-status-of-the-output-generation-task)
- [Annullare un&#39;attività di generazione output](#cancel-an-output-generation-task)
- [Eliminare un’attività di output](#delete-an-output-task)

### Visualizza lo stato dell&#39;attività di generazione output

Dopo aver avviato l&#39;attività di generazione dell&#39;output per una mappa o rigenerato gli argomenti selezionati, Experience Manager Guides invia l&#39;operazione alla coda di generazione dell&#39;output. Questa coda viene aggiornata in tempo reale, mostrando lo stato di ogni operazione di generazione output nella coda.

1. Nell’interfaccia utente di Assets, individua e apri il file di mappa di cui desideri controllare lo stato di generazione dell’output.

1. Selezionare **OUTPUT**.

   ![](images/output-queued.png)

   La pagina Output è divisa in due parti:

   - **Output in coda:**

     Elenca gli output in attesa di generazione o in fase di generazione. Le attività in coda o in corso vengono visualizzate con un&#39;icona blu prima del nome del predefinito. È inoltre possibile trovare l&#39;impostazione di generazione dell&#39;output o il predefinito utilizzato per l&#39;attività in coda, il tipo, l&#39;utente che ha avviato l&#39;attività, il tempo trascorso dalla data di accodamento dell&#39;attività e lo stato corrente.

     Selezionare il collegamento per accedere al **Dashboard di pubblicazione** e visualizzare lo stato di esecuzione corrente. Nel dashboard di pubblicazione è disponibile un elenco di tutte le attività di pubblicazione attive. I **Output in coda** e il collegamento **Dashboard di pubblicazione** vengono visualizzati solo quando sono presenti output in attesa di generazione o in fase di generazione. Non vengono visualizzate al termine delle attività di output.Per ulteriori dettagli su Publish Dashboard, visualizza [Gestisci le attività di pubblicazione utilizzando Publish Dashboard](generate-output-publish-dashboard.md#).

   - **Output generati**

     Elenca le attività di output completate. Anche in questo caso, le informazioni mostrate qui sono simili a quelle della sezione Output in coda, ma con alcune differenze. Sono disponibili nuove informazioni sotto forma di icona dei risultati di output e del tempo di generazione dell&#39;output.

     In questo elenco è possibile che siano presenti attività eseguite correttamente, attività eseguite con un messaggio o attività non riuscite. Le attività completate vengono visualizzate con l&#39;icona verde, quelle con un messaggio con l&#39;icona arancione e quelle non riuscite con l&#39;icona rossa.

     Per tutte le attività, il processo di pubblicazione crea un file di registro \(logs.txt\) a cui è possibile accedere selezionando il collegamento nella colonna **Generated At**. Per le attività con errori o messaggi, è possibile controllare il file di log, illustrato nella sezione [Visualizza e controllare il file di log](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

     >[!NOTE]
     >
     > Quando selezioni il collegamento dell’output PDF generato, ti viene chiesto di scaricare PDF.


### Annullare un&#39;attività di generazione output

Experience Manager Guides offre agli editori un modo semplice per annullare qualsiasi attività di pubblicazione in corso. In qualità di editore, puoi annullare un&#39;attività di pubblicazione in corso dalla console delle mappe DITA o dal [Dashboard di pubblicazione](generate-output-publish-dashboard.md#).

Per annullare un&#39;attività di generazione output dalla console delle mappe DITA, effettuare le seguenti operazioni:

1. Nell’interfaccia utente di Assets, individua e apri il file di mappa di cui desideri annullare un’attività di generazione output in corso.

1. Selezionare **OUTPUT**.

1. Nell&#39;elenco **Output in coda**, posizionare il puntatore del mouse su un&#39;attività che si desidera annullare.

1. Selezionare l&#39;icona **Annulla processo**.

   ![](images/cancel-publish-task-map-console.png)

1. Selezionare **Sì** al prompt dei messaggi **Conferma annullamento**.

   ![](images/confirm-cancel-output-map-console.png)

   Se l&#39;attività non è ancora stata avviata, il comando di annullamento viene eseguito sull&#39;attività. Per un&#39;attività che viene annullata, lo stato è impostato su Annullamento.

   Una volta annullata, l&#39;attività viene spostata nell&#39;elenco **Output generati** con stato **Annullato**. Quando passi il cursore del mouse sull’attività annullata, viene visualizzato il nome dell’utente che ha annullato l’attività. Nella schermata seguente, l&#39;attività *HTML5* è stata annullata.

   ![](images/cancelled-output-task.png)


### Eliminare un’attività di output

Quando si generano più output per una mappa DITA, in un periodo di tempo l&#39;elenco Output generati per tale mappa diventa molto lungo. In qualità di editore, è possibile cancellare la cronologia di output di qualsiasi file mappa rimuovendo le attività obsolete dall&#39;elenco *Output generati*. L&#39;output non viene rimosso dal sistema, ma solo la voce dell&#39;output generato viene rimossa dall&#39;elenco *Output generati*.

Per rimuovere un task di output dall&#39;elenco Output generato, effettuare le operazioni riportate di seguito.

1. Nell’interfaccia utente di Assets, individua e apri il file di mappa da cui desideri eliminare le attività.

1. Selezionare **OUTPUT**.

1. Nell&#39;elenco **Output generati**, posizionare il puntatore del mouse su un&#39;attività che si desidera eliminare.

1. Seleziona l’icona Elimina.

   ![](images/delete-output-task.png)

1. Selezionare **Sì** nella **Conferma eliminazione**.

   L&#39;attività viene eliminata dall&#39;elenco Output generati.

















