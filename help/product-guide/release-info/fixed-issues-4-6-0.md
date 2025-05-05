---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides versione 4.6.0
description: Scopri le correzioni di bug nella versione 4.6.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: d51cc5ed621d5f533815c677e23bd4c1f4a52de3
workflow-type: tm+mt
source-wordcount: '2011'
ht-degree: 0%

---


# Sono stati risolti i problemi nella versione 4.6.0 di (settembre 2024)


Questo articolo descrive i bug corretti in varie aree della versione 4.6.0 di Adobe Experience Manager Guides.


Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizzare [Novità della versione 4.6.0](whats-new-4-6.md).

Scopri le [istruzioni di aggiornamento per la versione 4.6.0](../release-info/upgrade-instructions-4-6-0.md).

## Authoring

- L&#39;opzione **Trova** non funziona nella visualizzazione **Source**. (18610)
- **Estrai** e **Archivia** le icone vengono visualizzate insieme quando `autocheckout` è configurato in xmleditor. (18088)
- Le mappe DITA di grandi dimensioni vengono caricate lentamente e richiedono tempo per passare alla visualizzazione **Layout**.  (17590)
- Gli errori relativi agli ID immagine duplicati negli argomenti impediscono all&#39;utente di salvare o creare un argomento. (17528)
- L&#39;operazione di copia e incolla di argomenti di dimensioni superiori a 15 KB non riesce e si verifica un errore imprevisto. (17171)
- La funzionalità per modificare lo stato del documento dal pannello **Proprietà file** non funziona correttamente e cambia allo stato *Bozza*. (17088)
- Quando si modificano le impostazioni dell&#39;editor XML utilizzando un profilo di cartella personalizzato, `ui_config.json` viene aggiornato con un file non corretto. (17011)
- I pannelli dei contenuti riutilizzabili non elencano gli elementi quando **Preferenze utente** è impostato per visualizzare i file in base a **Nome file**. (16896)
- I sottoelementi all&#39;interno dell&#39;elemento titolo della tabella non vengono riprodotti nella modalità **Anteprima** di Experience Manager Guides. (16691)
- **I caratteri speciali** scritti con caratteri di escape vengono rimossi dall&#39;argomento dopo il caricamento in Experience Manager Guides. (16495)
- I video Vimeo non supportano la funzionalità a schermo intero in Experience Manager Guides. (15996)
- Se si incollano lunghe sequenze di testo preformattato in `<pre>` o `<codeblock>` elementi, il testo risulterà troncato. (15859)
- L’eliminazione del contenuto si verifica a causa di GUID duplicati quando i modelli vengono installati tramite codice ma non vengono elaborati. (15858)
- Experience Manager Guides non rispetta l&#39;attributo **Ruolo di elaborazione** in modalità **Anteprima**. (15787)
- L&#39;editor elimina in modo intermittente il testo in eccesso oltre l&#39;area selezionata. (15708)
- Impossibilità di copiare e incollare tabelle di grandi dimensioni da documenti di Word o HTML nell&#39;editor Web. (15369)
- Mancanza di API o eventi per acquisire l’aggiunta di attributi a un elemento o l’inserimento di un nuovo elemento. (15351)
- Impossibile aggiungere il tag `<data>` nel tag `<ol>` nell&#39;editor Web. (15161)
- Il componente segnaposto **Elemento** causa il blocco dell&#39;interfaccia utente. (14957)
- L&#39;editor Web non è in grado di caricare i file con estensione pptx. (14837)
- Quando si trova un testo nell&#39;Editor Web, il cursore torna alla prima occorrenza del testo cercato premendo il tasto Invio. (14820)
- Il salvataggio automatico causa più problemi, riposiziona il cursore e richiede clic manuali nel documento. (14253)
- Premendo il tasto **Invio** in una cella di tabella all&#39;interno del testo, il paragrafo non viene diviso come previsto. (14251)
- I file di grandi dimensioni non vengono caricati nell’editor web e il browser viene bloccato. (13227)
- I risultati della ricerca sono disabilitati dopo l&#39;apertura di un file trovato tramite **Trova e sostituisci** globale. (12142)
- Nella vista origine, `</conbody>` viene inserito occasionalmente in posizioni non corrette. (11305)
- Il percorso del componente `/libs/fmdita/components/versions` è hardcoded e gli utenti non possono sovrapporlo. (8779)
- `<conref>` per un argomento a cui si fa riferimento all&#39;interno di una mappa DITA non viene riflesso nell&#39;anteprima all&#39;interno dell&#39;editor. (17794)
- La Guida DITA di Experience Manager non attiva la funzione Salva dopo l&#39;utilizzo della funzione di rientro automatico. (16482)
- La caratteristica di descrizione comando non consente di aggiornare il campo Source nell&#39;editor XML. (15847)
- La funzionalità **Condividi collegamento UUID** non funziona per le immagini in Adobe Experience Manager. (15598)
- Nella visualizzazione **Autore** si verifica un problema di copia e incolla quando si utilizzano spazi unificatori e si verifica un overflow del testo. (15541)
- Problemi di testo sovrapposti si verificano in `<reltable>` e `<fig>` tag. (15238)
- Si verificano problemi di visualizzazione momentanea di altri contenuti nel pannello **Attributi**. (15237)
- Nell&#39;elemento `<othermeta>` all&#39;interno di `<topicmeta>`, quando si aggiunge un elemento `<conref>` a un&#39;altra mappa DITA, anche l&#39;ID della mappa viene aggiunto insieme all&#39;ID dell&#39;elemento. (15226)
- Il cursore si sposta tra gli elementi del blocco quando si elimina un carattere o una parola all’interno del contenuto. (15224)
- Il messaggio di errore File estratto da &quot;&quot; non viene visualizzato correttamente quando si modificano file spostati da un&#39;altra scheda, quando i token sono scaduti o quando l&#39;utente è disconnesso. (15223)
- Impossibile aggiornare `<conref>` dal pannello **Attributi** quando si apportano modifiche. (15209)
- Quando si seleziona un&#39;immagine all&#39;interno di una cella di tabella, viene selezionata l&#39;intera cella. (15188)
- Il pannello **Attributi** non viene visualizzato nella visualizzazione Source dell&#39;editor Web. (14387)
- `<Topicref>` aggiunto utilizzando `<keyref>` non viene visualizzato in Native PDF. (11974)
- Gli spazi indesiderati e unificatori vengono aggiunti durante la modifica alla fine di un tag nell’editor web. (11786)
- Il contenuto viene eliminato durante la correzione degli errori ortografici nei file DITA. (11610)
- L&#39;apertura di un argomento o di una mappa DITA in una nuova scheda per la modifica blocca la navigazione della selezione nell&#39;interfaccia utente di Assets. (4992)
- L’eliminazione dei nodi di revisione impedisce l’apertura e la visualizzazione di commenti in Adobe Experience Manager Guides. (15366)
- La versione DITA visualizza erroneamente il nome utente nell&#39;interfaccia utente di Assets. (17580)
- L&#39;elemento `<title>` viene aggiunto automaticamente quando l&#39;elemento `<fig>` viene inserito come snippet. (18562)
- Si verificano dei problemi durante il caricamento di un numero elevato di file con set di dati densi in Experience Manager Guides.(17008)
- L&#39;editor Web non visualizza la parola chiave corretta per impostazione predefinita, soprattutto se la parola chiave è definita in modo diverso nelle mappe figlio. (14748)
- Lo stato del documento **1&rbrace; non viene visualizzato quando si modificano le proprietà di più di 50 file in blocco dalla visualizzazione Mappa dell&#39;editor Web.** (14574)
- Il comportamento del pulsante Chiudi non è coerente quando si utilizza la funzionalità Salvataggio automatico. (10996)
- Si verificano problemi di convalida negli elementi di MathML quando si inseriscono nuovi elementi o si modificano le equazioni. (10624)
- La funzionalità Revisioni non funziona con il testo che inizia con i caratteri coreani. (14538)
- Le immagini collegate degli argomenti non vengono visualizzate nella linea di base dopo la creazione della versione. (16931)

