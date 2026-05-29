---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 5.2.0
description: Scopri le correzioni di bug nella versione 5.2.0 di Adobe Experience Manager Guides.
source-git-commit: 5eee826022f798b4eb0014ea4b97d2916eb92f33
workflow-type: tm+mt
source-wordcount: '3559'
ht-degree: 0%

---

# Sono stati risolti i problemi nella versione 5.2.0 di (maggio 2026)

Questo articolo descrive i bug corretti in varie aree della versione 5.2.0 di Adobe Experience Manager Guides.

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizzare [Novità della versione 5.2.0](whats-new-5-2-0.md).

Scopri le [istruzioni di aggiornamento per la versione 5.2.0](upgrade-instructions-5-2-0.md).


## Authoring

- Se a un file DITAVAL viene aggiunto un elemento `prop` vuoto senza attributi o valori, non è possibile aggiungere ulteriori elementi `prop`. (GUIDES-33597)
- Dopo l&#39;aggiornamento di Experience Manager Guides alla versione 2025.08.0, l&#39;opzione per abilitare o disabilitare la scheda personalizzata **Acrolinx** non viene più visualizzata in **Impostazioni Workspace**. (GUIDES-35261)
- I CSS personalizzati applicati a un profilo a livello di cartella per argomenti o mappe vengono ripristinati allo stile predefinito nella modalità Anteprima dopo l’aggiornamento del browser. (GUIDES-31098)
- Le operazioni **Annulla** e **Ripristina** non funzionano come previsto nella visualizzazione Source dell&#39;editor per i file DITA. (GUIDE-24914, GUIDE-25034)
- Quando si fa riferimento a una mappa DITA in un argomento utilizzando l&#39;elemento `Xref`, viene visualizzato il nome file della mappa di riferimento anziché il titolo della mappa. (GUIDES-21759)
- Quando si aggiungono più file Schematron per la convalida tramite il pannello di destra dell&#39;interfaccia dell&#39;editor, viene visualizzato un errore **I file Schematron non esistono o contengono errori** anche se i file aggiunti sono validi e non contengono errori. (GUIDES-33731)
- Le equazioni di MathML grandi o complesse non vengono visualizzate nell’editor. (GUIDES-29095)
- Quando più mappe o argomenti DITA sono aperti e uno degli argomenti è chiuso, il pulsante **>>** che mostra tutte le schede aperte si sovrappone alle altre schede aperte sulla barra delle schede. (GUIDES-31421)
- Con il **flusso di lavoro di approvazione** abilitato, il pulsante **Avvia una nuova versione** non è visibile sulla barra degli strumenti dell&#39;editor se sono aperti sia il pannello Sinistra che il pannello Proprietà contenuto. (GUIDES-29093)
- Quando i nomi dei frammenti superano la larghezza del pannello dei frammenti, vengono disposti in modo errato sulla riga successiva, con conseguente sovrapposizione con frammenti adiacenti e impatto sulla leggibilità. (GUIDES-22685)
- Quando si aggiunge lo stesso riferimento più volte a una mappa DITA, la visualizzazione **Mappa** visualizza il titolo solo per l&#39;ultima occorrenza, mentre quelle precedenti mostrano l&#39;UUID del riferimento. (GUIDES-9699)
- I file DITAVAL rimangono modificabili anche quando sono bloccati da un altro utente o quando il server ha **Disabilita modifica senza bloccare il file** abilitato e il file è aperto in modalità di sola lettura. (GUIDES-27754)
- I registri per i nodi mancanti vengono generati da processi di pulizia interni non necessari e contrassegnati in modo errato come errori, con conseguente file di registro disordinati. (GUIDES-31765)
- Quando si modifica un file Schematron (`*.sch`) e si utilizza la funzione Trova e sostituisci, il pannello Trova e sostituisci appare parzialmente fuori schermo nella parte inferiore, impedendo l&#39;accesso ai relativi campi e controlli di input. (GUIDES-38412)
- Impossibile aggiungere più **etichette versione** a un argomento dalla finestra di dialogo **Salva come nuova versione**. (GUIDES-32716)
- Quando si seleziona un&#39;immagine nell&#39;editor utilizzando la finestra di dialogo **Seleziona file**, vengono visualizzati solo i formati raster (ad esempio JPG, PNG e GIF). I file vettoriali (ad esempio con estensione ai e eps) non vengono visualizzati e non possono essere selezionati. (GUIDES-45110)
- Al momento dell&#39;aggiornamento, l&#39;impostazione `tagsView` è disattivata per impostazione predefinita, anche se il suo valore predefinito in `ui_config.json` è impostato su `true`. (GUIDES-44651)
- Nell&#39;editor, i riferimenti ai file vengono visualizzati come GUID anziché come percorsi dei file nonostante la configurazione di `xmleditor.uuid`. (GUIDES-42438)
- Quando si applicano schemi Oggetto con valori chiave simili in un argomento DITA, questi vengono evidenziati con colori quasi identici, rendendo difficile distinguerli e identificare quale schema viene applicato. (GUIDES-38472)
- Quando si modifica una mappa Schema soggetti nella vista Autore, l&#39;aggiunta dell&#39;elemento `hasInstance` attiva automaticamente la finestra di dialogo di selezione del file, richiedendo agli autori di inserire un elemento `href` indesiderato che punta a una risorsa AEM. Inoltre, il pannello **Proprietà contenuto** non viene caricato per tali mappe, impedendo agli autori di aggiornare gli attributi degli elementi nella vista Autore e richiedendo loro di utilizzare la vista Source per l&#39;aggiornamento degli attributi. (GUIDES-38164)
- Quando si modifica un file `.ditaval`, tutti i commenti XML aggiunti nella visualizzazione Source vengono rimossi quando si passa alla visualizzazione Autore e quindi si torna alla visualizzazione Source. (GUIDES-33228)
- Quando si aggiorna un’equazione in linea di MathML utilizzando l’opzione Modifica MathML dal menu di scelta rapida, il valore aggiornato non viene visualizzato finché la pagina non viene aggiornata. (GUIDES-38198)
- Quando un argomento contiene molti elementi riutilizzabili (quelli con ID) aggiunti nel pannello Riutilizzabile, alcuni elementi potrebbero non essere accessibili a causa dell’altezza fissa del contenitore. (GUIDES-37220)
- Quando si inserisce un riferimento incrociato a un file, le icone per le mappe e gli argomenti sono identiche. (GUIDES-36662)
- Durante la modifica di una mappa, i simboli speciali in `navtitle` non vengono visualizzati per `topichead` nella visualizzazione Autore. (GUIDES-35435)

