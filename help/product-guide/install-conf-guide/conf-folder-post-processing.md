---
title: Configura nomi file
description: Scopri come disabilitare la postelaborazione per una cartella caricata in Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Disattiva la postelaborazione per una cartella

Per impostazione predefinita, tutte le risorse caricate vengono elaborate utilizzando il flusso di lavoro Risorsa di aggiornamento DAM. Nell’ambito di questo flusso di lavoro, Experience Manager Guides esegue un’ulteriore elaborazione, denominata postelaborazione. Questo aiuta anche a generare gli UUID

Durante il caricamento dei file e delle cartelle nel server *Adobe Experience Manager Assets*, puoi anche disabilitare la postelaborazione e la generazione di UUID.

Le schede seguenti forniscono istruzioni per disabilitare la postelaborazione per una cartella basata sulla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per disabilitare la post-elaborazione in un determinato percorso o ignorare la post-elaborazione per una cartella:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine) <br> **Valore predefinito**: `/content/dam/projects/translation_output` |
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine) <br> **Valore predefinito**: `/content/dam` |

>[!TAB On-Premise]

Per disabilitare la postelaborazione in un determinato percorso o ignorare la postelaborazione di una cartella, effettua le seguenti operazioni:


1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Selezionare l&#39;opzione **Percorsi ignorati per post-elaborazione** per ignorare una cartella per la post-elaborazione.

   Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine)

   **Valore predefinito**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Questa proprietà è disabilitata per impostazione predefinita e la scheda di traduzione è disponibile nel dashboard delle mappe.

1. Selezionare l&#39;opzione **Percorsi abilitati per post-elaborazione** per abilitare un percorso per la post-elaborazione.

   Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine)

   **Valore predefinito**: `/content/dam/`

   >[!NOTE]
   >
   > Questa proprietà è disabilitata per impostazione predefinita e la scheda di traduzione è disponibile nel dashboard delle mappe.


1. Fai clic su **Salva**.

>[!ENDTABS]

## Regole per abilitare o disabilitare la post-elaborazione

Per impostazione predefinita, la postelaborazione viene eseguita per ogni percorso di cartella nella cartella DAM di Experience Manager. Le configurazioni vengono applicate a qualsiasi cartella in base alle seguenti regole:

* Se il padre viene ignorato per la postelaborazione ma la cartella figlio è abilitata, il figlio e tutti i suoi successori vengono considerati abilitati.
* Se il padre è abilitato per la postelaborazione ma il figlio viene ignorato, il figlio e tutti i suoi successori vengono considerati ignorati.
* Se lo stesso percorso di cartella esiste nelle configurazioni ignorato.post.processing.paths e abilitato.post.processing.paths, viene considerato ignorato per la post-elaborazione.

