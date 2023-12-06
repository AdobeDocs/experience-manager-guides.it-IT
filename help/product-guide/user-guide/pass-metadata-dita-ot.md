---
title: Trasmettere i metadati all'output utilizzando DITA-OT
description: Scopri come trasmettere i metadati all’output utilizzando la pubblicazione DITA-OT nelle guide AEM.
exl-id: 70ca32dc-56c3-45ee-b6b9-0efb8cc79ea1
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Trasmettere i metadati all&#39;output utilizzando DITA-OT {#id21BJ00QD0XA}

I metadati sono informazioni aggiuntive sull’output. Nelle guide AEM puoi trasmettere i metadati esistenti o creare tag di metadati personalizzati. Utilizzando la pubblicazione DITA-OT, è possibile trasmettere metadati agli output in formato AEM, PDF, HTML5, EPUB e Personalizzato.

Per trasferire i metadati all&#39;output utilizzando la pubblicazione DITA-OT, effettuare le seguenti operazioni:

1. In **Interfaccia utente Assets**, passare al file di mapping DITA per il quale si desidera passare i metadati al DITA-OT e fare clic su di esso.
1. Seleziona e modifica un predefinito di output a cui desideri trasmettere i campi di metadati. Ad esempio, seleziona Predefinito di output PDF.
1. Seleziona **DITA-OT** in Genera &lt;output> Opzione Using nel predefinito di output selezionato.

   ![](images/custom-meta-data-output-preset.png){width="800" align="left"}

1. Dal menu a discesa Proprietà, selezionare i metadati che si desidera trasmettere alla pubblicazione DITA-OT.

   Nel menu a discesa Proprietà sono elencate sia le proprietà personalizzate che quelle predefinite. Ad esempio, nella schermata precedente l’autore è la proprietà personalizzata mentre `dc:description`, `dc:language`, `dc:title`, e `docstate` sono le proprietà predefinite.

   >[!NOTE]
   >
   > Queste proprietà vengono selezionate dal file metadataList disponibile nel percorso seguente:`/libs/fmdita/config/metadataList`. Per impostazione predefinita, in questo file sono elencate quattro proprietà: `dc:description`, `dc:language`, `dc:title`, e `docstate`.

   Questo file può essere sovrapposto in: `/apps/fmdita/config/metadataList`.

   Per passare una proprietà personalizzata per la quale hai già definito i valori, vedi [Utilizzare i metadati AEM nell&#39;output DITA-OT PDF](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Dalla sezione **Proprietà** , seleziona le proprietà personalizzate e predefinite richieste. Ad esempio, seleziona `author`, `dc:title`, e `dc:description`. Questi sono gli standard `metadata/properties` che viene creato una volta creato un file. Le proprietà selezionate sono elencate sotto la dropbox.

   ![](images/selected-metadata-properties.png){width="300" align="left"}

1. Clic **Fine** in alto a sinistra per salvare le modifiche.
1. Genera l’output.

Le proprietà dei metadati selezionate verranno passate all&#39;output generato utilizzando DITA-OT.

**Argomento padre:**[ Generazione di output](generate-output.md)
