---
title: Rapporto cronologia versioni file ripristinati
description: Visualizzare i rapporti sulla cronologia delle versioni dei file ripristinati in AEM Guides. Scopri come accedere ai registri di ripristino della versione dall’interfaccia utente di Assets, dall’anteprima dell’argomento e dalla selezione degli strumenti AEM.
exl-id: 74bef625-acd6-49a6-b983-881a782f68d6
feature: Report Generation
role: User
TQID: https://experienceleague.adobe.com/XgYartZNktcTWmpCR1MgxakbuVXm3AK0iJlLv7-8lxs
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: cdab8659-8d50-4417-b6fd-762f347c13eeid: fd456af4-cb12-4a34-8cc4-b74adf885626
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 471
ht-degree: 0%

---

# Rapporto cronologia versioni file ripristinati {#id205BBC00PRK}

Quando lavori su più versioni simultanee insieme a più autori, il contenuto è associato a più versioni. Potrebbero essere presenti alcune informazioni comuni a più versioni, che diversi autori potrebbero utilizzare nel loro progetto. Per gestire tali assegnazioni di lavoro, gli autori potrebbero finire con più versioni di file. Tali versioni potrebbero essere semplicemente una versione più recente di un file o un ripristino di una versione precedente. È un’attività complessa identificare quando un file è stato ripristinato e perché.

Adobe Experience Manager Guides consente di generare un rapporto sulla cronologia delle versioni per un singolo file o per tutti i file presenti in una cartella. Questa cronologia delle versioni offre una visualizzazione consolidata di tutte le versioni di un file che sono state ripristinate, di chi ha creato tali versioni e del motivo per cui le ha create.

Puoi accedere a questo rapporto dalle seguenti posizioni:

- **Interfaccia utente di Assets**: selezionando un file e aprendo **Cronologia versioni** dalla barra a sinistra. La visualizzazione **Cronologia versioni** contiene il collegamento **Ripristina registri versioni** nella parte inferiore del pannello. Quando selezioni questo collegamento, viene visualizzata la cronologia delle versioni ripristinate del file selezionato.

  ![](images/revert-log-from-assets-ui.png){width="300"}

- **Anteprima argomento**: quando visualizzi l&#39;anteprima di un argomento, puoi visualizzare anche il pannello **Cronologia versione** dalla barra a sinistra. Otterrai un pannello simile all&#39;interfaccia utente di Assets da cui puoi selezionare il collegamento **Ripristina registri versione** per accedere alla cronologia delle versioni ripristinate del documento attivo.

- **Sezione Strumenti di Adobe Experience Manager**: puoi accedere a questo rapporto anche dalla sezione Strumenti di Experience Manager. La procedura seguente spiega come accedere alla cronologia del ripristino della versione dalla sezione Strumenti di Experience Manager.


Per accedere al rapporto Cronologia ripristino, effettuare le operazioni riportate di seguito.

1. Seleziona il logo Adobe Experience Manager nella parte superiore e scegli **Strumenti**.

1. Selezionare **Guide** dall&#39;elenco degli strumenti.

1. Selezionare il riquadro **Cronologia ripristino versione**.

   Viene visualizzata una pagina vuota Ripristina cronologia versioni in cui è necessario cercare e selezionare un file o una cartella per generare il report.

1. Selezionare **Mostra registri** per generare il report per il file o la cartella selezionata.

   ![](images/revert-version-history-report.png)

   La relazione contiene i seguenti dettagli:

   - **Nome file**: titolo dell&#39;argomento. Selezionando il collegamento del titolo dell&#39;argomento si apre l&#39;anteprima dell&#39;argomento.

   - **Timestamp**: data e ora in cui l&#39;argomento è stato ripristinato a una versione precedente.

   - **Utente**: nome dell&#39;utente che ha ripristinato una versione precedente.

   - **Ripristina da**: il numero di versione originale del file da cui è stato ripristinato.

   - **Ripristina**: versione in cui è stato ripristinato il file.

   - **Commento**: qualsiasi commento fornito dall&#39;utente che ha ripristinato il file.


**Argomento padre:**[ Introduzione ai report](reports-intro.md)
