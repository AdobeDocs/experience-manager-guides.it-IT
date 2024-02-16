---
title: Note sulla versione | Novità della versione 4.2 delle Guide di Adobe Experience Manager
description: Scopri le funzioni nuove e migliorate delle versioni 4.2 delle Guide di Adobe Experience Manager
exl-id: 46367ccf-58ff-4889-8314-cdd5bf5d0f1d
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '2423'
ht-degree: 0%

---

# Novità della versione 4.2 delle guide di Adobe Experience Manager (febbraio 2023)

Questo articolo descrive le funzioni nuove e migliorate della versione 4.2 delle Guide di Adobe Experience Manager (in seguito denominate *Guide AEM*).

Per ulteriori dettagli sulle istruzioni di aggiornamento, sulla matrice di compatibilità e sui problemi risolti in questa versione, vedi [Note sulla versione](release-notes-4-2.md) articolo.

## Generare rapporti dall’editor web

Le guide AEM sono dotate di una funzione nell’editor web che consente di verificare la completezza complessiva dei documenti tecnici e di generare report per essi.
È possibile visualizzare l&#39;elenco degli argomenti e gestire i metadati di tutti i riferimenti per la mappa corrente da
**Rapporti** nell&#39;editor Web.

**Genera la vista Elenco argomenti**

È possibile generare l&#39;Elenco argomenti che fornisce informazioni dettagliate sugli argomenti, ad esempio il tipo di riferimento, lo stato del documento e l&#39;autore. È inoltre possibile generare il file CSV per scaricare lo snapshot corrente degli argomenti nella mappa DITA.

**Gestione dei metadati e modifica dello stato del documento**

È possibile applicare tag a un singolo argomento oppure utilizzare la funzione di assegnazione tag in blocco per applicare più tag a più argomenti, a una mappa DITA o a una mappa secondaria. È inoltre possibile modificare lo stato del documento di tutti gli argomenti selezionati al successivo possibile stato comune del documento.

<img src="assets/web-editor-metadata-panel.png" alt="gestire i metadati" width="600">

## UX rinnovata per la funzionalità di revisione

Ora le guide AEM forniscono un’interfaccia utente migliorata che consente di rivedere gli argomenti condivisi per la revisione. Nell’esperienza più recente, la funzionalità di revisione presenta i seguenti miglioramenti:

* Interfaccia utente aggiornata
* Pannello Condizioni che consente di evidenziare il contenuto in base alle condizioni disponibili nell’argomento.
* Ogni commento nel pannello dei commenti è collegato al testo corrispondente nell&#39;argomento corrente. Consente di identificare il testo commentato.
* I commenti vengono visualizzati nell&#39;ordine del testo commentato nel documento.
* Il nome dell&#39;attività di revisione viene visualizzato nel flusso di lavoro di revisione.
* Selezionare la rootmap per l&#39;attività di revisione utilizzata per risolvere tutti i riferimenti chiave e i termini del glossario utilizzati nel contenuto della revisione.
* Barra degli strumenti contestuale che consente di evidenziare o barrare rapidamente il testo.
* Menu Opzioni per modificare o eliminare i commenti.
* Per i commenti obsoleti, è possibile accedere alla visualizzazione affiancata che consente di confrontare la versione precedente dell&#39;argomento con la versione di revisione corrente
* Quando si utilizzano i filtri, i commenti nel pannello di destra vengono filtrati in base alla selezione e il numero di commenti nel pannello di sinistra viene aggiornato di conseguenza.


<img alt="attività di revisione" src="assets/comment-pop-up-panel.png" width="600">


Per ulteriori informazioni, consulta *Rivedi argomenti o mappe* nella guida Utilizzo delle guide di Adobe Experience Manager.

## Miglioramenti alla traduzione

Sono ora disponibili miglioramenti più semplici nel dashboard di traduzione che consentono di tradurre facilmente i documenti dall’editor web.


**Colonna Etichetta versione aggiunta al dashboard di traduzione**

Nel dashboard di traduzione è inoltre possibile visualizzare la colonna Etichetta versione. Viene visualizzata l&#39;etichetta per la versione selezionata del file di origine. Questo può aiutarti a selezionare tutti i file con un’etichetta specifica e a tradurli in una volta sola.

**Visualizza la differenza di versione per i file non sincronizzati dal dashboard di traduzione**

È ora possibile verificare le differenze tra la versione selezionata e l&#39;ultima versione di origine tradotta degli argomenti. Puoi anche scegliere di tradurre la **Non sincronizzato** file basati sulle modifiche apportate tra le due versioni di un argomento.

