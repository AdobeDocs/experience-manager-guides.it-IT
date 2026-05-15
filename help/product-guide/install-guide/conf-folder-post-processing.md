---
title: Configura nomi file
description: Scopri come disabilitare la postelaborazione per una cartella caricata in Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: ff6e1322-9655-42aa-b353-199c70c9de49
TQID: https://experienceleague.adobe.com/QGFFy-2t4eZYQwe6eGna-m7tOnxnEqmpL7sM5F2R-oo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 398
ht-degree: 0%

---

# Disattiva la postelaborazione per una cartella

Per impostazione predefinita, tutte le risorse caricate vengono elaborate utilizzando il flusso di lavoro Risorsa di aggiornamento DAM. Nell’ambito di questo flusso di lavoro, Experience Manager Guides esegue un’ulteriore elaborazione, denominata postelaborazione. Questo aiuta anche a generare gli UUID di.

Durante il caricamento dei file e delle cartelle nel server *Adobe Experience Manager Assets*, puoi anche disabilitare la postelaborazione e la generazione di UUID.


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

>[!NOTE]
>
> Oltre ai percorsi ignorati e abilitati configurati tramite la configurazione OSGi, il comportamento di post-elaborazione è influenzato anche da un nodo a livello di archivio situato in `/var/dxml/postprocess/ignoredPaths`. <br> Se una cartella viene esclusa in modo imprevisto dalla post-elaborazione e non è elencata nella configurazione OSGi, si consiglia di controllare questo nodo dell’archivio. Se il percorso è impostato su `true`, verrà ignorato. Per riabilitare l’elaborazione, puoi rimuovere manualmente la proprietà corrispondente dal nodo.

## Regole per abilitare o disabilitare la post-elaborazione

Per impostazione predefinita, la postelaborazione viene eseguita per ogni percorso di cartella nella cartella DAM di Experience Manager. Le configurazioni vengono applicate a qualsiasi cartella in base alle seguenti regole:

* Se il padre viene ignorato per la postelaborazione ma la cartella figlio è abilitata, il figlio e tutti i suoi successori vengono considerati abilitati.
* Se il padre è abilitato per la postelaborazione ma il figlio viene ignorato, il figlio e tutti i suoi successori vengono considerati ignorati.
* Se lo stesso percorso di cartella esiste nelle configurazioni ignorato.post.processing.paths e abilitato.post.processing.paths, viene considerato ignorato per la post-elaborazione.
