---
title: Configurare i filtri per la finestra di dialogo Sfoglia file
description: Scopri come configurare i filtri per la finestra di dialogo di navigazione dei file
exl-id: 1ef09820-3b18-4762-b177-4d40926e21f0
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# Configurare i filtri per la finestra di dialogo Sfoglia file {#id20CIL7009GN}

Quando si lavora nell&#39;editor Web, è necessario utilizzare la finestra di dialogo Sfoglia file per inserire elementi come immagine, riferimento o riferimento chiave. La finestra di dialogo Sfoglia file predefinita non offre alcuna opzione di filtro dei file. Puoi aggiungere filtri personalizzati che ti consentirebbero di accedere ai file richiesti in modo semplice e rapido.

Per aggiungere le opzioni di filtro dei file personalizzati alla finestra di dialogo Sfoglia file, effettua le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passare al file di configurazione predefinito disponibile nella posizione seguente:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Creare una copia del file di configurazione predefinito nella posizione seguente:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Accedi a e apri il `ui_config.json` file in `apps` per la modifica.

1. In `ui_config.json` aggiungere la definizione dei filtri che si desidera aggiungere.

   Il seguente frammento di codice mostra come aggiungere due opzioni di filtro: File DITA e File di immagine.

   ```json
   "browseFilters": [
       {
         "title": "DITA Files",
         "property": "jcr:content/metadata/dita_class",
         "operation": "exists"
       },
       {
         "title": "Image Files",
         "property": "jcr:content/metadata/dc:format",
         "value": [        
           "image/jpeg",
           "image/gif",
           "image/png"
         ]
       }
   ]
   ```

   Nel frammento di codice precedente, il primo filtro è per File DITA. La definizione del filtro accetta i seguenti parametri:

   - **titolo:**   Nome visualizzato del filtro. Questo titolo viene visualizzato come opzione di filtro nella finestra di dialogo Sfoglia file.

   - **proprietà:**   Proprietà da associare nei metadati del file. Ad esempio, per consentire solo i file che hanno `dita_class` nella loro proprietà, il filtro proprietà accetta &quot;`jcr:content/metadata/dita_class`&quot; come valore.

   - **operazione:**   Specifica &quot;`exists`&quot; per rilevare l’esistenza del valore specificato nel parametro della proprietà.

   Il secondo filtro è per File di immagine. I parametri sono simili a quelli del primo filtro, ad eccezione del `value` parametro. Il `value` Il parametro accetta un array di tipi di immagine come valore. Tutti i tipi di file specificati nel parametro value vengono cercati e visualizzati nella finestra di dialogo Sfoglia file. Tutti gli altri tipi di file vengono ignorati.

1. Salva il *ui\_config.json* e ricaricare l&#39;editor Web.

   Quando avvii la finestra di dialogo Sfoglia file, vengono visualizzate le opzioni di filtro configurate nel file ui\_config.json.

   ![](assets/file-browse-custom-filters.png){width="300" align="left"}
