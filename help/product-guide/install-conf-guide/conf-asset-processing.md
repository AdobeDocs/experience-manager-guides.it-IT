---
title: Configurare l’elaborazione delle risorse per Cloud Service
description: Scopri come configurare l’elaborazione delle risorse per Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 0b66a515-d8f1-4ea6-913f-e152ae114698
source-git-commit: 5af3356dff3c42b8a93ed97b5ee20b23976769a4
workflow-type: tm+mt
source-wordcount: '121'
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

1. Configura l&#39;impostazione **Abilita l&#39;elaborazione del processo pianificato da parte delle guide** (`enable.asset.processing.scheduler`) in base alle tue esigenze. Per impostazione predefinita, l’impostazione è attivata.

1. Seleziona **Salva**.

>[!ENDTABS]
