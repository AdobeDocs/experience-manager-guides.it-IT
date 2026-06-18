---
title: Configura richiesta di salvataggio come nuova versione alla chiusura
description: Scopri come configurare la richiesta di salvataggio come nuova versione alla chiusura
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: da41044a-bab0-456b-9543-effc88d1a2ae
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 1%

---

# Configura richiesta di salvataggio come nuova versione alla chiusura {#id222HBI00XXA}

Quando l&#39;utente cerca di chiudere un file aperto nell&#39;editor utilizzando il pulsante **Chiudi** nella scheda del file o l&#39;opzione **Chiudi** nel menu Opzioni, viene visualizzata una finestra di dialogo se il file contiene dati non salvati o una versione non salvata. Se la versione non viene salvata, viene richiesto di salvare il file come nuova versione.

Le seguenti schede forniscono istruzioni in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare un prompt da salvare come nuova versione alla chiusura:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Booleano \( true/ false\). <br>  **Valore predefinito**: true |

Quando questa configurazione è abilitata, la casella di controllo **Salva come nuova versione** è selezionata per impostazione predefinita nella finestra di dialogo.

Per ulteriori dettagli, consulta la sezione *File close and save scenarios* nella guida Using Adobe Experience Manager Guides as a Cloud Service (Utilizzo di).

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Selezionare l&#39;opzione **Richiedi nuova versione alla chiusura**.

1. Fai clic su **Salva**.


La casella di controllo **Salva come nuova versione** non è attivata per impostazione predefinita ed è necessario attivarla da configMgr.

Quando questa opzione è selezionata, la casella di controllo **Salva come nuova versione** è selezionata per impostazione predefinita nella finestra di dialogo.

Per ulteriori dettagli, consulta la sezione *File close and save scenarios* nella guida Using Adobe Experience Manager Guides as a Cloud Service (Utilizzo di).

>[!ENDTABS]