## Pubblicazione

- Il riferimento incrociato alla chiave non viene risolto nell’output di Native PDF. (18087)
- L&#39;errore **duplicate_value** si verifica in modo intermittente durante la ripubblicazione di un articolo esistente in Salesforce. (17932)
- La convalida della connessione Salesforce non riesce con l’URL fulmine. (17797)
- Quando si seleziona l&#39;opzione **Usa metadati aggiunti nell&#39;elemento topicmeta**, le proprietà dei metadati non vengono propagate nelle proprietà del documento dell&#39;output di PDF nativo.(17283)
- Il filtro delle condizioni nell&#39;output di PDF nativo non funziona come previsto rispetto a DITA-OT. (17095)
- Il sommario non rispetta i tag `<sub>` o `<sup>` nell&#39;output Native PDF. (17028)
- Il collegamento delle mappe incrociate non riesce a visualizzare tutte le mappe padre nelle impostazioni del contesto di pubblicazione per un collegamento con `scope="peer"`. (16700)
- La generazione del sito AEM e l’API di pubblicazione incrementale non funzionano come previsto. (16666)
- La generazione dell&#39;output del sito AEM non riesce se l&#39;opzione **Elimina sito orfano** è abilitata. (15896)
- I vecchi attributi vengono mantenuti nei **Predefiniti condizione** quando si aggiungono o si rimuovono attributi nuovi o esistenti. (15890)
- Nell’output JSON, i metadati della mappa o degli argomenti DITA non vengono propagati ai file di output JSON. (15713)
- Il contenuto della lingua RTL non viene gestito correttamente nell’output di pubblicazione di PDF nativi. (15709)
- La pubblicazione nativa di PDF ha esito negativo quando il predefinito viene rinominato. (15662)
- La proprietà **sourcePath** non è corretta nell&#39;output del sito AEM pubblicato. (15502)
- La selezione e la personalizzazione delle variabili di lingua non funzionano correttamente nel predefinito di output di Native PDF. (15399)
- La generazione nativa di PDF ha esito negativo quando si utilizza un foglio di stile o un modello di layout di grandi dimensioni. (15344)
- Il rendering del contenuto nell&#39;output pubblicato non viene eseguito correttamente se `<conref>` viene utilizzato con un percorso assoluto. (15222)
- La riduzione degli URL di AEM Sites non funziona a causa di conflitti tra `fmdita rewriter` e `ResourceResolver`. (14793)
- La generazione nativa di PDF non riesce e viene restituito un errore relativo all’ottenimento delle dipendenze per Node.js. (14445)
- Gli attributi **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** e **chunk=&quot;to-content&quot;** vengono visualizzati nell&#39;output di AEM Sites in modo indipendente. (14442)
- `<Conref>` non viene risolto nella modalità `Preview` dell&#39;editor Web e dell&#39;output di PDF nativo. (17827)
- In Native PDF gli argomenti DITA nidificati non vengono visualizzati correttamente nel sommario. (16742)
- Le miniature generate da **Dynamic Media** per i file video non persistono nell&#39;output pubblicato. (15656)
- Il PDF di riferimento non è attivato dal **dashboard di Publish in blocco** durante l&#39;attivazione in blocco del contenuto pubblicato. (17793)
- Se una cartella contenente mappe 2k è impostata nel percorso della cartella all&#39;interno di un profilo di cartella, le modifiche applicate al predefinito di output non vengono eseguite. (14852)
- La rigenerazione dell&#39;argomento non riesce a causa di un errore OOTB Regenerate Topic (Rigenera argomento OOTB) o incrementale dell&#39;API di pubblicazione. (18452)
- Il predefinito di condizione non recupera gli attributi aggiornati dopo l’aggiornamento di Experience Manager Guides. (18174)
- I riferimenti al contenuto non vengono risolti correttamente per l&#39;output di PDF nativo se il file contenente le definizioni chiave non si trova nella stessa cartella della mappa DITA. (15062)
- La dashboard di Publish in blocco è vuota per le mappe ancora in fase di traduzione. (19352)
- L’attivazione in blocco dei contenuti pubblicati non funziona per le mappe localizzate. (17638)



