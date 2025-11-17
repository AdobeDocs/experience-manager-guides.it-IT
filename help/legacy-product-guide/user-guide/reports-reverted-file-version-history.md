---
title: Rapporto cronologia versioni file ripristinati
description: Visualizzare i rapporti sulla cronologia delle versioni dei file ripristinati in AEM Guides. Scopri come accedere ai registri di ripristino della versione dall’interfaccia utente di Assets, dall’anteprima dell’argomento e dalla selezione degli strumenti AEM.
feature: Report Generation
role: User
hide: true
exl-id: c787947a-b235-4c12-a9cc-eac5136d31db
source-git-commit: 6261e1aa1966a81830fe8e5cf14337c8be4f81cb
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Rapporto cronologia versioni file ripristinati {#id205BBC00PRK}

Quando lavori su più versioni simultanee insieme a più autori, il contenuto è associato a più versioni. Potrebbero essere presenti alcune informazioni comuni a più versioni, che diversi autori potrebbero utilizzare nel loro progetto. Per gestire tali assegnazioni di lavoro, gli autori potrebbero finire con più versioni di file. Tali versioni potrebbero essere semplicemente una versione più recente di un file o un ripristino di una versione precedente. È un’attività complessa identificare quando un file è stato ripristinato e perché.

AEM Guides consente di generare un rapporto sulla cronologia delle versioni per un singolo file o per tutti i file presenti in una cartella. Questa cronologia delle versioni offre una visualizzazione consolidata di tutte le versioni di un file che sono state ripristinate, di chi ha creato tali versioni e del motivo per cui le ha create.

Puoi accedere a questo rapporto dalle seguenti posizioni:

- **Interfaccia utente di Assets**: selezionando un file e aprendo **Cronologia versioni** dalla barra a sinistra. La visualizzazione **Cronologia versioni** contiene il collegamento **Ripristina registri versioni** nella parte inferiore del pannello. Quando fai clic su questo collegamento, viene visualizzata la cronologia delle versioni ripristinate del file selezionato.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Anteprima argomento**: quando visualizzi l&#39;anteprima di un argomento, puoi visualizzare anche il pannello **Cronologia versione** dalla barra a sinistra. Otterrai un pannello simile all&#39;interfaccia utente di Assets da cui puoi fare clic sul collegamento **Ripristina registri versione** per accedere alla cronologia delle versioni ripristinate del documento attivo.

- **Sezione Strumenti di AEM**: puoi accedere a questo rapporto anche dalla sezione Strumenti di AEM. La procedura seguente spiega come accedere alla cronologia delle versioni ripristinate dalla sezione Strumenti di AEM.


Per accedere al rapporto Cronologia ripristino, effettuare le operazioni riportate di seguito.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Selezionare **Guide** dall&#39;elenco degli strumenti.

1. Fare clic sul riquadro **Cronologia ripristino versione**.

   Viene visualizzata una pagina vuota Ripristina cronologia versioni in cui è necessario cercare e selezionare un file o una cartella per generare il report.

1. Fare clic su **Mostra registri** per generare il report per il file o la cartella selezionata.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   La relazione contiene i seguenti dettagli:

   - **Nome file**: titolo dell&#39;argomento. Se si fa clic sul collegamento del titolo dell&#39;argomento, viene visualizzata l&#39;anteprima dell&#39;argomento.

   - **Timestamp**: data e ora in cui l&#39;argomento è stato ripristinato a una versione precedente.

   - **Utente**: nome dell&#39;utente che ha ripristinato una versione precedente.

   - **Ripristina da**: il numero di versione originale del file da cui è stato ripristinato.

   - **Ripristina**: versione in cui è stato ripristinato il file.

   - **Commento**: qualsiasi commento fornito dall&#39;utente che ha ripristinato il file.



**Argomento padre:**&#x200B;[&#x200B; Report](reports-intro.md)
