---
title: Configurare nomi di file automatici basati su UUID
description: Scopri come configurare i nomi di file automatici in base all’UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/2oXpOlXt4gZ3GELX7SmwPJoWJYM71f0cZFy2--M6AYM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 0%

---

# Configurare nomi di file automatici basati su UUID {#id205QG070D5Z}

Per impostazione predefinita, quando viene creato un file argomento o mappa, agli autori viene data un&#39;opzione per specificare anche il nome del file. Gli autori possono assegnare i nomi dei file in base alle proprie esigenze. Tuttavia, questo può causare incoerenza e un’ampia gamma di nomi di file può essere vista in un ampio sistema di documentazione. In qualità di amministratore, puoi impedire agli autori di assegnare nomi di file per i file creati nel sistema. Per ogni nuovo argomento o file mappa, puoi scegliere di assegnare automaticamente nomi di file basati su UUID.

Per assegnare automaticamente il nome di file basato su UUID per tutti i nuovi file creati nel sistema, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle *com.adobe.fmdita.xmleditor.config.XmlEditorConfig*.

1. Selezionare l&#39;opzione **Usa nomi file di sistema basati su UUID**.

1. Fai clic su **Salva**.


>[!NOTE]
>
> Per impostazione predefinita, questa opzione è disattivata. Quando questa opzione è attivata, gli autori non visualizzeranno l&#39;opzione per specificare il nome del file durante la creazione di un nuovo argomento o di un nuovo file di mappa. È possibile creare un nuovo argomento o un nuovo file di mappa dall’interfaccia utente di Assets e dall’editor web.

**Argomento padre:**&#x200B;[&#x200B; Configura nomi file](conf-file-names.md)
