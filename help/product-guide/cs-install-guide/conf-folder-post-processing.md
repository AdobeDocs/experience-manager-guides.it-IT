---
title: Configura nomi file
description: Scopri come disabilitare la postelaborazione per una cartella caricata in Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: fedd04f4a261ec199f86cb38ecd57e76b9393ae5
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---


# Disattiva la postelaborazione per una cartella

Per impostazione predefinita, tutte le risorse caricate vengono elaborate utilizzando il flusso di lavoro Risorsa di aggiornamento DAM. Experience Manager Guide esegue un’elaborazione aggiuntiva, denominata postelaborazione, come parte di questo flusso di lavoro. Questo aiuta anche a generare gli UUID

Durante il caricamento di file e cartelle in *Adobe Experience Manager Assets* server, puoi anche disabilitare la post-elaborazione e la generazione di UUID.


Utilizzare le istruzioni in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per disabilitare la post-elaborazione in un determinato percorso o ignorare la post-elaborazione per una cartella:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (multivalore, stringhe con percorso omesso `/` alla fine) <br> **Valore predefinito**: `/content/dam/projects/translation_output` |


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (multivalore, stringhe con percorso omesso `/` alla fine) <br> **Valore predefinito**: `/content/dam` |


## Regole per abilitare o disabilitare la post-elaborazione

Per impostazione predefinita, la postelaborazione viene eseguita per ogni percorso di cartella nella cartella DAM di Experience Manager. Le configurazioni vengono applicate a qualsiasi cartella in base alle seguenti regole:

* Se il padre viene ignorato per la postelaborazione ma la cartella figlio è abilitata, il figlio e tutti i suoi successori vengono considerati abilitati.
* Se il padre è abilitato per la postelaborazione ma il figlio viene ignorato, il figlio e tutti i suoi successori vengono considerati ignorati.
* Se lo stesso percorso di cartella esiste nelle configurazioni ignorato.post.processing.paths e abilitato.post.processing.paths, viene considerato ignorato per la post-elaborazione.
