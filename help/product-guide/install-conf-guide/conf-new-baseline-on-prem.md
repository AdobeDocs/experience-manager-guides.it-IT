---
title: Configura nuova linea di base per on-premise
description: Scopri come abilitare o disabilitare New Baseline for On-Premise
feature: Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 4abf673f636ffd20d087c99b5112d8504929a6ee
workflow-type: tm+mt
source-wordcount: '124'
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
>Dopo aver abilitato questa funzione, è necessario eseguire la migrazione delle baseline esistenti alla nuova baseline. Per istruzioni dettagliate e un video dettagliato, visualizzare [Nuova baseline in Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

