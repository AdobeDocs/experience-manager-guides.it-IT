---
title: Rapporto cronologia versioni file ripristinati
description: Visualizzare i rapporti sulla cronologia delle versioni dei file ripristinati nelle guide AEM. Scopri come accedere ai registri di ripristino della versione dall’interfaccia utente di Assets, dall’anteprima dell’argomento e dalla selezione degli strumenti AEM.
exl-id: 74bef625-acd6-49a6-b983-881a782f68d6
feature: Report Generation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Rapporto cronologia versioni file ripristinati {#id205BBC00PRK}

Quando lavori su più versioni simultanee insieme a più autori, il contenuto è associato a più versioni. Potrebbero essere presenti alcune informazioni comuni a più versioni, che diversi autori potrebbero utilizzare nel loro progetto. Per gestire tali assegnazioni di lavoro, gli autori potrebbero finire con più versioni di file. Tali versioni potrebbero essere semplicemente una versione più recente di un file o un ripristino di una versione precedente. È un’attività complessa identificare quando un file è stato ripristinato e perché.

Le guide AEM consentono di generare un rapporto sulla cronologia delle versioni per un singolo file o per tutti i file di una cartella. Questa cronologia delle versioni offre una visualizzazione consolidata di tutte le versioni di un file che sono state ripristinate, di chi ha creato tali versioni e del motivo per cui le ha create.

Puoi accedere a questo rapporto dalle seguenti posizioni:

- **Interfaccia utente Assets**: selezionando un file e aprendo la **Cronologia versioni** dalla barra a sinistra. Il **Cronologia versioni** la visualizzazione contiene **Ripristina registri di versione** nella parte inferiore del pannello. Quando fai clic su questo collegamento, viene visualizzata la cronologia delle versioni ripristinate del file selezionato.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Anteprima argomento**: quando visualizzi l’anteprima di un argomento, puoi visualizzare anche **Cronologia versioni** dalla barra a sinistra. Otterrai un pannello simile all’interfaccia utente Assets da cui puoi fare clic sul pulsante **Ripristina registri di versione** collegamento per accedere alla cronologia delle versioni ripristinate del documento attivo.

- **Sezione Strumenti AEM**: puoi accedere a questo rapporto anche dalla sezione Strumenti AEM. La procedura seguente spiega come accedere alla cronologia delle versioni ripristinate dalla sezione Strumenti AEM.


Per accedere al rapporto Cronologia ripristino, effettuare le operazioni riportate di seguito.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Fai clic sul pulsante **Cronologia ripristino versione** affiancare.

   Viene visualizzata una pagina vuota Ripristina cronologia versioni in cui è necessario cercare e selezionare un file o una cartella per generare il report.

1. Clic **Mostra registri** per generare il report per il file o la cartella selezionata.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   La relazione contiene i seguenti dettagli:

   - **Nome file**: titolo dell’argomento. Se si fa clic sul collegamento del titolo dell&#39;argomento, viene visualizzata l&#39;anteprima dell&#39;argomento.

   - **Timestamp**: data e ora in cui l’argomento è stato ripristinato a una versione precedente.

   - **Utente**: nome dell’utente che ha ripristinato una versione precedente.

   - **Ripristina da**: numero di versione originale del file da cui è stato ripristinato.

   - **Ripristina**: versione a cui è stato ripristinato il file.

   - **Commento**: qualsiasi commento dato dall’utente che ha ripristinato il file.


**Argomento padre:**[ Rapporti](reports-intro.md)
