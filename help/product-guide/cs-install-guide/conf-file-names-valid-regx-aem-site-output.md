---
title: Configurare nomi di file validi per l'output del sito AEM
description: Scopri come configurare nomi di file validi per l’output del sito AEM
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 1%

---

# Configurare nomi di file validi per l&#39;output del sito AEM {#id214GK0X0KXA}

Analogamente all&#39;elenco di caratteri validi per i nomi di file consentiti per gli argomenti DITA, è inoltre possibile configurare un elenco di caratteri validi per i nomi di file per l&#39;output del sito AEM. Alcuni dei caratteri noti non consentiti in un URL sono: ``'<>`@$``. Questi caratteri sono configurati per la conversione automatica in un carattere di sottolineatura &quot;`_`&quot; quando vengono trovati durante la generazione dei nomi dei file di output del sito AEM.

Utilizzare le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per impostare caratteri validi nell’output del sito AEM:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Aggiungi i caratteri da sostituire con un trattino basso nei nomi dei file di output del sito AEM. <br> **Valore predefinito**: ``'<\>\`@$`` |

**Argomento padre:**[ Configura nomi file](conf-file-names.md)
