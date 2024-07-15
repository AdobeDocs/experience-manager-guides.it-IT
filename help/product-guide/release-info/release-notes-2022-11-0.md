---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di novembre 2022
description: Versione di novembre di Adobe Experience Manager Guides as a Cloud Service
exl-id: 9f329ec1-dd74-47cc-8567-3fadd962584a
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1384'
ht-degree: 0%

---

# Versione di novembre di Adobe Experience Manager Guides as a Cloud Service

## Aggiornamento alla versione di novembre

Aggiorna la configurazione corrente di Adobe Experience Manager Guides as a Cloud Service (in seguito denominato *AEM Guides as a Cloud Service*) eseguendo i seguenti passaggi:
1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
1. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei Cloud Service a 2022.11.198.
1. Apporta le modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione di novembre di AEM Guides as a Cloud Service.

## Passaggi per indicizzare il contenuto esistente (solo se utilizzi una versione precedente alla versione di settembre di AEM Guides as a Cloud Service)

Effettua le seguenti operazioni per indicizzare il contenuto esistente e utilizzare il nuovo testo Trova e sostituisci a livello di mappa:

* Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate || Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Ad esempio: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Una volta completato il processo, la richiesta di GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di novembre 2022 di AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Non compatibile | Aggiornamento 2020 4 e versioni successive |
| | |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.11.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Nuove funzioni e miglioramenti

AEM Guides as a Cloud Service fornisce miglioramenti e nuove funzioni nella versione di novembre:


### Eliminare i file dal pannello dell’archivio

Ora è possibile eliminare facilmente i file (file singolo alla volta) dal menu **Opzioni** del file selezionato dal pannello del repository.
<img src="assets/repository-delete-file.png" alt="Elimina dall’archivio" width="500">

Viene visualizzata una richiesta di conferma prima di eliminare il file. Se non viene fatto riferimento al file da alcun altro file, questo viene eliminato e viene visualizzato un messaggio di operazione riuscita.

Se il file selezionato è estratto, non è possibile eliminarlo e viene visualizzato un messaggio di errore. Se il file selezionato viene aggiunto a una raccolta di preferiti o se vi si fa riferimento da un altro file, l&#39;AEM guida l&#39;utente e controlla la conferma e ti offre la possibilità di eliminarlo con forza. Se si elimina un argomento di riferimento e si è aperto il file contenente riferimenti per la modifica, verrà visualizzato il collegamento interrotto per il file di riferimento.

**Nota**: è inoltre possibile eliminare il file selezionato utilizzando il tasto Elimina della tastiera.


### Rimozione delle versioni selezionate dei file

Durante la creazione e la gestione del contenuto, è possibile che vengano create molte versioni dei file DITA nell&#39;archivio. AEM Guides consente di eliminare versioni precedenti dei file DITA dall&#39;archivio e di liberare spazio su disco.

<img src="assets/preview-purge-report.png" alt="Anteprima report di eliminazione" width="500">


AEM Guides non elimina la prima versione del file o una versione inclusa in una baseline o a cui è applicata un&#39;etichetta. L’operazione di rimozione non elimina nemmeno i file inclusi in un flusso di lavoro di traduzione o revisione. Puoi scegliere il numero di versioni da mantenere e decidere anche di eliminare i file che sono più vecchi del numero di giorni definito.

Prima di avviare l&#39;operazione di rimozione, è possibile visualizzare in anteprima il report per visualizzare le versioni che verranno eliminate. È quindi possibile decidere di avviare o annullare l&#39;operazione di rimozione.

<img src="assets/download-purge-report.png" alt="Rapporto di eliminazione PDownload" width="500">

Una volta completata l&#39;operazione di rimozione, è possibile controllare il report di rimozione per visualizzare i file eliminati.

### Gestire i predefiniti di output per Profilo globale e Cartella

AEM Guides offre la funzione di creare e gestire predefiniti di output per i profili globali e cartelle. Puoi quindi utilizzare facilmente questi predefiniti di output per generare l’output per tutte le mappe correlate al profilo globale o cartella.

<img src="assets/add-global-output-preset.png" alt="Aggiungi profilo globale" width="400">

**Nota** Solo gli utenti amministratori a livello di cartella possono creare predefiniti per profili globali e di cartelle.

Questi predefiniti globali vengono visualizzati nella scheda **Output** di tutte le mappe correlate. Puoi utilizzarli per generare l’output per tutte le mappe correlate. Per generare l&#39;output di PDF, potete selezionare il predefinito come predefinito di default di PDF. Puoi anche **Modificare**, **Rinominare**, **Duplicare** o **Eliminare** un predefinito di output esistente dal menu **Opzioni**.