## Gestione risorse

- Quando ricarichi un’immagine modificata tramite l’interfaccia utente di Experience Manager Guides, la rappresentazione originale dell’immagine viene aggiornata ma il contenuto DITA associato continua a visualizzare la versione precedente dell’immagine. (GUIDES-33693)
- Quando si tenta di spostare due o più cartelle dal percorso di origine a un percorso diverso (utilizzando lo strumento Spostamento in blocco), l’operazione non riesce se i nomi delle cartelle iniziano con la stessa stringa (ad esempio, Product e ProductImages). (GUIDES-29096)
- L&#39;eliminazione di una risorsa ricercata dall&#39;interfaccia utente di Omnisearch Assets ignora la finestra di avviso **Forza eliminazione** ed elimina direttamente la risorsa, anche quando vi si fa riferimento nel contenuto DITA esistente. (GUIDES-17232)
- Impossibile rimuovere le etichette di versione dal pannello **Cronologia versioni** nell&#39;interfaccia utente di Assets. (GUIDES-38276)
- Quando si crea un argomento in una cartella il cui nome contiene spazi, viene erroneamente creata una cartella duplicata in cui gli spazi vengono sostituiti da trattini e l&#39;argomento viene salvato in tale cartella anziché nella cartella originale. (GUIDES-41938)
- Durante la prima traduzione di mappe di grandi dimensioni, vengono creati file XML vuoti per la lingua di destinazione, con conseguente aumento del carico del server e rallentamento delle prestazioni. (GUIDES-41613)
- Nella ricerca di Assets, le risorse secondarie e i nodi di metadati (come immagini e PDF) non vengono inclusi correttamente nei risultati. Inoltre, per un predefinito di output quando si applicano filtri DITAVAL, la ricerca restituisce file DITAVAL generati internamente e creati da predefiniti condizione. (GUIDES-35418)
- Quando si caricano risorse il cui nome file contiene caratteri non validi, la risorsa non viene caricata e viene visualizzato un messaggio non corretto **Il file è bloccato da un altro utente** nonostante la risorsa sia stata sbloccata. (GUIDES-32680)