## Gestione


- La conversione da InDesign a DITA ha un percorso di configurazione hardcoded, pertanto i file di configurazione personalizzati non vengono scelti. (16891)
- I **Resource Resolver** non chiusi causano un aumento del conteggio delle sessioni e `PathNotFoundException` errori dopo la versione 4.3.1 di Experience Manager Guides. (15604)
- Errore durante l’installazione dei pacchetti Guide negli archivi di grandi dimensioni. (15160)
- La creazione di una baseline utilizzando l’API Java non funziona con Experience Manager Guides. (14787)
- L&#39;API `/bin/fmdita/import` rimane bloccata nella richiesta in sospeso a tempo indefinito quando le risorse in caricamento superano i 500 MB. (14743)
- La modifica di una baseline esistente e la selezione di una versione specifica attivano errori di applicazione. (14451)
- Esecuzione dello script postprocess non riuscita a causa dell&#39;eccezione **FileNotFoundException**. (16517)
- I titoli dinamici con `<conkeyref>` non vengono visualizzati nell&#39;elenco degli argomenti del report. (16967)
- I conteggi imprecisi dell&#39;**Elenco argomenti** si verificano nell&#39;interfaccia utente di Experience Manager Guides Reports a causa delle proprietà senza patch durante la copia delle risorse DITA. (15529)
- Gli argomenti contenenti riferimenti esterni con %20 nell&#39;URL visualizzano riferimenti a file interrotti. (15347)
- Le proprietà fmditaMaprefs e fmditakeydefrefs visualizzano percorsi relativi, nonostante l&#39;impostazione di percorsi assoluti per la mappa DITA e gli argomenti. (18353)
- Il percorso della funzionalità di sovrapposizione è hardcoded per il file in lingua coreana e non è selezionato correttamente. (17089)
- L&#39;ora predefinita nella creazione della baseline nell&#39;editor Web viene visualizzata come 00:00 invece dell&#39;ora corrente. (15215)

