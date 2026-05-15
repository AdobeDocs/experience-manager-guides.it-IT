---
title: Rapporto sullo stato della conversione
description: Converte documenti di formati diversi in DITA in AEM Guides. Scopri come aggiungere filtri e visualizzare un rapporto sullo stato della conversione.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
feature: Report Generation
role: User
TQID: https://experienceleague.adobe.com/-Jgxys5YiwelOf7jQHYQ4Y9ARYzwLCZ8lNStdnT4oLI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: cdab8659-8d50-4417-b6fd-762f347c13ee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 318
ht-degree: 0%

---

# Rapporto sullo stato della conversione {#id205BBA00WZZ}

Adobe Experience Manager Guides fornisce una solida funzione di conversione per convertire documenti di vari formati in DITA. Il rapporto Stato conversione fornisce una visualizzazione consolidata di tutte le attività di conversione eseguite da Experience Manager Guides.

Per visualizzare il rapporto Stato conversione, effettuare le seguenti operazioni:

1. Seleziona il logo Adobe Experience Manager nella parte superiore e scegli **Strumenti**.

1. Selezionare **Guide** dall&#39;elenco degli strumenti.

1. Selezionare il riquadro **Rapporto sullo stato di conversione**.

   Viene visualizzato il Rapporto sullo stato della conversione per tutti i task di conversione eseguiti sul sistema.

   ![](images/conversion-status-report-new.png)

1. La pagina del rapporto è divisa in due parti:

   - **Filtro:**

     Puoi filtrare i dati del rapporto in base al tipo di file e allo stato della conversione. In Tipo file è possibile scegliere di visualizzare i dati del report per documenti di Word, HTML strutturati, XML, DocBook e IDML. Nello stato è possibile scegliere di visualizzare i dati del report per le attività eseguite correttamente, non riuscite, attive o in coda.

     La schermata seguente mostra i dati del rapporto per le attività di conversione con stato Completato.

     ![](images/conversion-report-failed-active-queued-new.png)

   - **Dati report:**

     I dati del rapporto contengono le colonne seguenti:

      - **Nome file**: nome del file di origine in cui è stato eseguito il processo di conversione. Se si seleziona il collegamento Nome file, viene visualizzata la posizione del documento di origine.

      - **Tipo file**: tipo di documento di origine, ad esempio Word, HTML strutturato, XML, IDML e DocBook.

      - **Aggiunto da**: nome dell&#39;utente che ha eseguito l&#39;attività di conversione.

      - **Data aggiunta**: data in cui è stata eseguita l&#39;attività. Selezionando il collegamento Data aggiunta si scarica il file di registro.

      - **Percorso**: percorso completo del documento di origine.

      - **Stato**: stato delle attività di conversione - Completate, Non riuscite, Attive o In coda.

      - **Output**: percorso del documento convertito. Selezionando sul collegamento Output si raggiunge la posizione in cui viene salvato l’output.


**Argomento padre:**&#x200B;[&#x200B; Introduzione ai report](reports-intro.md)
