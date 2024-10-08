---
title: Integrazione di editor XML basati su desktop
description: Scopri come integrare editor XML basati su desktop
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: 434d7efd24147af23b4c65aeebf4c144ce3adda7
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Integrazione di editor XML basati su desktop {#id181GB01G0HS}

Sul mercato sono disponibili molti editor XML e potrebbe essere già in uso. Adobe FrameMaker è uno degli editor XML più potenti, fornito con il connettore AEM. Utilizzando il connettore AEM in FrameMaker, è possibile connettersi facilmente all&#39;archivio AEM, estrarre e archiviare i file e modificarli direttamente nel FrameMaker. È inoltre possibile configurare Experience Manager Guides per l&#39;avvio del FrameMaker dall&#39;editor Web. Dopo aver aperto il file nel FrameMaker, è possibile modificarlo e archiviarlo nuovamente nell&#39;archivio AEM.

## Abilitare la modifica di file nel FrameMaker dall&#39;editor Web

È possibile utilizzare FrameMaker o qualsiasi altro editor DITA per creare e aggiornare il contenuto DITA. Tuttavia, se l&#39;organizzazione utilizza il FrameMaker come editor DITA, è possibile offrire agli utenti un&#39;opzione per aprire i documenti DITA direttamente nel FrameMaker dall&#39;AEM.

Per impostazione predefinita, gli utenti non visualizzano il pulsante **Apri nel FrameMaker** sulla barra degli strumenti AEM. Per aggiungere questo pulsante sulla barra degli strumenti AEM, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.
   ![](assets/open-in-fm-config.png)

1. Selezionare l&#39;opzione **Mostra apertura nel pulsante di FrameMaker**.

1. FrameMaker Se utilizzi la versione 4.6 e la versione di settembre 2022 - Aggiornamento 3, devi abilitare la configurazione **FrameMaker versione 2022 aggiornamento 3 o superiore** affinché gli utenti possano trasmettere al FrameMaker i dettagli del server Experience Manager Guides. Per impostazione predefinita, è disabilitato.


1. Fai clic su **Salva**.


Quando si abilita l&#39;opzione **Mostra apertura nel pulsante di FrameMaker**, il pulsante **Apri nel FrameMaker** viene visualizzato quando si seleziona un file DITA nell&#39;archivio AEM. Quando questa opzione è *non abilitata*, il pulsante **Apri nel FrameMaker** viene visualizzato solo quando si seleziona un file con estensione fm o book nell&#39;archivio.



