---
title: Configura Regx per caratteri validi per i nomi di file
description: Scopri come configurare Regx per caratteri validi per i nomi di file
exl-id: 876dfc77-078f-4341-b99d-02a453d2e065
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---

# Configura Regx per caratteri validi per i nomi di file {#id214BD0550E8}

A partire dalla versione 3.8 delle guide AEM, in qualità di amministratore, puoi definire un elenco di caratteri speciali validi consentiti nei nomi dei file. Nelle versioni precedenti, gli utenti potevano definire nomi di file contenenti caratteri speciali come `@`, `$`, `>`, e altro ancora. Questi caratteri speciali causavano problemi durante l’apertura degli argomenti da DITA Map Dashboard o quando si faceva clic sul collegamento dell’argomento nel sommario, che spesso impediva l’apertura della pagina a causa di caratteri speciali nell’URL.

Utilizzando la configurazione che consente di definire un regx per caratteri validi per i nomi di file, puoi avere il controllo completo sul modo in cui i file vengono denominati internamente nel sistema. È possibile definire un elenco di caratteri speciali consentiti nei nomi dei file. Per impostazione predefinita, la configurazione del nome file valido contiene &quot;`a-z A-Z 0-9 - _`&quot;. Durante la creazione di un nuovo file, puoi usare qualsiasi carattere speciale nel titolo del file, ma internamente verrà sostituito con &quot;`-`&quot; nel nome del file. Ad esempio, puoi assegnare al file il titolo &quot;Introduzione 1&quot; o &quot;Introduction@1&quot;; il nome file corrispondente generato in entrambi i casi sarà &quot;Introduzione-1&quot;.

Quando definisci un elenco di caratteri validi, ricorda che questi caratteri &quot;`*/:[\]|#%{}?&<>"/+`&quot; sarà sempre sostituito da &quot;`-`&quot;.

Se non configuri l’elenco dei caratteri speciali validi, il processo di creazione del file potrebbe fornire risultati imprevisti. Per evitare tali errori, si consiglia vivamente di apportare questa modifica alla configurazione immediatamente dopo l’aggiornamento della build alla versione 3.8.

Per configurare regx per caratteri \(o allowed\) validi nei nomi dei file, effettuare le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su *com.adobe.fmdita.config.ConfigManager* pacchetto.

1. In **Regex per caratteri validi** , assicurarsi che la proprietà sia impostata su \[-a-zA-Z0-9\_\]. È possibile aggiungere altri caratteri all&#39;elenco, tuttavia, deve contenere questi caratteri di base e l&#39;elenco deve iniziare con un trattino &quot;-&quot;.

   >[!NOTE]
   >
   > Questa proprietà si applica solo ai nomi di file e non ai nomi di cartelle.

1. Fai clic su **Salva**.


>[!NOTE]
>
> Analogamente all&#39;elenco dei caratteri validi per i nomi di file, è inoltre possibile specificare un elenco di caratteri validi per i nomi di file per l&#39;output del sito AEM. Per ulteriori dettagli, consulta [Configurare nomi di file validi per l&#39;output del sito AEM](conf-file-names-valid-regx-aem-site-output.md#).

**Argomento padre:**[ Configura nomi file](conf-file-names.md)
