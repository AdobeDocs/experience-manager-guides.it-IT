---
title: Integrazione di editor XML basati su desktop
description: Scopri come integrare editor XML basati su desktop
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
exl-id: 86ba53fa-0e08-4791-9018-09fe974691da
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Integrazione di editor XML basati su desktop

Sul mercato sono disponibili molti editor XML e potrebbe essere già in uso. Adobe FrameMaker è uno degli editor XML più potenti, fornito con il connettore AEM. Utilizzando il connettore AEM in FrameMaker, è possibile connettersi facilmente all’archivio AEM, estrarre e archiviare i file e modificarli direttamente in FrameMaker. È inoltre possibile configurare Experience Manager Guides per l&#39;avvio di FrameMaker dall&#39;editor Web. Dopo aver aperto il file in FrameMaker, puoi modificarlo e archiviarlo nuovamente nell’archivio di AEM.

## Abilitare la modifica di file in FrameMaker dall’editor Web

È possibile utilizzare FrameMaker o qualsiasi altro editor DITA per creare e aggiornare il contenuto DITA. Tuttavia, se l&#39;organizzazione utilizza FrameMaker come editor DITA, è possibile offrire agli utenti un&#39;opzione per aprire i documenti DITA direttamente in FrameMaker da AEM.


Per impostazione predefinita, gli utenti non visualizzano il pulsante **Apri in FrameMaker** sulla barra degli strumenti di AEM. Per aggiungere questo pulsante sulla barra degli strumenti di AEM, effettua le seguenti operazioni:

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per aggiungere questo pulsante sulla barra degli strumenti di AEM:


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Booleano \(true/false\). Se si desidera visualizzare il pulsante **Apri in FrameMaker**, impostare questa proprietà su true. <br> **Valore predefinito**: false |



Se utilizzi la versione 2409 e la versione di settembre 2022 di FrameMaker - Aggiornamento 3, devi abilitare la configurazione **FrameMaker versione 2022 aggiornamento 3 o superiore** affinché gli utenti possano trasmettere i dettagli del server Experience Manager Guides a FrameMaker.  Per impostazione predefinita è disabilitato.


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Booleano \(true/false\). Se utilizzi FrameMaker versione di settembre 2022 - Aggiornamento 3 , imposta questa proprietà su true. <br> **Valore predefinito**: false |



Quando si imposta la proprietà *openinframebuttonshow* su true, viene visualizzato il pulsante **Apri in FrameMaker** quando si seleziona un file DITA nell&#39;archivio AEM. Se questa proprietà non è impostata su *true*, il pulsante **Apri in FrameMaker** viene visualizzato solo quando si seleziona un file con estensione fm o book nell&#39;archivio.
