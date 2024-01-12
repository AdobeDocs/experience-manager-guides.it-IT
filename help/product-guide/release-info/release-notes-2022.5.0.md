---
title: Note sulla versione | Guide di Adobe Experience Manager as a Cloud Service, versione di maggio 2022
description: Versione di maggio di Adobe Experience Manager Guides as a Cloud Service
exl-id: 7928a300-5ec9-492c-b9be-02b6f87638c6
feature: Release Notes
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Versione di maggio di Adobe Experience Manager Guides as a Cloud Service

## Aggiornamento alla versione di maggio

Aggiorna le guide Adobe Experience Manager correnti as a Cloud Service (in seguito denominate *Guide AEM as a Cloud Service*) eseguendo i seguenti passaggi:
1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
1. Aggiorna `<dox.version>` proprietà in `/dox/dox.installer/pom.xml` file del codice Git dei tuoi Cloud Service in 2022.5.144.
1. Apporta le modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione as a Cloud Service di maggio delle guide AEM.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di maggio 2022 delle guide dell’AEM as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Non compatibile | Aggiornamento 2020 4 e versioni successive |
| | |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac |
| --- | --- | --- |
| 2022.5.0 | 2.6.9. | 2.6.9. |
|  |  |  |


## Nuove funzioni e miglioramenti

AEM Guides as a Cloud Service fornisce molti miglioramenti e nuove funzioni nella versione di maggio:

### Editor Web avanzato

* **Creare mappe in base a modelli personalizzati**

Ora è disponibile la potente funzione per creare modelli di mappa personalizzati. È possibile utilizzarli per creare mappe DITA insieme ai modelli di argomento e ai modelli di mappa a cui si fa riferimento nel modello di mappa.

![modelli dita](assets/dita-templates.png)

Puoi anche fare riferimento ad altri modelli di mappa e modelli di argomento dal modello di mappa personalizzato. I modelli di mappa indicati possono fare riferimento a vari modelli di mappa, modelli di argomento, argomenti, mappe, immagini, video e altre risorse.

![creare modelli dita](assets/create-dita-template.png)

Il modello di mappa personalizzato può aiutarti a replicare molto facilmente i modelli di mappa e l’intera struttura di cartelle a cui si fa riferimento. Questi modelli personalizzati sono particolarmente utili per creare e ricreare più mappe che hanno strutture e riferimenti ricorsivi.

* Il **Inserisci parola chiave** è stata migliorata. È ora possibile trovare più facilmente una parola chiave da inserire poiché le parole chiave sono elencate in ordine alfabetico. È inoltre possibile cercare le parole chiave digitando una stringa di ricerca nella casella Cerca.

![parola chiave insert](assets/insert-keyword.png)

* Ora nella vista Archivio i file vengono caricati in batch. Vengono caricati 75 file alla volta. Questo caricamento batch è efficiente e consente di accedere ai file più rapidamente rispetto al caricamento di tutti i file esistenti in una cartella.

![carica altri file](assets/load-more-files.png)

* È possibile eseguire il rendering di immagini SVG che includono dati incorporati o collegamenti in tutte le schermate dell&#39;editor XML, incluse le visualizzazioni Anteprima e Autore.

* Il file XSD/DTD predefinito può essere aggiornato alla versione più recente

### Processo di traduzione migliorato

* **Possibilità di creare un progetto di traduzione con ambito**
Se devi creare solo l’ambito per un progetto da tradurre, puoi selezionare **Crea un nuovo progetto di traduzione ambito**. Questo non invierà le copie per la traduzione e lo stato di traduzione originale dei file viene mantenuto.

![progetto di traduzione ambito](assets/scoping-translation-project.png)

* Se si rifiuta la traduzione di uno o più argomenti in un processo di traduzione, lo stato In corso di tutti gli argomenti rifiutati viene ripristinato allo stato originale.

* Il **Lingue** visualizza le cartelle della lingua insieme ai relativi codici di lingua. Ad esempio, francese (fr) e tedesco (de).

* La funzione di traduzione ora supporta anche il codice della lingua, che include sia il paese che la lingua. Ad esempio: `fr-fr`, `en-us`.

![traduzione in lingua](assets/translation-languages.png)

* Quando si carica una mappa DITA all&#39;esterno della cartella della lingua, non viene registrata alcuna eccezione nel backend.

Per ulteriori dettagli sulla traduzione, vedi *Traduci documenti dall&#39;editor Web* in Utilizzo delle guide di Adobe Experience Manager as a Cloud Service.


### Pubblicazione avanzata

* È inoltre possibile accedere al **Pubblica dashboard** dalla scheda Output durante la generazione dell&#39;output dal dashboard delle mappe. Nel dashboard di pubblicazione è disponibile un elenco di tutte le attività di pubblicazione attive.

![uscite in coda](assets/queued-output.png)

