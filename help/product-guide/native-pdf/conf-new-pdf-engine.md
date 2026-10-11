---
title: Abilita nuovo motore PDF
description: Scopri come abilitare il nuovo motore PDF in Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced
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
source-wordcount: '74'
ht-degree: 2%
---

# Configurare il motore PDF nativo v2

Il nuovo motore di pubblicazione per PDF nativo, ovvero _motore PDF nativo v2_, fornisce funzionalità di rendering PDF aggiornate e correzioni per _problemi del motore PDF nativo v1_.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](../install-conf-guide/download-install-config-override.md) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

| PID | Chiave proprietà | Valore proprietà |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Valore predefinito: `v1` |

