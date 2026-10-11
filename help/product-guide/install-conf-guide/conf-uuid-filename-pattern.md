---
title: Configura pattern nome file UUID
description: Scopri come configurare il pattern del nome file UUID
feature: Migration
role: Admin
level: Experienced
exl-id: 63d19ec4-1313-4691-b83e-38b67f9d2050
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: 5be0fc8f-1cff-5c3e-bb92-2903a56a3de6
    internal-label: Migration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 1%
---
# Configura pattern nome file UUID

Quando importi il contenuto, non è necessario che i nomi dei file siano basati sull’UUID. In un sistema che utilizza nomi di file basati su UUID, è obbligatorio fare riferimento a tutti i file utilizzando i loro UUID anziché i nomi di file originali. Se un file importato non ha nomi di file basati su UUID, potete configurare il sistema per aggiungere un UUID alle proprietà del file. Questo UUID viene quindi utilizzato per fare riferimento a tali file dove UUID non viene utilizzato per la denominazione dei file.

## Passaggi per configurare il pattern del nome file UUID

Le schede seguenti forniscono istruzioni per configurare il pattern del nome file UUID in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare il pattern del nome file UUID:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Stringa che specifica il regex per il pattern del nome file UUID. <br> Se un file non segue il pattern specificato, viene aggiunto un UUID alla proprietà del file e tutti i riferimenti al file vengono aggiornati con l’UUID assegnato al file. <br> **Valore predefinito**: `"^GUID-(?<id>.*)"` |

>[!TAB On-Premise]

Effettua le seguenti operazioni per controllare i nomi dei file in base a un pattern UUID e assegnare UUID ai file a cui non è stato assegnato un UUID:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.fmdita.config.ConfigManager*.

1. Nella proprietà **UUID Filename Patterns**, specifica un pattern per verificare i nomi del file importato.

   Se un file non segue il pattern specificato, viene aggiunto un UUID alla proprietà del file e tutti i riferimenti al file vengono aggiornati con l’UUID assegnato al file.

1. Seleziona **Salva**.

>[!ENDTABS]
