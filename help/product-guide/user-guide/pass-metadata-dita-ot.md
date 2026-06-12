---
title: Trasmettere i metadati all'output utilizzando DITA-OT
description: Scopri come trasmettere i metadati all’output utilizzando la pubblicazione DITA-OT in AEM Guides.
exl-id: 70ca32dc-56c3-45ee-b6b9-0efb8cc79ea1
feature: Publishing, Metadata Management
role: User
TQID: https://experienceleague.adobe.com/X840xTCOxbuqBpg8-YYbmFKOuF-KDHX-tGyj8rEG0hE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 620
ht-degree: 0%

---

# Trasmettere i metadati all&#39;output utilizzando DITA-OT {#id21BJ00QD0XA}

I metadati sono informazioni aggiuntive sull’output. In Adobe Experience Manager Guides, puoi trasmettere i metadati esistenti o creare tag di metadati personalizzati. È possibile trasmettere metadati agli output di formato AEM, PDF, HTML5, EPUB e Personalizzato utilizzando la pubblicazione DITA-OT.

Esistono due modi per trasmettere i metadati all&#39;output utilizzando DITA-OT:

- [Utilizzo della console Mappa](#using-map-console)
- [Utilizzo del dashboard delle mappe](#using-map-dashboard)

## Utilizzo della console Mappa

Per trasferire i metadati all&#39;output utilizzando la pubblicazione DITA-OT, effettuare le seguenti operazioni:

1. [Aprire il file mappa DITA nella console mappe](./open-files-map-console.md) per la quale si desidera passare i metadati al DITA-OT.
1. Seleziona e apri un predefinito di output a cui desideri trasmettere i campi di metadati. Ad esempio, seleziona Predefinito di output PDF. Verificare che sia stato creato utilizzando l&#39;opzione **DITA-OT**.
1. Dall&#39;elenco a discesa **Proprietà file** selezionare i metadati che si desidera passare alla pubblicazione DITA-OT.

   ![](images/custom-metadata-output-preset-new.png)

   Nel menu a discesa Proprietà sono elencate sia le proprietà personalizzate che quelle predefinite. Ad esempio, nella schermata precedente `dc:description`, `dc:language`, `dc:title` e `docstate` sono le proprietà predefinite.

   >[!NOTE]
   >
   > Queste proprietà vengono selezionate dal file metadataList disponibile nel percorso seguente:`/libs/fmdita/config/metadataList`. Per impostazione predefinita, in questo file sono elencate quattro proprietà: `dc:description`, `dc:language`, `dc:title` e `docstate`.

   Il file può essere sovrapposto in: `/apps/fmdita/config/metadataList`.

   Per passare una proprietà personalizzata per la quale sono già stati definiti i valori, visualizzare [Utilizzare i metadati di AEM nell&#39;output di PDF DITA-OT](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Le proprietà selezionate sono elencate sotto il menu a discesa.

   ![](images/metadata-added-dropdown.png){width="300"}

1. Seleziona **Salva** in alto a destra per salvare le modifiche.
1. Selezionare **Genera output**.

Le proprietà dei metadati selezionate verranno passate all&#39;output generato utilizzando DITA-OT.

>[!NOTE]
>
> A partire dalla versione 2502 di Experience Manager Guides, la funzionalità di trasmissione degli argomenti dei metadati delle mappe radice tramite la riga di comando DITA-OT è stata dichiarata obsoleta. Tuttavia, per evitare interruzioni, è stata aggiunta una nuova proprietà in `Config.Manager` per abilitare o disabilitare la funzionalità.  Per ulteriori dettagli, visualizzare [Configurare le impostazioni di generazione output](../cs-install-guide/conf-output-generation.md#configure-the-dita-ot-command-line-arguement-field-on-the-dita-map-dashboard).

## Utilizzo del dashboard delle mappe

Se si lavora nell&#39;**interfaccia utente di Assets**, eseguire la procedura seguente per passare i metadati all&#39;output utilizzando la pubblicazione DITA-OT:

1. Nell&#39;**interfaccia utente di Assets**, passare al file di mapping DITA per il quale si desidera passare i metadati al DITA-OT e selezionarlo.
1. Seleziona e modifica un predefinito di output a cui desideri trasmettere i campi di metadati. Ad esempio, seleziona Predefinito di output PDF.
1. Selezionare l&#39;opzione **DITA-OT** nel predefinito di output selezionato.

   ![](images/custom-meta-data-output-preset.png)

1. Dal menu a discesa Proprietà, selezionare i metadati che si desidera trasmettere alla pubblicazione DITA-OT.

   Nel menu a discesa Proprietà sono elencate sia le proprietà personalizzate che quelle predefinite. Ad esempio, nella schermata precedente l&#39;autore è la proprietà personalizzata, mentre `dc:description`, `dc:language`, `dc:title` e `docstate` sono le proprietà predefinite.

   >[!NOTE]
   >
   > Queste proprietà vengono selezionate dal file metadataList disponibile nel percorso seguente:`/libs/fmdita/config/metadataList`. Per impostazione predefinita, in questo file sono elencate quattro proprietà: `dc:description`, `dc:language`, `dc:title` e `docstate`.

   Il file può essere sovrapposto in: `/apps/fmdita/config/metadataList`.

   Per passare una proprietà personalizzata per la quale sono già stati definiti i valori, visualizzare [Utilizzare i metadati di AEM nell&#39;output di PDF DITA-OT](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Dal menu a discesa **Proprietà**, seleziona le proprietà personalizzate e predefinite richieste. Selezionare ad esempio `author`, `dc:title` e `dc:description`. Questi sono i `metadata/properties` standard che vengono creati dopo la creazione di un file. Le proprietà selezionate sono elencate sotto la dropbox.

   ![](images/selected-metadata-properties.png){width="300"}

1. Seleziona **Fine** in alto a sinistra per salvare le modifiche.
1. Genera l’output.

Le proprietà dei metadati selezionate verranno passate all&#39;output generato utilizzando DITA-OT.



**Argomento padre:**&#x200B;[&#x200B; Generazione output](generate-output.md)
