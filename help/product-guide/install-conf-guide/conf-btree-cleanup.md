---
title: Configura processo di pulizia archivio riferimenti
description: Configura processo di pulizia archivio riferimenti
feature: Output Generation
role: Admin
level: Experienced
exl-id: 58f98313-fc91-43b3-9553-aa5ab4946925
source-git-commit: 370a28a06a37b632873a79c9b83b8660a0221dd8
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