## Pubblicazione

- Quando si pubblica una mappa DITA utilizzando la linea di base su AEM Sites (con mappatura di componenti legacy), vengono pubblicati anche gli elementi mappa con l&#39;attributo `processing-role = resource-only`. (GUIDES-37649)
- In alcuni casi, la proprietà `jcr:content/fmUuidOfSource` risulta mancante nelle pagine di output di AEM Sites (con mappatura dei componenti legacy), pertanto le nuove pagine di contenuto create non sono individuabili. (GUIDES-34242)
- Il filtro dei contenuti tramite filtri DITAVal e predefiniti condizionali non funziona per la pubblicazione Salesforce. (GUIDES-33515)
- Impossibile creare un predefinito PDF nativo per una mappa se nella gerarchia del contenuto è presente una cartella con lo stesso nome. (GUIDES-33012)
- Quando l&#39;output del PDF nativo viene generato utilizzando una linea di base dinamica, il termine **PDFProject** viene visualizzato come titolo del PDF invece del titolo effettivo della mappa. (GUIDES-31102)
- La generazione dell&#39;output PDF nativo con alcuni valori di attributo `print` nei riferimenti argomento non funziona come previsto. (GUIDES-31101)
- Quando una cartella contenente mappe DITA viene spostata utilizzando l&#39;interfaccia utente di Assets o l&#39;opzione **Spostamento in blocco**, le raccolte di mappe esistenti e le raccolte di attivazione in blocco che fanno riferimento a tali mappe non vengono caricate. (GUIDES-28355)
- Quando sposti una cartella contenente una mappa con predefiniti di condizione, le condizioni non vengono applicate nell’output generato dopo lo spostamento. (GUIDES-28352)
- Quando si genera l&#39;output di AEM Sites utilizzando la mappatura dei componenti legacy, gli argomenti che utilizzano l&#39;attributo `copy-to` vengono pubblicati con il nome dell&#39;argomento `copy-from` invece del nome impostato nell&#39;attributo `copy-to`. (GUIDES-22155)
- L&#39;attivazione di una o più mappe DITA dal **dashboard di pubblicazione in blocco** genera registri di dimensioni eccessive. (GUIDES-20746)
- Durante la generazione di PDF, le regole di filtro in un file DITAVAL vengono ignorate se qualsiasi nome di proprietà contiene un punto. (GUIDES-33229)
- La pubblicazione in Salesforce mostra uno stato di completamento nell&#39;interfaccia utente anche quando una mappa DITA contenente un elemento `topichead` non riesce a pubblicare gli argomenti al suo interno. (GUIDES-32143)
- Per il predefinito di output di HTML5, la funzionalità filtro di ricerca non funziona in AEM Assets per il filtro DITAVAL, in quanto i file corrispondenti non vengono visualizzati quando si seleziona il filtro DITAVAL. (GUIDES-28231)
- Durante la generazione di un PDF nativo per una mappa DITA con più argomenti, se un argomento contiene un elemento `fig` all&#39;interno di un elemento `figgroup` insieme a un elemento `title`, il titolo `figgroup` non viene visualizzato correttamente come titolo del capitolo nel sommario. (GUIDES-23223)
- Quando si duplicano i modelli PDF dall’interfaccia utente, viene duplicato anche l’UUID, causando l’eliminazione dei file dei modelli e la generazione di output PDF errati. (GUIDES-30456)
- Durante la generazione di PDF nativi per una mappa DITA, il titolo dell&#39;elemento `example` viene riprodotto come livello di intestazione `h1`, causando incoerenza visiva e struttura del sommario non corretta. (GUIDES-19958)
- Quando lo stesso argomento viene riutilizzato in più mappe con diversi predefiniti condizionali, la pubblicazione della mappa più recente in Salesforce sovrascrive il contenuto dell’argomento, causando la visualizzazione di dati errati agli utenti delle mappe pubblicate in precedenza. (GUIDES-37806)
- Quando si pubblica un PDF nativo per una mappa che include un&#39;elaborazione condizionale o alcune mappe nidificate, l&#39;elemento `dc:title` definito nella mappa non viene visualizzato nella copertina di PDF, causando la perdita del titolo della copertina. (GUIDES-37733)
- La generazione dell&#39;output del sito AEM (mediante la mappatura di componenti compositi) per una mappa non riesce e genera un errore quando la variabile `map_title` è presente nel percorso di output. (GUIDES-36968)
- Quando nel predefinito di output Native PDF viene specificato un percorso di output con una barra finale, l’interfaccia utente aggiunge automaticamente una barra finale aggiuntiva, creando un percorso con doppia barra che in alcuni scenari causa il mancato caricamento di PDF. (GUIDES-34932)
- Quando si pubblicano pagine AEM Sites generate da contenuti DITA tramite Pubblicazione rapida o Gestisci pubblicazione, le risorse DITA associate vengono pubblicate in modo non intenzionale. (GUIDES-27967)
- Quando si pubblica una mappa in AEM Sites (utilizzando il mapping di componenti legacy), i riferimenti incrociati (`xrefs`) con `scope = peer` che eseguono il targeting dei sottoelementi di un argomento (come i paragrafi) in una mappa diversa non vengono risolti nell&#39;ID elemento specifico, ma solo nell&#39;argomento principale, causando il caricamento della pagina all&#39;inizio dell&#39;argomento anziché lo scorrimento alla sezione desiderata. (GUIDES-21802)
- Quando si pubblica una mappa DITA utilizzando la linea di base su AEM Sites (con mappatura di componenti legacy), vengono pubblicati anche gli elementi mappa con l&#39;attributo `processing-role = resource-only`. (GUIDES-34298)
- Quando le modifiche a un predefinito di output in un profilo Cartella vengono applicate alle mappe esistenti, viene reimpostato il **Contesto di pubblicazione** salvato per il predefinito AEM Sites. (GUIDES-38377)
- Il simbolo del marchio (®) non viene visualizzato sulla copertina dell&#39;output del PDF nativo quando l&#39;elemento `tm` viene utilizzato all&#39;interno del titolo di una mappa o di un bookmap. (GUIDES-28832)
- Quando si pubblica una mappa utilizzando un modello PDF nativo, il **Titolo mappa** non include il contenuto degli elementi figlio utilizzati nella mappa `title` e il filtro del contenuto corrispondente non viene applicato al titolo.(GUIDES-33730)
- I collegamenti peer tra mappe nell&#39;output di AEM Sites non vengono risolti quando puntano a un `topicref` che utilizza `chunk="to-content"`. (GUIDES-37873)
- Durante la pubblicazione, i file associati ai contrassegni basati su DITAVAL vengono spostati in una nuova cartella generata dal sistema invece di rimanere nella posizione relativa prevista nell&#39;output. (GUIDES-37564)
- Quando si utilizzano più file DITAVAL con condizioni in conflitto, l&#39;output del PDF nativo non riesce. (GUIDES-37484)
- Durante la creazione o la modifica di un argomento che include una citazione, se il campo Autore non viene aggiunto nella finestra di dialogo della citazione, il PDF non viene generato. (GUIDES-37934)
- Durante la generazione dell&#39;output di AEM Sites, i titoli delle mappe contenenti parole chiave e titoli di argomenti con l&#39;elemento `<ph>` non vengono inclusi nell&#39;output pubblicato. (GUIDES-36641)
- Il file CSS (`rhdefault.css`) viene applicato in modo errato al modello di PDF nonostante non venga fatto riferimento a alcun CSS, causando la perdita dei registri di errore del file CSS.(GUIDES-31752)
- Quando si scaricano file temporanei per una mappa con una linea di base durante la pubblicazione di un predefinito, il file `metadata.xml` fa erroneamente riferimento a `versionPath` invece che a `dampath`.(GUIDES-29815)
- Per l&#39;output PDF nativo, l&#39;elemento `<alt>` per le immagini viene ignorato, impedendo l&#39;applicazione di testo alternativo per l&#39;accessibilità. (GUIDES-29087)
- Nell&#39;output del PDF nativo, l&#39;elemento `abbreviated-form` visualizza `glossterm` anziché `glossSurfaceForm` o `glossAcronym` designato. (GUIDES-26393)
- Durante l&#39;attivazione in blocco, la creazione del pacchetto aggiunge filtri per tutti i percorsi elencati nella proprietà `fileReference` di una pagina, inclusi i percorsi esterni e peer. (GUIDES-24887)
- Quando si pubblica utilizzando un predefinito personalizzato con contenuto che contiene collegamenti a PDF senza l’ambito impostato come esterno, il processo non viene completato. (GUIDES-21708)
- La pubblicazione di Salesforce non riesce e viene generato un errore di applicazione quando esiste già un argomento con lo stesso nome e URL. (GUIDES-32390)
- La sillabazione automatica non viene applicata nell&#39;output PDF nativo, anche quando l&#39;impostazione **Usa sillabazione automatica** è abilitata per il predefinito di output. (GUIDES-19703)

