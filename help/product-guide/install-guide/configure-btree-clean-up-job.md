---
title: Configura processo di pulizia dell'albero B per i servizi locali
description: Configura processo di pulizia dell'albero B per i servizi locali
feature: Output Generation
role: Admin
level: Experienced
exl-id: ff6f968c-3440-4757-882a-676711ad05c3
TQID: https://experienceleague.adobe.com/qvOHGtHbgKS3xUv0pEXKTqeWblIDj8JKJwik8heXwPo
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 156
ht-degree: 2%

---

# Configurare la pulizia dell&#39;albero B

Imposta il processo di pulizia dell&#39;albero B e gestisci l&#39;impostazione `Guides B-tree deletion` per mantenere il sistema ottimizzato e l&#39;archiviazione pulita.

## Configura processo di pulizia albero B

Per configurare il processo di pulizia della struttura B, effettuare le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob*.

1. Aggiornare l&#39;espressione cron per impostare la frequenza di esecuzione del processo di pianificazione della pulizia dell&#39;albero B.

1. Configurare il modulo di pianificazione della pulizia dell&#39;albero B come illustrato di seguito.

   ![](assets/btree-cleanup-config.png)

1. Seleziona **Salva**.


## Configura le guide dell&#39;eliminazione dell&#39;albero B impostazione di abilitazione

Per abilitare l’impostazione, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.fmdita.config.ConfigManager*.
1. Abilitare l&#39;impostazione `Guides btree deletion enabled`.

   ![](assets/btree-cleanup-setting.png)

1. Seleziona **Salva**.
