---
title: Native PDF | Processo di configurazione del nodo per la pubblicazione nativa di PDF
description: Scopri come configurare il processo del nodo per la pubblicazione nativa di PDF
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 1%

---

# Configura processo nodo per pubblicazione PDF nativa

La pubblicazione PDF nativa avvia un processo NodeJs separato per convertire i file generati nel processo di pubblicazione in un PDF finale. Per supportare scenari diversi, potrebbe essere necessario modificare le configurazioni del processo Node che esegue la pubblicazione di PDF nativi. Ad esempio, per eseguire carichi di lavoro più grandi, è necessario aumentare la dimensione heap massima disponibile per il processo NodeJs generato.

Utilizzare le istruzioni fornite in [Sostituzioni configurazione](../cs-install-guide/download-install-additional-config-override.md) per creare il file di configurazione.Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

| PID | Chiave proprietà | Valore proprietà |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valore stringa per impostare qualsiasi standard `NODE_OPTIONS`.<BR> Valore predefinito: &quot;&quot; |