* Dal dashboard delle mappe puoi selezionare più file DITAVAL per generare contenuto condizionale. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. Puoi anche passare il cursore sul nome del file per visualizzare il percorso nell’archivio AEM in cui è memorizzato il file.

* **Funzione obsoleta**
AEM as a Cloud Service non supporta più la generazione di formato di output DITA per i documenti di FrameMaker. Questa opzione DITA è stata rimossa anche dai predefiniti di output del dashboard Mappa.

### Miglioramento della pubblicazione basata su articoli

L’editor XML consente di mappare più categorie di prodotti in un articolo durante la pubblicazione in un profilo Salesforce.

### Altre funzioni migliorate

* La modalità Anteprima supporta anche `deliveryTarget` attributo di elaborazione condizionale in DITA. È disponibile come opzione nel filtro a discesa insieme a **pubblico**, **piattaforma**, **prodotto**, prop, **altre proprietà**.
* È stata fornita l&#39;opzione per la sincronizzazione forzata tra il server AEM in ossigeno e il sistema locale.

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

* Nel pannello di revisione dell&#39;editor Web, l&#39;utente non è in grado di rispondere ai commenti di revisione. (9667)
* L’applicazione rimane vuota quando si fa clic su una cartella vuota dopo averla aggiornata tramite il menu Opzioni. (9639)
* Una nuova versione viene creata quando **Salva e chiudi** il file archiviato. (9638)
* Il pulsante Chiudi non viene visualizzato quando **Salva come nuova versione** la casella di controllo è attivata. (9637)
* Il PDF corretto non viene pubblicato se viene prima pubblicato tramite un PDF separato per ciascun capitolo e quindi un singolo file PDF (la casella Crea file PDF separati non è selezionata). (9632)
* La dashboard delle mappe genera un problema di metadati per gli utenti non amministratori. (9620)
* Una volta creata una baseline, lo stato viene impostato su Non riuscito nell’interfaccia utente (la chiamata di recupero dello stato non riesce) se il server contiene più di 10000 file. (9608)
* L’archiviazione di dati di grandi dimensioni nelle proprietà genera un errore di pubblicazione in quanto il flusso di lavoro di pubblicazione diviso non riesce. (9586)
* Attributi condizionali Lo stato dei filtri non viene mantenuto quando si passa da Anteprima a Origine e si torna alla modalità Anteprima. (9553)
* Il nome della mappa di registro viene lasciato vuoto nella vista Archivio se non viene fornito alcun nome tramite `mainbooktitle` tag. (9538)
* Si verifica un errore HTTP 400 durante l’apertura di un file caricato con ossigeno. (9535)
* I predefiniti di una mappa precedentemente aperta rimangono visibili nella scheda Output all&#39;apertura di una mappa senza predefiniti definiti. (9523)
* La funzionalità di ricerca per Tag e attributi non funziona nel pannello Struttura. (9506)
* La raccolta appena creata non è visibile finché il browser non viene aggiornato. (9505)
* Le etichette degli attributi condizionali (non i valori) vengono visualizzate in modalità sorgente quando si aggiungono tutte le condizioni tramite l’opzione &quot;Aggiungi tutte le proprietà&quot;. (9501)
* I file vengono estratti automaticamente al ripristino di qualsiasi versione. (9482)
* Nell’interfaccia utente di Assets, al ripristino della versione di un file vengono visualizzate differenze di marca temporale non corrette. (9480)
* Vengono aggiunti più elementi dai risultati della ricerca durante l&#39;inserimento di elementi nell&#39;elemento topicref della mappa DITA. (9474)
* Se l&#39;impostazione **Crea nuova versione per file caricato** è ON, viene creata una nuova versione al momento del ripristino e del salvataggio su qualsiasi nodo bloccato. (9473)
* La visualizzazione del testo di Riferimento chiave e di Riferimento chiave del contenuto non viene mantenuta quando si modifica l’URL del collegamento, se il testo visualizzato non viene aggiunto durante la definizione del riferimento chiave. (9458)
* In Cronologia versioni, il numero di versione e l&#39;etichetta non vengono visualizzati per la versione corrente. (9446)
* L’editor si blocca quando alcuni file di contenuto vengono aperti nell’editor. (9443)
* La ricerca nel pannello Archivio e nella finestra di dialogo Sfoglia topicref blocca lo schermo quando il contenuto è di grandi dimensioni. (9432)
* I metadati passati all’output del sito AEM non rispettano la linea di base del contenuto. (9416)
* Oxygen verifica una versione errata di un argomento dopo il ripristino di una versione in AEM. (9411)
* La linea di base non riuscita disattiva la modifica nella scheda Predefinito del dashboard delle mappe. (9403)
* L’errore viene sempre registrato durante la creazione di un nuovo contenuto. (9388)
* Le nuove risorse DITA create vengono sempre estratte da un altro utente. 9387
* L&#39;elemento Rename non funziona correttamente durante la conversione di topicref in glossref. 9380
* L’etichetta della versione non viene visualizzata come elenco a discesa in **Salva come nuova versione** . (9379)
* Le condizioni non vengono applicate al passaggio tra versioni diverse da **Mostra differenze** a discesa. (9366)
* Si verificano diversi problemi durante l’utilizzo dei filtri di anteprima. (9365)
* Impossibile inserire risorse non DITA e DITAVAL nel riferimento argomento. 9363
* La traduzione approvata non viene integrata nella lingua di destinazione quando il codice della lingua di destinazione contiene cinque caratteri come `fr_ca`. 9357
* Impossibile cercare i file tramite **Trova file nella cartella** dal **Altre opzioni** e l’app non risponde. (9337)
* La finestra di dialogo Sfoglia si blocca se è presente un numero elevato di tasti. (9332)
* I file DITAVAL non funzionano durante la pubblicazione basata su articoli. (9330)
* L’ordine delle note a piè di pagina non è corretto nell’output del sito AEM. (9327)
* La ricerca non viene eseguita automaticamente quando si cambia il percorso di selezione. (9323)
* Al termine della traduzione, viene creata una versione aggiuntiva per la risorsa tradotta. (9310)
* Impossibile eliminare gli utenti amministratore dal profilo della cartella. (9306)
* La mappa principale aggiornata da Riferimento chiave contenuto non viene impostata finché la pagina non viene aggiornata. (9302)
* Autenticazione Web non funzionante in ossigeno. (9296)
* I collegamenti web con caratteri codificati non funzionano correttamente. (9227)
* Il file non viene estratto quando viene aperto in ossigeno. (9217)
* L&#39;aggiornamento dei file estratti non funziona con la registrazione con l&#39;autenticazione Web in ossigeno. (9179)
* Le schede Traduzione e Linea di base sono visibili per un certo periodo di tempo sul dashboard Mappa. (9146)
* Si verificano problemi di esperienza o di funzionalità durante il ricaricamento del profilo cartella. (9103)
* L’eliminazione dell’editor di layout di pagina non comporta la sua chiusura dal pannello centrale nella vista Autore. (9087)
* Errore di convalida nell&#39;editor Web quando si rimuove un&#39;immagine e si salva la nuova versione del documento. (8985)
* Impossibile visualizzare tutte le `glossrefs` nel pannello Glossario (contenuto specifico). (8886)
* `xref` senza testo non viene visualizzato nell’output di pubblicazione basato su articoli. (8764)
* I riferimenti interrompono le immagini in movimento o i file multimediali che hanno uno spazio nei nomi dei file. (8624)
* I riferimenti si interrompono durante la scelta `Select All` e lo spostamento di file multimediali o contenuti DITA in un&#39;altra cartella. (8622)
* I processi di output con stato come &quot;In attesa&quot; o &quot;In esecuzione&quot; non vengono eliminati nel dashboard di pubblicazione.  (8569)
* La funzione di eliminazione dell&#39;output ha esito negativo se è presente un numero elevato di nodi della cronologia di output rimasti. (8568)
* Il pacchetto Add on DITA impedisce il rilevamento delle risorse duplicate DAM. (8417)
* Pulsante Crea attività di revisione abilitato per i file non DITA. (8401)
* Viene visualizzata la finestra di dialogo Inserisci riferimenti quando si aggiunge un riferimento soggetto a una mappa mediante l&#39;interfaccia utente. (8212)
* Spazio imprevisto trovato in ogni spazio vuoto `entry` quando l&#39;attributo outputclass viene aggiunto a `tgroup` elemento. (7532)
* Il pannello dell’archivio non visualizza le icone di blocco file archiviate o estratte al termine dell’azione. (5817)
* L’icona Blocca viene visualizzata nella vista archivio anche quando il file viene archiviato dall’editor.  (5756)
* Siti mancanti nei predefiniti AEM nella scheda Output. (9567)
* L&#39;editor XML si blocca quando si tenta di modificare alcuni file DITA. (9537)
* L&#39;esecuzione di una ricerca nell&#39;editor XML determina il blocco della pagina. (9452)
* Il download della mappa con linea di base non funziona se il contenuto viene spostato in un’altra cartella. (9331)
* Il ricaricamento non riesce in ossigeno quando i file esistono già nell’AEM nella stessa posizione. (9328)
* La posizione di evidenziazione non è corretta nella vista affiancata. (9305)
* Dopo il check-in di un documento da Oxygen a AEM, il contenuto giapponese nel documento viene sostituito da punti interrogativi (???). (9276)
* Il caricamento di file da Oxygen a AEM non riesce. 9157
* La notifica e-mail non viene inviata quando un’attività di revisione viene riassegnata nella casella in entrata. (8376)

## Problemi noti

All’apertura dell’editor, la pagina vuota viene visualizzata in modo intermittente.
