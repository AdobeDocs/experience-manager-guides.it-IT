---
title: Integrazione di editor XML basati su desktop
description: Scopri come integrare editor XML basati su desktop
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Integrazione di editor XML basati su desktop {#id181GB01G0HS}

Sul mercato sono disponibili molti editor XML e potrebbe essere già in uso. Adobe FrameMaker è uno degli editor XML più potenti, fornito con il connettore AEM. Utilizzando il connettore AEM in FrameMaker, è possibile connettersi facilmente all&#39;archivio AEM, estrarre e archiviare i file e modificarli direttamente nel FrameMaker. Puoi anche configurare le guide AEM per avviare il FrameMaker dall’editor web. Dopo aver aperto il file nel FrameMaker, è possibile modificarlo e archiviarlo nuovamente nell&#39;archivio AEM.

## Abilitare la modifica di file nel FrameMaker dall&#39;editor Web

È possibile utilizzare FrameMaker o qualsiasi altro editor DITA per creare e aggiornare il contenuto DITA. Tuttavia, se l&#39;organizzazione utilizza il FrameMaker come editor DITA, è possibile offrire agli utenti un&#39;opzione per aprire i documenti DITA direttamente nel FrameMaker dall&#39;AEM.

Per impostazione predefinita, gli utenti non visualizzano **Apri nel FrameMaker** sulla barra degli strumenti AEM. Per aggiungere questo pulsante sulla barra degli strumenti AEM, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacchetto.

   ![](assets/open-in-fm-toolbar.png){width="550" align="left"}

1. Seleziona la **Mostra pulsante Apri in FrameMaker** opzione.

1. Fai clic su **Salva**.


Quando si abilita **Mostra pulsante Apri in FrameMaker** , quindi **Apri nel FrameMaker** viene visualizzato quando si seleziona un file DITA nell&#39;archivio AEM. Quando questa opzione è *non abilitato*, il **Apri nel FrameMaker** viene visualizzato solo quando si seleziona un file fm o book nel repository.
