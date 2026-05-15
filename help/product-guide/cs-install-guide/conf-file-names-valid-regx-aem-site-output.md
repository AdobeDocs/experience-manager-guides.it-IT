---
title: Configurare nomi di file validi per l’output del sito AEM
description: Scopri come configurare nomi di file validi per l’output del sito AEM
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/hhc9Q8A-Eq3e8PAHHDXf1jXf8qVb-p4sU3Cum53ra9M
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 145
ht-degree: 1%

---

# Configurare nomi di file validi per l’output del sito AEM {#id214GK0X0KXA}

Analogamente all&#39;elenco di caratteri validi per i nomi di file consentiti per gli argomenti DITA, è inoltre possibile configurare un elenco di caratteri validi per i nomi di file per l&#39;output del sito AEM. Alcuni dei caratteri noti non consentiti in un URL sono: ``'<>`@$``. Questi caratteri sono configurati per la conversione automatica in un carattere di sottolineatura &quot;`_`&quot; quando vengono trovati durante la generazione dei nomi dei file di output del sito AEM.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per impostare caratteri validi nell’output del sito AEM:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Aggiungi i caratteri da sostituire con un trattino basso nei nomi dei file di output del sito AEM. <br> **Valore predefinito**: ``'<\>\`@$`` |

**Argomento padre:**[ Configura nomi file](conf-file-names.md)
