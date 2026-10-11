---
title: Configurare i filtri dello stato del documento
description: Scopri come configurare i filtri per lo stato del documento
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6dee8479-770f-48d7-9939-5035388d16d8
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%
---
# Configurare i filtri dello stato del documento per Cloud Service

Adobe Experience Manager Guides offre la funzione di eseguire ricerche in un file in base al suo stato corrente del documento. È possibile utilizzare la ricerca con filtro per cercare i file dall&#39;interfaccia del repository per sfogliare i file.

Per configurare i filtri dello stato del documento, effettuare le seguenti operazioni:

1. Accedi a Adobe Experience Manager come amministratore.
1. Seleziona il collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti, quindi selezionare **Profili cartella**.
1. Apri il riquadro **Profilo globale**. Puoi anche selezionare una sezione del profilo di cartella specifica se desideri che queste modifiche vengano applicate solo a tale cartella invece che a livello globale.
1. Passa a **Configurazione editor XML**.
1. Seleziona l&#39;icona **Modifica** in alto.
1. Seleziona l&#39;icona **Scarica** per scaricare il file `ui\_config.json` nel sistema locale.
Nel file `ui\_config.json` scaricato, fare riferimento alla sezione seguente:

   ```
   "repositoryFilters": [
       {
       "title": "Document state",
       "property": "jcr:content/metadata/docstate",
       "children": [
           {
           "title": "Draft",
           "value": "Draft"
           },
           {
           "title": "Edit",
           "value": "Edit"
           },
           {
           "title": "In-Review",
           "value": "In-Review"
           },
           {
           "title": "Approved",
           "value": "Approved"
           },
           {
           "title": "Reviewed",
           "value": "Reviewed"
           },
           {
           "title": "Done",
           "value": "Done"
           }
       ]
       }
   ]
   ```

   Questo frammento rappresenta i filtri predefiniti per lo stato del documento disponibili in Experience Manager Guides.

1. Puoi personalizzare i valori del filtro in base al flusso di lavoro della tua organizzazione. Ad esempio, per aggiungere uno stato del documento personalizzato **In sospeso**, inserire la voce seguente in `children`:

   ```
   {
       "title": "Pending",
       "value": "Pending"
   }
   ```

1. Una volta aggiornato, salva il file e caricalo.

I filtri configurati vengono visualizzati nel pannello **Filtri** nell&#39;archivio nella home page.

**Argomento padre:**[ Personalizza editor](customize-overview.md)
