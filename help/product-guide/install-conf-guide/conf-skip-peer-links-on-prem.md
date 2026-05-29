---
title: Configurare il salto dei collegamenti dei peer per la linea di base V1 in locale
description: Scopri come abilitare o disabilitare il salto dei collegamenti tra pari per la baseline V1 in On-Premise
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%

---

# Configurare il salto dei collegamenti dei peer per la baseline precedente in On-Premise

I passaggi seguenti spiegano come abilitare il salto dei collegamenti tra pari per la vecchia linea di base nell’ambiente locale.

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle **com.adobe.fmdita.config.ConfigManager**.

1. Abilita l&#39;impostazione **Ignora collegamenti peer per la linea di base V1** (guides.baseline.v1.skip.peer.links). Per impostazione predefinita, questa impostazione è disabilitata.

1. Seleziona **Salva**.
