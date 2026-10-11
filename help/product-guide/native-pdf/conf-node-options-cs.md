---
title: PDF nativo | Configura processo nodo per pubblicazione PDF nativa
description: Scopri come configurare il processo del nodo per la pubblicazione nativa di PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: 5321c785-8259-4ee2-9ada-ee70fb99b4fd
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
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
