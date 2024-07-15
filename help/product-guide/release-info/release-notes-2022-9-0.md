---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di settembre 2022
description: Versione di settembre di Adobe Experience Manager Guides as a Cloud Service
exl-id: f6247f91-43cc-43a4-a6f8-3b1f09d0533f
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 0%

---

# Versione di settembre di Adobe Experience Manager Guides as a Cloud Service

## Aggiornamento alla versione di settembre

Aggiorna la configurazione corrente di Adobe Experience Manager Guides as a Cloud Service (in seguito denominato *AEM Guides as a Cloud Service*) eseguendo i seguenti passaggi:
1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
1. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei Cloud Service a 2022.9.178.
1. Apporta le modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione di settembre di AEM Guides as a Cloud Service.

## Passaggi per indicizzare il contenuto esistente

Effettua le seguenti operazioni per indicizzare il contenuto esistente e utilizzare il nuovo testo Trova e sostituisci a livello di mappa:
* Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexin`.
(Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate ||  Esempio:   `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)
* L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Ad esempio: `http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)`
* Una volta completato il processo, la richiesta di GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.


## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di settembre 2022 di AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Non compatibile | Aggiornamento 2020 4 e versioni successive |
| | |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.9.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Nuove funzioni e miglioramenti

AEM Guides as a Cloud Service fornisce molti miglioramenti e nuove funzioni nella versione di settembre:


### Creare una baseline dinamica basata su etichette

Ora AEM Guides offre la funzione di creare linee di base dinamiche basate su etichette. Se si genera una baseline, si scarica una baseline o si crea un progetto di traduzione utilizzando una baseline, i file vengono selezionati in modo dinamico in base alle etichette aggiornate. Questa funzione è utile in quanto non è necessario modificare la linea di base quando si aggiornano le etichette.
È inoltre possibile esportare l&#39;istantanea della baseline come CSV.

![Crea previsioni](assets/dynamic-baseline.png)

### Trova e sostituisci il testo a livello di mappa

È ora possibile cercare all&#39;interno di una mappa i file che contengono testo specifico. Il testo cercato viene evidenziato nei file. È inoltre possibile sostituire la parola o la frase cercata con un&#39;altra parola o frase all&#39;interno dei file.
Seleziona l&#39;icona **Sostituisci** per sostituire l&#39;occorrenza corrente e l&#39;icona **Sostituisci tutto nel file** per sostituire tutte le occorrenze nel file selezionato.

![Trova Sostituisci nella mappa](assets/map-find-replace.png)

Per impostazione predefinita, le opzioni **File di estrazione prima di sostituzione** e **Crea nuova versione dopo sostituzione** sono selezionate, pertanto un file viene estratto prima di sostituire il testo e viene creata una nuova versione dopo la sostituzione del testo.

### Visualizza la differenza di versione per i file non sincronizzati dal dashboard di traduzione

Ora puoi scegliere di tradurre i file **Non sincronizzati** in base alle modifiche apportate tra le due versioni di un argomento.\
![Dashboard di traduzione](assets/translation-version-diff.png)
Dal dashboard di traduzione, puoi facilmente vedere le differenze tra l’ultima versione tradotta e la versione corrente del file selezionato.

![finestra di dialogo per differenza versione](assets/version-diff.png)

In base alle differenze, puoi decidere se tradurre o meno un argomento.

### Interfaccia utente metadati disponibile per i predefiniti di PDF

È possibile impostare i metadati dal predefinito di output di una mappa DITA. È possibile impostare i metadati Titolo, Autore, Oggetto e Parole chiave. Questi metadati vengono mappati ai metadati nelle Proprietà file del PDF di output.
Questi metadati sostituiscono i metadati definiti a livello di libro. Potete definire i metadati in modo specifico in ciascun predefinito di output e trasmetterli al PDF di output.

![Metadati nel predefinito](assets/preset-metadata.png)


## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

