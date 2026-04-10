---
title: Configurare la visualizzazione dei collegamenti basati su UUID
description: Scopri come configurare la visualizzazione dei collegamenti basati su UUID
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 1%

---

# Configurare la visualizzazione dei collegamenti basati su UUID {#id2035G20M0QN}

Per impostazione predefinita, quando crei un collegamento utilizzando l’opzione Inserisci riferimento o Inserisci contenuto riutilizzo nell’editor, il collegamento viene creato utilizzando l’UUID del contenuto a cui si fa riferimento. La proprietà **Link** \(nel pannello Proprietà\) del contenuto a cui si fa riferimento può essere configurata per mostrare il percorso relativo del contenuto a cui si fa riferimento o l&#39;UUID. Per Cloud Service, per impostazione predefinita l’UUID del contenuto a cui si fa riferimento viene visualizzato nel pannello Proprietà. Per On-Premise, questa visualizzazione è controllata dall&#39;opzione **Abilita UUID** in `configMgr`. Per impostazione predefinita, è attivato, il che implica che l’UUID del contenuto a cui si fa riferimento è visualizzato nel pannello Proprietà.

Le schede seguenti forniscono istruzioni per mostrare il percorso relativo o l’UUID del contenuto a cui si fa riferimento nell’editor in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per visualizzare il percorso relativo o l’UUID del contenuto a cui si fa riferimento nell’editor.

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Booleano \(true/false\). Se desideri visualizzare il percorso relativo del contenuto collegato, imposta questa proprietà su false. <br> **Valore predefinito**: true |


>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nelle impostazioni *XmlEditorConfig*, l&#39;opzione **Abilita UUIDs** è abilitata per impostazione predefinita. Ciò implica che l&#39;UUID del contenuto a cui si fa riferimento viene visualizzato nella proprietà **Link** nel pannello Proprietà.

   Se desideri visualizzare il percorso relativo del contenuto collegato, deseleziona l&#39;opzione **Abilita UUID**.

1. Fai clic su **Salva**.

>[!ENDTABS]

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](customize-overview.md)
