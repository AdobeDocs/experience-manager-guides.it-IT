---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2026.06.0
description: Scopri le correzioni di bug nella versione 2026.06.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 318f2b7a530e50ca4432313650801b2293d6697e
workflow-type: tm+mt
source-wordcount: '2171'
ht-degree: 0%

---

# Sono stati risolti i problemi nella versione 2026.06.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2026.06.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizza [Novità della versione 2026.06.0](whats-new-2026-06-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.06.0](upgrade-instructions-2026-06-0.md).

## Authoring

- Quando si attiva tra i campi **Larghezza** e **Altezza** nella finestra di dialogo delle proprietà dell&#39;immagine utilizzando dimensioni basate su unità come `in`, `mm` o `px`, i valori continuano ad aumentare in modo incrementale invece di rimanere stabili. (GUIDES-45929)

## Editor 2.0

- Copiare e incollare `<keywords>` all&#39;interno di `<topicmeta>` in un `<keydef>` o `<topicref>` fa sì che le parole chiave vengano inserite all&#39;interno di tag esterni indesiderati. (GUIDES-45800)
- Le dimensioni immagine specificate con unità quali `mm` non vengono riprodotte correttamente, pertanto le immagini vengono visualizzate con le dimensioni originali anziché con le dimensioni specificate. (GUIDES-46275)
- Quando si esegue un trascinamento della selezione con la vista Tag attivata, la selezione del contenuto insieme a tag XML o DITA parziali lascia indietro i tag orfani indesiderati, causando la visualizzazione o il contenuto errati. (GUIDES-28191)
- Nella visualizzazione Tag di una tabella, premendo il tasto freccia su quando il cursore è posizionato nella cella direttamente sotto un tag di immissione compresso, il tag compresso viene ignorato e il cursore viene spostato all&#39;inizio del documento. (GUIDES-45408)
- Quando si esegue un&#39;operazione dalla barra degli strumenti contestuale della tabella, la barra degli strumenti viene chiusa in modo imprevisto, interrompendo le operazioni successive della tabella. (GUIDES-45405)
- Dopo aver utilizzato **Inserisci dopo** o **Inserisci prima** dalla visualizzazione Struttura o dalla breadcrumb, il cursore si sposta in una posizione arbitraria anziché all&#39;interno del tag appena aggiunto. (GUIDES-45147)
- Quando l&#39;opzione **Modifica MathML** non viene visualizzata correttamente in modalità di sola lettura o quando un file viene estratto da un altro utente, consente agli utenti di aggiornare il contenuto di MathML anche se il file non deve essere modificabile. (GUIDES-45172)
- Quando si elimina un commento XML utilizzando il tasto backspace, il tag di commento non viene rimosso dopo l&#39;eliminazione del relativo contenuto e l&#39;operazione di eliminazione continua nell&#39;elemento precedente. (GUIDES-45240)
- Utilizzando l&#39;opzione **Copia percorso** o **Copia UUID** per le immagini, restituisce il percorso completo della rappresentazione anziché il percorso originale della risorsa. (GUIDES-45278)
- Quando si copia e incolla il contenuto dello stesso argomento in una posizione non valida nell&#39;editor, viene inserito un tag `<foreign>` non desiderato. (GUIDES-45378)
- In Windows, se si copia e si incolla una riga di tabella, all&#39;elemento di tabella verranno aggiunti attributi imprevisti, ad esempio `data-pm-slice`, causando errori di markup che impediscono il salvataggio del documento. (GUIDES-45784)
- Se si utilizza l&#39;opzione **Copia** dal menu di scelta rapida in una mappa o in un argomento e si incolla il contenuto, verranno inseriti ulteriori `<data>` tag nell&#39;output incollato. (GUIDES-45703)
- Quando si trascina una selezione parziale da un elemento `cmd`, il contenuto non può essere rilasciato tra il testo esistente o alla fine di un altro elemento `cmd`. (GUIDES-44883)
- Quando si applica un attributo `scale` a una tabella, la tabella non viene rappresentata alle dimensioni configurate nelle modalità Creazione e Anteprima. (GUIDES-45984)
- Incollando le immagini copiate da fonti esterne come Paint o lo strumento di cattura, l&#39;immagine non viene inserita nell&#39;argomento. (GUIDES-45983)
- Il `keyref` utilizzato nel titolo di un argomento derivato da una mappa di parole chiave non viene visualizzato nel sommario o nella scheda dell&#39;argomento dopo il salvataggio, anche dopo l&#39;aggiornamento di un browser. (GUIDES-45799)
- Quando si apre un&#39;attività di revisione nell&#39;Editor utilizzando la visualizzazione affiancata per la versione con commenti, la versione viene visualizzata come Nessuna anziché come versione associata per l&#39;argomento. (GUIDES-45127)
- Quando si accede alla pagina dell&#39;attività Rivedi, le interruzioni di pagina tra gli argomenti non vengono visualizzate, determinando il rendering continuo delle sezioni di contenuto. (GUIDES-46777)
- Lo stile della pagina di revisione non è coerente con l&#39;esperienza del nuovo editor e genera un&#39;esperienza visiva incoerente (GUIDES-46061)

