---
title: Configura replica DITA Assets
description: Scopri come configurare la replica delle risorse dita
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 3%

---

# Configurare la replica delle risorse DITA

Le schede seguenti forniscono istruzioni per configurare la funzione di replica di risorse DITA in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](../install-conf-guide/download-install-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Valore predefinito:** &quot;true&quot; |

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.fmdita.config.ConfigManager*.

1. Configurare l&#39;impostazione `Replicate DITA assets` in base alle proprie esigenze. Per impostazione predefinita, l’impostazione è attivata.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Seleziona **Salva**.

>[!ENDTABS]
