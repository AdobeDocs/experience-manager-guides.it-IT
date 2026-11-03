---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2026.11.0
description: Scopri le correzioni di bug nella versione 2026.11.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f33da832def2bf2cc8caf46f3b6f8102bcfafb19
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 0%

---

# Sono stati risolti i problemi nella versione 2026.11.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2026.11.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizza [Novità della versione 2026.11.0](./whats-new-2026-11-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.11.0](./upgrade-instructions-2026-11-0.md).

## Editor 2.0

- Quando si seleziona una riga di tabella utilizzando le breadcrumb nell&#39;editor e si seleziona l&#39;opzione **Elimina** dal menu di scelta rapida, viene rimosso solo il contenuto della cella anziché l&#39;intera riga. (GUIDES-56759)
- Quando si incolla una tabella da Microsoft Word, vengono create le celle della riga di intestazione, ma il loro contenuto viene perso. (GUIDES-49847)
- Le modifiche rilevate nei file creati prima dello spostamento nell&#39;editor 2.0 non vengono visualizzate nel pannello **Rileva modifiche**. (GUIDES-44777)
- Quando il codice viene incollato in un elemento `codeblock`, da Microsoft Word o da editor di testo simili, utilizzando la combinazione di tasti Ctrl+V, le interruzioni di riga e gli spazi iniziali vengono persi e il codice viene appiattito in un&#39;unica riga. (GUIDES-33247)

## Authoring

- Quando la shell unificata è abilitata, l’intestazione di Adobe Experience Manager Guides viene visualizzata anche nell’editor e nella console Mappa. (GUIDES-56812)
- Nell&#39;interfaccia utente di Assets, per le risorse non DITA vengono visualizzate azioni specifiche per DITA come **Visualizza origine**, **Modifica argomenti** e **Condividi collegamento UUID**. Inoltre, **Condividi collegamento UUID** genera un collegamento non valido per le risorse che non hanno un UUID. (GUIDES-47043)
- Nel pannello Schema soggetto, il titolo visualizzato viene scelto solo dall&#39;attributo `navtitle`. L&#39;elemento `navtitle` viene ignorato anche quando sono presenti entrambi. (GUIDES-37722)
- Nella **visualizzazione Titolo** del pannello Archivio, i puntini di sospensione non sono inizialmente visibili per i file con nomi lunghi. Facendo clic con il pulsante destro del mouse su un file di questo tipo, i puntini di sospensione e il menu di scelta rapida vengono visualizzati molto a destra del file, talvolta in parte fuori schermo. (GUIDES-37118)
- Nel pannello Condizioni, le condizioni vengono ordinate alfabeticamente in base ai loro valori anziché alle loro etichette. (GUIDES-14593)
- Nei modelli di output, il pulsante **Nuovo stile** (+) non viene visualizzato nel pannello Stili quando viene aperto un foglio di stile, ad esempio layout.css. (GUIDES-49448)

## Gestione risorse

- Quando carichi un file modificato utilizzando l&#39;opzione **Sovrascrivi file esistente**, il caricamento risulta completato se il file esistente non ha un UUID di Guide ed è memorizzato in una cartella elencata in **Percorsi ignorati per la post-elaborazione**. Tuttavia, il file esistente non viene sovrascritto e non viene creata alcuna nuova versione. (GUIDES-55866)
- In un bookmap, quando un elemento `booktitle` contiene più sottoelementi, ad esempio `booklibrary` e `mainbooktitle`, viene aggiunto spazio vuoto tra i rispettivi valori nei metadati `dc:title`. (GUIDES-28877)

## Pubblicazione

