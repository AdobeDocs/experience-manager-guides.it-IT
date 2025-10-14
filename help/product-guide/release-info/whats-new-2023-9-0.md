---
title: Note sulla versione | Novità di Adobe Experience Manager Guides, versione di settembre 2023
description: Scopri le funzioni nuove e migliorate nella versione di settembre 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: d185d27f-0cbb-4ec6-ac65-cb69f7572c3f
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# Novità della versione di settembre 2023 di Adobe Experience Manager Guides as a Cloud Service

Questo articolo descrive le funzioni nuove e migliorate della versione di settembre 2023 di Adobe Experience Manager Guides (in seguito denominate *AEM Guides as a Cloud Service*).

Per ulteriori dettagli sulle istruzioni di aggiornamento, sulla matrice di compatibilità e sui problemi risolti in questa versione, consulta [Note sulla versione](release-notes-2023-9-0.md).

## Connessione a un&#39;origine dati e inserimento degli argomenti

AEM Guides fornisce connettori predefiniti per la connessione con le origini dati, rendendo AEM Guides un vero e proprio hub di contenuti. In questo modo è possibile risparmiare tempo e fatica, che altrimenti verrebbero utilizzati per l&#39;aggiunta o la replica manuale dei dati.

Oltre ai connettori predefiniti come JIRA e SQL (MySQL, PostgreSQL, SQL Server, SQLite), l’amministratore può anche configurare connettori per database MariaDB, H2DB, AdobeCommerce e Elasticsearch. Possono inoltre aggiungere altri connettori estendendo le interfacce predefinite.

Puoi visualizzare i connettori configurati nel pannello **Origini dati** nell&#39;Editor Web.

<img src="assets/data-sources.png" alt="Elenco origini dati nel pannello" width="300">

*Visualizza le origini dati connesse.*

È ora possibile anche creare un argomento da un&#39;origine dati connessa. Un argomento può contenere dati in vari formati, ad esempio tabelle, elenchi e paragrafi. Consente inoltre di creare una mappa DITA per tutti gli argomenti. È possibile associare i metadati all&#39;argomento quando si estrae da un&#39;origine dati.

