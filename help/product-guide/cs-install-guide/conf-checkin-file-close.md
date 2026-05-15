---
title: Configurare la richiesta di archiviazione di un file alla chiusura
description: Scopri come configurare la richiesta di archiviazione di un file alla chiusura
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/Obg0rrng-HngZvxc2mtVt16YUylMAR7mIUgC9yKn-qU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 172
ht-degree: 1%

---

# Configurare la richiesta di archiviazione di un file alla chiusura {#id222HC040PE8}

Quando l&#39;utente cerca di chiudere un file aperto nell&#39;editor Web utilizzando il pulsante **Chiudi** nella scheda del file o l&#39;opzione **Chiudi** nel menu Opzioni, viene visualizzata una finestra di dialogo se il file contiene dati non salvati o una versione non salvata. All&#39;utente viene richiesto di sbloccare il file se è bloccato.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per configurare un prompt per archiviare un file alla chiusura:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booleano \( true/ false\).<br> **Valore predefinito**: false |

Quando questa configurazione è abilitata, la casella di controllo **Sblocca file** è selezionata per impostazione predefinita nella finestra di dialogo.

Per ulteriori dettagli, consulta la sezione *File close and save scenarios* nella guida Using Adobe Experience Manager Guides as a Cloud Service (Utilizzo di).

**Argomento padre:**[ Personalizza editor Web](conf-web-editor.md)
