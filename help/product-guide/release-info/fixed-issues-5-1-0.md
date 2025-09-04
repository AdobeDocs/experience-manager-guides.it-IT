---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 5.1.0
description: Scopri le correzioni di bug nella versione 5.1.0 di Adobe Experience Manager Guides.
source-git-commit: 6c29d5540f48c850416db279b4392b6042c8ca2c
workflow-type: tm+mt
source-wordcount: '1789'
ht-degree: 1%

---

# Sono stati risolti i problemi nella versione 5.1.0 di (settembre 2025)

Questo articolo descrive i bug corretti in varie aree della versione 5.1.0 di Adobe Experience Manager Guides.


Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 5.1.0](whats-new-5-1-0.md).

Scopri le [istruzioni di aggiornamento per la versione 5.1.0](upgrade-instructions-5-1-0.md).


## Authoring

- I file **CSS** e **Layout di pagina** nei modelli PDF nativi presentano un comportamento di blocco dei file incoerente, che consente di apportare modifiche anche quando i file sono bloccati. (GUIDES-26688)
- L’aggiornamento della pagina dopo l’aggiunta di pulsanti personalizzati al pannello sinistro crea schede duplicate. (GUIDES-30899)
- Quando si aggiunge contenuto XML contenente parentesi angolari (ad esempio &lt;/ o />) all&#39;interno di un elemento `code block` in un argomento, l&#39;elemento blocco di codice appare vuoto nell&#39;output finale. (GUIDES-31007)
- I valori delle variabili globali `canCheckIn` e `canCheckOut` non vengono impostati correttamente quando un file viene estratto e archiviato dalla barra degli strumenti dell&#39;editor.(GUIDES-29890)
- Quando una mappa DITA è selezionata nella vista Mappa, il conteggio delle selezioni non viene visualizzato correttamente in un primo momento perché i nodi figlio della mappa non sono selezionati. Il conteggio corretto delle selezioni e l’inclusione di tutti i nodi figlio si riflettono solo sulla selezione successiva. (GUIDES-25663)
- I file Markdown non vengono recuperati quando si esegue una ricerca nel pannello Archivio utilizzando il filtro **Argomento DITA**. Inoltre, **Trova e sostituisci** non funziona per i file Markdown e il contenuto correlato. (GUIDES-27133)
- Impossibile personalizzare il menu a discesa **Menu** della barra degli strumenti dell&#39;editor utilizzando il framework delle estensioni. Di conseguenza, non è possibile nascondere o visualizzare i pulsanti esistenti o aggiungere nuovi pulsanti nel menu a discesa. (GUIDES-28748)
- Quando si aggiunge un commento XML all&#39;interno di un elemento nella visualizzazione Source, gli spazi iniziali e finali attorno al commento vengono persi quando si passa da una visualizzazione all&#39;altra. (GUIDES-29781)
- Le opzioni multimediali non funzionano se sono presenti nell&#39;icona con i puntini di sospensione (il menu **Altro**) nella barra degli strumenti. (GUIDES-29583)
- Quando si crea un nuovo argomento tramite l&#39;interfaccia utente o l&#39;editor di Assets, l&#39;argomento non si apre automaticamente nell&#39;editor se l&#39;impostazione `xmleditor.uniquefilenames` è impostata su true in `XMLEditorConfig`. (GUIDES-28171)
- Gli spazi aggiunti all’interno di un’equazione MathML nella vista Source non vengono mantenuti quando si passa da una vista dell’editor all’altra. (GUIDES-26111)
- Se non si chiudono le connessioni della sessione JCR durante l’aggiornamento o la creazione di argomenti, si verificano perdite di memoria e tempi di inattività del servizio. (GUIDES-26282)
- Trascinando le colonne, la larghezza cambia da valori percentuali a pixel e vengono generate tabelle distorte o non allineate.(GUIDES-23128)
- Quando il contenuto viene incollato in un `code block` o quando vengono aggiunti spazi in `code block` e la visualizzazione viene cambiata, la spaziatura viene persa. (GUIDES-27478)
- Quando si aggiunge una mappa a `bookmap`, questa viene archiviata in `fmditatopicrefs` anziché in `fmditamaprefs`. (GUIDES-25480)
- La finestra di dialogo **Inserisci immagine** non viene riprodotta correttamente in schermate ad alta risoluzione o ingrandite causando la scomparsa del titolo della figura e dei campi di testo alternativi. (GUIDES-26459)
- Impossibile caricare la casella di inserimento dei caratteri speciali nell’editor per le impostazioni internazionali tedesche. (GUIDES-24537)
- I commenti e le etichette aggiunti durante il salvataggio di una nuova versione di un file DITAVAL non vengono salvati nella cronologia delle versioni con la nuova versione. (GUIDES-24076)
- I riferimenti in uscita e in entrata in **Proprietà file** nel pannello di destra non vengono aggiornati correttamente quando si passa da un file di mappa all&#39;altro. Questo problema si verifica in modo specifico quando i file di mappa contengono un numero elevato di riferimenti. (GUIDES-23344)
- Il filtro dell&#39;archivio non mantiene l&#39;ordine dei filtri personalizzati definiti in `ui_config.json`. (GUIDES-21193)
- L&#39;eliminazione di più righe di testo in un elemento `codeblock` crea uno spazio vuoto che non può essere rimosso dalla visualizzazione Autore. (GUIDES-20672)
- Non è possibile generare nuovi ID per gli elementi quando questi vengono aggiunti tramite snippet o creati tramite modelli, anche quando l&#39;opzione **genera automaticamente ID** è abilitata in `XMLEditorConfig`. (GUIDES-21734)
- La creazione di una nuova risorsa DITA dai modelli DITA copia le proprietà di replica dai modelli DITA corrispondenti. (GUIDES-25145)
- Impossibile accedere alle proprietà del file dal pannello dell’archivio se il nome della cartella principale include il carattere &quot;&amp;&quot;. (GUIDES-25762)
- La chiusura di un file di argomento consente di salvarlo come nuova versione, anche quando l&#39;argomento è bloccato. Questo problema si verifica in modo specifico quando l&#39;opzione **Richiedi nuova versione alla chiusura** è abilitata in `XMLEditorConfig`. (GUIDES-23875)
- La larghezza massima corrente del pannello dell’archivio nasconde i titoli degli argomenti e delle mappe quando la gerarchia dei contenuti è profondamente nidificata. (GUIDES-27751)

