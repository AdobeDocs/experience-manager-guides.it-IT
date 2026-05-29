---
title: Configura nuovo editor
description: Scopri come abilitare o disabilitare il nuovo editor
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Configura nuovo editor per on-premise

>[!IMPORTANT]
>
> Distribuisci le configurazioni di sistema tramite il codice anziché applicarle manualmente nell’ambiente di runtime.

I passaggi seguenti spiegano come abilitare il nuovo editor nell’ambiente locale.

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle **com.adobe.fmdita.config.ConfigManager**.

1. Abilita l&#39;impostazione **Abilita editor 2.0** (`enable.markup.editor`).

1. Seleziona **Salva**.