<img src="assets/translation-version-diff.png" alt="bacheca di traduzione" width="600">



**Passa l’etichetta della versione alla versione di destinazione**

Le guide AEM consentono di passare l&#39;etichetta del file di origine al file di destinazione. Questo consente di identificare facilmente la versione sorgente del file tradotto.

<img alt="etichette di traduzione" src="assets/translation-pass-source-label.png" width="600">

Ad esempio, se disponi di alcuni file sorgente a cui è applicata l’etichetta di versione Release 1.0, puoi anche trasmettere l’etichetta di origine (Release 1.0) al file tradotto.

**Forza sincronizzazione per risorse non sincronizzate**

Se apporti modifiche ad alcune risorse, le guide AEM le contrassegna come non sincronizzate. Puoi tradurre nuovamente le risorse modificate o scegliere di ignorare lo stato Non sincronizzato. Ad esempio, se hai apportato alcune modifiche minori che non richiedono alcuna traduzione, puoi contrassegnarle come In sincronia.

**Visualizza progetti di traduzione in corso per un argomento o una mappa**

Alcuni dei riferimenti nel dashboard di traduzione potrebbero essere in corso. Ora AEM Guides fornisce una funzione per aiutarti a visualizzare l’elenco di tutti i progetti di traduzione in corso (insieme alla lingua di destinazione) che contengono il riferimento selezionato.

Per ulteriori informazioni, consulta *Traduci documenti dall&#39;editor Web* nella guida Utilizzo delle guide di Adobe Experience Manager.

## Genera output in vari formati dall’editor web

Ora è possibile generare facilmente l&#39;output per gli argomenti o la mappa DITA dall&#39;Editor Web. Puoi configurare vari predefiniti di output come Sito AEM, PDF, HTML5, JSON (un formato di output headless) e output personalizzato. Utilizzale per generare i rispettivi output. È possibile definire gli attributi negli argomenti DITA e quindi utilizzare il predefinito di condizione per applicare una condizione durante la pubblicazione dell&#39;output. È inoltre possibile utilizzare la funzione di pubblicazione della linea di base per pubblicare selettivamente una versione specifica della mappa o dell&#39;argomento DITA.

**Gestire i predefiniti di output per Profilo globale e Cartella**

Le guide AEM consentono di creare e gestire predefiniti di output per i profili globali e cartelle. Puoi quindi utilizzare facilmente questi predefiniti di output per generare l’output per tutte le mappe correlate al profilo globale o cartella.

<img alt="aggiungi predefinito" src="assets/add-global-output-preset.png" width="400">


Questi predefiniti globali vengono visualizzati sotto **Output** di tutte le mappe correlate. Puoi utilizzarli per generare l’output per tutte le mappe correlate. Per generare l&#39;output di PDF, potete selezionare il predefinito come predefinito di default PDF. È inoltre possibile **Modifica**, **Rinomina**, **Duplica**, o **Elimina** un predefinito di output esistente da **Opzioni** menu.

>[!NOTE]
>
>Solo gli utenti amministratori a livello di cartella possono creare predefiniti globali e di profilo cartella.

## Trova e sostituisci il testo a livello di mappa

È ora possibile cercare all&#39;interno di una mappa i file che contengono testo specifico. Il testo cercato viene evidenziato nei file. È inoltre possibile sostituire la parola o la frase cercata con un&#39;altra parola o frase all&#39;interno dei file. Seleziona la **Sostituisci occorrenza singola** per sostituire l&#39;occorrenza corrente e il **Sostituisci tutto nel file** per sostituire tutte le occorrenze nel file selezionato. Puoi selezionare **Sostituisci tutto** per sostituire tutte le occorrenze del termine ricercato in tutti i file.

<img src="assets/map-find-replace.png" alt="mappa trova sostituisci" width="600">


Per impostazione predefinita, le opzioni **Estrai il file prima della sostituzione** e **Crea nuova versione dopo la sostituzione** vengono selezionati, in modo che un file venga estratto prima di sostituire il testo e venga creata una nuova versione dopo la sostituzione del testo. È inoltre possibile eseguire ricerche nella stringa nei riferimenti indiretti all&#39;interno della mappa DITA. Per impostazione predefinita, questa opzione è disabilitata, pertanto la ricerca viene eseguita solo sui riferimenti diretti.

## Vista Layout nell’Editor mappa