### Colonna Etichetta versione aggiunta al dashboard di traduzione

Nel dashboard di traduzione è inoltre possibile visualizzare la colonna Etichetta versione. Viene visualizzata l&#39;etichetta per la versione selezionata del file di origine. Questo può aiutarti a selezionare tutti i file con un’etichetta specifica e a tradurli in una volta sola.

<img src="assets/send-translation.png" alt="invia per traduzione" width="600">


### Native PDF | PDF con barra delle modifiche che mostra la differenza tra le versioni dei documenti

Ora puoi creare un PDF che mostra le differenze di contenuto tra due versioni utilizzando la barra delle modifiche. È possibile scegliere di confrontare la versione corrente con una baseline della versione precedente o confrontare le due versioni della baseline selezionate.

<img src="assets/pdf-change-version.png" alt="spdf-change-version" width="600">

Nel PDF viene visualizzata una barra delle modifiche che indica il contenuto modificato, inserito o eliminato. Sono inoltre disponibili le seguenti opzioni:
* Mostra il contenuto inserito in verde e sottolineato
* Mostra il contenuto eliminato in rosso e contrassegnato con barrato

### Native PDF | Supporto variabile per percorso di output e nome file PDF

Ora puoi anche utilizzare le seguenti variabili predefinite per definire il percorso di output e il file di PDF. Puoi utilizzare una singola variabile o una combinazione di variabili per definire queste opzioni:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (solo per il percorso di output)
* `${path_after_langfolder}` (solo per il percorso di output)


### Native PDF | Genera sommario per mappe DITA e riordina i layout di pagina

È inoltre possibile generare il sommario nelle mappe DITA utilizzando un&#39;impostazione PDF avanzata del modello. Puoi scegliere di abilitare o disabilitare la visualizzazione dei vari layout di pagina e anche riordinarne la posizione.

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

* Native PDF | `conkeyref` non viene risolto nell&#39;output PDF generato. (10564)
* Native PDF | Si verificano dei problemi durante l’accesso ai metadati di una mappa nell’output di PDF. (10556)
* Native PDF | Lo stile in linea viene utilizzato per generare i tag anziché il nome della classe.  (10498)
* L’editor web carica una pagina vuota in modo intermittente. (10678)
* La pubblicazione PDF non riesce se viene creato un predefinito tramite la duplicazione di un predefinito esistente. (10584)
* Il pulsante **Visualizza registro** non funziona se la generazione di PDF non riesce per un predefinito. (10576)
* Nota all’interno di un tag para che è un riferimento conf non viene visualizzato nell’anteprima. (10559)
* Se si preme backspace alla fine di una voce di elenco, l’intero elenco viene rimosso. (10540)
* Quando si utilizza un&#39;esportazione PDF nativa, `<indexterm>` nidificati non sono nidificati nell&#39;indice. (10521)
* Il pulsante **Rientro automatico** nella barra degli strumenti non è presente nella visualizzazione Source. (10448)
* Il primo carattere di una voce di elenco viene perso durante la creazione dell’elenco nell’editor. (10447)
* Se una versione di una risorsa DITA viene modificata e salvata nella finestra di modifica della baseline, vengono visualizzati più pop-up. (10399)
* Errore dell&#39;applicazione quando si fa clic sul pulsante **Modifica** dopo aver selezionato tutti i predefiniti di output dal pannello Generazione rapida. (10388)
* I metadati personalizzati per l&#39;argomento DITA non vengono mantenuti quando si esegue un&#39;azione di copia e incolla dall&#39;interfaccia utente di Assets. (10367)
* L’elaborazione Post è bloccata per l’intera cartella lingua le cui risorse sono presenti in un progetto di traduzione attivo. (10332)
* La scheda Modello nell&#39;editor XML non è visibile agli amministratori dei profili di cartelle. (10266)
* Si verificano problemi di navigazione nell’editor web dopo l’aggiornamento 4.0. (10159)
* I file SVG non vengono visualizzati in modalità Anteprima. (10010)
* Se la scheda Output dell&#39;editor contiene più predefiniti, non è possibile scorrere la sezione dei predefiniti e non vengono visualizzati tutti i predefiniti. (9787)
* Le opzioni **Modifica** e **Annota** per un&#39;immagine non funzionano correttamente nella vista a colonne. (8758)
* Il collegamento tra pari non viene risolto e viene visualizzato come testo normale nell’output generato. (7774)
