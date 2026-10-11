---
title: Configurare la visualizzazione dei collegamenti basati su UUID
description: Scopri come configurare la visualizzazione dei collegamenti basati su UUID
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/--RdjezGIsplCdBLF8u-3LvR92rVBcgGmPo8a7GbQys'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
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
source-wordcount: '162'
ht-degree: 1%
---
# Configurare la visualizzazione dei collegamenti basati su UUID {#id2035G20M0QN}

Per impostazione predefinita, quando si crea un collegamento utilizzando l&#39;opzione Inserisci riferimento o Inserisci contenuto riutilizzo nell&#39;editor Web, il collegamento viene creato utilizzando l&#39;UUID del contenuto di riferimento. La proprietà **Link** \(nel pannello Proprietà\) del contenuto a cui si fa riferimento può essere configurata per mostrare il percorso relativo del contenuto a cui si fa riferimento o l&#39;UUID. Per impostazione predefinita, l’UUID del contenuto a cui si fa riferimento viene visualizzato nel pannello Proprietà.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per visualizzare il percorso relativo o l’UUID del contenuto a cui si fa riferimento nell’editor Web:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Booleano \(true/false\). Se desideri visualizzare il percorso relativo del contenuto collegato, imposta questa proprietà su false. <br> **Valore predefinito**: true |

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