- Nella console Mappa, dopo la generazione dell&#39;output per una mappa, il pulsante **Genera** è disabilitato all&#39;apertura di un&#39;altra mappa. L&#39;aggiornamento del browser attiva nuovamente il pulsante. (GUIDES-54591)
- La pubblicazione di determinate mappe in un sito AEM con mappatura dei componenti non riesce durante la creazione del sommario. (GUIDES-53807)
- La pubblicazione di una mappa in un sito AEM con mappatura dei componenti non riesce se la mappa contiene un elemento `topicref` con un attributo `navtitle` e nessun attributo `href`. Anche i tentativi successivi non riescono, anche dopo la rimozione dell’elemento, finché i nodi del sito generati non vengono eliminati. (GUIDES-53707)
- Nell’output del sito AEM con mappatura dei componenti, le intestazioni Markdown dei livelli da 2 a 6 vengono visualizzate come intestazioni di livello 1. (GUIDES-51134)
- Per l’output del sito AEM con mappatura dei componenti, i metadati del prologo, come autore, parole chiave e ID risorsa, vengono visualizzati nel corpo della pagina dell’output pubblicato. (GUIDES-44087)
- Quando un argomento viene pubblicato in ServiceNow, il corpo dell&#39;articolo include la breve descrizione e il prologo dell&#39;argomento. (GUIDES-47868)
- Quando un argomento già pubblicato in ServiceNow viene nuovamente pubblicato, viene creato un nuovo articolo in stato Bozza invece di sovrascrivere quello esistente. (GUIDES-37872)
- Quando i predefiniti per le condizioni escludono i riferimenti agli argomenti durante la pubblicazione in Salesforce, la generazione dell’output viene segnalata come non riuscita, anche se gli argomenti rimanenti vengono pubblicati correttamente. (GUIDES-37807)
- La pubblicazione di una mappa di grandi dimensioni in Salesforce non riesce e viene generato un errore di timeout del gateway. (GUIDES-33722)
- La pubblicazione di una mappa in Salesforce non riesce e viene visualizzato un errore di limite superato quando una richiesta contiene più di 25 operazioni. (GUIDES-33721)
- Nel dashboard delle mappe (precedente), **Aggiungi tutti** in un predefinito di condizione esistente non rileva i valori di condizione aggiunti o modificati dopo la creazione del predefinito. (GUIDES-45940)
- I registri nella pagina **Cronologia output** contenente avvisi sono visualizzati con un&#39;icona verde che non indica la presenza di avvisi. (GUIDES-27000)
- Il glossario non viene incluso nell’output quando nessun termine nel contenuto della mappa fa riferimento a una voce del glossario. (GUIDES-52964)
- Gli argomenti di una mappa secondaria a cui si fa riferimento in un&#39;appendice vengono visualizzati come capitoli invece che come contenuto dell&#39;appendice. (GUIDES-52775)
- Quando la lingua di output è impostata su Cinese (semplificato), alcuni caratteri in cinese semplificato vengono riprodotti con un font giapponese. (GUIDES-48094)
- Le voci di indice perdono il testo degli elementi figlio, ad esempio `keyword`, `ph` e `sup`. Di conseguenza, alcune etichette indice sono incomplete o vuote. (GUIDES-40902)
- Gli spazi intorno agli elementi `option` in linea non vengono mantenuti e il testo adiacente viene visualizzato unito. (GUIDES-40900)

## Traduzione

- Nella pagina Traduzione, la ricerca e l&#39;ordinamento per **Titolo** utilizzano il valore dei metadati localizzati invece del titolo visualizzato nella colonna. (GUIDES-45396)

## Rivedere

- Nella pagina **Revisori**, durante la creazione o la modifica di un&#39;attività di revisione, i pulsanti **Cancella selezione**, **Aggiungi revisori**, **Rimuovi revisori** e **Riassegna revisori** sono attivati per impostazione predefinita, anche quando non è selezionata alcuna riga. (GUIDES-35125)
- Nella casella in entrata di AEM, le notifiche relative alle attività di revisione, come l’assegnazione delle attività, i feedback ricevuti, le menzioni e i promemoria scaduti o in ritardo, vengono visualizzati senza alcun nome di progetto. (GUIDES-10912)
- Nella visualizzazione affiancata di un argomento in un&#39;attività di revisione, il contenuto contrassegnato con barrato viene visualizzato con una formattazione diversa nelle due visualizzazioni. (GUIDES-56079)

