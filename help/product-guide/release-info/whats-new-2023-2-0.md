---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di febbraio 2023
description: Versione di febbraio di Adobe Experience Manager Guides as a Cloud Service
exl-id: 090eaf94-fe3a-47e9-9937-f84f8434550d
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 0%

---

# Novità della versione di febbraio 2023 di Adobe Experience Manager Guides as a Cloud Service

Questo articolo descrive le funzioni nuove e migliorate nella versione di febbraio 2023 di Adobe Experience Manager Guides (in seguito denominato *AEM Guides as a Cloud Service*).

Per ulteriori dettagli sulle istruzioni di aggiornamento, sulla matrice di compatibilità e sui problemi risolti in questa versione, consulta l&#39;articolo [Note sulla versione](release-notes-2023-2-0.md).


## Generare rapporti dall’editor web

AEM Guides dispone di una funzione nell’editor web che consente di verificare la completezza complessiva dei documenti tecnici e di generare per essi rapporti.
È possibile visualizzare l&#39;elenco degli argomenti, gestire i metadati e visualizzare gli elementi multimediali utilizzati in tutti i riferimenti per la mappa corrente dalla
Scheda **Rapporti** nell&#39;editor Web.

**Generare la visualizzazione Elenco argomenti**

È possibile generare l&#39;Elenco argomenti che fornisce informazioni dettagliate sugli argomenti, ad esempio il tipo di riferimento, lo stato del documento e l&#39;autore. È inoltre possibile generare il file CSV per scaricare lo snapshot corrente degli argomenti nella mappa DITA.

**Gestione dei metadati e modifica dello stato del documento**

È possibile applicare tag a un singolo argomento oppure utilizzare la funzione di assegnazione tag in blocco per applicare più tag a più argomenti, a una mappa DITA o a una mappa secondaria. È inoltre possibile modificare lo stato del documento di tutti gli argomenti selezionati al successivo possibile stato comune del documento.

<img src="assets/web-editor-metadata-panel.png" alt="gestire i metadati" width="600">

**Genera il report multimediale**

È possibile generare il report multimediale che contiene informazioni dettagliate sul file multimediale utilizzato nei riferimenti all&#39;interno della mappa corrente. È possibile filtrare e ordinare i file multimediali elencati nel report.
È inoltre possibile generare il file CSV per scaricare l&#39;istantanea corrente dei file multimediali utilizzati nella mappa DITA.

<img src="assets/web-editor-reports-multimedia.png" alt="report multimediale" width="600">

## UX rinnovata per la funzionalità di revisione

Ora le guide AEM forniscono un’interfaccia utente migliorata che consente di rivedere gli argomenti condivisi per la revisione. Nell’esperienza più recente, la funzionalità di revisione presenta i seguenti miglioramenti:

* Interfaccia utente aggiornata
* Pannello Condizioni che consente di evidenziare il contenuto in base alle condizioni disponibili nell’argomento
* Ogni commento nel pannello dei commenti è collegato al testo corrispondente nell&#39;argomento corrente. Consente di identificare il testo commentato.
* I commenti vengono visualizzati nell&#39;ordine del testo commentato nel documento.
* Il nome dell&#39;attività di revisione viene visualizzato nel flusso di lavoro di revisione.
* Selezionare la rootmap per l&#39;attività di revisione utilizzata per risolvere tutti i riferimenti chiave e i termini del glossario utilizzati nel contenuto della revisione.
* Barra degli strumenti contestuale che consente di evidenziare o barrare rapidamente il testo
* Menu Opzioni per modificare o eliminare i commenti
* Per i commenti obsoleti, è possibile accedere alla visualizzazione affiancata che consente di confrontare la versione precedente dell&#39;argomento con la versione di revisione corrente.
* Quando si utilizzano i filtri, i commenti nel pannello di destra vengono filtrati in base alla selezione e al
il numero di commenti nel pannello a sinistra viene aggiornato di conseguenza.


  <img alt="attività di revisione" src="assets/comment-pop-up-panel.png" width="600">



## Miglioramenti alla traduzione

Sono ora disponibili miglioramenti più semplici nel dashboard di traduzione che consentono di tradurre facilmente i documenti dall’editor web.

**Passa l&#39;etichetta della versione alla versione di destinazione**

AEM Guides consente di passare l’etichetta del file di origine al file di destinazione. Questo consente di identificare facilmente la versione sorgente del file tradotto.

<img alt="etichette di traduzione" src="assets/translation-pass-source-label.png" width="600">

Ad esempio, se disponi di alcuni file sorgente a cui è applicata l’etichetta di versione Release 1.0, puoi anche trasmettere l’etichetta di origine (Release 1.0) al file tradotto.

**Forza sincronizzazione per risorse non sincronizzate**

Se apporti modifiche ad alcune delle risorse, AEM Guides le contrassegna come non sincronizzate. Puoi tradurre nuovamente le risorse modificate o scegliere di ignorare lo stato Non sincronizzato. Ad esempio, se hai apportato alcune modifiche minori che non richiedono alcuna traduzione, puoi contrassegnarle come In sincronia.

<img src="assets/translation-version-diff.png" alt="bacheca di traduzione" width="600">

**Visualizza progetti di traduzione in corso per un argomento o una mappa**

