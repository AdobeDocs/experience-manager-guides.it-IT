---
title: Suggerimenti avanzati basati sull’intelligenza artificiale per l’authoring dei contenuti
description: Scopri come visualizzare e utilizzare i suggerimenti avanzati basati sull’intelligenza artificiale nell’editor web.
exl-id: 23c5285e-0d4f-484a-a062-fe1ba1608b8d
source-git-commit: 75425d82ee55485503ea6678030c5e919e50a691
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 0%

---

# Suggerimenti avanzati basati sull’intelligenza artificiale per l’authoring dei contenuti

Experience Manager Guides fornisce la funzionalità **Suggerimenti avanzati** che consente di creare contenuti coerenti e precisi.

Durante la creazione di contenuti, la funzionalità **Suggerimenti avanzati** può eseguire ricerche utilizzando l&#39;intelligenza artificiale e mostrare il contenuto esistente semanticamente simile al contenuto. Puoi quindi scegliere come riferimento il contenuto corrispondente che desideri includere nell’argomento corrente.

Questo consente di riutilizzare il contenuto esistente dall’archivio della documentazione e creare contenuti coerenti. Stai creando un documento contenente informazioni su **Adobe Firefly**, incluso un paragrafo su **Adobe**. In tal caso, puoi visualizzare e aggiungere rapidamente il riferimento al contenuto da un altro argomento, come **Adobe Photoshop**, che include lo stesso paragrafo.





Quando apri un argomento nell&#39;editor Web, il pannello **Suggerimenti avanzati** viene visualizzato a destra.

>[!NOTE]
>
> L&#39;amministratore deve configurare la funzionalità **Suggerimenti avanzati**. Per ulteriori dettagli, vedi la sezione [Configurare i suggerimenti avanzati basati sull&#39;intelligenza artificiale per l&#39;authoring](../cs-install-guide/conf-smart-suggestions.md) nella Guida all&#39;installazione e alla configurazione per i Cloud Service.

![Pannello suggerimenti avanzati](images/smart-suggestions-panel.png){width="300" align="left"}

*Visualizza il pannello **Suggerimenti avanzati**.*

Per visualizzare i suggerimenti avanzati per l’aggiunta di riferimenti di contenuto appropriati all’argomento, effettua le seguenti operazioni:

1. Seleziona **Suggerimenti avanzati** ![icona suggerimenti avanzati](images/smart-suggestions-icon.svg) per aprire il pannello.



   >[!NOTE]
   >
   > Nei [profili globali o a livello di cartella](../cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions), l&#39;amministratore deve definire i file o le cartelle da indicizzare per i suggerimenti avanzati, il numero minimo di caratteri da immettere per visualizzare i suggerimenti e il numero massimo di suggerimenti visualizzabili nell&#39;elenco.

1. Inserisci il contenuto dell’argomento per visualizzare i suggerimenti correlati. Assicurati che la lunghezza del carattere del contenuto superi quella impostata dall’amministratore nel profilo della cartella per visualizzare i suggerimenti di contenuto.

1. Seleziona **Suggerimenti per il tag corrente** ![icona tag corrente di suggerimenti avanzati](images/smart-suggestions-current-tag-icon.svg) per visualizzare i suggerimenti di creazione per il tag corrente in cui si posiziona il puntatore del mouse.  I suggerimenti per visualizzare e aggiungere riferimenti al contenuto dai file indicizzati vengono visualizzati in base al contenuto nel tag corrente.

   Scelta rapida da tastiera: **Windows** (*Ctrl* + *K*), **macOS** (*Comando* + *K*)
1. Selezionare **Suggerimenti per il documento completo** ![icona del documento completato con suggerimenti avanzati](images/smart-suggestions-complete-document-icon.svg) per visualizzare i suggerimenti in base al contenuto presente nel documento completo.  Accanto al contenuto in cui è stata trovata una corrispondenza appropriata viene visualizzata l&#39;icona dei suggerimenti avanzati ![suggerimenti avanzati](images/smart-suggestions-complete-document-icon.svg).

   Scelta rapida da tastiera: **Windows** ( *Ctrl* + *Shift* + *K* ), **macOS** (*Command* + *Shift* + *K* )

   >[!NOTE]
   >
   > Puoi visualizzare solo i suggerimenti per il riquadro di visualizzazione corrente (il contenuto visibile sullo schermo). Per visualizzare i suggerimenti per qualsiasi altro contenuto del documento, scorrere verso l&#39;alto o verso il basso per visualizzarli nel riquadro di visualizzazione, quindi selezionare l&#39;icona ![suggerimenti avanzati](images/smart-suggestions-complete-document-icon.svg).

1. Per visualizzare i suggerimenti avanzati, seleziona l&#39;icona **Suggerimenti avanzati** ![icona suggerimenti avanzati](images/smart-suggestions-complete-document-icon.svg) accanto ai tag aggiunti al documento.
1. Puoi visualizzare i suggerimenti avanzati nella casella **Riutilizza contenuto** suggerimenti.  Experience Manager Guides fornisce suggerimenti per abbinare esattamente contenuti e contenuti con lo stesso significato. Ad esempio, puoi cercare l’argomento che contiene il numero di versione esatto, come &quot;versione 2023.03.12 di&quot;. Puoi anche cercare &quot;L&#39;Adobe ha sede a San Jose, California&quot; e trovare contenuti simili come &quot;San Jose ha la sede di molte aziende di software come Adobe&quot;.
1. Seleziona **Informazioni contenuto** ![Informazioni contenuto](images/smart-suggestions-content-info-icon.svg) per visualizzare i dettagli.
   ![Pannello informazioni contenuto](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Visualizza informazioni dettagliate sul riferimento contenuto.*

   1. Il titolo dell&#39;argomento che contiene il riferimento al contenuto viene visualizzato come collegamento ipertestuale.
   1. Percorso del file che contiene il riferimento al contenuto.
   1. Il tipo di riferimento in cui viene fatto riferimento al contenuto.
   1. I nomi dei file DITA in cui viene fatto riferimento all&#39;argomento vengono visualizzati come collegamenti ipertestuali.
1. Seleziona **Anteprima contenuto suggerito** ![icona di anteprima suggerimenti avanzati](images/smart-suggestions-preview-icon.svg) per confrontare il contenuto corrente con il contenuto suggerito. Questo consente di confrontare le differenze e determinare se aggiungere il riferimento al contenuto per il contenuto suggerito e renderlo coerente o mantenere il contenuto corrente.

   ![Anteprima contenuto suggerita](images/smart-suggestions-suggested-content-preview.png){width="800" align="left"}

   *Anteprima del confronto tra il contenuto corrente e il contenuto suggerito.*

1. Fai clic su **Accetta** per aggiungere il riferimento al contenuto suggerito nella finestra di dialogo **Anteprima contenuto suggerito**.
1. Puoi anche selezionare **Accetta** o **Rifiuta** nella casella dei suggerimenti **Riutilizza contenuto** per i consigli appropriati.


Questa funzione intelligente è utile e riduce al minimo lo sforzo della ricerca manuale dei contenuti, consentendoti di concentrarsi di più sulla generazione di nuovi contenuti. Inoltre, facilita una migliore collaborazione in team e aiuta a mantenere la coerenza nei contenuti creati da vari autori.

>[!NOTE]
>
>I suggerimenti avanzati non mantengono i dati oltre la sessione corrente. Per le risposte, i suggerimenti avanzati si basano esclusivamente sull’indice creato sul contenuto presente nel database interno. Gli strumenti di intelligenza artificiale esterni non vengono utilizzati per garantire che i dati rimangano all’interno del sistema.
