---
title: Configurare la richiesta di archiviazione di un file alla chiusura
description: Scopri come configurare la richiesta di archiviazione di un file alla chiusura
exl-id: d184c97f-8405-4bcd-963d-635f17584897
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---

# Configurare la richiesta di archiviazione di un file alla chiusura {#id222HC040PE8}

Quando l&#39;utente cerca di chiudere un file aperto nell&#39;editor Web utilizzando il pulsante **Chiudi** nella scheda del file o l&#39;opzione **Chiudi** nel menu Opzioni, viene visualizzata una finestra di dialogo se il file contiene dati non salvati o una versione non salvata. All&#39;utente viene richiesto di sbloccare il file se è bloccato.

La casella di controllo **Sblocca file** non è attivata per impostazione predefinita ed è necessario attivarla da configMgr. Per abilitare l’opzione per impostazione predefinita nell’editor web, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Selezionare l&#39;opzione **Richiedi archiviazione alla chiusura**.

1. Fai clic su **Salva**.


Quando questa configurazione è abilitata, la casella di controllo **Sblocca file** è selezionata per impostazione predefinita nella finestra di dialogo.

Per ulteriori dettagli, consulta la sezione *File close and save scenarios* nella guida Using Adobe Experience Manager Guides as a Cloud Service.

**Argomento padre:**&#x200B;[ Personalizza editor Web](conf-web-editor.md)
