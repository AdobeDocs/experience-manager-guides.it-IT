---
title: Creare predefiniti di output dall’editor web
description: Crea predefiniti di output dall’editor web. Scopri come modificare, rinominare, duplicare ed eliminare un predefinito di output in AEM Guides.
exl-id: cd38b039-ef91-45c9-a226-433e57b09873
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: https://experienceleague.adobe.com/e5BEPmlmFDY2ipC8nNQPjrgGx3cV6AaD4PmZYw4hAYI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 368
ht-degree: 0%

---

# Creare predefiniti di output per la Knowledge Base dall&#39;editor {#id218CL400JW3}

Per creare predefiniti di output per la mappa DITA, effettuate le seguenti operazioni:

1. Nell’interfaccia utente di Assets, individua il file di mappa da modificare.

1. Per ottenere un blocco esclusivo sul file mappa, selezionare il file mappa e selezionare **Estrai**.

1. Selezionare l&#39;opzione **Modifica argomenti** dal menu Azioni del file di mapping.

   Il file di mappa viene aperto per la modifica nell&#39;editor.

   >[!NOTE]
   >
   > Potete aggiungere o eliminare qualsiasi argomento dalla mappa utilizzando l&#39;Editor mappe avanzato. Per ulteriori dettagli, visualizzare [Utilizzare l&#39;Editor mappe avanzato](map-editor-advanced-map-editor.md#).

1. Seleziona l&#39;icona **Apri nella console delle mappe**. La mappa si apre nella console delle mappe.

1. Passare alla scheda **Predefiniti di output** e selezionare l&#39;icona + per creare un predefinito di output per la mappa DITA.

1. Selezionare **Knowledge Base** dal menu a discesa **Tipo**, immettere il nome e selezionare **Adobe Experience Manager** nella finestra di dialogo **Nuovo predefinito di output**.
1. Selezionare l&#39;opzione **Aggiungi al profilo cartella corrente** per creare un predefinito di output per il profilo cartella corrente. L&#39;icona ![icona profilo cartella](images/global-preset-icon.svg) indica un predefinito a livello di profilo della cartella.

   Ulteriori informazioni su [Gestire i predefiniti di output globali e del profilo cartella](./web-editor-manage-output-presets.md).

1. Seleziona **Aggiungi**.

   Viene creato il predefinito per la Knowledge Base.


   ![Nuovo ](images/knowledge-base-preset-dialog-box.png)

Una volta creato il predefinito, è possibile generare l&#39;output per articoli specifici della knowledge base. A tale scopo, passare alla scheda **Articoli** e selezionare gli argomenti per i quali si desidera generare l&#39;output.
1. Seleziona **Genera output** nella parte superiore per generare l&#39;output.

   ![](images/add-preset-articles-tab_cs.png)

1. Nel prompt **Conferma file per la pubblicazione**, selezionare i file da pubblicare e confermare selezionando **Pubblica**.

   ![Nuovo ](images/knowledge-base-confirm-files-for-publishing.png)

Viene visualizzato lo stato del processo di generazione dell&#39;output. Nella colonna **Argomenti** sono elencati gli argomenti per i quali viene generato l&#39;output mentre nella colonna **Stato** è visualizzato lo stato di pubblicazione di ciascun argomento.


![](images/add-preset-output-generated_cs.png)

Per visualizzare l&#39;output, chiudere la finestra di dialogo Output generato e selezionare **Visualizza output** nella pagina predefinita.


>[!NOTE]
>
> È inoltre possibile rinominare, duplicare o eliminare un predefinito di output esistente dal menu Opzioni.



**Argomento padre:**[ Pubblicazione basata su articolo dall&#39;editor](web-editor-article-publishing.md)
