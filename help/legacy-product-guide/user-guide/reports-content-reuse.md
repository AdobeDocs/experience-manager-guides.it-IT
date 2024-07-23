---
title: Rapporto sul riutilizzo dei contenuti
description: Scopri come visualizzare il rapporto sul riutilizzo dei contenuti in AEM Guides. Genera il report per trovare la percentuale di riutilizzo del contenuto.
feature: Report Generation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Rapporto sul riutilizzo dei contenuti {#id205BB900OQD}

Un altro rapporto utile che puoi generare è il Rapporto sul riutilizzo dei contenuti. Questo rapporto calcola la percentuale media di utilizzo del contenuto, che è molto utile per i project manager e i responsabili aziendali per visualizzare la quantità di contenuto riutilizzato.

>[!TIP]
>
> Per garantire il corretto funzionamento del rapporto sul riutilizzo dei contenuti, devi abilitare il flusso di lavoro di post-elaborazione. Contatta l’amministratore di sistema per abilitare i flussi di lavoro di post-elaborazione.

Per visualizzare il rapporto sul riutilizzo del contenuto, effettua le seguenti operazioni:

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Fare clic sulla sezione **Report sul riutilizzo contenuto**.

1. Fai clic su **Sfoglia** per scegliere un percorso in cui si trovano gli argomenti o immetti manualmente il percorso.

   Il rapporto viene generato analizzando il contenuto della cartella principale e di tutte le cartelle secondarie.

1. Fare clic su **Genera report** per ottenere il report sul riutilizzo dei contenuti.

   ![](images/content-reuse-uuid.png){width="800" align="left"}

   La pagina del rapporto è divisa in due parti:

   - **Riepilogo report:**

     Elenca il riutilizzo medio del contenuto, calcolato come Istanze di riutilizzo del contenuto/Conteggio totale argomenti. Questo rapporto prende in considerazione tutti i riferimenti diretti ai contenuti di primo livello e i riferimenti agli argomenti per il calcolo. Il valore Istanze di riutilizzo del contenuto viene calcolato come la somma totale dei valori nel campo Numero di volte riutilizzate. L’argomento più ampiamente riutilizzato è elencato anche nel Riepilogo del rapporto. Se si fa clic sul collegamento dell&#39;argomento nell&#39;argomento più riutilizzato, viene aperta l&#39;anteprima dell&#39;argomento.

   - **Dettagli:**

     La sezione Dettagli contiene le colonne seguenti:

      - **Titolo**: titolo dell&#39;argomento. Se si fa clic sul collegamento del titolo dell&#39;argomento, viene visualizzata l&#39;anteprima dell&#39;argomento.

      - **UUID**: identificatore univoco universale \(UUID\) del file.

      - **Dimensione**: dimensione file in byte.

      - **Stato**: lo stato corrente del documento: Bozza, In revisione o Esaminato.

      - **Numero di riutilizzi**: numero di riutilizzi dell&#39;argomento corrispondente. Calcolato come somma totale delle voci nelle colonne Con riferimento da meno 1.

      - **Con riferimento da**: gli argomenti in cui è stato fatto riferimento all&#39;argomento corrispondente. In questo caso, vengono considerati solo i riferimenti diretti \(primo livello\). Più argomenti sono separati da virgole. L&#39;UUID del file a cui si fa riferimento è indicato anche tra parentesi.Facendo clic sul collegamento del titolo dell&#39;argomento si apre l&#39;anteprima dell&#39;argomento.


>[!NOTE]
>
> Puoi anche esportare il rapporto sul riutilizzo dei contenuti in formato CSV. A tale scopo, fai clic sul collegamento Esporta in CSV nell’angolo in alto a sinistra dello schermo e scegli una posizione in cui salvare il file CSV. Puoi quindi aprire il file CSV in qualsiasi editor CSV.

**Argomento padre:**[ Report](reports-intro.md)
