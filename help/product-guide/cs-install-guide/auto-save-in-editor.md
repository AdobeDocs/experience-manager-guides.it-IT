---
title: Configurare il salvataggio automatico dei file nell’editor web
description: Scopri come configurare il salvataggio automatico dei file nell’editor web
exl-id: 4d99c3d8-cf6a-4cf3-aaec-9009a0376c1e
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/yHZSl9G2a6ras7kUUpNho5TG8yeIJzeFXzwxGQSWp44'
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
source-wordcount: '190'
ht-degree: 1%
---
# Configurare il salvataggio automatico dei file nell’editor web {#id199CC0J0M5Z}

Una delle funzioni più comuni nell’editor basato su browser è la possibilità di salvare i dati dopo un periodo di tempo specifico. AEM Guides Web Editor supporta anche il salvataggio automatico di file di argomenti e mappe nell&#39;intervallo di tempo specificato. Quando questa funzione viene attivata, viene salvata la copia di lavoro dell&#39;argomento o della mappa. Non è stata creata una nuova versione dell&#39;argomento o della mappa. Per creare una nuova versione, è necessario fare clic sull&#39;icona Salva revisione nella barra degli strumenti dell&#39;editor Web.

La funzione di salvataggio automatico non è abilitata per impostazione predefinita ed è necessario abilitarla utilizzando il file di configurazione.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per configurare l’intervallo di tempo per il salvataggio automatico e il salvataggio automatico del file:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Booleano \(true/false\).<br> **Valore predefinito**: false |
| `xmleditor.autosaveinterval` | Specifica l’intervallo di tempo in secondi per attivare la funzione di salvataggio automatico. |  |

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
