---
title: Configura richiesta di salvataggio come nuova versione alla chiusura
description: Scopri come configurare la richiesta di salvataggio come nuova versione alla chiusura
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: da41044a-bab0-456b-9543-effc88d1a2ae
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
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