## Gestione risorse

- Quando una mappa contiene un `topicref` esterno che punta a una risorsa non DITA (ad esempio `.html`), la relativa anteprima non viene visualizzata nell&#39;interfaccia utente di Assets. (GUIDES-45409)
- La finestra di dialogo Bulk Move Tool (Strumento Spostamento in blocco) si sovrappone e non dispone di una barra di scorrimento quando viene selezionato un numero elevato di cartelle di origine, rendendo il campo del percorso di destinazione e i pulsanti di azione inaccessibili agli utenti che utilizzano solo il mouse. (GUIDES-45805)
- Quando la risorsa viene copiata dall&#39;interfaccia utente di Assets, viene ricevuta una notifica per `DXML reprocessing failure`. Questa notifica è fuorviante e contribuisce all’ingombro della casella in entrata poiché la copia è stata completata correttamente. (GUIDES-45012)
- Quando apri il pannello Filtro nella barra a sinistra di Assets all’interno di una cartella, il campo e i facet di ricerca rimangono disattivati fino a quando il pannello non viene chiuso e riaperto. (GUIDES-42652)
- I frammenti di contenuto e le risorse di traduzione intermedie creati durante i flussi di lavoro di traduzione vengono elaborati involontariamente dal processo di elaborazione delle risorse pianificato, causando eccezioni nei registri e un’elaborazione errata delle risorse non ancora pronte. (GUIDES-42582)

## Pubblicazione

- Quando si utilizzano i file `.plt` e `.css` nei modelli di PDF, l&#39;opzione **Genera ID** è disponibile nel menu di scelta rapida visualizzato facendo clic con il pulsante destro del mouse, anche se non è applicabile a questi tipi di file. (GUIDES-45254)
- Il pulsante **Salva** non è abilitato per impostazione predefinita quando si riapre un predefinito AEM Sites nativo appena creato dopo un aggiornamento del browser, anche se non sono state apportate modifiche. (GUIDES-45171)
- Durante la duplicazione di un predefinito PDF nativo contrassegnato come predefinito, anche il duplicato viene impostato come predefinito di default. Dovrebbe essere designato un solo predefinito alla volta. (GUIDES-44786)
- L&#39;attributo `outputclass` non viene propagato all&#39;output HTML o PDF nativo generato, impedendo alle classi personalizzate applicate alle equazioni MathML di influire sull&#39;output di cui è stato eseguito il rendering. (GUIDES-44393)
- L’attivazione in blocco dell’output di AEM Sites generato utilizzando il nuovo modello AEM Sites non riusciva, impedendo la corretta replica nell’istanza Publish. (GUIDES-44049)
- Sono stati identificati `jackson-databind` JAR vulnerabili (versione 2.9.8) in bundle con AEM Guides nel pacchetto DITA-OT. (GUIDES-43081)
- L’apertura di un output AEM Sites nativo da una raccolta mappe genera un errore che indica che la risorsa non è stata trovata, impedendo l’accesso all’output generato. (GUIDES-42065)
- L&#39;elemento `<reltable>` in una mappa DITA viene ignorato durante la generazione di PDF nativi, causando l&#39;assenza nell&#39;output di &quot;Concetti correlati&quot;, &quot;Attività correlate&quot; e sezioni di rimando generate automaticamente simili. (GUIDES-38333)
- Quando si pubblica una mappa DITA con `processing-role=resource-only` elementi in AEM Sites (con mappatura dei componenti legacy), vengono generate pagine del sito orfane per tali elementi in scenari aggiuntivi, ad esempio elementi `topicgroup` e configurazioni di contenuto specifiche. (GUIDES-37650)
- Quando si aggiunge una mappa con un nome lungo a una raccolta mappe, l’interfaccia utente della raccolta mappe viene riprodotta in un layout distorto. Questo problema è stato risolto con l&#39;insieme New Maps. (GUIDES-42062)
- Pubblicazione con il motore PDF nativo v1:
   - Quando si genera l’output del PDF nativo per determinati contenuti, in PDF viene riprodotto solo il rendering della prima pagina, nonostante il HTML intermedio contenente il contenuto completo per più pagine. (GUIDES-28270)
   - L’ordine di lettura dei contenuti nell’output PDF nativo con le impostazioni di accessibilità abilitate non è corretto. I numeri di pagina dei piè di pagina vengono letti prima del contenuto principale anziché alla fine. (GUIDES-27790)
   - La barra dei colori nell&#39;output del PDF nativo non si estende per l&#39;intera larghezza della pagina e si sovrappone quando la dimensione della pagina viene personalizzata, causando la visualizzazione di alcune caselle di colore nascoste. (GUIDES-15505)
   - Il selettore di pseudo-classe CSS `:is()` non viene rispettato nell&#39;output PDF nativo, con conseguenti differenze di stile rispetto al rendering del browser. (GUIDES-11328)

  >[!NOTE]
  >
  > I problemi sopra riportati sono stati risolti con il motore PDF nativo v2. Per ulteriori dettagli, visualizzare [Utilizzare il motore PDF nativo v2](../native-pdf/new-pdf-engine.md).