## Rivedi

- Il recupero dell’elenco utenti durante la creazione di un’attività di revisione ha esito negativo se il numero di utenti supera i 25. (17329)
- Gli argomenti della revisione non vengono visualizzati nell’ordine corretto. (16319)
- Nell&#39;editor Web, il pannello Revisione viene caricato lentamente. (14680)
- I revisori non possono aggiungere, evidenziare o eliminare spazi durante la revisione di un documento in Experience Manager Guides. (14752)
- Quando un utente aggiorna un’attività di revisione, non tutti i revisori assegnati ricevono una notifica sull’aggiornamento. (9496)

## Traduzione

- I riferimenti delle risorse tradotte non vengono aggiornati. (18086)
- Impossibile creare progetti XLIFF con traduzione umana. (16964)
- Il titolo con `<conref>` o `<conkeyref>` non viene risolto nelle dashboard di Baseline e di Traduzione dell&#39;editor Web. (16961, 16879)
- Con la versione 4.3.1 di Experience Manager Guides, i progetti di traduzione non aggiungono nuovi processi linguistici a Adobe Experience Manager 6.5 SP18. (15398)
- **Accetta traduzione** non completa la traduzione dei file temporanei. (14665)
- L’aggiunta di un argomento aggiornato in un progetto di traduzione attivo genera un argomento duplicato e il processo non riesce. (7688)
- I riferimenti non vengono filtrati correttamente come diretti o indiretti durante la traduzione in più lingue. (17891)
- La traduzione basata su XLIFF non riesce e viene restituito un errore per gli utenti &quot;non amministratori&quot;.(17296)
- Il titolo dei file tradotti torna all’inglese dopo la seconda traduzione, anche se il contenuto è stato tradotto. (15200)
- Quando si seleziona un progetto di traduzione con **Stato traduzione** come **In corso**, viene visualizzata una pagina errata. (13248)
- Ai progetti di traduzione creati selezionando l&#39;opzione **Crea solo struttura** non sono assegnati UUID. (18980)


## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 4.6.0:
- L&#39;apertura di un predefinito di **AEM Sites** (non legacy) contrassegna l&#39;argomento come danneggiato.
- Il pannello selezionato non viene mantenuto durante l&#39;aggiornamento del browser dalla scheda **Output**.
- Impossibile trascinare gli argomenti tra due `topicrefs` nella visualizzazione **Autore**.
- Il filtro delle condizioni applicato nel predefinito non viene applicato tramite **Scarica come PDF**.
- La generazione di un singolo argomento dal pannello Mappa genera tutti gli argomenti selezionati nel predefinito **AEM Sites** (non legacy).
- Il riferimento dell&#39;argomento risulta interrotto nell&#39;interfaccia utente quando viene inserito dalla barra degli strumenti superiore della mappa DITA.
- La generazione di PDF nativi ha esito negativo per una mappa DITA se sono presenti riferimenti mancanti.
- Una volta aggiornato lo stato del documento di un argomento a **Fine**, l&#39;icona **Avvia una nuova versione** è disponibile solo nella modalità **Anteprima** dell&#39;argomento.
- Quando si seleziona un file DITA nell&#39;interfaccia utente di Asset, viene visualizzata l&#39;opzione **Apri nel FrameMaker**, anche se è disabilitata nelle impostazioni di configurazione.




