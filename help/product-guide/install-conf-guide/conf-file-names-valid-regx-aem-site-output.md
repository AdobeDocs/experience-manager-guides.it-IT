---
title: Configurare nomi di file validi per l’output del sito AEM
description: Scopri come configurare nomi di file validi per l’output del sito AEM
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '217'
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
