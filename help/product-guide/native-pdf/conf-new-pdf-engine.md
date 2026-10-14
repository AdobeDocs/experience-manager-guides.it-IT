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
source-git-commit: f89becea89888f7dec81e18c9220dcabda8f4e7d
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 4%
---

# Configurare il motore PDF nativo v2

Il nuovo motore di pubblicazione per PDF nativo, ovvero _motore PDF nativo v2_, fornisce funzionalità di rendering PDF aggiornate e correzioni per _problemi del motore PDF nativo v1_.

>[!BEGINTABS]
>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](../install-conf-guide/download-install-config-override.md) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

| PID | Chiave proprietà | Valore proprietà |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Valore predefinito: `v1` |

>[!TAB On-Premise]


Per le distribuzioni on-premise, la disponibilità dipende dalle versioni di AEM e Java.

Il _motore PDF nativo v2_ richiede **Java 17 o versione successiva**.

- **AEM 6.5:** Il motore di pubblicazione nativo di PDF v2 non è supportato perché AEM 6.5 viene eseguito su Java 8.
- **AEM 6.5 LTS:** Il motore di pubblicazione nativo di PDF v2 è abilitato per impostazione predefinita. Non è richiesta alcuna configurazione aggiuntiva.

Se si preferisce tornare al _motore nativo di PDF v2_ con AEM 6.5 LTS, disinstallare il pacchetto di pubblicazione di PDF:
`/crx/packmgr/index.jsp#/etc/packages/com.adobe.guides/pdf-publisher-package-3.0.0.zip` da Gestione pacchetti CRX.

>[!ENDTABS]

