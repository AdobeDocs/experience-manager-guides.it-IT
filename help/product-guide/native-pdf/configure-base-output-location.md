---
title: Configurare la posizione di output di base per l'output di pubblicazione per i servizi locali
description: Configurare la posizione di output di base per l'output di pubblicazione per i servizi locali
feature: Output Generation
role: Admin
level: Experienced
exl-id: ae1d805a-7b79-4b76-8be2-a19c5552530c
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%

---

# Configura posizione output di base per l&#39;output di pubblicazione per i servizi locali

Per configurare la posizione di output di base, effettuare le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle *com.adobe.fmdita.config.ConfigManager*.

1. Aggiorna la proprietà **Posizione output di base** per specificare il percorso predefinito nell&#39;archivio AEM in cui verrà salvato PDF dopo la pubblicazione. Inoltre, se viene immesso un percorso non valido, verrà automaticamente ripristinato il percorso predefinito: /content/dam/fmdita-outputs.

1. Fai clic su **Salva**.
