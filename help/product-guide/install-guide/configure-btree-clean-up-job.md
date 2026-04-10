---
title: Configura processo di pulizia dell'albero B per i servizi locali
description: Configura processo di pulizia dell'albero B per i servizi locali
feature: Output Generation
role: Admin
level: Experienced
exl-id: ff6f968c-3440-4757-882a-676711ad05c3
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '145'
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

   ![](assets/btree-cleanup-config.png){align="left"}

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

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Seleziona **Salva**.
