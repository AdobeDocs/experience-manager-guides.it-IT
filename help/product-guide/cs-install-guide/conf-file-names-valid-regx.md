---
title: Configura Regx per caratteri validi per i nomi di file
description: Scopri come configurare Regx per caratteri validi per i nomi di file
exl-id: 05e9ca3c-28ff-4f82-8061-3d20307890ff
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Configura Regx per caratteri validi per i nomi di file {#id214BD0550E8}

A partire dalla versione 3.8 delle guide AEM, in qualità di amministratore, puoi definire un elenco di caratteri speciali validi consentiti nei nomi dei file. Nelle versioni precedenti, gli utenti potevano definire nomi di file contenenti caratteri speciali come `@`, `$`, `>`, e altro ancora. Questi caratteri speciali causavano problemi durante l’apertura degli argomenti dal dashboard delle mappe DITA o durante la selezione del collegamento dell’argomento nel sommario, che spesso impediva l’apertura della pagina a causa di caratteri speciali nell’URL.

Utilizzando la configurazione che consente di definire un regx per caratteri validi per i nomi di file, puoi avere il controllo completo sul modo in cui i file vengono denominati internamente nel sistema. È possibile definire un elenco di caratteri speciali consentiti nei nomi dei file. Per impostazione predefinita, la configurazione del nome file valido contiene &quot;`a-z A-Z 0-9 - _`&quot;. Durante la creazione di un nuovo file, puoi usare qualsiasi carattere speciale nel titolo del file, ma internamente verrà sostituito con &quot;`-`&quot; nel nome del file. Ad esempio, puoi assegnare al file il titolo &quot;Introduzione 1&quot; o &quot;Introduction@1&quot;; il nome file corrispondente generato in entrambi i casi sarà &quot;Introduzione-1&quot;.

Quando definisci un elenco di caratteri validi, ricorda che questi caratteri &quot;`*/:[\]|#%{}?&<>"/+`&quot; sarà sempre sostituito da &quot;`-`&quot;.

Se non configuri l’elenco dei caratteri speciali validi, il processo di creazione del file potrebbe fornire risultati imprevisti. Per evitare tali errori, si consiglia vivamente di apportare questa modifica alla configurazione.

Utilizzare le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per configurare regex per caratteri validi per i nomi di file:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | Il valore è un pattern regex. Deve contenere tre caratteri di base e l’elenco deve iniziare con un trattino \(-\).<br> **Valore predefinito**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> Analogamente all&#39;elenco dei caratteri validi per i nomi di file, è inoltre possibile specificare un elenco di caratteri validi per i nomi di file per l&#39;output del sito AEM. Per ulteriori dettagli, consulta [Configurare nomi di file validi per l&#39;output del sito AEM](conf-file-names-valid-regx-aem-site-output.md#).

**Argomento padre:**[ Configura nomi file](conf-file-names.md)