## Traduzione

- Quando si ingrandisce la schermata dell&#39;interfaccia utente di traduzione, il pulsante **Invia per traduzione** si sposta sotto i puntini di sospensione e viene attivato anche senza selezionare alcuna risorsa. (GUIDES-33720)
- Quando si selezionano file con stato **Non sincronizzato** nell&#39;interfaccia utente di traduzione e la larghezza dello schermo è limitata a causa dell&#39;apertura dei pannelli Sinistra e Destra, l&#39;etichetta **Invia per traduzione** viene troncata. (GUIDES-33692)
- Quando un&#39;immagine inizialmente gestita come risorsa specifica per la lingua con una versione specifica (ad esempio, in `/en/`) viene spostata in una cartella globale con una versione aggiornata e viene eseguita l&#39;esportazione della linea di base, la nuova linea di base continua a fare riferimento a versioni obsolete specifiche per la lingua dell&#39;immagine, causando un&#39;esportazione della linea di base non riuscita. (GUIDES-39394)
- Durante l&#39;elaborazione dei progetti di traduzione creati all&#39;esterno di Experience Manager Guides, vengono generati più messaggi di registro di errore che indicano che la proprietà *`fmTarget`non è stata trovata*. (GUIDES-37804)

## Riferimento

- Durante la creazione di una linea di base dinamica, a volte l’editor non risponde a causa di più richieste API simultanee, causando l’arresto di tutte le altre operazioni. (GUIDES-39054)
- I riferimenti ad argomenti all&#39;interno di una mappa vengono erroneamente visualizzati come indiretti quando si utilizza un oggetto DITA-OT personalizzato, anche se vi si fa riferimento direttamente. Questo problema è stato risolto con la nuova esperienza linea di base. (GUIDES-19286)
- I riferimenti con `scope="peer"` non vengono inclusi correttamente nel contesto di base e la pubblicazione richiede più tempo del previsto. Questo problema è stato risolto con la nuova esperienza linea di base. (GUIDES-41823)