## Gestione risorse

- Copiare una cartella con un numero elevato di risorse dall’interfaccia utente di Assets causa un timeout API. L’operazione continua a essere eseguita nel backend e viene completata dopo un certo periodo di tempo, ma nell’interfaccia utente non viene visualizzato alcun messaggio di esito positivo o negativo o di notifica. (GUIDES-30900)
- L’operazione di copia e incolla eseguita su una cartella nell’interfaccia utente di Assets non riesce a causa di errori di post-elaborazione. (GUIDES-30840)
- L’operazione di copia e incolla non riesce per le cartelle contenenti risorse composte (risorse con risorse secondarie) nell’interfaccia utente di Assets. (GUIDES-28107)
- Le cartelle con un numero elevato di risorse non vengono caricate correttamente nel repository. (GUIDES-32500)
- I nomi dei nodi delle cartelle non vengono visualizzati correttamente al posto dei titoli delle cartelle nell’editor. (GUIDES-32402)
- Si verifica un errore durante il caricamento di risorse con caratteri non supportati o non consentiti nei nomi dei file. (GUIDES-28845)
- Quando aprite un argomento nella vista Autore dopo un aggiornamento del browser, i tag applicati in precedenza nel pannello Proprietà file non vengono mantenuti e l&#39;aggiunta di nuovi tag sovrascrive quelli esistenti, in particolare quando è disponibile un numero elevato di tag da selezionare. (GUIDES-29078)
- Quando si genera un report metadati per una mappa DITA contenente un numero elevato di risorse, il pulsante **Gestisci** non risponde o mostra una risposta ritardata. (GUIDES-28443)
- Lo stato del documento della copia di lavoro di un argomento viene visualizzato rispetto a tutte le versioni di tale argomento nell&#39;interfaccia utente Traduzione e baseline. (GUIDES-20674)

## Rivedere

- I tentativi di creare attività di revisione tramite il flusso di lavoro di AEM hanno esito negativo in quanto il nodo di revisione non viene creato. (GUIDES-28214)
- La visualizzazione del documento nell’interfaccia utente di revisione non racchiude il contenuto per alcune dimensioni dello schermo, richiedendo agli utenti di scorrere in orizzontale per visualizzare l’intero contenuto. (GUIDES-25292)
- L’aggiornamento dei dettagli di un’attività di revisione nel dashboard Revisione non conferma se l’aggiornamento è stato eseguito correttamente o meno. (GUIDES-8051)

## Traduzione

- Le traduzioni inviate tramite Experience Manager Guides non includono le risorse associate, pertanto il pulsante **Avvia** per il processo di traduzione non sarà più disponibile per gli utenti. (GUIDES-28237)

## Pubblicazione

