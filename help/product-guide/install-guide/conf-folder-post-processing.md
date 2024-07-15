---
title: Configura nomi file
description: Scopri come disabilitare la postelaborazione per una cartella caricata in Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: ff6e1322-9655-42aa-b353-199c70c9de49
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Disattiva la postelaborazione per una cartella

Per impostazione predefinita, tutte le risorse caricate vengono elaborate utilizzando il flusso di lavoro Risorsa di aggiornamento DAM. Nell’ambito di questo flusso di lavoro, Experience Manager Guides esegue un’ulteriore elaborazione, denominata postelaborazione. Questo aiuta anche a generare gli UUID

Durante il caricamento dei file e delle cartelle nel server *Adobe Experience Manager Assets*, puoi anche disabilitare la postelaborazione e la generazione di UUID.


Per disabilitare la postelaborazione in un determinato percorso o ignorare la postelaborazione di una cartella, effettua le seguenti operazioni:


1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Selezionare l&#39;opzione **Percorsi ignorati per elaborazione Post** per ignorare una cartella per la post-elaborazione.

   Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine)

   **Valore predefinito**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Questa proprietà è disabilitata per impostazione predefinita e la scheda di traduzione è disponibile nel dashboard delle mappe.

1. Selezionare l&#39;opzione **Percorsi abilitati per elaborazione Post** per abilitare un percorso per la post-elaborazione.

   Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine)

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
