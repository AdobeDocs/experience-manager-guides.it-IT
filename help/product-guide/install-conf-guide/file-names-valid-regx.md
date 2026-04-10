---
title: Configura Regx per caratteri validi per i nomi di file
description: Scopri come configurare Regx per caratteri validi per i nomi di file
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 0%

---

# Configura Regx per caratteri validi per i nomi di file {#id214BD0550E8}

A partire da AEM Guides versione 3.8, in qualità di amministratore, puoi definire un elenco di caratteri speciali validi consentiti nei nomi dei file. Nelle versioni precedenti, gli utenti potevano definire nomi di file contenenti caratteri speciali come `@`, `$`, `>` e altri. Questi caratteri speciali causavano problemi durante l’apertura degli argomenti dal dashboard delle mappe DITA o durante la selezione del collegamento dell’argomento nel sommario, che spesso impediva l’apertura della pagina a causa di caratteri speciali nell’URL.

Utilizzando la configurazione che consente di definire un regx per caratteri validi per i nomi di file, puoi avere il controllo completo sul modo in cui i file vengono denominati internamente nel sistema. È possibile definire un elenco di caratteri speciali consentiti nei nomi dei file. Per impostazione predefinita, la configurazione del nome file valido contiene &quot;`a-z A-Z 0-9 - _`&quot;. Durante la creazione di un nuovo file, è possibile inserire qualsiasi carattere speciale nel titolo, ma internamente verrà sostituito con &quot;`-`&quot; nel nome del file. Ad esempio, puoi assegnare al file il titolo &quot;Introduzione 1&quot; o &quot;Introduction@1&quot;; il nome file corrispondente generato in entrambi i casi sarà &quot;Introduzione-1&quot;.

Quando definisci un elenco di caratteri validi, ricorda che questi caratteri &quot;`*/:[\]|#%{}?&<>"/+`&quot; verranno sempre sostituiti con &quot;`-`&quot;.

Se non configuri l’elenco dei caratteri speciali validi, il processo di creazione del file potrebbe fornire risultati imprevisti. Per evitare tali errori, si consiglia vivamente di apportare questa modifica alla configurazione.

Le seguenti schede forniscono istruzioni per configurare Regx per caratteri di nome file validi in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per configurare regex per caratteri validi per i nomi di file:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | Il valore è un pattern regex. Deve contenere tre caratteri di base e l&#39;elenco deve iniziare con un trattino \(-\).<br> **Valore predefinito**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> Analogamente all&#39;elenco dei caratteri validi per i nomi di file, è possibile specificare anche un elenco di caratteri validi per i nomi di file per l&#39;output del sito AEM. Per ulteriori dettagli, vedere [Configurare nomi di file validi per l&#39;output del sito AEM](conf-file-names-valid-regx-aem-site-output.md#).

>[!TAB On-Premise]

Per configurare regx per caratteri \(o allowed\) validi nei nomi dei file, effettuare le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle *com.adobe.fmdita.config.ConfigManager*.

1. Nella proprietà **Regex per caratteri validi**, verificare che la proprietà sia impostata su \[-a-zA-Z0-9\_\]. È possibile aggiungere altri caratteri all&#39;elenco, tuttavia, deve contenere questi caratteri di base e l&#39;elenco deve iniziare con un trattino &quot;-&quot;.

   >[!NOTE]
   >
   > Questa proprietà si applica solo ai nomi di file e non ai nomi di cartelle.

1. Fai clic su **Salva**.


>[!NOTE]
>
> Analogamente all&#39;elenco dei caratteri validi per i nomi di file, è possibile specificare anche un elenco di caratteri validi per i nomi di file per l&#39;output del sito AEM. Per ulteriori dettagli, vedere [Configurare nomi di file validi per l&#39;output del sito AEM](conf-file-names-valid-regx-aem-site-output.md#).

>[!ENDTABS]
