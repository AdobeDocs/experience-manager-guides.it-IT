---
title: Imposta l'Editor mappe avanzato come predefinito
description: Scopri come impostare l’Editor mappe avanzato come predefinito
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Imposta l&#39;Editor mappe avanzato come predefinito {#id181AI0003PN}

AEM Guides è dotato di un Basic Map Editor e di un Advanced Map Editor. Basic Map Editor offre tutte le funzioni necessarie per creare il file di mappa. L’Editor mappe avanzato è molto più ricco di funzioni ed è integrato all’interno dell’Editor web. Advanced Map Editor consente agli autori di creare e modificare file di mappe DITA con un&#39;interfaccia di facile utilizzo.

Per impostazione predefinita, ogni volta che viene creato un nuovo file mappa, questo viene aperto nell&#39;Editor mappa di base. È possibile modificare questo comportamento abilitando l’impostazione per aprire l’Editor mappe avanzato per impostazione predefinita.

Per impostare l&#39;Editor mappe avanzato come editor predefinito per i file di mappa, effettuate le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacchetto.

1. Seleziona la **Nascondi editor mappe di base** opzione.

   Selezionando questa opzione, gli utenti non visualizzeranno il collegamento Editor mappe di base nell&#39;interfaccia utente. Per impostazione predefinita, i file di mappa si aprono nell’Editor mappe avanzato.
