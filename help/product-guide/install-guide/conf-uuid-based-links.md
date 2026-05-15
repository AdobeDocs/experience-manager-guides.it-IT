---
title: Configurare la visualizzazione dei collegamenti basati su UUID
description: Scopri come configurare la visualizzazione dei collegamenti basati su UUID
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/QlYbIRVwAM10wfcu-Fz3CzOkCCUDZHbVzZo3xCxT3wI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 211
ht-degree: 0%

---

# Configurare la visualizzazione dei collegamenti basati su UUID {#id2035G20M0QN}

Per impostazione predefinita, quando si crea un collegamento utilizzando l&#39;opzione Inserisci riferimento o Inserisci contenuto riutilizzo nell&#39;editor Web, il collegamento viene creato utilizzando l&#39;UUID del contenuto di riferimento. La proprietà **Link** \(nel pannello Proprietà\) del contenuto a cui si fa riferimento può essere configurata per mostrare il percorso relativo del contenuto a cui si fa riferimento o l&#39;UUID. Questa visualizzazione è controllata dall&#39;opzione **Abilita UUID** in configMgr. Per impostazione predefinita, è attivato, il che implica che l’UUID del contenuto a cui si fa riferimento è visualizzato nel pannello Proprietà.

Per visualizzare il percorso relativo o l’UUID del contenuto a cui si fa riferimento nell’editor web, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nelle impostazioni *XmlEditorConfig*, l&#39;opzione **Abilita UUIDs** è abilitata per impostazione predefinita. Ciò implica che l&#39;UUID del contenuto a cui si fa riferimento viene visualizzato nella proprietà **Link** nel pannello Proprietà.

   Se desideri visualizzare il percorso relativo del contenuto collegato, deseleziona l&#39;opzione **Abilita UUID**.

1. Fai clic su **Salva**.


**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
