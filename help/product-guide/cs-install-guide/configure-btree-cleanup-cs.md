---
title: Configurare il processo di pulizia della struttura B per Cloud Services
description: Configurare il processo di pulizia della struttura B per Cloud Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: de464e92-f17b-4c99-98f2-fdba8d214129
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '125'
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
