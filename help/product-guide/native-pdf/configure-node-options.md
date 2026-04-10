---
title: PDF nativo | Processo di configurazione nodo per pubblicazione PDF nativa
description: Scopri come configurare il processo del nodo per la pubblicazione nativa di PDF
feature: Output Generation
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 1%

---

# Configurare il processo del nodo per la pubblicazione nativa di PDF per Cloud Service

La pubblicazione nativa di PDF avvia un processo NodeJs separato per convertire i file generati nel processo di pubblicazione in un PDF finale. Per supportare scenari diversi, potrebbe essere necessario modificare le configurazioni del processo Nodo che esegue la pubblicazione nativa di PDF. Ad esempio, per eseguire carichi di lavoro più grandi, è necessario aumentare la dimensione heap massima disponibile per il processo NodeJs generato.

Utilizzare le istruzioni fornite in [Sostituzioni configurazione](../install-conf-guide/download-install-config-override.md) per creare il file di configurazione.Nel file di configurazione, specificare i dettagli (proprietà) seguenti:

| PID | Chiave proprietà | Valore proprietà |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valore stringa per impostare qualsiasi `NODE_OPTIONS` standard.<BR> Valore predefinito: &quot;&quot; |
