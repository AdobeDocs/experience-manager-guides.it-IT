---
title: Configurare la visualizzazione dei collegamenti basati su UUID
description: Scopri come configurare la visualizzazione dei collegamenti basati su UUID
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---

# Configurare la visualizzazione dei collegamenti basati su UUID {#id2035G20M0QN}

Per impostazione predefinita, quando si crea un collegamento utilizzando l&#39;opzione Inserisci riferimento o Inserisci contenuto riutilizzo nell&#39;editor Web, il collegamento viene creato utilizzando l&#39;UUID del contenuto di riferimento. La proprietà **Link** \(nel pannello Proprietà\) del contenuto a cui si fa riferimento può essere configurata per mostrare il percorso relativo del contenuto a cui si fa riferimento o l&#39;UUID. Per impostazione predefinita, l’UUID del contenuto a cui si fa riferimento viene visualizzato nel pannello Proprietà.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per visualizzare il percorso relativo o l’UUID del contenuto a cui si fa riferimento nell’editor Web:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Booleano \(true/false\). Se desideri visualizzare il percorso relativo del contenuto collegato, imposta questa proprietà su false. <br> **Valore predefinito**: true |

**Argomento padre:**&#x200B;[ Personalizza editor Web](conf-web-editor.md)
