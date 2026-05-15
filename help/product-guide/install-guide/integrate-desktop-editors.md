---
title: Integrazione di editor XML basati su desktop
description: Scopri come integrare editor XML basati su desktop
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/wILI1Y5nUtUiEuHG0wN4q2KCQko5mKN6CKy1Cs5kxTU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 322
ht-degree: 0%

---

# Integrazione di editor XML basati su desktop {#id181GB01G0HS}

Sul mercato sono disponibili molti editor XML e potrebbe essere già in uso. Adobe FrameMaker è uno degli editor XML più potenti, fornito con il connettore AEM. Utilizzando il connettore AEM in FrameMaker, è possibile connettersi facilmente all’archivio AEM, estrarre e archiviare i file e modificarli direttamente in FrameMaker. È inoltre possibile configurare Experience Manager Guides per l&#39;avvio di FrameMaker dall&#39;editor Web. Dopo aver aperto il file in FrameMaker, puoi modificarlo e archiviarlo nuovamente nell’archivio di AEM.

## Abilitare la modifica di file in FrameMaker dall’editor Web

È possibile utilizzare FrameMaker o qualsiasi altro editor DITA per creare e aggiornare il contenuto DITA. Tuttavia, se l&#39;organizzazione utilizza FrameMaker come editor DITA, è possibile offrire agli utenti un&#39;opzione per aprire i documenti DITA direttamente in FrameMaker da AEM.

Per impostazione predefinita, gli utenti non visualizzano il pulsante **Apri in FrameMaker** sulla barra degli strumenti di AEM. Per aggiungere questo pulsante sulla barra degli strumenti di AEM, effettua le seguenti operazioni:

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



