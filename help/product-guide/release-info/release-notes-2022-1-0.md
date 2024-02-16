---
title: Note sulla versione per [!DNL AEM Guides], versione di gennaio 2022
description: Versione di gennaio di [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: b2da77fa-f17c-440b-be59-acaafcd9a57c
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 0%

---

# Versione di gennaio di [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Aggiornamento alla versione di gennaio

Aggiorna il tuo attuale [!DNL Adobe Experience Manager Guides] as a Cloud Service (in seguito denominato [!DNL AEM Guides] as a Cloud Service) eseguendo le seguenti operazioni:
1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
1. Aggiorna `<dox.version>` proprietà in `/dox/dox.installer/pom.xml` file del codice Git dei tuoi Cloud Service in 2022.1.78.
1. Esegui il commit delle modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione di gennaio di [!DNL AEM Guides] as a Cloud Service.

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate da [!DNL AEM Guides] Versione as a Cloud Service di gennaio 2022.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Non compatibile | Aggiornamento 2020 4 e versioni successive |
| | |


### Connettore ossigeno

| [!DNL AEM Guides] Versione cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.1.0 | 2.4.0 | 2.4.0 | 2,2 | 2,2 |
|  |  |  |  |  |


## Nuove funzioni e miglioramenti

### Pubblicazione basata su articolo

Con la versione di gennaio, è stata introdotta una funzione di pubblicazione basata su articoli integrata nell’editor web. È possibile utilizzare la funzione di pubblicazione basata su articoli per generare in modo incrementale l&#39;output di uno o più argomenti o pubblicare il contenuto in una piattaforma della Knowledge Base.

Questa funzione consente agli utenti di creare la mappa DITA in modo additivo e pubblicare argomenti quando e come sono pronti. Dopo aver pubblicato la mappa, utilizza la funzione di pubblicazione basata su articoli per ottenere una pubblicazione incrementale solo per gli articoli aggiornati.

![Pubblicazione basata su articolo](assets/article-based-publishing.png)

Oltre all&#39;AEM, puoi utilizzare questa funzione esclusiva per pubblicare i tuoi articoli su tutti i portali della knowledge base, ad esempio Salesforce. Questa funzione viene fornita anche con un modello di contenuto OOTB, basato sui componenti core AEM, che consente di creare un archivio dei contenuti tecnici basato sulla conoscenza. L’aspetto eccezionale di questo modello è che è completamente personalizzabile in base ai requisiti organizzativi e può supportare anche casi di utilizzo come portali Intranet aziendali.
È inoltre possibile filtrare gli articoli in base allo stato del documento e all&#39;ora di modifica.

Questo articolo on-the-go basato sulle esigenze di pubblicazione non solo offre un controllo completo sulla pubblicazione dei contenuti, ma riduce anche il tempo complessivo di pubblicazione dei contenuti aggiornati.
Quando pubblichi gli articoli utilizzando questo modello, può anche trasmettere i metadati alle pagine pubblicate.
Per ulteriori dettagli, consulta *Pubblicazione basata su articolo dall’editor web* nella Guida utente.

### Editor Web migliorato

Nell’editor web sono stati introdotti numerosi miglioramenti e nuove funzioni:

* Il supporto per lo schema soggetto è stato aggiunto anche nell’editor web. È ora possibile creare e utilizzare lo schema soggetto utilizzando il pannello Schema soggetto. Con l&#39;aggiunta dello schema argomento, è ora possibile utilizzare metadati e tassonomia aziendali propri.

![Schema soggetto](assets/subject-scheme-panel.png)

* In questa versione è stato introdotto un nuovo strumento per il glossario, che consente di gestire i glossari in blocco. Questo strumento consente di convertire rapidamente il testo in glossario e glossario in termini in blocco per una mappa selezionata o per argomenti aperti.

![Punto attivo glossario](assets/glossary-hotspot-tool.png)

* È stata aggiunta la funzionalità di aggiornamento nel pannello Contenuto riutilizzabile, che consente di aggiornare rapidamente il contenuto riutilizzabile nei file di riferimento.
* Il nuovo indicatore della copia di lavoro indica se la copia corrente del file è sincronizzata o meno con la versione salvata.

![Indicatore di versione](assets/version-update-indicator.png)

* Il filtro di ricerca nel pannello Archivio e la finestra di dialogo di navigazione dei file sono stati migliorati per fornire ulteriori opzioni di filtro, che possono essere ulteriormente personalizzate.

![Filtri di ricerca nell’archivio](assets/repository-filter-search.png)

* È ora possibile caricare i file con estensione docx dall&#39;editor Web.

### Autore con FrameMaker

Ora è possibile creare e pubblicare i documenti in FrameMaker. Il FrameMaker viene fornito con un connettore predefinito per Adobe Experience Manager. In FrameMaker è disponibile un&#39;interfaccia di facile utilizzo che consente di gestire le versioni dei documenti in un ambiente distribuito e collaborativo.

Dopo aver creato il contenuto, FrameMaker consente di pubblicare i documenti in diversi formati: PDF, HTML5, EPUB e DITA. È inoltre possibile eseguire varie operazioni di gestione dei file, ad esempio l&#39;estrazione, l&#39;estrazione con gli elementi dipendenti, l&#39;archiviazione, l&#39;aggiornamento e così via.
Per eseguire l’authoring con FrameMaker in [!DNL AEM Guides] FrameMaker di utilizzo as a Cloud Service versione 2020.4 e successive.

### Nuovo dashboard di traduzione

Nell’editor web è stata introdotta una nuova dashboard di traduzione con le seguenti funzioni:

* Ordinamento, ricerca e filtro dell&#39;elenco degli argomenti.
* Filtra il contenuto per tipo di riferimento: riferimenti diretti o indiretti.
* Navigazione semplice per trovare un progetto esistente durante l’avvio di una richiesta di traduzione.
* È stato introdotto un meccanismo di traduzione multilingue per evitare la creazione di più progetti per ogni lingua quando viene avviata una richiesta di traduzione per più lingue.
* È stata introdotta una configurazione per nascondere la scheda di traduzione nel dashboard delle mappe. Per impostazione predefinita, è visibile. Puoi scegliere di tradurre il contenuto utilizzando il dashboard delle mappe o l’editor web.

![Dashboard di traduzione](assets/translation-from-web-editor.png)

### Pubblicazione avanzata

* Gli autori possono ora passare metadati a livello di mappa e di argomento alla pubblicazione DITA-OT. Questa funzione è utile quando i modelli di PDF personalizzati sono progettati per utilizzare le proprietà dei metadati dei file come tag, autore, stato del documento e altro ancora.

![Metadati DITA-OT](assets/custom-meta-data-output-preset.png)

* È stata aggiunta una nuova configurazione per consentire agli utenti di mantenere o eliminare le versioni degli argomenti che vengono eliminati quando **Elimina e crea** viene utilizzata nella generazione dell’output del sito AEM.

### Gestione file migliorata

Durante l’utilizzo dei file in AEM Assets è ora possibile visualizzare i seguenti miglioramenti:
* Sono state introdotte una nuova esperienza di caricamento dei file e una nuova finestra di dialogo per la scelta di una strategia di risoluzione dei conflitti.

![Conflitto di caricamento file](assets/file-upload-name-conflict.png)

* Possibilità di creare una nuova versione del file caricato con la possibilità di impedire la sovrascrittura di un file estratto.
* Ora è possibile visualizzare un&#39;anteprima delle immagini direttamente dalla visualizzazione Cronologia versioni. Inoltre, per i file DITA e non DITA, Cronologia versioni mostra separatamente le informazioni sulla versione corrente.

![Miniatura cronologia versioni](assets/version-history-preview-image.png)

* Ogni volta che l&#39;utente crea un file DITA, il nome del file predefinito viene visualizzato in piccolo maiuscolo per essere in linea con lo scenario di creazione di cartelle AEM native.

### Nuova funzione di esportazione dei rapporti

I rapporti sono molto utili per identificare lo stato del contenuto. [!DNL AEM Guides] as a Cloud Service fornisce vari rapporti per assumere il controllo del contenuto. Ora non solo puoi visualizzare i rapporti, ma puoi anche esportare i dati del rapporto in un file CSV per visualizzarli e condividerli con il tuo team più ampio. I dati dei rapporti possono fornire un rapido sguardo a eventuali collegamenti interrotti o immagini mancanti.

![Esportazione report](assets/export-report.png)

### Migliore esperienza di aggiornamento di Oxygen DAM

Quando si aggiornano i file dal server AEM in Oxygen, viene visualizzato un messaggio di avvertenza se nella sessione corrente di Oxygen sono presenti file non salvati. È possibile scegliere di annullare l&#39;operazione di aggiornamento per salvare eventuali file non salvati. Senza questa funzione, gli utenti perdevano informazioni non salvate nei loro documenti.


### Altri miglioramenti funzionali

* Ora puoi creare un nuovo **Progetto Dita** modello sotto **/apps/projects/templates** percorso.
* Ora scarica il predefinito **ui_config.json** dai profili delle cartelle. Questa può essere utilizzata per unire le modifiche personalizzate dalla **ui_config.json** durante l&#39;aggiornamento.
* Non è necessario cancellare la cache del browser anche quando sono presenti nuove versioni dei file JS.

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Editor web

* I conref appaiono di colore rosso anche quando non sono rotti. (8239)
* Il valore per l&#39;attributo condizionale non viene compilato automaticamente quando si seleziona Aggiungi tutte le proprietà nell&#39;editor DITAVAL. (8234)
* Gli autori non sono in grado di inserire un’immagine in un argomento utilizzando un percorso relativo. (8112)
* Nella pagina delle attività di revisione non vengono visualizzati i file multimediali se nel nome del file sono presenti spazi. (8111)
* I parametri di conversione Ph aggiunti nella cella della tabella vengono visualizzati in rosso. (8083)
* I collegamenti nell’attività di revisione non verranno aggiornati quando vengono spostati i file in revisione. (8080)
* L’editor web non esegue correttamente il rendering delle immagini con proprietà di ridimensionamento impostate su 75% o su un valore superiore. (8073)
* Le immagini GIF vengono sottoposte a rendering come immagini statiche nell’Editor web. (8024)
* Un riferimento conkeyref in un elemento nota non viene visualizzato nell&#39;anteprima o nell&#39;output dell&#39;editor Web. (8006)
* xref a un elemento che è esso stesso un conref non viene risolto nell’editor. (7933)
* Il rendering del titolo con chiave non viene eseguito correttamente nell’anteprima dell’editor e nel pannello Archivio. (7909)
* I frammenti con caratteri speciali non vengono memorizzati correttamente. (7908)
* Il salvataggio di un argomento dopo la formattazione delle equazioni MathML genera un errore. (7954)
* keydef con (tm) non vengono riprodotti correttamente nell&#39;editor e l&#39;output del sito AEM conteneva simboli TM duplicati. (7859)
* Il trascinamento di uno snippet non funziona come per le DTD. (7758)
* HTML ignora le dimensioni definite personalizzate per gli elementi grafici. (7718)
* l&#39;attributo conrefend non viene aggiornato quando il file di origine viene spostato. (7698)
* L’utilizzo di documenti di riferimento di tipo argomento causa diversi problemi all’interfaccia utente. (7656)
* I file DITAVAL non vengono visualizzati quando l&#39;autore aggiunge ditavalref in una mappa. (7594)
* Spazio imprevisto in ogni spazio vuoto `<entry>` quando l&#39;attributo outputclass viene aggiunto a `<tgroup>` elemento. (7532)
* Il pulsante Origine non funziona per gli argomenti aperti tramite la dashboard delle mappe. (7465)
* Con la funzione di stampa gradevole vengono inserite righe e spazi vuoti che possono essere visualizzati quando il file viene aperto in FrameMaker o ossigeno. (7408)
* Le mappe con href=&quot;/&quot; in uno qualsiasi degli argomenti non vengono pubblicate sui siti AEM. (7405)
* Sono stati riscontrati problemi di prestazioni nell’editor quando la mappa principale presenta un numero elevato di chiavi. (7400)
* Lo stato del documento per una mappa con modello personalizzato non viene ereditato dal profilo degli stati corrispondente. (7359)
* `<tm>` elemento renderizzato in modo errato come elemento blocco. (7286)
* I modelli duplicati vengono visualizzati nel pannello dei modelli dell’editor quando viene creato un nuovo modello. (5814)
* I modelli definiti in ui_config per le immagini per l’impostazione di un attributo aggiuntivo non sono applicabili nei casi di trascinamento della selezione. (5713)
* L’aspetto predefinito di uicontrol nella menucascata non è corretto. (5483)
* I modelli personalizzati per Argomento/Mappa non mostrano il nuovo nome nell’interfaccia utente. Il nome viene visualizzato come &quot;Topic&quot;/&quot;Map&quot; (Argomento/Mappa) invece del nome configurato. (4958)
* Possibilità di cancellare la rootmap dalle impostazioni delle preferenze utente. (8534)
* Una raccolta di mappe appena creata non viene elencata, anche dopo l’aggiornamento della pagina.(8603)
* Impossibile chiudere l&#39;argomento sbloccato. (8545)
* Il passaggio tra la modalità di origine e la modalità di modifica contrassegna l’argomento come sporco e richiede che il contenuto venga salvato nuovamente.(8524)
* Il pannello Riutilizza contenuto si blocca durante la ricerca di caratteri speciali `[` o `*` .(8279)
* Il cursore non viene visualizzato nella barra di ricerca quando si apre la finestra di dialogo Inserisci elemento utilizzando la scelta rapida da tastiera Alt+Invio.(7912)
* L’opzione di ricerca cerca solo nei nomi dei file e non nel contenuto. (7784)


### Connettore ossigeno

* I file la cui cartella principale contiene caratteri speciali restituiscono un errore durante il caricamento in ossigeno. (8054)
* Quando un documento appena creato viene aperto in ossigeno, viene generato l&#39;errore &quot;Impossibile trovare GUID&quot;. (7856)
* L&#39;opzione Check-in è disattivata dopo che il file è stato estratto dall&#39;AEM mediante Modifica in ossigeno. (7471)


### Rivedi

* La sincronizzazione in tempo reale non funziona per i commenti. (7661)

### Dashboard mappa

* Impossibile visualizzare il contenuto di riferimento nel titolo di un argomento nella scheda degli argomenti o dei rapporti della dashboard delle mappe. (8263)
* Output AEM Sites | jcr:title della pagina del sito generata non viene aggiornato quando viene aggiornato il titolo dell&#39;argomento DITA. (8131)
* Il download di MAP non scarica i file video utilizzati negli argomenti. (8070)
* I file multimediali non vengono scaricati quando il tag dell’oggetto viene utilizzato tramite l’API di scaricamento della mappa dei libri. (8057)
* Nella scheda Rapporti viene visualizzato un rapporto errato se un argomento contiene conref to file il cui titolo inizia con conref. (4698)
* La finestra di dialogo Applica etichette nella scheda Baseline non visualizza le etichette nel menu a discesa. (8455)

### Pubblicazione

* La creazione di PDF non riesce per la prima volta quando si seleziona Abilita controllo delle versioni. (8053, 8294)
* Lo spazio vuoto viene aggiunto automaticamente dopo un tag &quot;tm;&quot; nell’output del sito AEM. (7964)
* Impossibile visualizzare i video di YouTube nell’output del sito AEM. (7401)
* Il filtro per etichetta non riesce per il contenuto di riferimento dopo che l’utente fa clic su Sfoglia tutti gli argomenti nella scheda della linea di base del dashboard delle mappe. (7388)
* Pubblicazione argomento con elemento `<tm>` il valore della proprietà SM o reg non viene visualizzato correttamente nell&#39;output generato. (7239)
* Per la pubblicazione della linea di base con l’immagine non viene selezionata la versione più recente dell’immagine nell’output pubblicato. (7231)
* Gli argomenti di riferimento relativi vengono visualizzati nella scheda della linea di base. (5424)
* La pubblicazione incrementale per un argomento il cui titolo contiene conkeyref non funziona come previsto. 4474
* Il titolo della pagina non viene utilizzato per la generazione dell’URL di output anche se questa impostazione è selezionata. (8257)
* Pubblicazione della linea di base con selezione della versione corrente delle immagini anziché del nodo bloccato. Questo viene visualizzato anche se il nome di un file contiene spazio o caratteri speciali. (8274, 8322)
* La pubblicazione incrementale non riesce per la mappa DITA con lo schema del tipo soggetto con mapref. (8218)
* Viene aggiunto un valore Null ogni volta che viene aggiunta una mappa al dashboard di pubblicazione in blocco. (8695)
* Quando si utilizza la pubblicazione della linea di base con l’immagine come riferimento nell’argomento, l’immagine non viene pubblicata nell’output. (8564)
* La pubblicazione non riesce con un’eccezione se la linea di base utilizzata nella pubblicazione dei siti AEM viene eliminata. (8572)
* La rigenerazione dell&#39;argomento non funziona. (8091)
* Si sono verificati problemi con la pubblicazione delle note a piè di pagina nelle tabelle. (4709)

### AEM Assets

* Sono stati riscontrati problemi di prestazioni durante l’esecuzione della selezione/eliminazione su un enorme set di contenuti nell’interfaccia utente di Assets. (8238)
* La funzione di ricerca salvata (raccolta avanzata) si interrompe se si aggiunge il predicato DITA ai filtri di ricerca. (8048)
* Il ripristino dell’immagine alla versione precedente non funziona. (DXML-7903)
* L’opzione Elimina è visibile anche per gli autori che non dispongono dell’autorizzazione per l’eliminazione. (7322)
* La sovrapposizione CCMS per l’editor risorse interrompe il rendering dell’opzione Elimina. (8093)
* Impossibile eliminare il profilo del documento. (8604)
* I riferimenti si interrompono quando si esegue &quot;Seleziona tutto&quot; e si sposta il contenuto multimediale/Dita_Content in un&#39;altra cartella. (8621)
* Nello spostamento delle risorse si verificano riferimenti errati nell’origine. (8627)
* La vista a elenco fisso non viene caricata. (8542)

### Importazione dei contenuti

* Conversione da HTML a DITA | Una tabella con &quot;tr&quot; con voci &quot;td&quot; vuote causa l’inserimento di righe aggiuntive nell’output. (8132)
* Conversione da HTML a DITA | Se un HTML ha una tabella con più tbody, l’operazione non riesce, ad eccezione di. (7940)
* Conversione da HTML a DITA | si verifica un errore se il HTML di origine contiene commenti. (7937)
* L&#39;importazione di file DITA 1.3 causa la trasformazione di alcuni href in collegamenti non corretti. (8019)

## Problemi noti

L’Adobe ha identificato i seguenti problemi noti per [!DNL AEM Guides] Versione as a Cloud Service di gennaio 2022.


### Problemi noti relativi alla soluzione alternativa

Utilizza la soluzione alternativa specificata per i seguenti problemi noti:

* L’autenticazione web non funziona per il connettore ossigeno su Mac.
  **Soluzione alternativa**: per il momento, usa il connettore ossigeno su Windows.

* Nel browser Firefox, i commenti di revisione non possono essere importati senza aprire la visualizzazione affiancata.
  **Soluzione alternativa**: utilizza il browser Chrome per il momento.

* I riferimenti si interrompono quando si spostano immagini o file multimediali che contengono spazio nei nomi dei file.
  **Soluzione alternativa**: rinominare il file e rimuovere gli spazi dal nome del file prima di spostarli.

* Il dashboard delle mappe non viene caricato in modo intermittente nell’ultima versione del browser Chrome.
  **Soluzione alternativa**: aggiorna la pagina del dashboard delle mappe.

### Altri problemi noti

* Se l&#39;ossigeno è collegato a [!DNL AEM Guides] utilizzando l’autenticazione web, la disconnessione non riesce.
* Impossibile riassegnare le attività di revisione agli utenti.
* Nell’interfaccia utente di Map Collection sono presenti problemi, come se il testo fosse distorto e **Seleziona tutto** funzionalità non funziona correttamente.
