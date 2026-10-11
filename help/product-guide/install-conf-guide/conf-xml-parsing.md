---
title: Configurare l’entità di analisi XML per Cloud Service e On-Premise
description: Scopri come configurare l’entità di analisi XML per Cloud Service e On-Premise
feature: Output Generation
role: Admin
level: Experienced
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
source-wordcount: '311'
ht-degree: 1%
---
# Configura limite dimensioni entità parser XML

Experience Manager Guides consente di configurare un limite alle dimensioni totali delle entità accettate dal parser XML durante la pubblicazione. Questo aiuta a prevenire problemi come attacchi di espansione di entità XML e l’elaborazione di payload di dimensioni eccessive.

>[!NOTE]
>
>Puoi configurare un limite alla dimensione totale dell’entità accettata dal parser XML durante la pubblicazione, riducendo i rischi come attacchi di espansione dell’entità XML e l’elaborazione di payload di dimensioni eccessive. La gestione dei limiti di dimensione delle entità differisce tra Java 21 e Java 25; di conseguenza, si consiglia agli ambienti che eseguono l’aggiornamento a Java 25 di rivedere e convalidare la propria configurazione per garantire che i flussi di lavoro di pubblicazione continuino a funzionare senza errori.

Questa configurazione include due proprietà correlate:

* **Applica limite dimensioni totali entità parser XML** (`dxml.publish.xml.apply.total.entity.size.limit`): abilita o disabilita il controllo del limite dimensioni totali entità.
* **Limite dimensioni totali entità parser XML** (`dxml.publish.xml.total.entity.size.limit`): specifica il valore (caratteri) JAXP `totalEntitySizeLimit` applicato ai parser XML protetti quando il flag di applicazione è abilitato.

Le schede seguenti forniscono istruzioni per configurare queste proprietà in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.apply.total.entity.size.limit` | **Valore predefinito:** &quot;true&quot; |
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.total.entity.size.limit` | **Valore predefinito:** &quot;50000000&quot; |

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService*.

1. Configura le seguenti impostazioni in base alle tue esigenze:

   * **Applica limite dimensioni totali entità parser XML** (`dxml.publish.xml.apply.total.entity.size.limit`): per impostazione predefinita, questa impostazione è disabilitata.
   * **Limite dimensioni totali entità parser XML** (`dxml.publish.xml.total.entity.size.limit`): per impostazione predefinita, questo valore è impostato su `50000000` caratteri. Questa impostazione ha effetto solo quando è abilitata l&#39;impostazione **Applica limite dimensioni totali entità parser XML**.

1. Seleziona **Salva**.

>[!ENDTABS]