* Editor web | Quando si spostano elementi all’interno di un argomento, gli ID assegnati sugli elementi vengono sovrascritti dagli ID assegnati automaticamente. (7895)
* Rileva modifiche | Il contenuto viene perso quando viene inserito un nuovo elemento utilizzando il tasto Invio. (10246)
* La mappa secondaria a cui fa riferimento la mappa principale nei modelli dita non viene creata. (10231)
* Editor XML | La funzione di copia e incolla non funziona in modalità di creazione. (10309)
* Se sono selezionate più etichette di versione, queste non vengono deselezionate. (9561)
* La navigazione automatica al percorso nella finestra di dialogo Sfoglia sito non funziona come la navigazione dei file. (9920)
* Il pannello Struttura non visualizza il contenuto quando si passa dalla modalità **Autore** alla modalità **Source**. (10319)
* Non è possibile confermare in un nuovo argomento creato utilizzando un contenuto nel modello di argomento. L’ID hash copiato non viene aggiornato nella copia del contenuto. (9890)
* Web-Editor | Non esiste alcun caricatore durante la creazione di una mappa dal modello di mappa. (9891)
* Nuovo editor mappa | Il testo in grassetto o corsivo aggiunto nel titolo della mappa non viene mantenuto se si passa dalla visualizzazione **Autore** alla visualizzazione **Layout**. (10218)
* Nuovo editor mappa | Le condizioni applicate a qualsiasi riferimento non possono essere rimosse dalla vista Layout. (10213)
* Nuovo editor mappa | L’applicazione di riferimenti a condizioni non funziona nella vista Layout, come nella vista Author. (10198)
* Nuovo editor mappa | Sposta a sinistra dal menu di scelta rapida rimuove il riferimento se non può essere spostato a sinistra. (10219)
* Nuovo editor mappa |L’icona non viene visualizzata correttamente per i riferimenti in una mappa creata con la vista Layout. (10197)
* Pannello archivio | Se si fa clic con il pulsante destro del mouse nel pannello dell’archivio, viene generato un errore dell’applicazione. (10123)
* Trova e sostituisci | La modalità scura non è leggibile per i risultati di ricerca nell’editor web. (9978)
* Traduzione | I metadati e i tag non vengono propagati alle copie tradotte. (4696)
* Quando si copia e incolla un contenuto (ctrl+c/ctrl+v) viene generato un errore in modalità di creazione. (10304)
* Modello PDF | Se si aggiungono immagini di sfondo a qualsiasi layout di pagina, il percorso immagine viene visualizzato come assoluto e le immagini non vengono visualizzate nel PDF di output. (10297)
* Native PDF | Il titolo del capitolo e l’intestazione del capitolo non funzionano nella pubblicazione PDF. (9947)
* Native PDF | `xref` per un concetto non è risolto correttamente per un argomento DITA specifico. (10229)
* Native PDF | Impossibile visualizzare il testo della didascalia per una tabella nell’output PDF generato. (9827)
* Native PDF | I riferimenti nelle appendici non vengono visualizzati come appendici nell’output di PDF. (10182)
* Native PDF | L&#39;attributo di frame per una tabella non viene propagato al HTML temp (come classe). (10353)
* Native PDF | i file HTML temporanei aggiungono le classi colsep e rowsep a td e th anche se il loro valore è 0 nel DITA di origine. (10352)
* Native PDF |  I metadati per il dato aggiunto nel layout di pagina non vengono rispettati. (10377)
* Native PDF |  La generazione di PDF non riesce per contenuti specifici. (9927)
* Native PDF | Il contenuto tramite conkeyref non viene visualizzato nell’output PDF. (9836)
* Native PDF | I riferimenti a tasti per i tasti con immagini o collegamenti esterni non vengono risolti. (10063)
* Nella vista Creazione di una mappa non viene visualizzato il testo segnaposto per l&#39;elenco tabelle e l&#39;elenco figure. (10330)
* Quando si crea una nuova baseline, il filtro già selezionato non viene applicato. (9954)
* File video mancante dalla linea di base se il nome della cartella principale contiene uno spazio. 10031)
* Durante la creazione della linea di base non viene selezionata la versione più recente se il fuso orario dell’utente è diverso da quello del server. (10190)
* La scelta rapida Ctrl + F non apre la finestra modale di ricerca del browser sulla console Assets dopo l’installazione di AEM Guides 4.1 su AEM 6.5.12. (10189)


## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione di AEM Guides as a Cloud Service di settembre 2022.


* La baseline dinamica non è integrata con la pubblicazione della knowledge base.

* Traduzione | Viene visualizzata l’icona Differenza di versione per il contenuto sorgente a causa di eventuali modifiche nel contenuto di destinazione.
