---
title: Configurare l’inizializzazione della copia di destinazione nel flusso di lavoro di traduzione per On-Premise
description: Scopri come abilitare o disabilitare l’inizializzazione della copia di destinazione nel flusso di lavoro di traduzione per On-Premise
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 1%

---

# Configurare l’inizializzazione della copia di destinazione nel flusso di lavoro di traduzione per On-Premise

I passaggi seguenti spiegano come abilitare l’inizializzazione della copia di destinazione nel flusso di lavoro di traduzione per l’ambiente locale.

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle **com.adobe.fmdita.config.ConfigManager**.

1. Abilita o disabilita l&#39;impostazione **Inizializza la copia per lingua di destinazione con il contenuto di origine** ( translation.workflow.propagate.source.content) in base alle tue esigenze. Questa impostazione è applicabile solo quando il flusso di lavoro di traduzione legacy è disabilitato.

1. Seleziona **Salva**.