## Rivedere

- Quando si assegna un utente a un’attività di revisione, il menu a discesa elenca tutti gli utenti anziché solo quelli associati ai progetti selezionati, generando opzioni utente non valide. (GUIDES-37781)
- Quando un revisore completa un’attività di revisione o l’iniziatore aggiorna un’attività di revisione senza inserire commenti, nell’e-mail di notifica inviata viene visualizzato il commento precedente più recente. (GUIDES-33590)

## Rapporti

- Quando si apre un report per una mappa, si verifica un ritardo nel caricamento del pannello Filtri (GUIDES-39385)
- Il report Elenco interrotto include erroneamente collegamenti esterni, `keyrefs` validi e parole chiave risolti correttamente nell&#39;ambito della mappa corrente. (GUIDES-27774)

## Platform

- I registri di errori generati durante il caricamento di una risorsa tramite l’interfaccia utente di Assets o la creazione di un nuovo file dall’interfaccia dell’editor utilizzano erroneamente il termine `predecessor` invece di `successor` nel messaggio del registro. (GUIDES-35607)
- Se si utilizza `scope="external"` come riferimento al contenuto DAM in un argomento o in una mappa, il percorso relativo della risorsa viene sostituito da un GUID. (GUIDES-38783)
- Quando un argomento contiene un numero elevato di riferimenti collegati da cartelle con molti file, l’istanza di authoring può diventare lenta o non rispondere, in alcuni casi richiedendo il riavvio dell’istanza. (GUIDES-43547)
- Quando si tenta di salvare un argomento o una mappa, l&#39;operazione potrebbe non riuscire a intermittenza con un errore **Impossibile salvare il file**, in particolare durante l&#39;elaborazione intensiva delle risorse o i flussi di lavoro di traduzione in esecuzione in background. (GUIDES-37837)


