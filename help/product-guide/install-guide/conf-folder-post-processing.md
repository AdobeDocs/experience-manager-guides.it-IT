---
title: Configura nomi file
description: Scopri come disabilitare la postelaborazione per una cartella caricata in Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 532e7c562a233619a8c4b7cbdbaef44bc73eb4b2
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---


# Disattiva la postelaborazione per una cartella

Per impostazione predefinita, tutte le risorse caricate vengono elaborate utilizzando il flusso di lavoro Risorsa di aggiornamento DAM. Experience Manager Guide esegue un’elaborazione aggiuntiva, denominata postelaborazione, come parte di questo flusso di lavoro. Questo aiuta anche a generare gli UUID

Durante il caricamento di file e cartelle in *Adobe Experience Manager Assets* server, puoi anche disabilitare la post-elaborazione e la generazione di UUID.


Per disabilitare la postelaborazione in un determinato percorso o ignorare la postelaborazione di una cartella, effettua le seguenti operazioni:


1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su **com.adobe.fmdita.config.ConfigManager** pacchetto.

1. Seleziona la **Percorsi ignorati per la post-elaborazione** per ignorare una cartella per la post-elaborazione.

   Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (multivalore, stringhe con percorso omesso `/` alla fine)

   **Valore predefinito**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Questa proprietà è disabilitata per impostazione predefinita e la scheda di traduzione è disponibile nel dashboard delle mappe.

1. Seleziona la **Percorsi abilitati per la post-elaborazione** per abilitare un percorso per la post-elaborazione.

   Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (multivalore, stringhe con percorso omesso `/` alla fine)

   **Valore predefinito**: `/content/dam/`

   >[!NOTE]
   >
   > Questa proprietà è disabilitata per impostazione predefinita e la scheda di traduzione è disponibile nel dashboard delle mappe.


1. Fai clic su **Salva**.



## Regole per abilitare o disabilitare la post-elaborazione

Per impostazione predefinita, la postelaborazione viene eseguita per ogni percorso di cartella nella cartella DAM di Experience Manager. Le configurazioni vengono applicate a qualsiasi cartella in base alle seguenti regole:

* Se il padre viene ignorato per la postelaborazione ma la cartella figlio è abilitata, il figlio e tutti i suoi successori vengono considerati abilitati.
* Se il padre è abilitato per la postelaborazione ma il figlio viene ignorato, il figlio e tutti i suoi successori vengono considerati ignorati.
* Se lo stesso percorso di cartella esiste nelle configurazioni ignorato.post.processing.paths e abilitato.post.processing.paths, viene considerato ignorato per la post-elaborazione.
