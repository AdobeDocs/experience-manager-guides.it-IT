---
title: Native PDF | Configurare i flag JVM per la pubblicazione nativa di PDF
description: Configurare i flag JVM per la pubblicazione nativa di PDF
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---

# Configurare i flag JVM per la pubblicazione nativa di PDF

La pubblicazione nativa di PDF avvia un processo JVM separato per generare un PDF. Potrebbe essere necessario modificare le configurazioni di questa JVM per supportare scenari diversi. Ad esempio, per eseguire carichi di lavoro più grandi, è necessario aumentare la dimensione heap massima disponibile per il processo JVM generato.

Per configurare i flag JVM di pubblicazione nativa di PDF AEM, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona la *com.adobe.fmdita.config.ConfigManager* pacchetto.

1. Aggiornare la proprietà **Opzioni della riga di comando Java per pdf nativo** (*native.pdf.java.opts*) per superare eventuali flag JVM standard.



1. Fai clic su **Salva**.
