---
title: Configura richiesta di salvataggio come nuova versione alla chiusura
description: Scopri come configurare la richiesta di salvataggio come nuova versione alla chiusura
exl-id: 1b8c3eaa-a654-4563-9541-18a59b7d306c
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configura richiesta di salvataggio come nuova versione alla chiusura {#id222HBI00XXA}

Quando l&#39;utente tenta di chiudere un file aperto nell&#39;editor Web utilizzando **Chiudi** nella scheda del file o nella **Chiudi** nel menu Opzioni, viene visualizzata una finestra di dialogo se il file contiene dati non salvati o una versione non salvata. Se la versione non viene salvata, viene richiesto di salvare il file come nuova versione.

Il **Salva come nuova versione** La casella di controllo non è attivata per impostazione predefinita ed è necessario attivarla da configMgr. Per abilitare l’opzione per impostazione predefinita nell’editor web, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacchetto.

1. Seleziona la **Chiedi nuova versione alla chiusura** opzione.

1. Fai clic su **Salva**.


Quando questa opzione è selezionata, il **Salva come nuova versione** è selezionata per impostazione predefinita nella finestra di dialogo.

Per ulteriori dettagli, consulta *Scenari di chiusura e salvataggio dei file* nella guida Utilizzo delle guide di Adobe Experience Manager as a Cloud Service.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