- Nell’output del PDF nativo, l’elenco degli indici (LOI) viene visualizzato in ordine non alfabetico e i termini degli indici nidificati non vengono raggruppati correttamente, rendendo difficile la navigazione nell’indice. (GUIDES-29090)
- L&#39;elenco a discesa **Modello per pagina mappa** e **Modello per pagina argomento** nella pagina predefinita di output di mappatura dei componenti di AEM Sites appare vuoto se il percorso di destinazione contiene una variabile con due punti. (GUIDES-28119)
- Quando una mappa DITA contiene diversi tipi di riferimenti ad argomenti quali Concetto, Riferimento o Attività e viene unita utilizzando l&#39;attributo `chunk=to-content` per generare output a pagina singola in AEM Sites con mappatura dei componenti, il contenuto non viene pubblicato correttamente a causa di errori di pubblicazione. (GUIDES-28118)
- La pubblicazione di una mappa DITA con l&#39;attributo `chunk=to-content` crea nodi JCR duplicati nel nuovo output di AEM Sites, determinando una struttura di contenuto ridondante in AEM Sites. (GUIDES-28104)
- Quando si pubblica una mappa DITA utilizzando il nuovo output di AEM Sites, se un argomento ha l&#39;attributo `chunk =to-content` e l&#39;output è impostato per l&#39;utilizzo dei titoli degli argomenti come nomi di pagina, il nome della pagina generata visualizza erroneamente la parola **chunk** invece di mantenere il nome dell&#39;argomento originale. (GUIDES-28102)
- La proprietà `cq:template` impostata nel modello di argomento di AEM Guides per la nuova pubblicazione AEM Sites visualizza un valore non corretto che influisce sulla struttura del modello e sul rendering del contenuto. (GUIDES-27789)
- La pubblicazione nativa di PDF continua a tempo indeterminato se il contenuto DITA ha un collegamento a Internet senza avere ambito come `external`. (GUIDES-26434)
- La pubblicazione di PDF nativi e di siti AEM si blocca e viene messa in coda, in presenza di errori nel contenuto. (GUIDES-26516)
- Durante la generazione di pagine del sito AEM con titoli che includono più parole separate da spazi, il titolo della mappa visualizza i trattini invece degli spazi. (GUIDES-27903)
- Per il PDF nativo, non è stato risolto un nome di proprietà di metadati non valido. Verrà visualizzato come `unresolved property name` in **proprietà documento**. (GUIDES-25680)
- Il testo su più righe all&#39;interno di `codeblock` causa problemi di riversamento del testo durante la generazione di PDF. (GUIDES-15541)
- Quando si aggiungono mappe alla raccolta di mappe, vengono visualizzate risorse diverse dalle mappe (come argomenti, ecc.) e anche le lingue delle mappe tradotte non vengono ordinate correttamente.(GUIDES-25085)
- Nell’output legacy di AEM Sites, i collegamenti di sezione all’interno di argomenti nidificati di una mappa non vengono risolti correttamente se impostati manualmente in modalità Source o se il contenuto viene importato da un’origine esterna. Invece di passare alla sezione desiderata, vengono reindirizzati all’argomento principale che contiene l’argomento nidificato. (GUIDES-26103)
- Se l&#39;attributo `scope=external` non è presente nei collegamenti esterni in un argomento DITA, la pubblicazione di HTML5 non riesce senza indicare i file in cui l&#39;attributo non è presente nei log degli errori. (GUIDES-25969)
- Impossibile incorporare collegamenti video in PDF nativo anche quando l&#39;opzione **Incorpora file multimediali** è abilitata nel predefinito PDF. (GUIDES-9989)
- Impossibile passare le proprietà dei metadati per mappare le pagine di destinazione generate con la nuova pubblicazione AEM Sites. (GUIDES-27288)

## Riferimento

- Copiando una mappa DITA dall&#39;interfaccia utente di Assets, anche la Baseline associata viene copiata nella nuova mappa. (GUIDES-11227)
- Quando si crea una nuova baseline con un numero elevato di etichette, questa impedisce il recupero di tutte le etichette. (GUIDES-16232)

## Home page

- La home page diventa vuota se uno dei file elencati nel widget **File recenti** è basato su un modello il cui modello di origine non include una miniatura. (GUIDES-31506)

## Platform

- Quando si lavora con raccolte di grandi dimensioni, si verificano problemi di prestazioni quali tempi di caricamento più lunghi e timeout intermittenti. (GUIDE-29065, GUIDE-28793)
- Le vulnerabilità associate alla libreria Guava obsoleta vengono utilizzate nei componenti AEM Guides caricati su Experience Manager Guides.(GUIDES-27402)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 5.1.0:


- Se il revisore completa l&#39;attività senza aggiungere alcun commento, nella notifica e-mail inviata all&#39;iniziatore dell&#39;attività viene visualizzato il commento più recente a livello di attività. (GUIDES-33590)
- Nella finestra di dialogo Unisci, l’elenco a discesa mostra erroneamente il contenuto principale invece di mostrare le versioni disponibili dell’argomento selezionato. (GUIDES-30820)
- Passando da un predefinito all&#39;altro che utilizza la stessa linea di base, il pulsante Salva viene disattivato per il predefinito corrente. (GUIDES-28025)
- Quando si incolla nuovo contenuto in una nuova riga all’interno di un elemento codeblock, viene inserita automaticamente una riga vuota.(GUIDES-27842)
- Un argomento all&#39;interno di una mappa DITA non viene pubblicato nell&#39;output di AEM Sites quando viene utilizzato sia come keydef che come topicref all&#39;interno delle relative mappe secondarie. (GUIDES-22269)
- Nel pannello Proprietà contenuto, il campo Attributi si chiude automaticamente quando si tenta di aggiornare un riferimento dalla finestra di dialogo Aggiorna collegamento, impedendo l’aggiornamento del collegamento. (GUIDES-17767)