---
title: Configurare i filtri di testo
description: Scopri come configurare i filtri di testo
exl-id: 0963606c-010e-4a72-b7bf-850b86b34a84
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Configurare i filtri di testo {#id21BPD0FK0XA}

Le guide AEM consentono di cercare testo nei file presenti nel percorso selezionato dell’archivio AEM. È possibile utilizzare la ricerca con filtro per cercare i file dal pannello del repository o per sfogliare i file. Quando si lavora nell&#39;editor Web, è necessario utilizzare la finestra di dialogo Sfoglia file per inserire elementi come immagine, riferimento o riferimento chiave.

Per impostazione predefinita, è possibile utilizzare alcuni filtri migliorati per eseguire ricerche nei file nell’archivio AEM. È possibile filtrare tutti i file DITA o i file non DITA presenti nel percorso selezionato. È inoltre possibile cercare valori specifici negli attributi degli elementi DITA. È inoltre possibile cercare i file estratti dall&#39;utente specificato.

>[!NOTE]
>
> Puoi anche configurare il profilo globale e aggiungere altri filtri per la ricerca.

Per configurare i filtri di testo, effettua le seguenti operazioni:

1. Accedi a Adobe Experience Manager come amministratore.
1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul pulsante **Profilo globale** affiancare.
1. Fai clic su **Configurazione editor XML**.
1. Fai clic su **Modifica** nella parte superiore.
1. Fai clic su **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.
   1. Configura i filtri nel file. Puoi anche aggiungere filtri personalizzati, come illustrato nell’esempio seguente:

      Nel frammento di codice riportato di seguito viene illustrato come aggiungere opzioni di filtro File DITA, Elementi DITA non DITA ed Elementi sottoposti a Check-Out da file. Contiene anche un filtro personalizzato: Tag.

      ```
       "operation":"like"
                                      },
                                      {
                                      "title":"Checked out by",
                                      "property":"jcr:content/cq:drivelock",
                                      "operation":"like",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Checked out by"
                                      },
                                      "children":[
                                      {
                                      "title":"Check out"
                                      }
                                      ]
                                      },
                                      {
                                      "title":"Tags",
                                      "property":"jcr:content/metadata/cq:tags",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Enter Tag"
                                      },
                                      "children":[
                                      {
                                      "title":"Tags"
                                      }
                                      ]
                                      }
                                      ]
      ```

      Nel frammento di codice precedente, il primo filtro è per File DITA. La definizione del filtro accetta i seguenti parametri:

      ****Titolo****: nome visualizzato del filtro. Questo titolo viene visualizzato come opzione di filtro nella finestra di dialogo Sfoglia file.

      ****Proprietà****: proprietà da associare nei metadati del file. Ad esempio, per consentire solo i file la cui proprietà contiene i metadati dita\_class, il filtro proprietà accetta &quot;jcr:content/metadata/dita\_class&quot; come valore.

      ****Operazione **:**Specifica &quot;exists&quot; (esiste) per rilevare l’esistenza del valore specificato nel parametro della proprietà

1. Carica il file ui\_config.json aggiornato contenente i filtri aggiunti.

I filtri configurati sono disponibili nel pannello dei filtri.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
