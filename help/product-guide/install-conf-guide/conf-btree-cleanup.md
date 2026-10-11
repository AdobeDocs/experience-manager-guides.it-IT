---
title: Configura processo di pulizia archivio riferimenti
description: Configura processo di pulizia archivio riferimenti
feature: Output Generation
role: Admin
level: Experienced
exl-id: 58f98313-fc91-43b3-9553-aa5ab4946925
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 3%
---
# Configura pulizia archivio di riferimento

Imposta il processo di pulizia dell&#39;archivio di riferimento e gestisci l&#39;impostazione `Guides BTree deletion` per mantenere il sistema ottimizzato e l&#39;archiviazione pulita.

## Configura processo di pulizia archivio di riferimento

Le schede seguenti forniscono istruzioni per configurare il processo di pulizia dell’archivio di riferimento in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Valore predefinito:** &quot;0 0 0 * * ?&quot; |

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob*.

1. Aggiornare l&#39;espressione cron per impostare la frequenza di esecuzione del processo di pianificazione della pulizia dell&#39;archivio di riferimento.

1. Configura la pianificazione di pulizia dell’archivio di riferimento come mostrato di seguito.

   ![](assets/btree-cleanup-config.png)

1. Seleziona **Salva**.

>[!ENDTABS]

## Configura le guide dell&#39;eliminazione dell&#39;albero B impostazione di abilitazione

Le seguenti schede forniscono istruzioni per abilitare l’impostazione in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Valore predefinito:** &quot;True&quot; |

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.fmdita.config.ConfigManager*.
1. Abilita l&#39;impostazione **Eliminazione btree abilitata** (btree.deletion.enabled).

   ![](assets/btree-cleanup-setting.png)

1. Seleziona **Salva**.

>[!ENDTABS]
