---
title: Abilita nuovo motore PDF
description: Scopri come abilitare il nuovo motore PDF in Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 7f2b24b0ffbedaa3542de9d75d10aa155f6c3c0e
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
