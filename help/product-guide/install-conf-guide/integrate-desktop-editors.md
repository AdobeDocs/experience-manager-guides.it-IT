---
title: Integrazione di editor XML basati su desktop
description: Scopri come integrare editor XML basati su desktop
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 1%

---

# Integrazione di editor XML basati su desktop

Sul mercato sono disponibili molti editor XML e potrebbe essere già in uso. Adobe FrameMaker è uno degli editor XML più potenti, fornito con il connettore AEM. Utilizzando il connettore AEM in FrameMaker, è possibile connettersi facilmente all’archivio AEM, estrarre e archiviare i file e modificarli direttamente in FrameMaker. È inoltre possibile configurare Experience Manager Guides per l&#39;avvio di FrameMaker dall&#39;editor Web. Dopo aver aperto il file in FrameMaker, puoi modificarlo e archiviarlo nuovamente nell’archivio di AEM.

## Abilitare la modifica di file in FrameMaker dall’editor Web

È possibile utilizzare FrameMaker o qualsiasi altro editor DITA per creare e aggiornare il contenuto DITA. Tuttavia, se l&#39;organizzazione utilizza FrameMaker come editor DITA, è possibile offrire agli utenti un&#39;opzione per aprire i documenti DITA direttamente in FrameMaker da AEM.


Per impostazione predefinita, gli utenti non visualizzano il pulsante **Apri in FrameMaker** sulla barra degli strumenti di AEM.

Le schede seguenti forniscono istruzioni per aggiungere questo pulsante sulla barra degli strumenti di AEM in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per aggiungere questo pulsante sulla barra degli strumenti di AEM:


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Booleano \(true/false\). Se si desidera visualizzare il pulsante **Apri in FrameMaker**, impostare questa proprietà su true. <br> **Valore predefinito**: false |



Se utilizzi la versione 2409 e la versione di settembre 2022 di FrameMaker - Aggiornamento 3, devi abilitare la configurazione **FrameMaker versione 2022 aggiornamento 3 o superiore** affinché gli utenti possano trasmettere i dettagli del server Experience Manager Guides a FrameMaker.  Per impostazione predefinita è disabilitato.


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Booleano \(true/false\). Se utilizzi FrameMaker versione di settembre 2022 - Aggiornamento 3 , imposta questa proprietà su true. <br> **Valore predefinito**: false |



Quando si imposta la proprietà *openinframebuttonshow* su true, viene visualizzato il pulsante **Apri in FrameMaker** quando si seleziona un file DITA nell&#39;archivio AEM. Se questa proprietà non è impostata su *true*, il pulsante **Apri in FrameMaker** viene visualizzato solo quando si seleziona un file con estensione fm o book nell&#39;archivio

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.
   ![](assets/open-in-fm-config.png)

1. Selezionare l&#39;opzione **Mostra apertura nel pulsante FrameMaker**.

1. Se utilizzi la versione 4.6 e la versione di settembre 2022 di FrameMaker - Aggiornamento 3, devi abilitare la configurazione **FrameMaker versione 2022 aggiornamento 3 o superiore** affinché gli utenti possano trasmettere i dettagli del server Experience Manager Guides a FrameMaker. Per impostazione predefinita, è disabilitato.


1. Fai clic su **Salva**.


Quando si abilita l&#39;opzione **Mostra apertura nel pulsante FrameMaker**, il pulsante **Apri in FrameMaker** viene visualizzato quando si seleziona un file DITA nell&#39;archivio AEM. Quando questa opzione è *non abilitata*, il pulsante **Apri in FrameMaker** viene visualizzato solo quando si seleziona un file con estensione fm o book nell&#39;archivio.

>[!ENDTABS]
