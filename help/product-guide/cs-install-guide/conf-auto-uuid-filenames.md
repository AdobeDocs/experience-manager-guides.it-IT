---
title: Configurare nomi di file automatici basati su UUID
description: Scopri come configurare i nomi di file automatici in base all’UUID
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/HxTJaPGbwH31vitQ-Cu6wPyCuzZSWDXtq6xMY4hXEAI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 1%

---

# Configurare nomi di file automatici basati su UUID {#id205QG070D5Z}

Per impostazione predefinita, quando viene creato un file argomento o mappa, agli autori viene data un&#39;opzione per specificare anche il nome del file. Gli autori possono assegnare i nomi dei file in base alle proprie esigenze. Tuttavia, questo può causare incoerenza e un’ampia gamma di nomi di file può essere vista in un ampio sistema di documentazione. In qualità di amministratore, puoi impedire agli autori di assegnare nomi di file per i file creati nel sistema. Per ogni nuovo argomento o file mappa, puoi scegliere di assegnare automaticamente nomi di file basati su UUID.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare i nomi di file automatici in base all’UUID:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Booleano \(true/false\).<br> **Valore predefinito**: false |

>[!NOTE]
>
> Quando questa opzione è attivata, gli autori non visualizzeranno l&#39;opzione per specificare il nome del file durante la creazione di un nuovo argomento o di un nuovo file di mappa. È possibile creare un nuovo argomento o un nuovo file di mappa dall’interfaccia utente di Assets e dall’editor web.

**Argomento padre:**[ Configura nomi file](conf-file-names.md)
