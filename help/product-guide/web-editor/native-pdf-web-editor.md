---
title: Native PDF | Generazione output PDF
description: Scopri come utilizzare la pubblicazione PDF nativa, creare e generare un predefinito di output PDF, scaricare file temporanei dopo la generazione dell’output PDF nativa e utilizzare le variabili di lingua nelle guide AEM.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
feature: Publishing, Web Editor, Native PDF Output
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '3196'
ht-degree: 0%

---

# Pubblica output PDF

Con le guide AEM, puoi generare PDF di singoli argomenti o un intero file di mappa. Puoi pubblicare il contenuto in formato PDF utilizzando uno dei tre metodi seguenti:

* **DITA-OT**

Utilizzare questo metodo per generare un output PDF per una mappa dal dashboard delle mappe. Puoi impostare le proprietà di pubblicazione prima di generare il PDF creando un predefinito di output per la mappa aperta nel dashboard delle mappe. Per creare o modificare un predefinito di output, *Informazioni sui predefiniti di output* sezione nella sezione [Guida utente as a Cloud Service alle guide dell’AEM](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Per ulteriori informazioni sulla generazione di un PDF utilizzando il metodo DITA-OT, vedere [Genera PDF utilizzando DITA-OT](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-pdf.html).

* **FrameMaker Publishing Server (FMPS)**

Utilizzare questo metodo per generare un output PDF non solo dal contenuto DITA, ma anche dai documenti di FrameMaker (con estensione book e fm) disponibili nell&#39;archivio AEM. Il PDF può essere creato configurando un predefinito di output e pubblicato utilizzando FrameMaker Publishing Server (FMPS). Puoi progettare e configurare l’aspetto dell’output per PDF e altri formati e memorizzarlo in un file di impostazione (.sts). Questo file di impostazione viene quindi utilizzato da FMPS per generare l&#39;output per una mappa DITA o un file book. Per creare o modificare un predefinito di output, consultate  *Informazioni sui predefiniti di output* sezione nella sezione [Guida utente as a Cloud Service alle guide dell’AEM](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Per ulteriori informazioni sulla configurazione di FMPS, consulta [Genera output da documenti di FrameMaker](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Ffm-output-generatation.html).

* **Pubblicazione nativa di PDF**

Utilizza questo metodo per generare un output PDF ricco di funzioni basato sugli standard W3C CSS3 e CSS paged media. Con la pubblicazione di PDF nativi, puoi utilizzare i modelli per impostare il layout e lo stile dei contenuti e applicare varie impostazioni per perfezionare le impostazioni di PDF. Inoltre, puoi modificare e creare modelli personalizzati con l’editor di modelli.

Per ulteriori informazioni sulla pubblicazione di PDF nativi, consulta [Utilizzo della pubblicazione nativa di PDF](#native-pdf-publishing).


## Utilizzo della pubblicazione nativa di PDF {#native-pdf-publishing}

Durante l’authoring dei contenuti, è fondamentale assicurarsi che siano ottimizzati per la visualizzazione, la modifica e la stampa. Utilizzando gli standard W3C CSS3 per lo stile dei contenuti e gli standard CSS per i file multimediali di paging per le proprietà di definizione delle pagine, quali dimensioni, margini, orientamento, interruzioni di pagina, intestazioni, piè di pagina e numerazione delle pagine, è possibile impostare la visualizzazione e il layout per il documento PDF per garantire coerenza e usabilità. La funzione di pubblicazione di PDF nativi utilizza questi standard per generare un PDF.

Con la pubblicazione nativa di PDF, puoi utilizzare modelli predefiniti per garantire la coerenza del layout e della struttura del contenuto, applicare fogli di stile per modificare l’aspetto dell’output, ottimizzare PDF, impostare gli indicatori della stampante, consentire il supporto di utilità per la lettura dello schermo, impostare la conformità di PDF, i font da incorporare e molto altro.

La generazione di un PDF tramite la pubblicazione di PDF nativi presenta due aspetti:

* Utilizzo di modelli per applicare lo stile al contenuto, impostare i layout di pagina e varie impostazioni per ottimizzare le PDF. Gli autori possono scegliere di utilizzare/modificare i modelli di esempio forniti o creare modelli personalizzati e impostare opzioni di configurazione avanzate utilizzate da autori e sviluppatori.

* Crea o configura un predefinito di output PDF per controllare le impostazioni di PDF. Una volta creato un predefinito di output PDF, puoi generare il PDF.

Per ulteriori informazioni, consulta [Generare un output PDF](#generate-pdf-output).

## Creare un predefinito di output PDF {#create-output-preset}

Il primo passaggio nella generazione di un output PDF consiste nella creazione di un predefinito di output PDF, ovvero una raccolta di proprietà di pubblicazione assegnate a una mappa. Potete creare un predefinito di output per qualsiasi mappa aperta nel pannello Vista mappa o configurare un predefinito esistente per generare rapidamente un PDF per la stessa mappa.

Dal predefinito di output di PDF puoi selezionare un modello, applicare condizioni, impostare restrizioni per controllare il modo in cui un utente interagisce con il PDF, configurare impostazioni avanzate come la compressione, la conformità e altro ancora.

Per creare o configurare un predefinito di output PDF:

1. Nella scheda Output, fai clic su **Predefiniti** nella barra laterale a sinistra.
Viene visualizzato il pannello Predefinito. <br>
<img src="assets/preset-panel.png" alt="pannello predefinito" width="600">

1. Nell’output **Predefiniti** eseguire una delle operazioni seguenti:
   * Fate doppio clic su un predefinito di output PDF predefinito per visualizzarlo.
   * Fai clic sull’icona + accanto a **Predefiniti** per aggiungere un nuovo predefinito di output di **Tipo: PDF**

1. Per configurare le impostazioni di un predefinito PDF esistente:
   * Fai clic su  **Opzioni** ![opzioni](assets/options.svg) accanto al predefinito di output desiderato e seleziona **Modifica**.
È possibile utilizzare le seguenti impostazioni nella **Generale**, **Metadati**, **Layout**, **Sicurezza**, e **Avanzate** schede per configurare un predefinito di output di PDF:

**Generale**

Consente di specificare le impostazioni di output di base, ad esempio il percorso di output, il nome del file PDF e altro ancora.

| Impostazione | Descrizione |
| --- | --- |
| **Percorso di output** | Percorso all’interno dell’archivio AEM in cui è memorizzato l’output del PDF. Assicurati che il percorso di output non si trovi all’interno della cartella del progetto. Se questo campo viene lasciato vuoto, l&#39;output viene generato nella posizione di output predefinita della mappa DITA.<br>Per definire il percorso di output è inoltre possibile utilizzare le seguenti variabili predefinite. Puoi utilizzare una singola variabile o una combinazione di variabili per definire questa opzione. <br> `${map_filename}`: utilizza il nome dei file di mappa DITA per creare il percorso di destinazione. <br> `${map_title}`: utilizza il titolo della mappa DITA per creare il percorso di destinazione. <br>`${preset_name}`: utilizza il nome del predefinito di output per creare il percorso di destinazione. <br> `${language_code}`: utilizza il codice della lingua in cui si trova il file di mappa per creare il percorso di destinazione. <br> `${map_parentpath}`: utilizza il percorso completo del file di mappa per creare il percorso di destinazione.  <br>`${path_after_langfolder}`: utilizza il percorso del file di mappa dopo la cartella della lingua per creare il percorso di destinazione. |
| **File PDF** | Specificare un nome di file per il salvataggio del PDF. Per impostazione predefinita, il nome del file PDF aggiunge il nome della mappa DITA insieme al nome del predefinito. Ad esempio, ditamap è &quot;TestMap&quot; e il nome del predefinito è &quot;preset1&quot;; il nome predefinito del pdf sarà &quot;TestMap_preset1.pdf&quot;. <br>Per definire il file di PDF puoi inoltre utilizzare le seguenti variabili predefinite. Puoi utilizzare una singola variabile o una combinazione di variabili per definire questa opzione. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Applica condizioni tramite** | Per il contenuto condizionale, scegli una delle opzioni seguenti per generare un output PDF in base a tali condizioni: <br><ul> <li> **Nessuna applicazione** Seleziona questa opzione se non desideri applicare alcuna condizione alla mappa e al contenuto sorgente. <br><li> **File Ditaval** Selezionate un file DITAVAL per generare contenuto condizionale. Per selezionare, fai clic su in base a Predefinito condizione e individua il file. <br> <li> **Predefinito condizione** Seleziona un predefinito di condizione dal menu a discesa per applicare una condizione durante la pubblicazione dell’output. Questa opzione è visibile se è stata aggiunta una condizione per il file di mapping DITA. Le impostazioni condizionali sono disponibili nella scheda Predefiniti condizione della console delle mappe DITA. Per ulteriori informazioni sul predefinito di condizione, consulta [Utilizzare i predefiniti per le condizioni](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Usa linea di base** | Se è stata creata una baseline per la mappa DITA selezionata, selezionare questa opzione per specificare la versione da pubblicare. Consulta [Utilizzare la previsione](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) per ulteriori dettagli. |
| **Crea PDF con barra di modifica tra le versioni pubblicate** | Utilizza le seguenti opzioni per creare un PDF che mostri le differenze di contenuto tra due versioni utilizzando le barre di modifica:   <br><ul><li> **Linea di base della versione precedente** Scegliere la versione della baseline da confrontare con la versione corrente o con un&#39;altra baseline. Nel PDF viene visualizzata una barra delle modifiche che indica il contenuto modificato. Una barra delle modifiche è una linea verticale che identifica visivamente il contenuto nuovo o rivisto. La barra delle modifiche viene visualizzata a sinistra del contenuto inserito, modificato o eliminato. <br> **Nota**: se selezioni **Usa linea di base** e scegliere una baseline da pubblicare, il confronto verrà eseguito tra le due versioni della baseline selezionate. Ad esempio, se si sceglie la versione di base 1.3 in **Usa linea di base** e la versione 1.1 in **Linea di base della versione precedente**, il confronto verrà eseguito tra la versione 1.1 e la versione 1.3 della linea di base. <br><li> **Mostra testo aggiunto** Selezionare questa opzione per mostrare il testo inserito in verde e sottolineato. Questa opzione è selezionata per impostazione predefinita. <br> <li> **Mostra testo eliminato** Selezionare questa opzione per mostrare il testo eliminato in rosso e contrassegnato con barrato. Questa opzione è selezionata per impostazione predefinita. <br>**Nota** È inoltre possibile personalizzare lo stile della barra delle modifiche, del contenuto inserito o del contenuto eliminato utilizzando il foglio di stile.<br></ul> |
| **Flusso di lavoro di post-generazione** | Seleziona questa opzione per visualizzare un elenco a discesa contenente tutti i flussi di lavoro configurati in AEM. Puoi selezionare il flusso di lavoro da eseguire dopo il completamento del flusso di lavoro di generazione PDF. |

**Metadati**

I metadati sono la descrizione o la definizione del contenuto. I metadati sono utili per la gestione dei contenuti e per la ricerca di file su Internet.

Utilizzare la scheda Metadati per impostare i campi metadati, ad esempio il nome dell&#39;autore, il titolo del documento, le parole chiave, le informazioni sul copyright e altri campi dati per l&#39;output PDF. Puoi anche aggiungere metadati personalizzati per l’output PDF.

Questi metadati vengono mappati ai metadati della scheda Descrizione in Proprietà documento del PDF di output.

**Nota**: questi metadati sostituiscono quelli definiti a livello di libro.

<img src="assets/pdf-metadata.png" alt="scheda metadati" width="600">

Dai predefiniti di output, **seleziona PDF** > **Metadati** per aggiungere e personalizzare le opzioni dei metadati.
* **Fornisci file XMP**

  I campi di metadati possono essere compilati direttamente importando [XMP](https://www.adobe.com/products/xmp.html) (piattaforma di metadati estensibile). Puoi scaricare un esempio di file XMP da qui.

[Scarica](assets/SampleXMP.xmp)

  In alternativa, puoi generare un file XMP utilizzando Adobe Acrobat.
   1. Clic **File** > **Proprietà** in Acrobat.
   1. Sotto **Descrizione**, fai clic su **Metadati aggiuntivi**.
   1. Dal pannello a sinistra, seleziona **Avanzate**.
   1. Fai clic su **Salva**.

  Il file XMP viene salvato sul dispositivo.

* **Fornisci nomi e valori di metadati**

   1. Aggiungi il nome selezionando dall’elenco a discesa o aggiungi metadati personalizzati digitando direttamente nel campo del nome.
   1. Inserisci il valore per i metadati e fai clic sull’icona &quot;+&quot;.
I metadati vengono aggiunti all’elenco dei metadati per PDF.

Puoi anche utilizzare le variabili per definire i valori dei metadati.  È possibile utilizzare i metadati definiti per il file mappa DITA o mappa segnalibro come variabili. I metadati si trovano sotto `/jcr:content/metadata` nodo del file mappa DITA o del file di mappa di un libro.
Quando utilizzi una variabile, il relativo valore viene scelto dalle proprietà dei metadati.

Per utilizzare una variabile, è necessario definirla nel `${<variable>}` formato.

Ad esempio, una delle proprietà di metadati definite in /`jcr:content/metadata` il nodo è
`dc:title`. È possibile specificare `${dc:title}`e il valore del titolo viene utilizzato nell’output finale.

Puoi utilizzare una singola variabile o una combinazione di variabili per definire i metadati. Ad esempio: `${dc:title} ${dc:docstate}`. Puoi anche utilizzare la combinazione di una variabile e una stringa.  Esempio: `View ${dc:title} in ${dc:language}`.

Utilizza le variabili di linguaggio per definire il valore localizzato delle proprietà dei metadati. A seconda della lingua scelta, il valore localizzato viene selezionato automaticamente nell’output di PDF. Ad esempio, puoi stampare &quot;Autore&quot; come valore dei metadati in inglese e &quot;Autorin&quot; in tedesco.

Formato: `${lng:<variable name>}`. Ad esempio: `${lng:author-label}` dove `author-label` è una variabile di linguaggio.

Passa il cursore sopra <img src="./assets/info-details.svg" alt= "icona info" width="25"> per visualizzare ulteriori dettagli su di essa.


**Layout**

Utilizzare per impostare i layout di pagina e specificare le opzioni di visualizzazione della pagina per l&#39;output PDF, ad esempio Visualizzazione pagina e impostazione dei livelli di zoom.

| Impostazione | Descrizione |
| --- | --- |
| **Modello PDF** | I modelli di PDF forniscono una chiara struttura per definire i layout di pagina, lo stile del contenuto e applicare varie impostazioni all’output di PDF. Seleziona dall’elenco a discesa Modello PDF per scegliere il modello desiderato. <br> Puoi anche selezionare **Sfoglia modello** <img src="./assets/browse-templates-icon.svg"  alt= "icona Sfoglia modelli" width="25">  per scegliere un modello. In **Seleziona modello PDF** finestra di dialogo puoi anche visualizzare l’anteprima della miniatura e visualizzare il titolo e la descrizione del modello selezionato. |
| **Visualizzazione pagina** | Utilizza Visualizzazione pagina per la visualizzazione della pagina che mostra come viene visualizzato il PDF all’apertura. Seleziona dall’elenco a discesa Visualizzazione pagina per scegliere una visualizzazione preferita. <br><ul><li> **Predefinito**  Viene visualizzato come impostazione predefinita del visualizzatore PDF sul computer di un utente.  <br> <li> **Visualizzazione a pagina singola** Visualizza una pagina alla volta.   <br> <li> **Scorrimento di una pagina** Visualizza una singola pagina in una colonna verticale continua.  <br> <li> **Visualizzazione a due pagine** Visualizza due pagine affiancate alla volta. .<br> <li> **Scorrimento di due pagine** Visualizza due pagine affiancate con scorrimento continuo. </ul> |
| **Zoom** | Selezionare questa opzione per ridimensionare la visualizzazione della pagina che mostra la modalità di visualizzazione del PDF all&#39;apertura.  <br><ul><li> **Predefinito** Visualizza come impostazione predefinita del visualizzatore di PDF sul computer di un utente    <br> <li> **100%** Fa apparire la pagina nelle sue dimensioni effettive.     <br> <li> **Adatta pagina** Adatta la larghezza e l&#39;altezza della pagina al riquadro del documento. .<br> <li> **Adatta larghezza pagina** Rende la larghezza della pagina piena della larghezza del riquadro del documento.  <br> <li> **Adatta altezza pagina** Fa in modo che l&#39;altezza della pagina riempia l&#39;altezza del riquadro del documento. </ul> |

**Sicurezza**

Protect il PDF aggiungendo restrizioni per aprire e leggere il file. Utilizza le opzioni seguenti per evitare accessi non autorizzati.

| Impostazione | Descrizione |
| --- | --- |
| **Imposta password per aprire il documento** | Seleziona questa opzione per aggiungere una password sicura per visualizzare il file PDF. Specificare una password in **Password utente** campo. Gli utenti possono aprire il PDF solo immettendo la password fornita in questo campo. |
| **Impostare le restrizioni per i documenti** | Seleziona per limitare il modo in cui gli utenti possono interagire con il PDF. Specificare una password in **Password proprietario** per il funzionamento delle seguenti impostazioni di restrizione.  <br><ul><li> **Stampa** Selezionare questa opzione per consentire a un utente di stampare il PDF. <br> <li> **Stampa di qualità bozza** Selezionare questa opzione per consentire a un utente di stampare il PDF a una risoluzione inferiore.  <br> <li> **Copia del contenuto** Seleziona questa opzione per consentire a un utente di copiare il contenuto dal PDF.   <br> <li> **Annotazioni** Seleziona questa opzione per consentire a un utente di aggiungere una nota o un commento nel PDF.  <br> <li> **Modifiche al contenuto** Seleziona questa opzione per consentire a un utente di modificare il contenuto del PDF.  <br> <li> **Copia del contenuto per l’accessibilità** Seleziona questa opzione per consentire agli assistenti vocali di leggere e navigare nel contenuto in PDF.  <br>  **Assembly documenti** Seleziona questa opzione per consentire agli utenti di inserire pagine nel PDF.  <br> **Nota**: gli utenti devono immettere la password del proprietario per modificare eventuali restrizioni da File > Proprietà in Adobe Acrobat. |

**Avanzate**

Utilizza le seguenti opzioni per specificare impostazioni avanzate per unire i PDF, utilizzare la compressione, selezionare lo standard di conformità e altro ancora.

| Impostazione | Descrizione |
| --- | --- |
| **Crea PDF accessibile (con tag)** | Seleziona questa opzione per generare un PDF con i tag. Un PDF con tag consente agli assistenti vocali di leggere e navigare più facilmente in contenuti, collegamenti ipertestuali, segnalibri e così via. Ad esempio, se una tabella viene contrassegnata, l’assistente vocale saprà che sta leggendo la tabella e non solo le righe e il testo. |
| **Unisci PDF inclusi nel sommario** | Selezionare questa opzione per unire i PDF esistenti nell&#39;output aggiungendoli alla mappa DITA come file di risorse. I PDF verranno inseriti nella posizione rappresentata nella mappa e le pagine verranno incrementate di conseguenza. |
| **Incorpora font usati** | Selezionare questa opzione quando si utilizzano caratteri che potrebbero non essere installati nel computer dell&#39;utente finale. Selezionando questa opzione, i font usati vengono incorporati nel PDF, garantendo all’utente di vedere il PDF come previsto anche se i font non sono installati nel computer. <br> **Nota**: un tipo di carattere può essere incorporato solo se contiene un’impostazione del fornitore che ne consente l’incorporamento. Prima di incorporare un carattere, assicurati di disporre dell’impostazione o della licenza richiesta. |
| **Usa sillabazione automatica** | Con la sillabazione automatica attivata, le parole alla fine delle righe vengono interrotte in posizioni grammaticalmente corrette con un trattino. |
| **Abilita JavaScript** | Abilita questa opzione se disponi di un codice JavaScript da utilizzare per trasformare il contenuto in modo dinamico prima di generare un PDF. |
| **Incorporare file multimediali** | Seleziona questa opzione per includere nel PDF qualsiasi contenuto audio, video e interattivo. |
| **Utilizza la compressione completa per ottimizzare le dimensioni dei PDF** | Selezionare questa opzione se si desidera comprimere/ridurre le dimensioni di un PDF di grandi dimensioni. Ricordate che la compressione del PDF può ridurre la qualità del file. |
| **Utilizza la compressione delle immagini per ottimizzare le dimensioni dei PDF** | Seleziona questa opzione se desideri comprimere/ridurre le dimensioni delle immagini utilizzate nel PDF. La compressione di un&#39;immagine può ridurne la qualità. |
| **Usa risoluzione personalizzata (pixel per pollice)** | Si tratta della risoluzione di visualizzazione della pagina in pixel per pollice. Immetti un valore preferito nel campo che viene visualizzato quando questa opzione è selezionata. Il valore predefinito è 96 pixel per pollice. Impostate un valore più alto per adattare più contenuto in pollice e viceversa, se impostate un valore più basso. |
| **Mostra filigrana** | Selezionare questa opzione per sovrapporre una filigrana nell&#39;output. È possibile immettere una nuova stringa di testo nella casella di testo con il carattere maiuscolo nel modo desiderato. <br><br>Utilizza variabili di testo o di lingua statiche per pubblicare la versione localizzata della filigrana.  A seconda della lingua scelta, il valore localizzato viene selezionato automaticamente nell’output di PDF. Ad esempio, è possibile stampare &quot;Publisher&quot; come filigrana in inglese e &quot;Auteure&quot; in francese.  <br> Formato: `${lng:<variable name>}`. Ad esempio: `$ {lng:publisher-label}` dove `publisher-label` è una variabile di linguaggio. <br> Passa il cursore sopra <img src="./assets/info-details.svg" alt= "icona info" width="25"> per visualizzare ulteriori dettagli su di essa. |
| **Abilita equazioni MathML** | Seleziona questa opzione per eseguire il rendering delle equazioni MathML presenti nel contenuto. In caso contrario, per impostazione predefinita, le equazioni verranno ignorate. |
| **Scarica file temporanei** | Selezionare questa opzione se si desidera scaricare i file di HTML provvisori creati durante la generazione dell&#39;output di PDF nativo. Successivamente puoi scaricare i file temporanei dopo aver generato l’output. |
| **Conformità PDF** | È lo standard al quale intendi salvare il PDF per assicurarti che sia conforme. Seleziona dall’elenco a discesa per scegliere dall’elenco degli standard PDF disponibili. Per ulteriori dettagli sugli standard supportati consulta [Informazioni sugli standard PDF](https://helpx.adobe.com/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |


## Generare un output PDF {#generate-pdf-output}

Dopo aver configurato il predefinito di output, potete generare l&#39;output dal pannello Predefiniti utilizzando **Genera predefinito** funzionalità.

1. Sotto **Autore** , seleziona la scheda **Archivio** Visualizza.\
   Verrà aperto il pannello Archivio.

1. Nel pannello Archivio, aprite il file di mappa DITA in **Vista mappa**.

1. In **Output** , fare clic su **Predefiniti** per visualizzare il pannello Predefinito.
Per creare o configurare un predefinito di output, consulta [Creare un predefinito di output PDF](#create-output-preset).
1. Per salvare le impostazioni, fare clic su **Salva tutto** ![salva tutto](assets/SaveFloppy_icon.svg) nell&#39;angolo superiore sinistro della barra degli strumenti standard nella visualizzazione Output.
1. Fai clic su **Genera predefinito** ![genera predefinito](assets/generate-output.svg) nella barra superiore.
Potete visualizzare una barra di avanzamento accanto al predefinito di output selezionato nel pannello Predefiniti di output.
1. Una volta completata la generazione dell’output, fai clic su  **Visualizza output** ![visualizza output](assets/view-output.svg) nella barra superiore per visualizzare l’output.\
   A **Completato** nell&#39;angolo inferiore destro dello schermo.
Se un output non ha esito positivo, viene visualizzato il seguente messaggio di errore.
<img src="assets/error-log.png" alt="registro errori" width="250">

Per visualizzare il registro degli errori, fare clic su **Ignora**, passa il puntatore sulla scheda del predefinito selezionato e fai clic su ![opzioni](assets/options.svg) **Opzioni** > **Visualizza registro**.

### Scarica i file temporanei dopo la generazione dell’output di Native PDF

Se si seleziona la **Scarica file temporanei** nelle impostazioni avanzate, è inoltre possibile scaricare i file HTML provvisori creati durante la generazione dell&#39;output di PDF nativa. Dopo aver generato l’output, puoi scaricare i file temporanei utilizzando **Scarica file temporanei** ![scaricare file temporanei](assets/native-pdf-download-temporary-files-icon.svg)nella barra superiore. Questa funzione consente di visualizzare gli stili e i layout provvisori di HTML e di correggere o modificare gli stili CSS in base alle tue esigenze.


>[!NOTE]
>
> Il **Scarica file temporanei**  ![scaricare file temporanei](assets/native-pdf-download-temporary-files-icon.svg) viene visualizzata solo se avete generato l&#39;ultimo output di PDF utilizzando il predefinito in cui avete selezionato l&#39;opzione nella **Avanzate** scheda.



### Utilizzare le variabili di lingua

Le guide AEM forniscono anche il supporto per le variabili di lingua. Seleziona **Variabili di lingua** <img src="./assets/language-variables.svg" width="25">  nel pannello a sinistra per definire una versione localizzata delle etichette predefinite, ad esempio Nota, Attenzione e Avvertenza, oppure testo statico nell’output di PDF. Per ulteriori dettagli, consulta [Supporto per le variabili di lingua](../native-pdf/native-pdf-language-variables.md).

