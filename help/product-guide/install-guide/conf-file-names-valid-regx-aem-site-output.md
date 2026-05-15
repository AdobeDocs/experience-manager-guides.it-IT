---
title: Configurare nomi di file validi per l’output del sito AEM
description: Scopri come configurare nomi di file validi per l’output del sito AEM
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/vGe4--XJ9VL5q74J7hVFCmD0vrBRnUkBAdZDCFcUxeU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 0%

---

# Configurare nomi di file validi per l’output del sito AEM {#id214GK0X0KXA}

Analogamente all&#39;elenco di caratteri validi per i nomi di file consentiti per gli argomenti DITA, è inoltre possibile configurare un elenco di caratteri validi per i nomi di file per l&#39;output del sito AEM. Alcuni dei caratteri noti non consentiti in un URL sono: ```'<>`@$```. Questi caratteri sono configurati per la conversione automatica in un carattere di sottolineatura &quot;_&quot; quando vengono trovati durante la generazione dei nomi dei file di output del sito AEM. La configurazione che consente di impostare caratteri validi nell&#39;output del sito AEM è presente nel bundle `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Impostare il set di caratteri non consentiti per la pubblicazione in AEM Sites** in modo da includere i caratteri che si desidera sostituire con un carattere di sottolineatura nei nomi dei file di output del sito AEM.

**Argomento padre:**&#x200B;[&#x200B; Configura nomi file](conf-file-names.md)