## Contenuto di apprendimento

- La generazione di un output SCORM per un corso di grandi dimensioni, in genere da 300 MB a 600 MB, richiede più di 30 minuti e non riesce senza i dettagli dell’errore nei registri. (GUIDES-56101)
- Impossibile impostare in Experience Manager Guides i criteri di completamento per un output SCORM. (GUIDES-55520)
- Le immagini in formato AVIF vengono visualizzate nell&#39;editor ma mancano nell&#39;output pubblicato. (GUIDES-55515)
- L&#39;attributo `href` viene rimosso dai tag di ancoraggio nell&#39;output pubblicato, pertanto i collegamenti non sono selezionabili. (GUIDES-55514)

## Platform

- Quando un utente viene assegnato come utente amministratore in un profilo di cartella ma non è membro del gruppo amministratori, non può aggiungere altri utenti amministratore. Anche se viene visualizzato un messaggio di successo, gli utenti appena aggiunti scompaiono dopo l’aggiornamento della pagina. (GUIDES-50144)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2026.11.0:

## Authoring

- Quando crei una mappa da un modello contenente argomenti dipendenti o sottopap, la creazione della mappa potrebbe non riuscire a intermittenza e generare un errore, in particolare quando il server è sottoposto a un carico elevato. (GUIDES-58715)

### Editor 2.0

- L&#39;opzione **Aggiorna attributo titolo navigazione** non aggiunge l&#39;attributo `@navtitle` agli elementi `topicref` esistenti in una mappa DITA. (GUIDES-54348)

**Rileva modifiche**

Quando **Rileva modifiche** è attivato:

- Le eliminazioni nidificate dallo stesso utente non vengono sempre unite in una singola voce quando l’elemento contenente il contenuto eliminato viene rinominato o formattato. (GUIDES-58429)
- Il pannello **Rileva modifiche** a volte mostra contenuto incompleto per l&#39;elemento padre quando un altro utente effettua un&#39;eliminazione nidificata. (GUIDES-58428)
- Il marcatore di rilegatura rosso non viene visualizzato a sinistra quando si elimina contenuto all&#39;interno di un inserimento creato da un altro utente. (GUIDES-58418)

### Pubblicazione

- Nell&#39;output PDF nativo, la formattazione apice e pedice non viene mantenuta nelle voci indice. (GUIDES-58349)
- Quando si utilizza lo stesso predefinito globale per generare output per mappe diverse, la selezione dell&#39;argomento della mappa precedente può influire sull&#39;output della nuova mappa. (GUIDES-58346)
- Quando una mappa libro contiene un capitolo con un `href` valido e un riferimento ad argomento nidificato, la pubblicazione della mappa in AEM Sites genera una pagina vuota. (GUIDES-58266)
- Quando passi alla scheda **Cronologia output** da un predefinito con modifiche non salvate, i pulsanti **Salva** e **Genera output** rimangono visibili. (GUIDES-57989)
- Quando un flusso di lavoro di post-pubblicazione è configurato per un predefinito, la durata di pubblicazione mostrata in **Cronologia output** non include il tempo impiegato dal flusso di lavoro. (GUIDES-57856)
- Impossibile annullare la generazione dell&#39;output PDF nativo dalla pagina **Cronologia output**. (GUIDES-57821)

### Rivedere

- L’apertura di un’attività di revisione creata nella versione 2026.08.0 o 2026.09.0 può causare errori dell’applicazione. (GUIDES-56583) <br>**Soluzione alternativa:** prima di eseguire l&#39;aggiornamento alla versione 2026.11.0, completa o chiude tutte le attività di revisione create in queste versioni.

