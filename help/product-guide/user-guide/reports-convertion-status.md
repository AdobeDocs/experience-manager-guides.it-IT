---
title: Rapporto sullo stato della conversione
description: Convertire documenti di formati diversi in DITA nelle guide AEM. Scopri come aggiungere filtri e visualizzare un rapporto sullo stato della conversione.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Rapporto sullo stato della conversione {#id205BBA00WZZ}

Le guide AEM forniscono una solida funzione di conversione per convertire documenti di vari formati in DITA. Il Rapporto sullo stato della conversione fornisce una visualizzazione consolidata di tutte le attività di conversione eseguite dalle guide AEM.

Per visualizzare il rapporto Stato conversione, effettuare le seguenti operazioni:

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Fai clic sul pulsante **Rapporto sullo stato della conversione** affiancare.

   Viene visualizzato il Rapporto sullo stato della conversione per tutti i task di conversione eseguiti sul sistema.

   ![](images/conversion-status-report.png){width="800" align="left"}

1. La pagina del rapporto è divisa in due parti:

   - **Filtro:**

     Puoi filtrare i dati del rapporto in base al tipo di file e allo stato della conversione. In Tipo file è possibile scegliere di visualizzare i dati del report per documenti di Word, HTML strutturati, XML e DocBook. Nello stato è possibile scegliere di visualizzare i dati del report per le attività eseguite correttamente, non riuscite, attive o in coda.

     Nella schermata seguente vengono visualizzati i dati del rapporto per le attività di conversione con stato Non riuscito, Attivo e In coda.

     ![](images/conversion-report-failed-active-queued.png){width="800" align="left"}

   - **Dati rapporto:**

     I dati del rapporto contengono le colonne seguenti:

      - **Nome file**: nome del file di origine su cui è stato eseguito il processo di conversione. Se si fa clic sul collegamento Nome file, viene visualizzata la posizione del documento di origine.

      - **Tipo di file**: tipo del documento di origine, che può essere Word, HTML strutturato, XML e DocBook.

      - **Aggiunto da**: nome dell’utente che ha eseguito l’attività di conversione.

      - **Data di aggiunta**: data in cui è stata eseguita l’attività. Facendo clic sul collegamento Data aggiunta, viene scaricato il file di registro.

      - **Percorso**: percorso completo del documento di origine.

      - **Stato**: stato delle attività di conversione - Completate, Non riuscite, Attive o In coda.

      - **Output**: percorso del documento convertito correttamente. Facendo clic sul collegamento Output si raggiunge la posizione in cui viene salvato l&#39;output.


**Argomento padre:**[ Rapporti](reports-intro.md)
