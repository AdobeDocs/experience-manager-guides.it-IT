---
title: Configurare il processo di pulizia della struttura B per Cloud Services
description: Configurare il processo di pulizia della struttura B per Cloud Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: de464e92-f17b-4c99-98f2-fdba8d214129
TQID: https://experienceleague.adobe.com/-n4Winzqo-HNb2FDH6RI223UT9uvuOc8-OT7mgXjblc
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 132
ht-degree: 3%

---

# Configurare la pulizia dell&#39;albero B

Imposta il processo di pulizia dell&#39;albero B e gestisci l&#39;impostazione `Guides BTree deletion` per mantenere il sistema ottimizzato e l&#39;archiviazione pulita.

## Configura processo di pulizia albero B

Per configurare il processo di pulizia della struttura B, effettuare le seguenti operazioni:

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](../cs-install-guide/download-install-additional-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Valore predefinito:** &quot;0 0 0 * * ?&quot; |


## Configura le guide dell&#39;eliminazione dell&#39;albero B impostazione di abilitazione

Per abilitare l’impostazione, effettua le seguenti operazioni:

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](../cs-install-guide/download-install-additional-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Valore predefinito:** &quot;True&quot; |
