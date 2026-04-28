---
title: Reverted files version history report
description: View reverted files version history reports in AEM Guides. Learn how to access revert version logs from the Assets UI, topic preview, and AEMs tools selection.
feature: Report Generation
role: User
hide: true
exl-id: c787947a-b235-4c12-a9cc-eac5136d31db
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# Reverted files version history report {#id205BBC00PRK}

When you are working on multiple simultaneous releases along with multiple authors, your content is bound to have multiple versions. There could be some common information across multiple releases, which different authors could use in their project. To handle such work assignments, authors could end up with multiple versions of files. Such versions could simply be a newer version of a file or a revert to an earlier version. It is a complex task to identify when a file was reverted and why.

AEM Guides allows you to generate a version history report for an individual file or for all files in a folder. This version history gives you a consolidate view of all versions of a file that were reverted and who created those versions and the reason for creating those versions.

You can access this report from the following places:

- **Assets UI**: by selecting a file and opening the **Version History** from the left rail. The **Version History** view contains the **Revert Version Logs** link at the bottom of the panel. When you click on this link, the selected file&#39;s history of the reverted versions is displayed.

  ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

- **Topic preview**: when you are previewing a topic, there also you can bring up the **Version History** panel from the left rail. You will get a panel similar to the Assets UI from where you can click the **Revert Version Logs** link to access the reverted version history of the active document.

- **AEM&#39;s Tools section**: you can also access this report from AEM&#39;s Tools section. The following procedure explains how you can access the revert version history from the AEM&#39;s Tools section.


Perform the following steps to access the Revert History report:

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Selezionare **Guide** dall&#39;elenco degli strumenti.

1. Click on the **Version Revert History** tile.

   A blank Revert Version History page is displayed wherein you need to browse to and select a file or folder to generate the report.

1. Click **Show Logs** to generate the report for the selected file or folder.

   ![](images/revert-version-history-report.png){width="800" align="left"}

   La relazione contiene i seguenti dettagli:

   - **Nome file**: titolo dell&#39;argomento. Se si fa clic sul collegamento del titolo dell&#39;argomento, viene visualizzata l&#39;anteprima dell&#39;argomento.

   - **Timestamp**: data e ora in cui l&#39;argomento è stato ripristinato a una versione precedente.

   - **Utente**: nome dell&#39;utente che ha ripristinato una versione precedente.

   - **Ripristina da**: il numero di versione originale del file da cui è stato ripristinato.

   - **Ripristina**: versione in cui è stato ripristinato il file.

   - **Commento**: qualsiasi commento fornito dall&#39;utente che ha ripristinato il file.



**Argomento padre:**&#x200B;[&#x200B; Report](reports-intro.md)
