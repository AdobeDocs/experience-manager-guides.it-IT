---
title: Configurare la posizione di output di base per l'output di pubblicazione per i servizi locali
description: Configurare la posizione di output di base per l'output di pubblicazione per i servizi locali
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: ab6f1f09de2ef758d7f05ba0a49194ac9f387dea
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


