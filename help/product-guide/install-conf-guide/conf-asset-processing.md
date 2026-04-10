---
title: Configurare l’elaborazione delle risorse per Cloud Service
description: Scopri come configurare l’elaborazione delle risorse per Cloud Service
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 3%

---

# Configurare la funzione di elaborazione delle risorse

Le schede seguenti forniscono istruzioni per configurare la funzione di elaborazione delle risorse in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Valore predefinito:** &quot;true&quot; |

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.fmdita.config.ConfigManager*.

1. Configurare l&#39;impostazione `Enable Guides asset processing scheduled job` in base alle proprie esigenze. Per impostazione predefinita, l’impostazione è attivata.

1. Seleziona **Salva**.

>[!ENDTABS]