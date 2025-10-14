---
title: Suggerimenti avanzati basati sull’intelligenza artificiale per l’authoring dei contenuti
description: Scopri come visualizzare e utilizzare i suggerimenti avanzati basati sull’intelligenza artificiale nell’editor web.
exl-id: 23c5285e-0d4f-484a-a062-fe1ba1608b8d
source-git-commit: dd6fae108ddca23d36615fe38d176723bc4cfe86
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 0%

---

# Suggerimenti avanzati basati sull’intelligenza artificiale per l’authoring dei contenuti

Adobe Experience Manager Guides fornisce suggerimenti avanzati per creare contenuti coerenti e precisi.

Durante l&#39;authoring dei contenuti, la funzione **Suggerisci contenuto riutilizzabile** nello strumento Assistente IA può eseguire ricerche utilizzando l&#39;intelligenza artificiale e mostrare il contenuto esistente che è semanticamente simile al contenuto. Puoi quindi scegliere come riferimento il contenuto corrispondente che desideri includere nell’argomento corrente.

Questo consente di riutilizzare il contenuto esistente dall’archivio della documentazione e creare contenuti coerenti. Si sta ad esempio creando un documento contenente informazioni su **Adobe Firefly**, incluso un paragrafo su **Adobe**. In tal caso, puoi visualizzare e aggiungere rapidamente il riferimento al contenuto da un altro argomento, come **Adobe Photoshop**, che include lo stesso paragrafo.
>[!NOTE]
>
> Nei [profili globali o a livello di cartella](../cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions), l&#39;amministratore deve definire i file o le cartelle da indicizzare per i suggerimenti avanzati, il numero minimo di caratteri da immettere per visualizzare i suggerimenti e il numero massimo di suggerimenti visualizzabili nell&#39;elenco.

Per visualizzare i suggerimenti avanzati per l’aggiunta di riferimenti di contenuto appropriati all’argomento, effettua le seguenti operazioni:


1. Seleziona il contenuto dell’argomento per visualizzare i suggerimenti correlati. Assicurati che la lunghezza del carattere del contenuto superi quella impostata dall’amministratore nel profilo della cartella per visualizzare i suggerimenti di contenuto.
1. Dal **pannello Authoring** nell&#39;Assistente di intelligenza artificiale, seleziona **Suggerisci contenuto riutilizzabile** ![ai icona di contenuto riutilizzabile &#x200B;](./images/ai-suggest-reusable-content-icon.svg).

1. Seleziona un tag per visualizzare i suggerimenti di authoring per il tag corrente.  I suggerimenti per visualizzare e aggiungere riferimenti al contenuto dai file indicizzati vengono visualizzati in base al contenuto nel tag corrente. È inoltre possibile selezionare più tag.


1. Selezionare tutti i tag per visualizzare i suggerimenti in base al contenuto presente nel documento completo.  Accanto al contenuto in cui è stata trovata una corrispondenza appropriata viene visualizzata l&#39;icona ![&#128279;](./images/ai-suggest-reusable-content-icon.svg) di **Suggerisci contenuto riutilizzabile** ai suggerisci contenuto riutilizzabile.



   >[!NOTE]
   >
   > Puoi visualizzare solo i suggerimenti per il riquadro di visualizzazione corrente (il contenuto visibile sullo schermo). Per visualizzare i suggerimenti per qualsiasi altro contenuto del documento, scorrere verso l&#39;alto o verso il basso per visualizzarlo nel riquadro di visualizzazione, quindi selezionare **Suggerisci contenuto riutilizzabile** ![ai icona Suggerisci contenuto riutilizzabile &#x200B;](./images/ai-suggest-reusable-content-icon.svg).


1. Puoi visualizzare i suggerimenti avanzati nel pannello dei suggerimenti.  Experience Manager Guides fornisce contenuti di suggerimento contestualmente simili o con lo stesso significato. Ad esempio, puoi cercare l’argomento che contiene il numero di versione esatto, come &quot;versione 2023.03.12 di&quot;. Puoi anche cercare &quot;Adobe ha la sede centrale a San Jose, California&quot; e trovare contenuti simili come &quot;San Jose ha la sede di molte aziende di software come Adobe&quot;.
1. Seleziona **Informazioni contenuto** ![Informazioni contenuto](images/smart-suggestions-content-info-icon.svg) per visualizzare i dettagli.

   ![Pannello informazioni contenuto](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Visualizza informazioni dettagliate sul riferimento contenuto.*

   1. Il titolo dell&#39;argomento che contiene il riferimento al contenuto viene visualizzato come collegamento ipertestuale.
   1. Percorso del file che contiene il riferimento al contenuto.
   1. Il tipo di riferimento in cui viene fatto riferimento al contenuto.
   1. I nomi dei file DITA in cui viene fatto riferimento all&#39;argomento vengono visualizzati come collegamenti ipertestuali.
1. Seleziona **Anteprima** ![icona anteprima](./images/expand-icon.svg) per confrontare il contenuto corrente con quello suggerito. Questo consente di confrontare le differenze e determinare se aggiungere il riferimento al contenuto per il contenuto suggerito e renderlo coerente o mantenere il contenuto corrente.

   ![Suggerisci anteprima contenuto riutilizzabile](images/ai-assistant-suggest-reusable-content.png)

   *Anteprima del confronto tra il contenuto corrente e il contenuto suggerito.*

1. Seleziona **Accetta** per aggiungere il riferimento al contenuto suggerito nell&#39;anteprima **Suggerisci contenuto riutilizzabile**.
1. Puoi anche selezionare **Accetta** o **Ignora** nel pannello dei suggerimenti per i consigli appropriati.


Questa funzione intelligente è utile e riduce al minimo lo sforzo della ricerca manuale dei contenuti, consentendoti di concentrarsi di più sulla generazione di nuovi contenuti. Inoltre, facilita una migliore collaborazione in team e aiuta a mantenere la coerenza nei contenuti creati da vari autori.

>[!NOTE]
>
>I suggerimenti avanzati non mantengono i dati oltre la sessione corrente. Per le risposte, i suggerimenti avanzati si basano esclusivamente sull’indice creato sul contenuto presente nel database interno. Gli strumenti di intelligenza artificiale esterni non vengono utilizzati per garantire che i dati rimangano all’interno del sistema.