## Problemi risolti disponibili con Editor 2.0

I seguenti problemi sono stati risolti e non si verificano più quando si utilizza l’Editor 2.0 (o Nuovo Editor):

- Quando due o più colonne vengono eliminate da una tabella, la struttura della tabella diventa incoerente o danneggiata. (GUIDES-35438)
- Quando si elimina una colonna da una tabella contenente celle unite, viene aggiunta una nuova colonna vuota. (GUIDES-30147)
- Quando si inserisce una nuova riga in una tabella esistente dal menu delle breadcrumb, la struttura della tabella cambia in modo imprevisto, con la conseguente perdita di bordi e l’aggiunta di una colonna. (GUIDES-29194)
- Nella vista Autore, se si copia e incolla una riga di tabella, il contenuto viene posizionato all&#39;esterno della tabella anziché essere inserito come nuova riga all&#39;interno della tabella. (GUIDES-24372)
- Quando un elemento di sezione selezionato mediante trascinamento del mouse in modalità Creazione viene copiato e incollato, viene convertito in elementi di paragrafo `(<p>)` invece di mantenere la struttura di sezione. (GUIDES-30023)
- Quando si modifica il testo evidenziato all&#39;interno di elementi quali step o uicontrol, il testo selezionato non viene sostituito correttamente e viene aggiunto o anteposto, generando errori di convalida. (GUIDES-24371)
- Quando la larghezza delle colonne di una tabella viene impostata utilizzando valori relativi, le colonne rimanenti non vengono regolate in modo proporzionale, causando un layout di tabella non allineato. (GUIDES-26109)
- Quando un titolo di argomento copiato viene incollato con i tag disattivati, al primo incolla viene applicato uno stile errato e il tipo nelle proprietà del contenuto viene assegnato come argomento invece che come titolo. (GUIDES-28838)
- Quando si modificano sezioni di contenuto di grandi dimensioni, lo scorrimento involontario fa sì che la vista Editor si sposti dal contenuto attivo. (GUIDES-35436)
- Quando si utilizza Backspace sugli elementi, l&#39;Editor scorre fino alla parte superiore dell&#39;argomento indipendentemente dalla posizione del cursore. (GUIDES-32520)
- Quando si utilizza il tasto freccia sinistra o freccia destra per spostarsi all’esterno dei tag in linea, il cursore si sposta inaspettatamente al primo tentativo. (GUIDES-26363)
- AEM Spellcheck funziona solo per la lingua en-US predefinita e non rispetta altre lingue. (GUIDES-14731)
- Quando nell&#39;Editor vengono sbloccati argomenti DITA di grandi dimensioni, lo stesso argomento viene riaperto in una scheda duplicata. Inoltre, viene attivato un avviso relativo al limite di tag in cui viene visualizzato `NaN` invece del numero effettivo di tag. (GUIDES-34008)
- I suggerimenti Acrolinx non vengono evidenziati correttamente nell&#39;Editor per gli argomenti di sola lettura o bloccati. (GUIDES-29614)
- Quando si crea un nuovo elemento `reltable` senza una riga di intestazione nella visualizzazione Autore, il layout della tabella cambia dopo l&#39;aggiunta di un argomento alla prima cella, causando la compressione della colonna successiva e rendendo difficile l&#39;inserimento di argomenti correlati. (GUIDES-19555)
- Quando si aggiunge un collegamento `xref` a una cella di una tabella in modalità Creazione, il collegamento non rimane contenuto all&#39;interno della cella e viene visualizzato tra celle adiacenti nella stessa riga. (GUIDES-5489)
- Quando si passa dalla visualizzazione Autore alla visualizzazione Source, la posizione del cursore non viene mantenuta e l&#39;editor torna in alto. Inoltre, negli argomenti lunghi, la posizione del cursore viene persa e si sposta in modo casuale al centro o in alto quando si passa dalla visualizzazione Autore a quella Source. (GUIDE-18114, GUIDE-21164)
- Premendo *Invio* all&#39;interno di un elemento `<li>` viene creato un nuovo elemento `<li>`, ma tornando a un elemento `<li>` precedente e premendo *Invio* il contenuto dell&#39;elemento corrente viene convertito in un elemento `<p>`, interrompendo la struttura dell&#39;elenco. (GUIDES-27505)