Alcuni dei riferimenti nel dashboard di traduzione potrebbero essere in corso. Ora AEM Guides fornisce una funzione per aiutarti a visualizzare l’elenco di tutti i progetti di traduzione in corso (insieme alla lingua di destinazione) che contengono il riferimento selezionato.


## Genera output in vari formati dall’editor web

Ora è possibile generare facilmente l&#39;output per gli argomenti o la mappa DITA dall&#39;Editor Web. Puoi configurare vari predefiniti di output come AEM Site, PDF, HTML5,
JSON (un formato di output headless) e output personalizzato. Puoi quindi utilizzarli per generare i rispettivi output.

È possibile definire gli attributi negli argomenti DITA e quindi utilizzare il predefinito di condizione per applicare una condizione durante la pubblicazione dell&#39;output. È inoltre possibile utilizzare la funzione di pubblicazione della linea di base per pubblicare selettivamente una versione specifica della mappa o dell&#39;argomento DITA.


## Trova e sostituisci il testo a livello di mappa

AEM Guides consente di cercare all’interno di una mappa i file che contengono testo specifico. Il testo cercato viene evidenziato nei file. Ora è anche possibile sostituire la parola o la frase cercata con un&#39;altra parola o frase all&#39;interno di tutti i file. Puoi selezionare l&#39;icona **Sostituisci tutto** a destra nella parte superiore dell&#39;elenco per sostituire tutte le occorrenze del termine cercato in tutti i file.

<img src="assets/map-find-replace.png" alt="mappa trova sostituisci" width="600">

## Eliminare e duplicare i file dal pannello dell’archivio

Ora puoi creare facilmente un duplicato o una copia di un file dal menu **Opzioni** del file selezionato nel pannello dell&#39;archivio. Per impostazione predefinita, il file viene creato con
un suffisso (ad esempio `filename_1.extension`).

<img src="assets/options-menu-repo-view-file-level.png" alt="menu opzioni file " width="500">


## Altri miglioramenti dell’editor web

* In AEM Guides è possibile eseguire alcune operazioni comuni per immagini e file multimediali utilizzando il menu di scelta rapida. Ora puoi anche individuare l’immagine o il supporto selezionato nell’archivio o visualizzare l’anteprima del file nell’interfaccia utente di Assets.

* Il nome del profilo cartella corrente viene visualizzato come etichetta per l&#39;icona Preferenze utente nella barra degli strumenti principale. Questo ti aiuta a identificare il profilo di cartella su cui stai lavorando.

* Quando apri una mappa nella vista mappa, il titolo della mappa corrente viene visualizzato al centro della barra degli strumenti principale. Questa funzione è utile per comunicare agli utenti quale mappa è attualmente aperta.


## Titolo da visualizzare al posto di UUID nell’editor di ossigeno

Ora AEM Guides ti consente di scegliere l&#39;opzione **Usa titolo nell&#39;editor e Gestione mappe** nelle impostazioni. Se si seleziona questa opzione, il titolo del file viene visualizzato nella scheda del file quando viene aperto nell&#39;Editor o in Gestione mappe DITA. Se non selezioni questa opzione, nella scheda del file viene visualizzato l’UUID del file.

## Pubblicazione basata su microservizi per AEM Guides as a Cloud Service

Il nuovo microservizio di pubblicazione consente di eseguire carichi di lavoro di pubblicazione di grandi dimensioni simultaneamente su AEM Guides as a Cloud Service e di sfruttare la piattaforma senza server Adobe I/O Runtime leader del settore.

Per ogni richiesta di pubblicazione, AEM Guides as a Cloud Service esegue un contenitore separato che viene ridimensionato orizzontalmente in base alle richieste dell’utente. In questo modo è possibile eseguire più richieste di pubblicazione e ottenere prestazioni migliori.

Per ulteriori dettagli, consulta [Configurare la nuova pubblicazione basata su microservizi per AEM Guides as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

## Native PDF | Aggiungere un segnalibro personalizzato nell’output di PDF

Ora puoi aggiungere un segnalibro personalizzato a un particolare contenuto nell’output PDF finale per facilitarne la navigazione. Questa opzione viene aggiunta al sommario creato dai titoli di argomento o di sezione nella mappa DITA.

## Native PDF | Applicare uno stile personalizzato alle voci del sommario e al contenuto dell’argomento

AEM Guides fornisce la funzione di applicare uno stile personalizzato alle voci del sommario o a un particolare argomento nell’output PDF. È ad esempio possibile modificare il colore del testo nel sommario e nel titolo dell&#39;argomento. È inoltre possibile applicare stili all&#39;intero contenuto dell&#39;argomento.


## Native PDF | Personalizzare lo stile del marcatore pagina nel componente Nota a piè di pagina

Ora è possibile applicare uno stile al marcatore di pagina nelle note a piè di pagina. Ad esempio, è possibile aggiungere parentesi quadre o modificarne il colore. Questi stili consentono agli utenti di identificare facilmente gli indicatori di pagina nel documento.

## Native PDF | Barra delle modifiche per indicare gli argomenti modificati nel sommario

AEM Guides ora consente di identificare rapidamente gli argomenti modificati nel sommario dell’output PDF.  Viene visualizzata una barra di modifica a sinistra degli argomenti modificati nel sommario. Puoi fare clic sull’argomento nel sommario e visualizzare le modifiche dettagliate.

<img src="assets/change-marker-toc.png" alt="Modifica marcatore nel sommario " width="500">
