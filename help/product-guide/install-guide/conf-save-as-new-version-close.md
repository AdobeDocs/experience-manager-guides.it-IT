---
title: Configura richiesta di salvataggio come nuova versione alla chiusura
description: Scopri come configurare la richiesta di salvataggio come nuova versione alla chiusura
exl-id: 1b8c3eaa-a654-4563-9541-18a59b7d306c
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configura richiesta di salvataggio come nuova versione alla chiusura {#id222HBI00XXA}

Quando l&#39;utente cerca di chiudere un file aperto nell&#39;editor Web utilizzando il pulsante **Chiudi** nella scheda del file o l&#39;opzione **Chiudi** nel menu Opzioni, viene visualizzata una finestra di dialogo se il file contiene dati non salvati o una versione non salvata. Se la versione non viene salvata, viene richiesto di salvare il file come nuova versione.

La casella di controllo **Salva come nuova versione** non è attivata per impostazione predefinita ed è necessario attivarla da configMgr. Per abilitare l’opzione per impostazione predefinita nell’editor web, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Selezionare l&#39;opzione **Richiedi nuova versione alla chiusura**.

1. Fai clic su **Salva**.


Quando questa opzione è selezionata, la casella di controllo **Salva come nuova versione** è selezionata per impostazione predefinita nella finestra di dialogo.

Per ulteriori dettagli, consulta la sezione *File close and save scenarios* nella guida Using Adobe Experience Manager Guides as a Cloud Service.

**Argomento padre:**[ Personalizza editor Web](conf-web-editor.md)
