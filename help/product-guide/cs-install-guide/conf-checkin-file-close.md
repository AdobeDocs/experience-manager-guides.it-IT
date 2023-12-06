---
title: Configurare la richiesta di archiviazione di un file alla chiusura
description: Scopri come configurare la richiesta di archiviazione di un file alla chiusura
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Configurare la richiesta di archiviazione di un file alla chiusura {#id222HC040PE8}

Quando l&#39;utente tenta di chiudere un file aperto nell&#39;editor Web utilizzando **Chiudi** nella scheda del file o nella **Chiudi** nel menu Opzioni, viene visualizzata una finestra di dialogo se il file contiene dati non salvati o una versione non salvata. All&#39;utente viene richiesto di sbloccare il file se è bloccato.

Utilizzare le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per configurare un prompt per archiviare un file alla chiusura:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booleano \( true/ false\).<br> **Valore predefinito**: false |

Quando questa configurazione è abilitata, il **Sblocca il file** è selezionata per impostazione predefinita nella finestra di dialogo.

Per ulteriori dettagli, consulta *Scenari di chiusura e salvataggio dei file* nella guida Utilizzo delle guide di Adobe Experience Manager as a Cloud Service.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
