---
title: Personalizza editor
description: Scopri come personalizzare la visualizzazione delle tabelle incollate nell’editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: e66c13e4-6dc0-41a0-8582-32bacec9ae6c
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
source-wordcount: '225'
ht-degree: 0%
---
# Configurare la visualizzazione delle tabelle incollate per Cloud Service

Utilizzando la barra degli strumenti secondaria nell&#39;editor, è possibile inserire una tabella semplice nella posizione valida corrente o successiva di un argomento. È inoltre possibile copiare una tabella da Microsoft Word o Excel e incollarla direttamente in un file di argomento.

Gli amministratori possono configurare la visualizzazione delle tabelle copiate. Per impostazione predefinita, tali tabelle copiate vengono visualizzate come `simpletable` nell&#39;editor. È tuttavia possibile modificare questa impostazione per visualizzare le tabelle copiate come `tgroup` aggiornando l&#39;impostazione di configurazione dell&#39;editor XML.

>[!NOTE]
>
> Se si copia una tabella con righe o colonne unite, la tabella verrà incollata come tabella normale `trgoup` e non `simpletable` indipendentemente dall&#39;impostazione della tabella configurata nella configurazione dell&#39;editor XML.

Per aggiornare il formato di tabella predefinito, effettuare le seguenti operazioni:

1. Apri la pagina Navigazioni Adobe Experience Manager e seleziona **Strumenti** a sinistra.
2. Nel pannello Strumenti, seleziona **Guide** dall&#39;elenco degli strumenti.
3. Selezionare **Profili cartella**, quindi selezionare il profilo in cui si desidera aggiornare l&#39;impostazione della tabella.
4. Passare alla scheda **Configurazione editor XML**.
5. Seleziona l&#39;icona **Modifica** in alto.
6. Seleziona l&#39;icona **Scarica** per scaricare il file `ui_config.json` nel sistema locale.
7. Nel file `ui_config.json`, aggiornare l&#39;impostazione `simpletable` come illustrato di seguito:

   ```
   "htmlToDitaMapping":{ "table": {
   "name" : "tgroup",
   "wrapTag" : {
       "dita" : "table",
       "html" : "div"
   }
   } },
   ```


Una volta aggiornato, salva il file e caricalo.
