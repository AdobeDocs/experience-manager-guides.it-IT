---
title: Configura nuova linea di base per on-premise
description: Scopri come abilitare o disabilitare New Baseline for On-Premise
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---

# Configura nuova linea di base per on-premise

>[!IMPORTANT]
>
> Distribuisci le configurazioni di sistema tramite il codice anziché applicarle manualmente nell’ambiente di runtime.

I passaggi seguenti spiegano come abilitare la nuova linea di base nell’ambiente locale.

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e seleziona il bundle **com.adobe.fmdita.config.ConfigManager**.

1. Abilita l&#39;impostazione **Abilita baseline più veloce (v2)**. È inoltre possibile eseguire ricerche con il nome di impostazione esatto `enable.baseline.v2`.

1. Seleziona **Salva**.

>[!NOTE]
>
>Dopo aver abilitato questa funzione, è necessario eseguire la migrazione delle baseline esistenti alla nuova baseline. Per istruzioni dettagliate e un video dettagliato, visualizzare [Nuova linea di base (Beta) in Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

