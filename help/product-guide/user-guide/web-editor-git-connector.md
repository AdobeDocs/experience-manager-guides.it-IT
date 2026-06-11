---
title: Importare contenuti dagli archivi Git con il connettore Git (Beta) in Experience Manager Guides
description: Scopri come il connettore Git (Beta) in Experience Manager Guides consente di importare contenuti dagli archivi Git, recuperare gli aggiornamenti, preservare i GUID e gestire i conflitti.
feature: Authoring, Features of Web Editor
role: User
TQID: https://experienceleague.adobe.com/DDAXW8cUFjvHUeJIbtL6FaHYSU7NW5fkzTai-7n90ms
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 5f626c210e74c6d11e2441f719cfbfeb33bf55c5
workflow-type: tm+mt
source-wordcount: 941
ht-degree: 0%

---

# Importare contenuti con il connettore Git (Beta)

>[!IMPORTANT]
>
> Il connettore Git è attualmente disponibile come funzione di Beta ed è disabilitato per impostazione predefinita. Per abilitare questa funzione, contatta il team Customer Success.

Il connettore Git consente di importare in Experience Manager Guides contenuti dagli archivi Git connessi. Dopo l’importazione dei contenuti, puoi utilizzare le funzioni di authoring, revisione, traduzione e pubblicazione di Experience Manager Guides per sviluppare e distribuire la documentazione.

Quando il contenuto cambia nell’archivio di origine, puoi recuperare gli aggiornamenti, esaminare i conflitti e sincronizzare le modifiche più recenti con Experience Manager Guides.

## Prerequisiti

Prima di iniziare a utilizzare questa funzione, assicurati che:

- La funzione del connettore Git deve essere abilitata per il tuo ambiente.
- (*Se abilitato*) L&#39;amministratore ha configurato il connettore Git nell&#39;ambiente. Per ulteriori dettagli, visualizzare [Creare e configurare il connettore Git dall&#39;interfaccia utente](../install-conf-guide/conf-git-connector.md).
- Hai accesso in *lettura* all&#39;archivio Git che contiene il contenuto da importare.
- Si conosce il ramo del repository e la cartella di origine che si desidera importare.
- Conosci la cartella di destinazione in Experience Manager Guides in cui verrà memorizzato il contenuto importato.

## Importa contenuto dall’archivio Git connesso

Dopo che l’amministratore ha configurato il connettore Git, puoi utilizzarlo dall’editor per iniziare a importare contenuti da un archivio Git.  Per importare il contenuto da un archivio Git, effettua le seguenti operazioni:

1. Nell’editor, apri il pannello a sinistra.
1. Selezionare **Origini dati**.

   Vengono visualizzate le origini dati collegate.

1. Selezionare il riquadro **Connettore Git**.

1. Seleziona l&#39;icona +, quindi seleziona **Importazione in blocco**.

   Viene visualizzata la finestra di dialogo **Importazione in blocco**.

   ![](images/git-bulk-importer-dialog.png)

1. Nella finestra di dialogo **Importazione in blocco**, specifica un nome per l&#39;importazione, seleziona una sottocartella dall&#39;archivio Git configurato e seleziona **Salva e recupera**.  L’elenco dei file disponibili per l’importazione viene visualizzato nella finestra di dialogo. Rivedi l’elenco e convalida il contenuto prima di continuare.

   ![](images/git-bulk-importer-import-all.png)

1. Dopo aver esaminato i file, selezionare **Importa tutto** per importare il contenuto in Experience Manager Guides.

   >[!NOTE]
   >
   > Puoi abilitare **Sincronizzazione automatica** per sincronizzare e importare automaticamente il contenuto dall&#39;archivio Git in Experience Manager Guides. Se vengono rilevati errori, la sincronizzazione automatica non viene attivata e l&#39;autore deve importare manualmente il contenuto selezionando **Importa tutto**. Una volta abilitata, la sincronizzazione automatica non può essere disabilitata per l’importazione.

Una volta importato, il contenuto viene archiviato nel percorso radice **Target AEM** configurato durante la configurazione del connettore Git.

## Gestire i contenuti importati da Git

Una volta importato il contenuto in Experience Manager Guides, puoi utilizzare le azioni disponibili per gestirlo e mantenerlo sincronizzato con le modifiche nell’archivio sorgente.

![](images/git-connector-imported-content-options.png){width="600"}

