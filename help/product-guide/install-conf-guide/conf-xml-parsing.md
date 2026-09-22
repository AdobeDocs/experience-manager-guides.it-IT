---
title: Configurare l’entità di analisi XML per Cloud Service e On-Premise
description: Scopri come configurare l’entità di analisi XML per Cloud Service e On-Premise
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e4019ae1e605bd26f7df676a4fab8c632fd8fa8e
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



