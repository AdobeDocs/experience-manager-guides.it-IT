---
title: PDF nativo | Configura processo nodo per pubblicazione PDF nativa
description: Scopri come configurare il processo del nodo per la pubblicazione nativa di PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 1%

---

# Configurare il processo del nodo per la pubblicazione nativa di PDF per Cloud Service

La pubblicazione nativa di PDF avvia un processo NodeJs separato per convertire i file generati nel processo di pubblicazione in un PDF finale. Per supportare scenari diversi, potrebbe essere necessario modificare le configurazioni del processo Nodo che esegue la pubblicazione nativa di PDF. Ad esempio, per eseguire carichi di lavoro più grandi, è necessario aumentare la dimensione heap massima disponibile per il processo NodeJs generato.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](../install-conf-guide/download-install-config-override.md) per creare il file di configurazione.Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

| PID | Chiave proprietà | Valore proprietà |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valore stringa per impostare qualsiasi `NODE_OPTIONS`.<BR> standard Valore predefinito: &quot;&quot; |
