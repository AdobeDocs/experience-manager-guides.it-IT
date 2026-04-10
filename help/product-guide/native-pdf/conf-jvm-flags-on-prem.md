---
title: PDF nativo | Configura i flag JVM per la pubblicazione PDF nativa
description: Configurare i flag JVM per la pubblicazione nativa di PDF
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '127'
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