## Traduzione

- L’applicazione di una linea di base a una mappa con molte risorse ritarda il caricamento del rapporto di traduzione per la lingua selezionata, talvolta causando un timeout della richiesta prima del rendering del rapporto. (GUIDES-45508)
- I gruppi di lingue nella scheda Traduzione in Impostazioni Workspace non vengono mantenuti quando la cartella della lingua selezionata utilizza un codice locale sillabato (ad esempio, `da-DK`) invece di un formato di sottolineatura (`da_dk`). (GUIDES-37843)

## Revisione

- Descrizione comando per l&#39;icona **Cronologia versioni** mancante nel pannello sinistro dell&#39;interfaccia utente di revisione accanto al nome dell&#39;argomento. (GUIDES-45511)
- Quando si modifica un&#39;attività di revisione attiva, se un argomento che fa già parte della revisione viene rimosso e quindi aggiunto di nuovo senza selezionare **Aggiorna**, le informazioni del revisore per tale argomento vengono perse. (GUIDES-38774)
- Il riquadro dei contenuti nell’interfaccia utente Revisione visualizza una barra di scorrimento orizzontale su determinate risoluzioni dello schermo, inclusa la risoluzione consigliata di 1600 px, che causa la visualizzazione dei commenti di revisione quando il contenuto si estende oltre la larghezza del riquadro. (GUIDES-44082)

## Contenuto di apprendimento

- Quando si aggiungono domande a un quiz utilizzando l’opzione Inserisci da banca domande, le domande con risposta breve non vengono elencate nonostante l’ID domanda sia valido. (GUIDES-44942)
- Quando si inseriscono domande utilizzando l’opzione Inserisci da banca domande, la finestra di dialogo Inserisci da banca domande viene visualizzata momentaneamente o ridimensionata in modo imprevisto all’apertura. (GUIDES-45524)
- Quando si inseriscono domande utilizzando l&#39;opzione Inserisci da banca domande, si verifica un errore se il titolo della domanda contiene un&#39;immagine. (GUIDES-45383)
- La selezione di un modello di output SCORM genera un errore di applicazione quando il titolo del modello è stato modificato. (GUIDES-45521)
- I file dei sottotitoli (`.vtt`) non sono visibili nel repository o nella visualizzazione Esplora risorse dopo il caricamento in una cartella. (GUIDES-46014)
- Durante il caricamento del contenuto video nell&#39;anteprima di HTML, il percorso di origine (`src`) include un percorso di copia trasformata aggiunto anziché mantenere il percorso del file originale, impedendo al video di essere eseguito correttamente. (GUIDES-41776)
- La pubblicazione dell’output SCORM dal browser Safari fa sì che il pacchetto venga scaricato come cartella invece di un file zip, insieme a problemi di rendering e funzionalità nel contenuto generato (ad esempio, contenuto esteso, pannello a soffietto non funzionante e altro ancora). (GUIDES-45119)
- Si osserva un ritardo prima che il pulsante Avanti venga attivato per i corsi, che influisce sull’esperienza di navigazione dell’Allievo. (GUIDES-45113)
- Lo stile delle domande a risposta breve non viene visualizzato correttamente nell’output di pubblicazione nonostante venga visualizzato correttamente nell’anteprima. (GUIDES-46478)
- Quando si genera l’output PDF per i corsi contenenti video, il contenuto video non viene renderizzato e viene visualizzato solo il percorso del file invece di un’immagine segnaposto, ad esempio una miniatura video o un’immagine copertina. Il problema è stato risolto abilitando l&#39;opzione **Incorpora file multimediali** nel predefinito di output PDF nativo.(GUIDES-45117)
- Le pseudo-classi e gli elementi CSS vengono visualizzati in bianco nell’Editor della guida, rendendoli invisibili o di difficile lettura sullo sfondo dell’editor. (GUIDES-45116)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2026.06.0:

