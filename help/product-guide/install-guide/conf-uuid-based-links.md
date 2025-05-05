---
title: Configurare la visualizzazione dei collegamenti basati su UUID
description: Scopri come configurare la visualizzazione dei collegamenti basati su UUID
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '209'
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


**Argomento padre:**&#x200B;[ Personalizza editor Web](conf-web-editor.md)