Ora è possibile visualizzare il layout completo di una mappa DITA nell&#39;Editor mappe. Quando apri una mappa per la modifica, viene aperta la vista Layout dell’Editor mappa. In questa vista è possibile visualizzare la gerarchia delle mappe in una vista ad albero. È inoltre possibile modificare e organizzare o strutturare gli argomenti in una mappa.

<img src="assets/layout-view-map.png" alt=" vista layout mappa" width="600">

La visualizzazione Layout contiene una barra degli strumenti separata che consente di eseguire molte attività sugli argomenti presenti in una mappa.
È possibile inserire riferimenti ad argomenti, gruppi di argomenti e definizioni chiave in una mappa. È possibile riorganizzare gli argomenti presenti in una mappa spostandoli verso l&#39;alto, verso il basso, a sinistra o a destra. È inoltre possibile trascinare gli argomenti per spostarli in una mappa. L&#39;Editor mappe fornisce anche le icone per bloccare o sbloccare i file, controllare la cronologia delle versioni ed eseguire una gestione delle etichette delle versioni.


La vista Layout fornisce anche **Opzioni di visualizzazione** per visualizzare o nascondere il numero di riga, visualizzare o nascondere una casella di controllo oppure visualizzare il nome o il titolo del file per gli argomenti di una mappa.
Puoi anche visualizzare gli argomenti in base ai filtri condizionali applicati.

Oltre ad organizzare gli argomenti nel file mappa, è possibile aggiungere, spostare, copiare, incollare o eliminare riferimenti utilizzando **Opzioni** disponibile per un elemento nella visualizzazione Layout.

<img src="assets/layout-inline-attributes.png" alt=" attributi di layout mappa" width="600">


Nel pannello di destra vengono visualizzate le Proprietà contenuto e le Proprietà mappa nella vista Layout dell’Editor mappa. Ora è anche possibile impostare le informazioni sui metadati per gli argomenti o la mappa. È possibile definire il Titolo navigazione, il Testo collegamento, la Descrizione breve e le Parole chiave per l&#39;argomento o la mappa selezionata.

Per ulteriori dettagli, consulta *Vista Layout* nella guida Utilizzo delle guide di Adobe Experience Manager.

## Pannello Generazione rapida

Le guide AEM forniscono il pannello Generazione rapida che consente di generare e visualizzare rapidamente l&#39;output dei predefiniti creati per la mappa DITA.

<img src="assets/quick-generate-map-view.png" alt=" pannello di generazione rapida" width="600">

In **Generazione rapida** è possibile visualizzare l&#39;elenco di tutti i predefiniti di output creati per la mappa DITA. Potete anche visualizzare rapidamente l&#39;output generato per i predefiniti. Al termine della generazione dell’output viene visualizzato un messaggio di esito positivo o negativo. Puoi anche visualizzare il registro degli errori che contiene i dettagli dell’errore che si è verificato nel processo di generazione.

## Creare una baseline dinamica basata su etichette

Le guide AEM consentono ora di creare linee di base dinamiche basate su etichette. Se si genera una baseline, si scarica una baseline o si crea un progetto di traduzione utilizzando una baseline, i file vengono selezionati in modo dinamico in base alle etichette aggiornate. Questa funzione è utile in quanto non è necessario modificare la linea di base quando si aggiornano le etichette.

<img src="assets/dynamic-baseline.png" alt=" linea di base dinamica" width="400">

## Eliminare e duplicare i file dal pannello dell’archivio

Ora è possibile eliminare facilmente i file (un singolo file alla volta) dalla **Opzioni** del file selezionato dal pannello del repository. Viene visualizzata una richiesta di conferma prima di eliminare il file. Se non viene fatto riferimento al file da alcun altro file, questo viene eliminato e viene visualizzato un messaggio di operazione riuscita.

<img src="assets/options-menu-repo-view-file-level.png" alt="menu opzioni file " width="500">

È inoltre possibile creare un duplicato o una copia del file selezionato. Per impostazione predefinita, il file viene creato con un suffisso (come filename_1.extension).


## Altri miglioramenti dell’editor web

* Nelle guide AEM è possibile eseguire alcune operazioni comuni per immagini e file multimediali utilizzando il menu di scelta rapida. Ora puoi anche individuare l’immagine o il supporto selezionato nell’archivio o visualizzare l’anteprima del file nell’interfaccia utente di Assets.

* Il nome del profilo cartella corrente viene visualizzato come etichetta per l&#39;icona Preferenze utente nella barra degli strumenti principale. Questo ti aiuta a identificare il profilo di cartella su cui stai lavorando.