## Editor 2.0

- Il passaggio tra le modalità Source e Autore causa incongruenze nei contenuti, con parti dell’argomento che scompaiono o non vengono riportate tra le modalità. (GUIDES-47432)

- Quando si utilizzano le modifiche Track, se si rifiuta l&#39;inserimento di un testo importato viene rimosso tutto il contenuto del tag anziché solo il contenuto specifico inserito. (GUIDES-48319)

- Il pulsante **Esporta come PDF** in modalità Anteprima non esegue alcuna azione quando la barra degli strumenti dell&#39;editor viene personalizzata utilizzando `editor_toolbar.json` in un profilo di cartella. (GUIDES-47525)

- Durante l’esecuzione di operazioni di eliminazione, è possibile che si verifichino alcune incongruenze minori nello spostamento e nella navigazione del cursore tra mappe immagine, elementi strutturati, tag di formattazione in linea e blocchi non unificabili, che occasionalmente possono causare un comportamento imprevisto del cursore o dell’eliminazione. (GUIDES-46756)

- L&#39;utilizzo di `Ctrl+click` su un collegamento interrotto in un editor mappe genera un errore dell&#39;applicazione. (GUIDES-45544)

- Premendo backspace all&#39;inizio di un paragrafo immediatamente successivo al contenuto di sola lettura (ad esempio un paragrafo `conref`) è possibile eliminare o unire in modo imprevisto il paragrafo modificabile, con conseguente eliminazione imprevista del paragrafo modificabile. (GUIDES-45049)

- Quando gli indicatori di condizione vengono applicati a elementi come `bodydiv`, si verifica un overflow degli indicatori nei tag adiacenti in Visualizzazione tag completa, con conseguente rendering visivo errato. (GUIDES-44971)

- Quando si lavora nell&#39;editor, non è possibile selezionare `keyrefs` o chiavi derivate dalle mappe (comprese le voci del glossario all&#39;interno delle mappe a cui si fa riferimento negli elementi `term` o `abbreviated-form`), con conseguente peggioramento dell&#39;esperienza di authoring. (GUIDES-45790) <br> **Soluzione**: è possibile modificare il valore di `keyref` dal pannello di destra utilizzando i valori degli attributi.

- Nella visualizzazione Struttura, la riattivazione di **Mostra testo** dopo la chiusura e la riapertura di un argomento non consente di visualizzare il testo accanto ai tag elemento. (GUIDES-48320) <br> **Soluzione**: abilitare l&#39;opzione **Mostra testo**, quindi riaprire l&#39;argomento. Dopo la riapertura, il testo viene visualizzato correttamente insieme ai tag elemento.

- Quando un tag in linea viene rinominato utilizzando l&#39;opzione **Rinomina elemento**, la breadcrumb non viene aggiornata immediatamente e riflette la modifica solo dopo lo spostamento del cursore nel tag o la modifica della modalità di visualizzazione. (GUIDES-44993) <br> **Soluzione**: aggiorna il browser dopo aver rinominato il tag in linea per aggiornare la breadcrumb.

- Quando un&#39;equazione MathML viene inserita come `conref`, il rendering non viene eseguito correttamente. (GUIDES-46601) <br> **Soluzione**: racchiudere l&#39;equazione di MathML in un elemento `<p>` e utilizzare tale elemento `<p>` come origine conref.

## Revisione

- Quando un’attività di revisione viene riassegnata a un utente che non fa parte del team di progetto, l’utente può eseguire azioni di revisione nonostante la mancata iscrizione al progetto, mentre la visibilità del revisore, il tracciamento dello stato di revisione e le notifiche di delega non funzionano correttamente. (GUIDES-46602)

## Pubblicazione

- Quando si pubblicano contenuti con il filtro DITAVAL che esclude tutte le voci degli elenchi puntati tramite la profilatura condizionale, l’output mantiene erroneamente un indicatore di punto elenco vuoto invece di rimuovere l’intera struttura dell’elenco. (GUIDES-47238)

- Quando si pubblica un output del sito AEM nativo con una nuova linea di base, l&#39;elenco degli argomenti appare vuoto e non consente di visualizzare gli argomenti inclusi nella linea di base selezionata. (GUIDES-46480) <br> **Soluzione**: pubblica l&#39;output del sito AEM nativo utilizzando la linea di base precedente, che può essere configurata tramite la gestione della configurazione.





