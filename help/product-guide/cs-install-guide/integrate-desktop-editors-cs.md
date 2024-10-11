---
title: Integrazione di editor XML basati su desktop
description: Scopri come integrare editor XML basati su desktop
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: b3ae1c02d3055fe15257d5de0365d30e7af21afb
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Integrazione di editor XML basati su desktop

Sul mercato sono disponibili molti editor XML e potrebbe essere già in uso. Adobe FrameMaker è uno degli editor XML più potenti, fornito con il connettore AEM. Utilizzando il connettore AEM in FrameMaker, è possibile connettersi facilmente all&#39;archivio AEM, estrarre e archiviare i file e modificarli direttamente nel FrameMaker. È inoltre possibile configurare Experience Manager Guides per l&#39;avvio del FrameMaker dall&#39;editor Web. Dopo aver aperto il file nel FrameMaker, è possibile modificarlo e archiviarlo nuovamente nell&#39;archivio AEM.

## Abilitare la modifica di file nel FrameMaker dall&#39;editor Web

È possibile utilizzare FrameMaker o qualsiasi altro editor DITA per creare e aggiornare il contenuto DITA. Tuttavia, se l&#39;organizzazione utilizza il FrameMaker come editor DITA, è possibile offrire agli utenti un&#39;opzione per aprire i documenti DITA direttamente nel FrameMaker dall&#39;AEM.


Per impostazione predefinita, gli utenti non visualizzano il pulsante **Apri nel FrameMaker** sulla barra degli strumenti AEM. Per aggiungere questo pulsante sulla barra degli strumenti AEM, effettua le seguenti operazioni:

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per aggiungere questo pulsante sulla barra degli strumenti AEM:


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Booleano \(true/false\). Se desideri visualizzare il pulsante **Apri nel FrameMaker**, imposta questa proprietà su true. <br> **Valore predefinito**: false |



Se utilizzi la versione 2409 e la versione di settembre 2022 - Aggiornamento 3 del FrameMaker, devi abilitare la configurazione **FrameMaker versione 2022 aggiornamento 3 o superiore** affinché gli utenti possano trasmettere i dettagli del server Experience Manager Guides al FrameMaker.  Per impostazione predefinita è disabilitato.


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Booleano \(true/false\). Se utilizzi la versione di settembre 2022 di FrameMaker - Aggiornamento 3 , imposta questa proprietà su true. <br> **Valore predefinito**: false |



Quando si imposta la proprietà *openinframebuttonshow* su true, viene visualizzato il pulsante **Apri nel FrameMaker** quando si seleziona un file DITA nell&#39;archivio AEM. Se questa proprietà non è impostata su *true*, il pulsante **Apri nel FrameMaker** viene visualizzato solo quando si seleziona un file con estensione fm o book nell&#39;archivio.