## Problemi noti

### Authoring

- Quando si caricano immagini contrassegnate nei file DITAVAL, le immagini si interrompono dopo un aggiornamento del browser quando l&#39;impostazione `Enable UUIDs` è disabilitata. (GUIDES-45853)
- Nell&#39;editor, `.ditval` e `.md` file diventano non modificabili quando *Approval Workflow* è abilitato. (GUIDES-42037)
- Se si seleziona un argomento in modalità Anteprima, non viene evidenziato nella vista Mappa se l&#39;argomento si trova all&#39;interno di tag di mappa segnalibro (frontmatter, capitolo, parte o batteria) o parte di contenuto ciclico. (GUIDES-42416)
- Quando un file viene aperto sia nell&#39;Editor che nel pannello Ricerca, l&#39;eliminazione dal pannello Esplora risorse rimuove il file e aggiorna l&#39;elenco Esplora risorse, ma l&#39;aggiornamento della pagina continua a visualizzare il file nel pannello Ricerca. (GUIDES-41935)

### Gestione risorse

- Nell&#39;interfaccia utente di Assets, il pulsante **Sposta** non viene attivato al primo tentativo quando sono selezionati più di 2 file o cartelle. (GUIDES-42721) <br> **Soluzione**: dopo aver selezionato più di due file o cartelle, attendere alcuni secondi prima di selezionare la cartella di destinazione.

### Rivedere

- Quando si aggiorna un&#39;attività di revisione attiva, se un argomento che fa già parte della revisione viene rimosso e quindi aggiunto di nuovo senza fare clic su Aggiorna, le informazioni relative al revisore nella scheda Revisori andranno perse. (GUIDES-38774)
- Quando un argomento in revisione viene rimosso da un&#39;attività di revisione in corso, lo stato del documento continua a rimanere **In revisione**, anche se l&#39;argomento non fa più parte di alcuna attività di revisione. (GUIDES-38709)<br>**Soluzione**: modificare lo stato del documento dell&#39;argomento da **In revisione** allo stato appropriato dalla pagina Proprietà o dal pannello Proprietà file.

### Editor 2.0

- Quando si copia e incolla il contenuto dello stesso argomento in una posizione non valida nell’editor, viene inserito un tag esterno non previsto. (GUIDES-45378)
- Se si copia e si incolla `<keywords>` all&#39;interno di `<topicmeta>` in `<keydef>` o `<topicref>`, verranno inseriti tag esterni non desiderati. (GUIDES-45800)
- Quando il contenuto viene copiato da una mappa o da un argomento tramite l&#39;opzione Copia nel menu di scelta rapida e quindi incollato, nel contenuto incollato vengono inseriti tag `<data>` aggiuntivi imprevisti. (GUIDES-45703)
- In Windows, se si copia e si incolla una riga di tabella, vengono aggiunti attributi indesiderati alla tabella, causando errori di markup e impedendo il salvataggio del documento. (GUIDES-45784)
- Trascinare la selezione attorno a una tabella o a una tabella semplice non funziona come previsto. (GUIDES-45406)
- Incollando le immagini da origini esterne, non vengono inserite nell&#39;argomento. (GUIDES-45983)
- Il contenuto MathML a cui si fa riferimento tramite `conref` non viene riprodotto correttamente. (GUIDES-46601)
- Il rendering degli attributi incompleto per gli elementi MathML e SVG interrompe le classi CSS personalizzate e la gestione degli attributi delle condizioni. (GUIDES-46371)
- Le equazioni di MathML racchiuse nei tag `foreign` e `equation-block` introducono spazi indesiderati e interrompono il comportamento di modifica. (GUIDES-46606)
- Se si trascina un elemento che contiene un riferimento a una chiave, `keyref` viene convertito in un percorso assoluto. (GUIDES-45701)
- Nell&#39;editor mappa, `Ctrl+click` su un collegamento interrotto attiva un errore dell&#39;applicazione. (GUIDES-45544)