* Quando apri una mappa nella vista mappa, il titolo della mappa corrente viene visualizzato al centro della barra degli strumenti principale. Questa funzione è utile per comunicare agli utenti quale mappa è attualmente aperta.

## Rimozione delle versioni selezionate dei file

Durante la creazione e la gestione del contenuto, è possibile che vengano create molte versioni dei file DITA nell&#39;archivio. Le guide AEM consentono di eliminare versioni precedenti dei file DITA dall&#39;archivio e liberare spazio su disco.

<img src="assets/preview-purge-report.png" alt="Anteprima report di eliminazione" width="500">

Le guide AEM non eliminano la prima versione del file o una versione inclusa in una baseline o a cui è applicata un&#39;etichetta. L’operazione di rimozione non elimina nemmeno i file inclusi in un flusso di lavoro di traduzione o revisione. Puoi scegliere il numero di versioni da mantenere e decidere anche di eliminare i file che sono più vecchi del numero di giorni definito.

Prima di avviare l&#39;operazione di rimozione, è possibile visualizzare in anteprima il report per visualizzare le versioni che verranno eliminate. È quindi possibile decidere di avviare o annullare l&#39;operazione di rimozione.

<img src="assets/download-purge-report.png" alt="Rapporto di eliminazione PDownload" width="500">

Una volta completata l&#39;operazione di rimozione, è possibile controllare il report di rimozione per visualizzare i file eliminati.

## Titolo da visualizzare al posto di UUID nell’editor di ossigeno

Ora AEM Guides consente di scegliere **Usa titolo nell’editor e nel gestore delle mappe** nelle impostazioni. Se si seleziona questa opzione, il titolo del file viene visualizzato nella scheda del file quando viene aperto nell&#39;Editor o in Gestione mappe DITA. Se non selezioni questa opzione, nella scheda del file viene visualizzato l’UUID del file.

## Interfaccia utente metadati disponibile per i predefiniti di PDF

È possibile impostare i metadati dal predefinito di output di una mappa DITA. È possibile impostare i metadati Titolo, Autore, Oggetto e Parole chiave. Questi metadati vengono mappati ai metadati nelle Proprietà file del PDF di output. Questi metadati sostituiscono i metadati definiti a livello di libro. Potete definire i metadati in modo specifico in ciascun predefinito di output e trasmetterli al PDF di output.

## Native PDF | PDF con barra delle modifiche che mostra la differenza tra le versioni dei documenti

Ora puoi creare un PDF che mostra le differenze di contenuto tra due versioni utilizzando la barra delle modifiche. È possibile scegliere di confrontare la versione corrente con una baseline della versione precedente o confrontare le due versioni della baseline selezionate.

<img src="assets/pdf-change-version.png" alt="pdf-change-version" width="600">

Nel PDF viene visualizzata una barra delle modifiche che indica il contenuto modificato, inserito o eliminato. Sono inoltre disponibili le seguenti opzioni:
* Mostra il contenuto inserito in verde e sottolineato
* Mostra il contenuto eliminato in rosso e contrassegnato con barrato

## Native PDF | Supporto variabile per percorso di output e nome file PDF

Ora puoi anche utilizzare le seguenti variabili predefinite per definire il percorso di output e il file di PDF. Puoi utilizzare una singola variabile o una combinazione di variabili per definire queste opzioni:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (Solo per il percorso di output)
* `${path_after_langfolder}` (Solo per il percorso di output)

## Native PDF | Genera sommario per mappe DITA e riordina i layout di pagina

È inoltre possibile generare il sommario nelle mappe DITA utilizzando un&#39;impostazione PDF avanzata del modello. Puoi scegliere di abilitare o disabilitare la visualizzazione dei vari layout di pagina e anche riordinarne la posizione.

## Native PDF | Aggiungere un segnalibro personalizzato nell’output di PDF

Ora puoi aggiungere un segnalibro personalizzato a un particolare contenuto nell’output PDF finale per facilitarne la navigazione. Questa opzione viene aggiunta al sommario creato dai titoli di argomento o di sezione nella mappa DITA.

## Native PDF | Applicare uno stile personalizzato alle voci del sommario e al contenuto dell’argomento

Le guide AEM consentono di applicare uno stile personalizzato alle voci del sommario o a un particolare argomento nell’output di PDF. È ad esempio possibile modificare il colore del testo nel sommario e nel titolo dell&#39;argomento. È inoltre possibile applicare stili all&#39;intero contenuto dell&#39;argomento.