Per ulteriori dettagli, visualizzare [Utilizzare i dati dell&#39;origine dati](../user-guide/web-editor-content-snippet.md).

## Aggiungere citazioni al contenuto

Le citazioni sono riferimenti all’origine delle informazioni aggiunte al contenuto. Le citazioni ti aiutano a stabilire credibilità e a prevenire il plagio. Le citazioni consentono ai lettori di individuare la sorgente e verificare le informazioni presentate nel testo.

In AEM Guides, puoi aggiungere citazioni o importarle e applicarle al contenuto. È possibile aggiungere queste citazioni da qualsiasi origine di libri, siti Web e giornali.

Dopo aver inserito le citazioni negli argomenti, è possibile visualizzarne l&#39;anteprima nell&#39;editor Web. Puoi anche pubblicare i contenuti con le citazioni utilizzando Native PDF.

![Citazioni elencate in un pannello](assets/citation-panel.png){width="300" align="left"}

*Visualizza l&#39;elenco delle citazioni nel pannello Citazioni.*

Per ulteriori dettagli, visualizza [Aggiungi e gestisci citazioni nel contenuto](../user-guide/web-editor-apply-citations.md).


## Da Publish a un frammento di contenuto

I frammenti di contenuto sono parti discrete di contenuto nell’AEM. Sono contenuti strutturati basati su un modello di contenuto. I frammenti di contenuto sono contenuti puri senza informazioni di progettazione o layout. Possono essere creati e gestiti indipendentemente dai canali supportati dall’AEM. La modularità e la riutilizzabilità dei frammenti di contenuto determinano maggiore flessibilità, coerenza, efficienza e gestione più semplice.

Ora AEM Guides offre un modo per pubblicare un argomento o gli elementi all’interno di un argomento in un frammento di contenuto. Puoi creare una mappatura basata su JSON tra un argomento e un modello per frammenti di contenuto. Utilizza questa mappatura per pubblicare in un frammento di contenuto il contenuto presente in alcuni o in tutti gli elementi di un argomento.

Sfrutta la potenza di AEM Guides e dei frammenti di contenuto e utilizza i frammenti di contenuto in qualsiasi sito AEM. Puoi anche estrarre i dettagli tramite API supportate da frammenti di contenuto.

![opzione per pubblicare il frammento di contenuto](assets/content-fragment-publish.png){width="550" align="left"}

*Publish argomento di un frammento di contenuto.*

Per ulteriori dettagli, visualizzare [Publish in un frammento di contenuto](../user-guide//publish-content-fragment.md).

## Revisione dei miglioramenti

AEM Guides fornisce ora una funzionalità di revisione migliorata con le seguenti funzionalità:

### Cerca argomenti di revisione

La conduzione delle recensioni è una caratteristica fondamentale di AEM Guides. Aiuta i revisori a rivedere i documenti loro assegnati .
È ora possibile cercare un argomento immettendo una parte del testo del titolo o del percorso file nella barra di ricerca della visualizzazione argomenti del pannello di revisione. È inoltre possibile scegliere di visualizzare tutti gli argomenti o visualizzare gli argomenti con commenti. Per impostazione predefinita, è possibile visualizzare tutti gli argomenti presenti nell&#39;attività di revisione. Per ulteriori dettagli, visualizzare [Rivedi argomenti](../user-guide/review-topics.md).

![Cerca in un pannello degli argomenti di revisione](assets/review-search-topic.png){width="800" align="left"}

*Cerca un argomento di revisione nel pannello di revisione.*



## Framework di estensione delle guide

Crea pacchetti personalizzati sopra AEM Guides per fornire estensibilità utilizzando AEM Guides Extension Framework. Questi pacchetti sono utili per sviluppatori e consulenti e consentono l’estensibilità ai componenti nell’editor. Possono essere indirizzati a pulsanti, finestre di dialogo e elenchi a discesa e aggiungere JavaScript personalizzati che possono interagire facilmente con l’interfaccia utente di AEM Guides.



## Miglioramenti di Native PDF

I seguenti miglioramenti apportati a Native PDF sono stati apportati nella versione di settembre 2023 per rendere AEM Guides un prodotto più robusto:



### Ordinare le pagine nell’output di PDF

Puoi mostrare o nascondere le seguenti sezioni nel PDF e anche disporre l’ordine in cui devono essere visualizzate nell’output PDF finale:

* Sommario
* Capitoli e argomenti
* Elenco delle figure
* Elenco delle tabelle
* Indice
* Glossario
* Citazione
* Layout di pagina

Se non desideri visualizzare una particolare sezione nell’output PDF, puoi nasconderla disattivando l’interruttore.

Per ulteriori dettagli, visualizzare [Ordine pagine](../native-pdf/components-pdf-template.md#page-order).

### Unisci pagine

In un output di PDF nativo per impostazione predefinita, tutte le sezioni iniziano su una nuova pagina. È ora possibile unire una sezione alla pagina precedente o a quella successiva. In questo modo la sezione viene pubblicata continuando con la pagina selezionata nell’output di PDF e non vi è alcuna interruzione di pagina tra le pagine.

Per ulteriori dettagli, visualizzare la descrizione della funzione **Unisci pagine** nella sezione [Ordine pagine](../native-pdf/components-pdf-template.md#page-order).

### Inizia qualsiasi capitolo dalla pagina corrente

È possibile impostare le impostazioni di configurazione di base per l&#39;avvio di un capitolo da una pagina pari o dispari, la struttura del sommario e definire il formato della linea guida per le voci del sommario.

Ora è anche possibile iniziare un capitolo dalla pagina corrente. Se scegli di farlo, tutti i capitoli vengono pubblicati in continuazione senza interruzioni di pagina. Ad esempio, se un capitolo termina a metà della pagina 15, anche il capitolo successivo inizia dalla quindicesima pagina.

Per ulteriori dettagli, visualizzare la descrizione della scheda **Generale** in [Impostazioni avanzate di PDF](../native-pdf/components-pdf-template.md#advanced-pdf-settings-advanced-pdf-settings).

### Pagine statiche

Puoi anche creare layout di pagina personalizzati e pubblicarli come pagine statiche nell’output di PDF. Questo consente di aggiungere qualsiasi contenuto statico come note o pagine vuote.

Per ulteriori dettagli, visualizzare la descrizione della funzionalità **Pagine statiche** nella sezione [Ordine pagine](../native-pdf/components-pdf-template.md#page-order).


### Variabili nei riferimenti incrociati

Potete utilizzare le variabili per definire un riferimento incrociato. Quando utilizzi una variabile, il relativo valore viene selezionato dalle proprietà.

Ora puoi anche utilizzare {figure} e {table}.
Utilizzare {figure} per aggiungere un riferimento incrociato al numero di figura. Il numero di figura viene selezionato dagli stili di numerazione automatica definiti per la didascalia delle figure.

Utilizzare {table} per aggiungere un riferimento incrociato al numero di tabella. Il numero di tabella viene selezionato dagli stili di numerazione automatica definiti per la didascalia.

Per ulteriori dettagli, visualizzare [Riferimenti incrociati](../native-pdf/components-pdf-template.md##cross-references).



### Riprogettazione dell’editor CSS

Ora l’editor CSS è stato riprogettato per offrire una migliore esperienza utente con selettori e proprietà di stile.

#### Miglioramento della finestra di dialogo Aggiungi stile

Ora puoi utilizzare selettori personalizzati per aggiungere stili complessi. Il nuovo campo Selettore consente di aggiungere selettori personalizzati oltre alla combinazione di Classe, Tag e Pseudo classe. Ad esempio, è possibile creare lo stile `table a.link` per tutti i collegamenti ipertestuali all&#39;interno di una tabella.

![aggiunta di stili nei modelli pdf nativi](assets/add-styles-native-pdf.png){width="300" align="left"}

*Aggiungi i dettagli per il nuovo stile.*

#### Personalizzare le proprietà dello stile

Ora AEM Guides presenta un nuovo pannello delle proprietà nella sezione di anteprima relativa agli stili. Potete modificare le proprietà degli stili in modo più efficiente e rapido dal pannello delle proprietà.


## Supporto per più definizioni di soggetti in una singola definizione di enumerazione

Ora puoi definire una o più definizioni dei soggetti in una mappa e le definizioni di enumerazione in un&#39;altra mappa, quindi aggiungere il riferimento alla mappa. I riferimenti di enumerazione dei soggetti vengono risolti nella stessa mappa o nella mappa di riferimento.

Ora puoi anche definire le condizioni e applicarle ad alcuni elementi specifici di un argomento.  Le condizioni sono visibili solo per questi elementi specifici e non per tutti gli altri elementi.

Per ulteriori dettagli sulla gestione delle definizioni gerarchiche delle definizioni e delle enumerazioni dei soggetti, vedere la descrizione della caratteristica Schema soggetto nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).





## Selezionare tutti i predefiniti in una raccolta mappe

È possibile non solo attivare un predefinito singolo e tutti i predefiniti di profilo di cartella, ma anche attivare tutti i predefiniti per una mappa DITA in un&#39;unica operazione.
![modificare una raccolta di mappe](assets/edit-map-collection-cs.png){width="800" align="left"}\
*Selezionare tutti i predefiniti in una raccolta mappe.*

Per ulteriori dettagli, visualizzare [Utilizza raccolta mappe per la generazione dell&#39;output](../user-guide/generate-output-use-map-collection-output-generation.md).


## Supporto dei PDF nativi nel dashboard Publish in blocco


Con la funzione Bulk Activation di AEM Guides, puoi attivare in modo rapido e semplice il contenuto dall’istanza di authoring a quella di pubblicazione. Nella mappa Bulk Activation puoi includere il predefinito di output PDF nativo, l’output Sito AEM, PDF, HTML5, Personalizzato e JSON.
Per ulteriori dettagli, visualizzare [Attivazione in blocco del contenuto pubblicato](../user-guide/conf-bulk-activation.md).

## Migliorato strumento di spostamento in blocco

Ora, in qualità di amministratore, puoi utilizzare il migliorato strumento Sposta in blocco per spostare cartelle con molti file da una posizione all’altra.
È possibile utilizzare la finestra di dialogo Sfoglia file per selezionare le cartelle di origine che si desidera spostare. È inoltre possibile selezionare il percorso di destinazione per spostare le cartelle di origine. Seleziona l&#39;icona ![info](assets/info-icon.svg) {width="25" align="left"} accanto a un campo per visualizzare ulteriori informazioni.

Per ulteriori dettagli, visualizzare [Sposta i file in blocco](../user-guide/authoring-file-management.md#move-files-bulk).


## Esperienza di anteprima migliorata dal menu di scelta rapida

Utilizza il menu di scelta rapida per visualizzare rapidamente in anteprima il file (.dita, .xml, audio, video o immagine) senza aprirlo. Ora è possibile ridimensionare il riquadro di anteprima e, se il contenuto contiene un collegamento di riferimento, è possibile selezionarlo per aprirlo in una nuova scheda.

![Riquadro di anteprima &#x200B;](assets/quick-preview_cs.png){width="800" align="left"}

*Anteprima del file nel riquadro.*

Per ulteriori dettagli sul menu di scelta rapida, vedere la descrizione della funzionalità **Opzioni per un file** nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).


## Utilizzare le variabili per la data e l&#39;ora correnti nelle opzioni Percorso di destinazione, Nome sito o Nome file

Durante la generazione di output nel sito o nei PDF AEM, è possibile utilizzare le variabili per impostare le opzioni **Percorso di destinazione**, **Nome sito** o **Nome file**. È ora possibile utilizzare anche le variabili `${system_date}` e `${system_time}`. Queste variabili consentono di aggiungere la data e l’ora correnti a queste opzioni.

Scopri come [utilizzare le variabili per impostare le opzioni Percorso di destinazione, Nome sito o Nome file](../user-guide/generate-output-use-variables.md).
