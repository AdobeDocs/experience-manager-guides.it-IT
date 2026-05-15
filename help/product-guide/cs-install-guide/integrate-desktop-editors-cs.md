---
title: Integrazione di editor XML basati su desktop
description: Scopri come integrare editor XML basati su desktop
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
exl-id: 86ba53fa-0e08-4791-9018-09fe974691da
TQID: https://experienceleague.adobe.com/4cejVcInzwcFBWgxobUvn7g2teizpQCCeTC2Z5CZ1K8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 368
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
