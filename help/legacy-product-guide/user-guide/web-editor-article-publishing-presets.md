---
title: Creare predefiniti di output dall’editor web
description: Crea predefiniti di output dall’editor web. Scopri come modificare, rinominare, duplicare ed eliminare un predefinito di output in AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: ce8e3614-907b-4172-a8f0-e81e4dc096df
TQID: https://experienceleague.adobe.com/nCmtXuQXfOVVHbmGrRT6rVzEa6NlR-o9TGmwhqczWPs
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 0%

---

# Creare predefiniti di output dall’editor web {#id218CL400JW3}

Per creare predefiniti di output per la mappa DITA, effettuate le seguenti operazioni:

1. Nell’interfaccia utente di Assets, individua il file di mappa da modificare.

1. Per ottenere un blocco esclusivo sul file mappa, selezionare il file mappa e fare clic su **Estrai**.

1. Selezionare l&#39;opzione **Modifica argomenti** dal menu Azioni del file di mapping.

   Il file mappa viene aperto per la modifica nell&#39;editor Web.

   >[!NOTE]
   >
   > Potete aggiungere o eliminare qualsiasi argomento dalla mappa utilizzando l&#39;Editor mappe avanzato. Per ulteriori dettagli, vedere [Utilizzare l&#39;Editor mappe avanzato](map-editor-advanced-map-editor.md#).

1. Nella scheda **Output**, selezionare l&#39;icona + per creare un predefinito di output per la mappa DITA.

   ![](images/output-tab-preset_cs.png){width="350"}

1. Immettere il nome del predefinito nella finestra di dialogo Aggiungi predefinito, quindi fare clic su **Aggiungi**.

1. Immetti i seguenti dettagli di configurazione.

   1. Selezionare le opzioni richieste nella scheda **Generale**. Potete scegliere di creare un predefinito di output con o senza condizioni. È inoltre possibile utilizzare un file DITVAL. AEM Guides consente inoltre di selezionare una baseline per la pubblicazione di una versione specifica della mappa DITA.
   1. Immetti i dettagli del sito AEM nella scheda **AEM**. **Sito** visualizza l&#39;elenco di AEM Sites disponibili nell&#39;archivio AEM. **Categoria**, **Modello sezione** e **Modello articolo** sono i componenti strutturali utilizzati per organizzare l&#39;aspetto dell&#39;output. Sono predefiniti nel modello Sito AEM.

      >[!NOTE]
      >
      > Aggiorna ciascun menu a discesa per ottenere l’ulteriore classificazione nel menu a discesa successivo.

   1. Dalla scheda **Articoli**, seleziona gli argomenti per i quali desideri generare l&#39;output.
1. Seleziona l&#39;icona **Genera predefinito** nella parte superiore per generare l&#39;output.

   ![](images/add-preset-articles-tab_cs.png){width="800"}

1. Viene visualizzato lo stato del processo di generazione dell’output. Nella colonna **Argomenti** sono elencati gli argomenti per i quali viene generato l&#39;output mentre nella colonna **Stato** è visualizzato lo stato di pubblicazione di ciascun argomento.

   Per visualizzare l&#39;output, posizionare il puntatore del mouse sull&#39;argomento e fare clic su Visualizza output.

   ![](images/add-preset-output-generated_cs.png){width="800"}


>[!NOTE]
>
> Potete anche modificare, rinominare, duplicare o eliminare un predefinito di output esistente dal menu Opzioni (Options).

![](images/edit-preset_cs.png){width="550"}

**Argomento padre:**[ Pubblicazione basata su articolo dall&#39;editor Web](web-editor-article-publishing.md)
