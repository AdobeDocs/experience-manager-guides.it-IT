---
title: Configurare i filtri per la finestra di dialogo Sfoglia file
description: Scopri come configurare i filtri per la finestra di dialogo di navigazione dei file
exl-id: 1ef2cec8-2e77-40c1-9ed2-324048bf65fb
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# Configurare i filtri per la finestra di dialogo Sfoglia file {#id20CIL7009GN}

Quando si lavora nell&#39;editor Web, è necessario utilizzare la finestra di dialogo Sfoglia file per inserire elementi come immagine, riferimento o riferimento chiave. La finestra di dialogo Sfoglia file predefinita non offre alcuna opzione di filtro dei file. Puoi aggiungere filtri personalizzati che ti consentirebbero di accedere ai file richiesti in modo semplice e rapido.

Per aggiungere le opzioni di filtro dei file personalizzati alla finestra di dialogo Sfoglia file, effettua le seguenti operazioni:

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto
1. Fai clic sull&#39;icona **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.
1. Nel file `ui_config.json` aggiungere la definizione dei filtri che si desidera aggiungere.

   Il seguente frammento di codice mostra come aggiungere due opzioni di filtro: File DITA e File di immagine.

   ```
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

   titolo
:   Nome visualizzato del filtro. Questo titolo viene visualizzato come opzione di filtro nella finestra di dialogo Sfoglia file.

   proprietà
:   Proprietà da associare nei metadati del file. Ad esempio, per consentire solo i file la cui proprietà contiene i metadati `dita_class`, il filtro proprietà accetta &quot; `jcr:content/metadata/dita_class`&quot; come valore.

   operazione
:   Specificare &quot; `exists`&quot; per verificare l&#39;esistenza del valore specificato nel parametro della proprietà.

   Il secondo filtro è per File di immagine. I parametri sono simili al primo filtro, ad eccezione del parametro `value`. Il parametro `value` accetta un array di tipi di immagine come valore. Tutti i tipi di file specificati nel parametro value vengono cercati e visualizzati nella finestra di dialogo Sfoglia file. Tutti gli altri tipi di file vengono ignorati.

1. Salva il file *ui\_config.json* e carica lo stesso. Ricaricare quindi l&#39;editor Web.

   Quando avvii la finestra di dialogo Sfoglia file, vengono visualizzate le opzioni di filtro configurate nel file ui\_config.json.

   ![](assets/file-browse-custom-filters.png)


**Argomento padre:**&#x200B;[ Personalizza editor Web](conf-web-editor.md)
