---
title: PDF nativo | Configura processo nodo per pubblicazione PDF nativa
description: Scopri come configurare il processo del nodo per la pubblicazione nativa di PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
TQID: https://experienceleague.adobe.com/7i-6SjvI5FuSNsWPy9sX96UsXld9fJjAjHNKDKzo824
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 122
ht-degree: 1%

---

# Configurare il processo del nodo per la pubblicazione nativa di PDF per Cloud Service

La pubblicazione nativa di PDF avvia un processo NodeJs separato per convertire i file generati nel processo di pubblicazione in un PDF finale. Per supportare scenari diversi, potrebbe essere necessario modificare le configurazioni del processo Nodo che esegue la pubblicazione nativa di PDF. Ad esempio, per eseguire carichi di lavoro più grandi, è necessario aumentare la dimensione heap massima disponibile per il processo NodeJs generato.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](../install-conf-guide/download-install-config-override.md) per creare il file di configurazione.Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

| PID | Chiave proprietà | Valore proprietà |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valore stringa per impostare qualsiasi `NODE_OPTIONS`.<BR> standard Valore predefinito: &quot;&quot; |
