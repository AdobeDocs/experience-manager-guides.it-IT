---
title: Generazione output incrementale
description: Scopri come funziona in AEM Guides la generazione di output incrementale per AEM Sites.
exl-id: 019d9fbf-2f23-4669-8022-d693be75c1c3
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---


# Generazione output incrementale

>[!NOTE]
>
> La generazione dell’output incrementale è applicabile solo all’output di AEM Sites. Inoltre, è possibile rigenerare solo gli argomenti DITA \(.dita/.xml\) da una mappa DITA o da mappe secondarie. Se si seleziona una mappa DITA, una mappa secondaria, un gruppo di argomenti o un argomento con `@processing-role="resource-only"`, l&#39;opzione di rigenerazione non è disponibile.

In alcuni casi è possibile aggiornare solo alcuni argomenti della mappa DITA e inviare in diretta solo gli argomenti aggiornati. Per gestire tali scenari, Experience Manager Guides consente di creare output incrementali. Se sono stati aggiornati alcuni argomenti, non è necessario rigenerare l&#39;intera mappa DITA. È possibile selezionare solo gli argomenti aggiornati e rigenerarli.

Se la mappa è bloccata e hai aggiornato un singolo argomento nella mappa, devi rigenerare l’intera mappa affinché l’argomento o il contenuto aggiornato si rifletta nell’output. L’opzione di rigenerazione dell’output non viene visualizzata a livello di argomento, ma è disponibile solo a livello di mappa \(chunked\). Questo è applicabile alla mappa principale e a tutte le mappe secondarie.

Per rigenerare l&#39;output per un argomento specifico o un gruppo di argomenti, effettuare le operazioni riportate di seguito.

>[!IMPORTANT]
>
> Durante la rigenerazione dell&#39;output di AEM Sites, l&#39;output viene creato utilizzando la versione corrente dei file e non la baseline allegata.

## Genera output incrementale dalla console Mappa

Per generare un output incrementale per AEM Sites utilizzando la console Mappa, effettua le seguenti operazioni:

1. [Aprire il file mappa DITA nella console Mappa](./open-files-map-console.md).
1. Seleziona il predefinito di AEM Sites per il quale desideri generare l’output incrementale.
1. Nella scheda **Argomenti** selezionare gli argomenti che si desidera pubblicare.

   ![elenco argomenti siti aem](images/aem-presets-topic-list.png) {align="left"}

   >[!NOTE]
   >
   > Quando si seleziona una baseline nella scheda **Contenuto**, nell&#39;elenco Argomento vengono visualizzati gli argomenti e le relative versioni dalla baseline allegata.<br><br>
   > La pubblicazione incrementale dall&#39;elenco Argomenti deve essere utilizzata solo quando non vi è alcuna modifica alla struttura della mappa. Se si verifica una modifica nella struttura della mappa o nel sommario, l’intera mappa deve essere pubblicata una volta per aggiornare il sommario.
1. Seleziona **Salva** per salvare le modifiche.
1. Selezionare **Genera output** per generare l&#39;output.


## Genera output incrementale dal dashboard Mappa

Per generare l’output incrementale per AEM Sites utilizzando il dashboard Mappa, effettua le seguenti operazioni:

1. Nell&#39;interfaccia utente di Assets, passare al file di mapping DITA e selezionarlo.

   Viene visualizzata la console Mappa DITA con l&#39;elenco dei predefiniti di output disponibili per generare l&#39;output.

1. Selezionare la scheda **Argomenti**.

   Viene visualizzato un elenco di argomenti disponibili nella mappa DITA.

1. Selezionate gli argomenti da rigenerare.

   >[!NOTE]
   >
   > Se sono stati aggiunti nuovi argomenti alla mappa DITA, non sarà possibile generarli da qui. È innanzitutto necessario pubblicare gli argomenti appena aggiunti utilizzando la funzione di pubblicazione mappa DITA.

   ![](images/regenerate-topics.png){align="left"}

1. Selezionare **Rigenera**.

   Viene visualizzata la pagina **Rigenera argomenti selezionati**.

1. Selezionate il predefinito di output da utilizzare per rigenerare gli argomenti selezionati.

1. Selezionare **Rigenera** per avviare il processo di generazione dell&#39;output.


>[!IMPORTANT]
>
> Se si rinomina un titolo di argomento e si rigenera l&#39;argomento, il titolo dell&#39;argomento aggiornato non viene riportato nel sommario della mappa DITA. Per aggiornare il titolo dell&#39;argomento nel sommario, è necessario generare l&#39;intera mappa DITA.

Puoi visualizzare lo stato corrente della richiesta di generazione output nella scheda **Output**. Per ulteriori informazioni, visualizzare [Visualizzare lo stato dell&#39;attività di generazione output](#view-the-status-of-the-output-generation-task).



**Argomento padre:** [Informazioni sui predefiniti di output](generate-output-understand-presets.md)
