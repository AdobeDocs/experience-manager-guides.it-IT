---
title: Configurare nomi di file validi per l’output del sito AEM
description: Scopri come configurare nomi di file validi per l’output del sito AEM
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: b2bc5159-2144-4683-970d-738949ac9662
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# Configurare nomi di file validi per l’output del sito AEM {#id214GK0X0KXA}

Analogamente all&#39;elenco di caratteri validi per i nomi di file consentiti per gli argomenti DITA, è inoltre possibile configurare un elenco di caratteri validi per i nomi di file per l&#39;output del sito AEM. Alcuni dei caratteri noti non consentiti in un URL sono: ``'<>`@$``. Questi caratteri sono configurati per la conversione automatica in un carattere di sottolineatura &quot;`_`&quot; quando vengono trovati durante la generazione dei nomi dei file di output del sito AEM.

Le schede seguenti forniscono istruzioni per configurare nomi di file validi per l’output del sito AEM in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per impostare caratteri validi nell’output del sito AEM:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Aggiungi i caratteri da sostituire con un trattino basso nei nomi dei file di output del sito AEM. <br> **Valore predefinito**: ``'<\>\`@$`` |

>[!TAB On-Premise]

La configurazione che consente di impostare caratteri validi nell&#39;output del sito AEM è presente nel bundle `com.adobe.fmdita.common.SanitizeNodeNameImpl`. **Impostare il set di caratteri non consentiti per la pubblicazione in AEM Sites** in modo da includere i caratteri che si desidera sostituire con un carattere di sottolineatura nei nomi dei file di output del sito AEM.

>[!ENDTABS]
