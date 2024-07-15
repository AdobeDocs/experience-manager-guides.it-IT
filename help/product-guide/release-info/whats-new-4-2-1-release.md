---
title: Note sulla versione | Novità di Adobe Experience Manager Guides versione 4.2.1
description: Scopri le funzioni nuove e migliorate di Adobe Experience Manager Guides versione 4.2.1
exl-id: 441aa7ec-d88c-42cb-83f0-d0f6e58bfa41
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Novità della versione 4.2.1 di Adobe Experience Manager Guides (maggio 2023)

Questo articolo descrive le funzioni nuove e migliorate della versione 4.2.1 di Adobe Experience Manager Guides (in seguito denominato *AEM Guides*).

Per ulteriori dettagli sulle istruzioni di aggiornamento, sulla matrice di compatibilità e sui problemi risolti in questa versione, consulta l&#39;articolo [Note sulla versione](release-notes-4-2-1.md).

## Passare dall&#39;Editor Web alla home page AEM

Ora è possibile passare facilmente dall’Editor Web alla pagina di navigazione AEM.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Fai clic sull&#39;icona **Guide** (![](assets/aem-guides-icon.png) ) per tornare alla pagina di navigazione AEM.


Per ulteriori dettagli, vedere [Pagina di navigazione AEM](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Supporto avanzato dei metadati nella pubblicazione PDF

AEM Guides ora fornisce supporto avanzato per i metadati mappati sui metadati nell’output PDF. Le opzioni relative ai metadati includono informazioni sul documento e sul relativo contenuto, ad esempio il nome dell&#39;autore, il titolo del documento, le parole chiave, le informazioni sul copyright e altri campi dati.

<img src="assets/pdf-metadata.png" alt=" metadati pdf nativi">

Puoi importare un file XMP e AEM Guides può scegliere le informazioni dal file. Puoi anche fornire i nomi e i valori dei metadati utilizzando il menu a discesa. Puoi anche aggiungere metadati personalizzati digitando direttamente nel campo del nome.

Per ulteriori dettagli, vedere la descrizione della funzionalità **Metadati** in [Creare un predefinito di output PDF](../web-editor/native-pdf-web-editor.md).

### Pannello Visualizzazione Struttura migliorata

AEM Guides fornisce un pannello Visualizzazione struttura migliorato in cui è possibile ottenere la visualizzazione gerarchica degli elementi utilizzati nel documento.

<img src="assets/select-element-content-outline-view_cs.png" alt=" metadati pdf nativi">

La vista Struttura offre i seguenti miglioramenti:

* Il menu a discesa Opzioni vista (View Options) viene visualizzato sopra il pannello Visualizzazione struttura (Outline View). Se un elemento ha un ID, un attributo e un testo, puoi selezionarli dal menu a discesa per visualizzarli insieme all’elemento. Gli attributi che possono essere visualizzati nel pannello Visualizzazione struttura sono determinati dalle impostazioni Attributi di visualizzazione configurate dall&#39;amministratore nelle **Impostazioni editor**.

* Utilizzando la funzione di ricerca, puoi cercare un elemento in base al suo nome, ID, testo o valore dell’attributo.

Per ulteriori dettagli, vedere la descrizione della funzionalità Visualizzazione struttura nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Generare il rapporto Multimedia dall’editor web

AEM Guides fornisce la funzione di generare i rapporti per i documenti tecnici.  È possibile utilizzare questa funzione per visualizzare l&#39;elenco degli argomenti e gestire i metadati dei documenti. Ora puoi anche visualizzare gli elementi multimediali utilizzati in tutti i riferimenti per la mappa corrente dalla scheda **Rapporti** nell&#39;Editor Web.

È possibile generare il report multimediale che contiene informazioni dettagliate sul file multimediale utilizzato nei riferimenti all&#39;interno della mappa corrente. È possibile filtrare e ordinare i file multimediali elencati nel report.
È inoltre possibile generare il file CSV per scaricare l&#39;istantanea corrente dei file multimediali utilizzati nella mappa DITA.

<img src="assets/web-editor-reports-multimedia.png" alt="report multimediale" width="600">

Per ulteriori dettagli, vedere la descrizione della funzionalità Generate a multimedia report nella sezione [DITA map report from the Web Editor](../user-guide/reports-web-editor.md).

## Native PDF | Barra delle modifiche per indicare gli argomenti modificati nel sommario

AEM Guides ora consente di identificare rapidamente gli argomenti modificati nel sommario dell’output PDF.  Viene visualizzata una barra di modifica a sinistra degli argomenti modificati nel sommario. Puoi fare clic sull’argomento nel sommario e visualizzare le modifiche dettagliate.

<img src="assets/change-marker-toc.png" alt="Modifica marcatore nel sommario " width="500">

Per ulteriori dettagli, vedere [Utilizzare gli stili delle barre di modifica personalizzate](../native-pdf/change-bar-style.md).



## Native PDF | Personalizzare lo stile del marcatore pagina nel componente Nota a piè di pagina

Ora è possibile applicare uno stile al marcatore di pagina nelle note a piè di pagina. Ad esempio, è possibile aggiungere parentesi quadre o modificarne il colore. Questi stili consentono agli utenti di identificare facilmente gli indicatori di pagina nel documento.

Per ulteriori dettagli, vedere [Utilizzare stili personalizzati nelle note a piè di pagina](../native-pdf/footnote-number-style.md).

## Aprire e riprodurre file video o audio nell&#39;editor Web

AEM Guides ora offre la funzione di aprire e riprodurre i file audio o video nell’editor web. È possibile modificare il volume o la visualizzazione del video. Nel menu di scelta rapida sono inoltre disponibili le opzioni per **Scarica**, modifica **Velocità riproduzione** o visualizza **Immagine nell&#39;immagine**.

<img src="assets/video-web-editor.png" alt="riproduci video" width="600">

Per ulteriori dettagli, vedere la descrizione della funzionalità Visualizzazione archivio nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).
