---
title: Imposta l'Editor mappe avanzato come predefinito
description: Scopri come impostare l’Editor mappe avanzato come predefinito
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Imposta l&#39;Editor mappe avanzato come predefinito {#id181AI0003PN}

AEM Guides viene fornito con un Editor di mappe di base e un Editor di mappe avanzato. Basic Map Editor offre tutte le funzioni necessarie per creare il file di mappa. L’Editor mappe avanzato è molto più ricco di funzioni ed è integrato all’interno dell’Editor web. Advanced Map Editor consente agli autori di creare e modificare file di mappe DITA con un&#39;interfaccia di facile utilizzo.

Per impostazione predefinita, ogni volta che viene creato un nuovo file mappa, questo viene aperto nell&#39;Editor mappa di base. È possibile modificare questo comportamento abilitando l’impostazione per aprire l’Editor mappe avanzato per impostazione predefinita.

Per impostare l&#39;Editor mappe avanzato come editor predefinito per i file di mappa, effettuate le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Selezionare l&#39;opzione **Nascondi editor mappe di base**.

   Selezionando questa opzione, gli utenti non visualizzeranno il collegamento Editor mappe di base nell&#39;interfaccia utente. Per impostazione predefinita, i file di mappa si aprono nell’Editor mappe avanzato.
