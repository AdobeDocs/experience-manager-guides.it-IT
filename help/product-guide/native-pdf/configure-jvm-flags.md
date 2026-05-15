---
title: PDF nativo | Configurare i flag JVM per la pubblicazione nativa di PDF
description: Configurare i flag JVM per la pubblicazione nativa di PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
TQID: https://experienceleague.adobe.com/UvDTutOu-rfQ7tNTMZ6f1dNYJ90dwSGCtTJvWWFm638
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 128
ht-degree: 1%

---

# Configurare i flag JVM per la pubblicazione nativa di PDF per on-premise

La pubblicazione nativa di PDF avvia un processo JVM separato per generare un PDF. Potrebbe essere necessario modificare le configurazioni di questa JVM per supportare scenari diversi. Ad esempio, per eseguire carichi di lavoro più grandi, è necessario aumentare la dimensione heap massima disponibile per il processo JVM generato.

Per configurare i flag JVM per la pubblicazione nativa di AEM Guides PDF, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.fmdita.config.ConfigManager*.

1. Aggiorna la proprietà **Java Command Line options for native pdf** (*native.pdf.java.opts*) per passare eventuali flag JVM standard.



1. Fai clic su **Salva**.
