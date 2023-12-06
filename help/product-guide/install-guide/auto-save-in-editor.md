---
title: Configurare il salvataggio automatico dei file nell’editor web
description: Scopri come configurare il salvataggio automatico dei file nell’editor web
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# Configurare il salvataggio automatico dei file nell’editor web {#id199CC0J0M5Z}

Una delle funzioni più comuni nell’editor basato su browser è la possibilità di salvare i dati dopo un periodo di tempo specifico. L&#39;editor Web delle guide AEM supporta inoltre il salvataggio automatico dei file argomento e mappa nell&#39;intervallo di tempo specificato. Quando questa funzione viene attivata, viene salvata la copia di lavoro dell&#39;argomento o della mappa. Non è stata creata una nuova versione dell&#39;argomento o della mappa. Per creare una nuova versione, è necessario fare clic sull&#39;icona Salva revisione nella barra degli strumenti dell&#39;editor Web.

La funzione di salvataggio automatico non è attivata per impostazione predefinita ed è necessario attivarla da configMgr. Per abilitare la funzione di salvataggio automatico nell’editor Web, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacchetto.

1. In *XmlEditorConfig* , selezionare la **Salvataggio automatico** opzione.

1. In **Intervallo salvataggio automatico** , specificare l&#39;intervallo di tempo in secondi per attivare la funzione di salvataggio automatico.

1. Fai clic su **Salva**.


**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
