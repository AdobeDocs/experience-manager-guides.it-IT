---
title: Configura nomi file
description: Scopri come disabilitare la postelaborazione per una cartella caricata in Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---

# Disattiva la postelaborazione per una cartella

Per impostazione predefinita, tutte le risorse caricate vengono elaborate utilizzando il flusso di lavoro Risorsa di aggiornamento DAM. Nell’ambito di questo flusso di lavoro, Experience Manager Guides esegue un’ulteriore elaborazione, denominata postelaborazione. Questo aiuta anche a generare gli UUID

Durante il caricamento dei file e delle cartelle nel server *Adobe Experience Manager Assets*, puoi anche disabilitare la postelaborazione e la generazione di UUID.


Utilizza le istruzioni in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per disabilitare la post-elaborazione in un determinato percorso o ignorare la post-elaborazione per una cartella:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine) <br> **Valore predefinito**: `/content/dam/projects/translation_output` |


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine) <br> **Valore predefinito**: `/content/dam` |


## Regole per abilitare o disabilitare la post-elaborazione

Per impostazione predefinita, la postelaborazione viene eseguita per ogni percorso di cartella nella cartella DAM di Experience Manager. Le configurazioni vengono applicate a qualsiasi cartella in base alle seguenti regole:

* Se il padre viene ignorato per la postelaborazione ma la cartella figlio è abilitata, il figlio e tutti i suoi successori vengono considerati abilitati.
* Se il padre è abilitato per la postelaborazione ma il figlio viene ignorato, il figlio e tutti i suoi successori vengono considerati ignorati.
* Se lo stesso percorso di cartella esiste nelle configurazioni ignorato.post.processing.paths e abilitato.post.processing.paths, viene considerato ignorato per la post-elaborazione.