- **Anteprima**: contenuto importato in anteprima. Se l&#39;archivio di origine contiene aggiornamenti, esaminare le differenze e utilizzare l&#39;opzione **Recupera di nuovo** per importare le modifiche più recenti.
- **Elimina**: rimuovi il contenuto importato non più necessario.
- **Rinomina**: rinomina il contenuto importato per facilitarne l&#39;identificazione.
- **Visualizza log**: visualizza il log di importazione per esaminare i dettagli dell&#39;operazione di importazione.
- **Visualizza report**: visualizza e scarica il **report di importazione in blocco**, che include dettagli quali:

   - numero totale di file importati
   - numero di importazioni riuscite
   - numero di importazioni non riuscite

  ![](images/git-connector-view-report.png){width="600"}

  Puoi anche scaricare il rapporto dettagliato. Se alcuni file non vengono importati, utilizzare **Riprova importazioni non riuscite** per provare di nuovo a importarli.

## Rivedere e risolvere i conflitti di contenuto

Quando recuperi nuovamente il contenuto da un archivio Git, vengono visualizzate come conflitti le differenze di contenuto tra la versione dell’archivio e il contenuto corrispondente disponibile in Experience Manager Guides. È necessario risolvere e unire tali conflitti prima di importare i dati in Experience Manager Guides.

Per risolvere e unire i conflitti, effettuare le seguenti operazioni:

1. Apri la finestra di dialogo Importazione in blocco e seleziona **Recupera di nuovo**.
1. Se vengono rilevati conflitti, viene visualizzata la scheda **Unisci richiesto** in cui sono elencati i file che contengono conflitti. Selezionare la scheda **Unione richiesta**, quindi selezionare un file dall&#39;elenco per esaminare e risolvere i conflitti.
1. Esamina il contenuto nelle sezioni seguenti:

   ![](images/git-connector-resolve-conflicts.png){width="600"}

   - Nella sezione **AEM** viene visualizzata la versione corrente del contenuto presente in Experience Manager Guides.
   - Nella sezione **Git** viene visualizzata la versione più recente del contenuto del repository.
   - Nella sezione **Unisci** viene visualizzato il contenuto unito.

1. Esamina le differenze evidenziate nell’editor e risolvi i conflitti utilizzando i controlli di unione:

   - Se desideri utilizzare le modifiche più recenti dall&#39;archivio Git, accertati che sia selezionata la casella di controllo per il conflitto nella sezione **Git**, quindi seleziona il controllo `<<<` corrispondente. Il contenuto Git selezionato sostituisce il contenuto in conflitto nella sezione **Unisci**.

     ![](images/git-connector-replace-with-git.png){width="600"}

   - Se si desidera mantenere il contenuto di entrambe le versioni, deselezionare la casella di controllo relativa al conflitto e quindi utilizzare il controllo `<<<` per aggiungere il contenuto richiesto alla sezione **Unisci** senza sostituire il contenuto esistente.

     ![](images/git-connector-keep-both-versions.png){width="600"}

   - Analogamente, è possibile utilizzare il controllo `>>>` nella sezione AEM per mantenere la versione attualmente disponibile in Experience Manager Guides.

     ![](images/git-connector-accept-aem-version.png){width="600"}

1. Dopo aver esaminato il contenuto unito, eseguire una delle operazioni seguenti:

   - Utilizza **Accetta modifiche da Git** quando la versione dell&#39;archivio deve sostituire il contenuto in conflitto.
   - Utilizza **Contrassegna come unito** dopo aver esaminato e aggiornato la versione unita per verificare che contenga il contenuto che desideri mantenere.
   - Utilizza **Reimposta** per ignorare tutti gli aggiornamenti uniti e ripristinare lo stato originale del contenuto.

Dopo aver contrassegnato come uniti tutti i file contenenti i conflitti, il pulsante **Importa tutti** è attivato. Seleziona **Importa tutto** per completare il processo di risoluzione dei conflitti.

Se l&#39;archivio contiene contenuto completamente nuovo, ad esempio un nuovo argomento, paragrafo o riga che non è in conflitto con il contenuto esistente, verrà visualizzato in **Aggiornamenti puliti**. Questi aggiornamenti non richiedono la risoluzione dei conflitti e possono essere importati direttamente.

![](images/git-connector-clean-updates.png){width="600"}


