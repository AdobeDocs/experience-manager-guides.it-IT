---
title: Migrare contenuti non DITA
description: Scopri come eseguire la migrazione di contenuti non DITA
exl-id: cf437fb8-ed33-47af-aa7e-ffd8acd232da
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2889'
ht-degree: 0%

---

# Migrare contenuti non DITA {#id181AH0R02HT}

In questa sezione viene illustrato il processo di migrazione dei documenti non DITA in formato DITA. Le guide AEM consentono la migrazione dalle seguenti origini:

- [Microsoft Word](#id1949B040Z5Z)

- [Documenti InDesign](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Documenti di FrameMaker non strutturati](#id1949B050VUI)

- [Qualsiasi altro documento strutturato](#id1949B0590YK)


## Migrazione di documenti di Microsoft Word {#id1949B040Z5Z}

Le guide AEM consentono di migrare i documenti di Word esistenti \(`.docx`\) nei documenti di tipo argomento DITA. È necessario specificare i percorsi delle cartelle di input e di output insieme ad altri parametri e il documento viene convertito in documento DITA. A seconda del contenuto, è possibile disporre di un file .dita e di un file .ditamap.

Per convertire un documento di Word in modo corretto, è necessario che il documento sia ben strutturato. Ad esempio, il documento deve avere un Titolo, seguito da Titolo 1, Titolo 2 e così via. Ciascuna intestazione deve avere un certo contenuto. Se il documento non è ben strutturato, il processo potrebbe non funzionare come previsto.

Per impostazione predefinita, le guide AEM utilizzano [Framework di trasformazione da Word a DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Questa trasformazione dipende dalla [mappatura stile-tag](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) file di configurazione. Per poter utilizzare correttamente la trasformazione Word2DITA, è necessario prendere in considerazione le seguenti linee guida per la preparazione del documento di Word per la conversione:

>[!NOTE]
>
> Se si apportano modifiche al file di configurazione della mappatura stile-tag predefinito, è necessario aggiornare e utilizzare le linee guida di conferma per la mappatura stile aggiornata.

- Assicurarsi che il documento inizi con un Titolo, che deve essere mappato al titolo della mappa DITA. Inoltre, il Titolo deve essere seguito da alcuni contenuti regolari.

- Dopo il titolo, dovrebbero essere presenti titolo 1, titolo 2 e così via. Ogni intestazione deve contenere del contenuto. Le intestazioni vengono convertite in nuovi argomenti di tipo Concetto. La gerarchia degli argomenti generati corrisponde ai livelli Titolo nel documento. Ad esempio, Titolo 1 precede Titolo 2 e Titolo 2 precede Titolo 3.

- Il documento deve avere almeno un contenuto di tipo Titolo.

- Verificare di non disporre di immagini raggruppate. Se nel documento sono presenti immagini raggruppate, separarle.

- Rimuovere tutte le intestazioni e i piè di pagina.

- Gli stili in linea come grassetto, corsivo e sottolineato vengono convertiti in `b`, `i`, e `u` elementi.

- Tutti gli elenchi ordinati e non ordinati vengono convertiti in `ol` e `ul` elementi. Questo vale anche per elenchi nidificati, elenchi all’interno di tabelle, note o note a piè di pagina.

- Tutti i collegamenti ipertestuali vengono convertiti in `xref`.

- Il nome del file convertito si basa sul testo dell&#39;intestazione seguito da un numero di file. Il numero di file è un numero sequenziale basato sulla posizione del testo dell&#39;intestazione nel documento. Ad esempio, se il testo di un titolo è &quot;Titolo di esempio&quot; ed è il decimo titolo del documento, il nome file risultante per questo argomento sarà simile a Sample\_Heading\_10.dita.


Per convertire i documenti di Word esistenti in documenti di tipo argomento DITA, effettuare le seguenti operazioni:

1. Utilizza Gestione pacchetti per scaricare il file /libs/fmdita/config/w2d\_io.xml.

1. Personalizzare il file w2d\_io.xml scaricato.

1. Aggiungi il file nella seguente posizione nell’archivio Git di Cloud Manager:

   /apps/fmdita/config/w2d\_io.xml

   Il `w2d_io.xml` Il file contiene i seguenti parametri configurabili:

   - In `inputDir` specificare il percorso della cartella di input in cui sono disponibili i documenti di Word di origine. Ad esempio, se i documenti di Word sono memorizzati in una cartella denominata `wordtodita` in `projects` , quindi specifica il percorso come: `/content/dam/projects/wordtodita/`

   - In`outputDir` , specificare il percorso della cartella di output o mantenere il percorso di output predefinito per salvare il documento DITA convertito. Se la cartella di output specificata non esiste in DAM, il flusso di lavoro di conversione crea la cartella di output.

   - Per `createRev` , specificare se deve essere creata una nuova versione dell&#39;argomento DITA convertito \(`true`\) o meno \(`false`\).

   - In `s2tMap` , specificare la posizione del file di mapping contenente i mapping degli stili di documento di Word agli elementi DITA. La mappatura predefinita viene memorizzata nel file che si trova in:

     ```
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Per ulteriori informazioni sulla struttura di `word-builtin-styles-style2tagmap.xml` e come personalizzarlo, consulta [Stile per mappatura tag](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) in *Guida utente di DITA for Publishers*.

   - Nell&#39;elemento props2Propagate specificare le proprietà da passare alla mappa DITA. Questa proprietà è necessaria per passare i metadati predefiniti come dc:title,dc:subject,dam:keywords,dam:category dai metadati del documento alle risorse DITA convertite.

1. Esegui la pipeline di Cloud Manager per distribuire la configurazione aggiornata.

1. Dopo aver configurato i parametri richiesti in `w2d_io.xml` , accedi all’AEM e apri l’interfaccia utente Assets.

1. Passa alla posizione della cartella di input \(`wordtodita`\).

1. Caricare i documenti Word di origine in questa cartella. Per informazioni sul caricamento di contenuti in DAM, consulta [Carica contenuto DITA esistente](migrate-content-upload-existing-dita-content.md#).


Utilizzo di `config` `/config` , puoi definire uno o più blocchi di configurazioni da convertire. Il flusso di lavoro di conversione viene eseguito e l&#39;output finale sotto forma di argomento DITA viene salvato nella posizione specificata in `outputDir` elemento.

**Aggiornamenti di personalizzazione per gli utenti esistenti**

Se sei un utente esistente per le guide AEM as a Cloud Service e per l’aggiornamento dalla versione di agosto 2021 alle versioni di gennaio 2022 o successive, aggiorna le proprietà specificate man mano che vengono spostati pochi file.

>[!NOTE]
>
> Questo aggiornamento è applicabile solo se si sta già utilizzando il flusso di lavoro di conversione da Microsoft Word a DITA.

- Percorso file: /apps/fmdita/config/w2d\_io.xml
- Modifica il valore di `<s2tMap>` da /apps/dxml/word2dita/word-builtin-styles-style2tagmap.xml a /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
- Apporta le modifiche necessarie nell’archivio Git di Cloud Manager; per il servizio cloud, tutti i file in /apps vengono sovrapposti tramite Cloud Manager Git.

## Migrazione di documenti Adobe InDesign {#id195AD0B0K5Z}

Le guide AEM consentono di convertire documenti InDesign. Analogamente a FrameMaker, InDesign consente anche di creare documenti non strutturati e strutturati. I documenti non strutturati utilizzano gli stili di paragrafo e di carattere per formattare il contenuto. Il documento strutturato utilizza gli elementi e gli attributi corrispondenti.

Il processo di conversione richiede la mappatura dei formati di paragrafo e stile di carattere agli elementi DITA pertinenti. Analogamente, in caso di documenti strutturati, il file di mappatura conterrà la mappatura uno-a-uno di elementi e attributi InDesign con elementi e attributi DITA.

Il processo di conversione prevede le seguenti azioni nel back-end:

- Il *Lingua markup InDesign* Il file \(IDML\) viene decompresso in una directory di lavoro.
- Il file designmap.xml viene letto per individuare i singoli brani InDesign.
- Tutti i brani vengono uniti in un&#39;unica istanza XML. I brani &quot;vuoti&quot; vengono eliminati.
- Tutti gli elementi grafici incorporati vengono esportati.
- Preconversione di strutture standard quali tabelle e immagini in formato DITA.
- Mappatura di stili o strutture all’output finale in base al file di mappatura.
- Creazione e convalida di singoli argomenti e file di mappe DITA.
- Eliminazione dei file temporanei.

In generale, il processo di conversione richiede di: [Prepara i file InDesign per la conversione](appendix.md#id195DBF0045Z)[appendix.md\#id195DBF0045Z](appendix.md#id195DBF0045Z) e [Preparare il file di mappatura per la migrazione da InDesign a DITA](appendix.md#id194AF0003HT)[appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT), è quindi necessario seguire la determinata procedura di esecuzione del processo di conversione.

Per convertire i documenti InDesign esistenti in documenti di tipo argomento DITA, effettuare le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passare al file di configurazione predefinito disponibile nella posizione seguente:

   `/libs/fmdita/config/idml2dita_io.xml`

1. Crea un nodo di sovrapposizione del `config` cartella all&#39;interno del `apps` nodo.

1. Passa al file di configurazione disponibile nella `apps` nodo:

   `/apps/fmdita/config/idml2dita_io.xml`

   Configura i seguenti parametri in `idml2dita_io.xml` file:

   - In `inputDir` specifica il percorso della cartella di input in cui sono disponibili i documenti InDesign di origine. Se ad esempio i documenti InDesign sono memorizzati in una cartella denominata `indesigntodita` in `projects` , quindi specifica il percorso come: `/content/dam/idmlfiles/indesigntodita/`

   - In`outputDir` , specificare il percorso della cartella di output o mantenere il percorso di output predefinito per salvare il documento DITA convertito. Se la cartella di output specificata non esiste in DAM, il flusso di lavoro di conversione crea la cartella di output.

   - In `mapStyle` , specificare la posizione del file di mapping che contiene i mapping degli stili di documento InDesign agli elementi DITA. La mappatura predefinita viene memorizzata nel file che si trova in:

     ```
     /stmap.adobeidml.xml
     ```

     >[!NOTE]
     >
     > Per ulteriori informazioni sulla struttura di `stmap.adobeidml.xml` e come personalizzarlo, consulta la sezione [appendix.md\#id194AF0003HT](appendix.md#id194AF0003HT) nell&#39;appendice.

1. Salva il `idml2dita_io.xml` file.

1. Dopo aver configurato i parametri richiesti in `idml2dita_io.xml` , accedi all’AEM e apri l’interfaccia utente Assets.

1. Passa alla posizione della cartella di input \(`indesigntodita`\).

1. Carica i documenti InDesign di origine in questa cartella. Per informazioni sul caricamento di contenuti in DAM, consulta [Carica contenuto DITA esistente](migrate-content-upload-existing-dita-content.md#).


## Migrazione di documenti XHTML {#id1949B04L0Y4}

Le guide AEM consentono di convertire i documenti XHTML esistenti in documenti di tipo argomento DITA. È necessario specificare i percorsi delle cartelle di input e di output insieme ad altri parametri e i documenti vengono convertiti in formato DITA. Per convertire i documenti HTML strutturati è possibile utilizzare due metodi:

- Carica tutti i documenti nella cartella di input oppure
- Crea un file ZIP di tutti i documenti insieme ai file multimediali e caricalo nella cartella di input. Questo approccio viene generalmente utilizzato per un set di file HTML collegati tra loro ed è disponibile un sommario \(index.html\). Il file index.html contiene collegamenti a tutti i file HTML del set.

Sia che si caricino tutti i file singolarmente che in un pacchetto ZIP, il processo di conversione crea una mappatura uno-a-uno tra i file HTML e i file DITA risultanti. Ciò significa essenzialmente che è presente un file .dita creato per ciascun file .html nella cartella di input.

Per caricare i documenti in un file ZIP, è necessario considerare i seguenti punti:

- Tutti gli argomenti a cui si fa riferimento devono trovarsi all&#39;interno del file ZIP.

- Tutti i file multimediali a cui si fa riferimento devono essere inclusi nei file di argomento utilizzando il collegamento relativo.

- Crea un file index.html e aggiungi i collegamenti agli argomenti che desideri aggiungere nel sommario. Questo file index.html viene utilizzato per creare il file di mapping DITA. Nel file index.html è inoltre possibile creare un elenco di argomenti nidificati, come illustrato nell&#39;esempio di codice seguente:

  ```
  <?xml version="1.0" encoding="UTF-8"?>
  <html
  xmlns="http://www.w3.org/1999/xhtml">
      <head>
          <title>Sample Index File</title>
      </head>
      <body>
          <h1>Sample Index</h1>
          <div class="content">
              <ul class="book">
                  <li class="topicref">
                      <a href="Topic1.html">Topic 1</a>
                      <ul class="book">
                          <li class="topicref">
                              <a href="Topic1-1.html">Topic 1.1</a>
                          </li>
                          <li class="topicref">
                              <a href="Topic1-2.html">Topic 1.2</a>
                          </li>
                      </ul>
                  </li>
                  <li class="topicref">
                      <a href="Topic2.html">Topic 2</a>
                  </li>
              </ul>
          </div>
      </body>
  </html>
  ```

  Nota che ogni `ul` il tag deve avere `class` attributo impostato su `book`. Analogamente, ogni `li` del tag `class` deve essere impostato su `topicref`.

- Se utilizzi gli stili in linea, converti gli stili in linea in classi di stile basate su CSS nel file XHTML. Utilizzare quindi la mappatura degli attributi di stile per convertire gli stili basati su classi in DITA `outputclass` nel file DITA convertito.

  Durante la generazione dell&#39;output HTML o AEM Site da questi file DITA, il `outputclass` Gli attributi possono essere utilizzati per applicare la classe di stile su HTML generati o sul sito AEM in modo che corrisponda al contenuto HTML di origine.


Oltre alle considerazioni per la creazione del file ZIP, il documento XHTML deve anche essere ben strutturato. Ad esempio, il documento deve avere *Titolo*, seguito da *Titolo 1*, *Titolo 2* e così via. Ciascuna intestazione deve avere un certo contenuto. Se il documento non è ben strutturato, il processo di migrazione potrebbe non funzionare come previsto.

Per convertire un documento XHTML esistente in argomento DITA, effettuare le seguenti operazioni:

1. Utilizza Gestione pacchetti per scaricare il file /libs/fmdita/config/h2d\_io.xml.

1. Personalizzare il file h2d\_io.xml scaricato.

1. Aggiungi il file nella seguente posizione nell’archivio Git di Cloud Manager:

   /apps/fmdita/config/h2d\_io.xml

   Il `h2d_io.xml` Il file contiene i seguenti parametri configurabili:

   - In `inputDir` , specificare il percorso della cartella di input in cui sono disponibili i documenti XHTML di origine. Ad esempio, se i documenti XHTML sono memorizzati in una cartella denominata `xhtmltodita` in `projects` , quindi specifica il percorso come: `/content/dam/projects/xhtmltodita/`

   - In`outputDir` , specificare il percorso della cartella di output o mantenere il percorso di output predefinito. Se la cartella di output specificata non esiste in DAM, il flusso di lavoro di conversione crea la cartella di output.

   - Per `createRev` , specificare se deve essere creata una nuova versione dell&#39;argomento DITA convertito \(`true`\) o meno \(`false`\).

1. Esegui la pipeline di Cloud Manager per distribuire la configurazione aggiornata.

1. Dopo aver configurato i parametri richiesti in `w2d_io.xml` , accedi all’AEM e apri l’interfaccia utente Assets.

1. *\(Facoltativo\)* È inoltre possibile aggiungere la sezione dei collegamenti correlati ai documenti convertiti. Per abilitare questa funzione, effettua le seguenti operazioni:

   >[!NOTE]
   >
   > Per impostazione predefinita, la sezione dei collegamenti correlati non viene creata nei documenti convertiti.

   1. Utilizza Gestione pacchetti per scaricare il file /libs/fmdita/html2dita/h2d.xsl.

   2. Cerca il seguente parametro:

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Imposta il valore del parametro precedente su `true()`.

   4. Esegui il commit del file aggiornato nella seguente posizione nell’archivio Git di Cloud Manager:

      /libs/fmdita/html2dita/

   5. Esegui la pipeline di Cloud Manager per distribuire la configurazione aggiornata.

1. Passa alla posizione della cartella di input \(`xhtmltodita`\).

1. Carica i documenti XHTML di origine in questa cartella. Per informazioni sul caricamento di contenuti in DAM, consulta [Carica contenuto DITA esistente](migrate-content-upload-existing-dita-content.md#).


Utilizzo di `<config> </config>` , puoi definire uno o più blocchi di configurazioni da convertire. Il flusso di lavoro di conversione viene eseguito e l&#39;output finale sotto forma di argomento DITA viene salvato nella posizione specificata in `outputDir` elemento.

## Migrazione di documenti di FrameMaker non strutturati {#id1949B050VUI}

Le guide AEM consentono di convertire il FrameMaker non strutturato esistente \(`.fm` e `.book`\) in documenti DITA. Il primo passo è quello di creare mappature di stile utilizzando il FrameMaker e salvare tali impostazioni in un file con estensione sts. Quindi, se utilizzi DITA personalizzato, puoi mappare gli elementi personalizzati con i formati del FrameMaker di origine in `ditaElems.xml` file. Ad esempio, se hai creato un elemento personalizzato denominato `impnote` per gestire tutte le note importanti, puoi definire questo elemento personalizzato nel `ditaElems.xml` file. Una volta definito questo elemento personalizzato, le guide AEM non genereranno un errore durante la conversione di un documento di FrameMaker contenente `impnote` elemento.

Inoltre, se si desidera specificare alcuni attributi aggiuntivi con l&#39;elemento DITA personalizzato o valido, è possibile definirli nel file style2attrMap.xml. Ad esempio, puoi specificare `type` attributo con il valore di `important` da trasmettere con `impnote` elemento. Queste informazioni aggiuntive possono essere specificate nel file style2attrMap.xml.

Oltre a specificare

Per convertire i documenti di FrameMaker non strutturati esistenti in formato DITA, effettuare le seguenti operazioni:

1. Creare le mappature di stile nel FrameMaker e salvare tali impostazioni in un file con estensione sts.

1. Utilizza Gestione pacchetti per scaricare il file /libs/fmdita/config/ditaElems.xml.

1. Se disponi di elementi DITA personalizzati, definiscili nella `ditaElems.xml` file disponibile nella posizione seguente:

   `/libs/fmdita/config/ditaElems.xml`

1. Crea una copia del file ditaElems.xml nel percorso seguente nell’archivio Git di Cloud Manager:

   `/apps/fmdita/config/ditaElems.xml`

1. Passa al file di configurazione disponibile nella `apps` nodo:

   `/apps/fmdita/config/ditaElems.xml`

   Il `ditaElems.xml` Il file contiene un singolo parametro configurabile:

   - In `elem` , specificare il nome dell&#39;elemento personalizzato che si desidera utilizzare nei documenti DITA convertiti. Questo elemento viene trasmesso così come è nei documenti DITA generati.

1. Se desideri specificare attributi aggiuntivi, definiscili nella sezione `style2attrMap.xml` file disponibile nella posizione seguente:

   `/libs/fmdita/config/style2attrMap.xml`

1. Crea un nodo di sovrapposizione del `config` cartella all&#39;interno del `apps` nodo.

1. Passa al file di configurazione disponibile nella `apps` nodo:

   `/apps/fmdita/config/style2attrMap.xml`

   Il `style2attrMap.xml` Il file contiene i seguenti parametri configurabili:

   - In `fmStyle` , specificare il formato di origine utilizzato nel documento di FrameMaker da mappare.

   - In`ditaAttr` , specificare l&#39;attributo DITA che si desidera associare al formato di origine.

   - In `ditaVal` , specificare il valore per l&#39;attributo mappato. Se non si dispone di alcun valore, è possibile lasciare vuota questa voce.

1. Salva il `style2attrMap.xml` file.

1. Dopo aver configurato i parametri richiesti in `style2attrMap.xml` , accedi all’AEM e apri l’interfaccia utente Assets.

1. Passare al documento di FrameMaker che si desidera convertire e fare clic su di esso.

   Viene visualizzata la console Mappa DITA con l&#39;elenco dei predefiniti di output disponibili per generare l&#39;output.

1. Selezionate il formato di output DITA e configurate i parametri richiesti.

   >[!NOTE]
   >
   > È necessario utilizzare lo stesso file di impostazioni \(.sts\) creato in FrameMaker. Inoltre, specifica il Nome impostazioni e il Percorso di destinazione.

1. Fai clic su **Genera** per avviare il processo di generazione dell&#39;output.


Utilizzo di `<attrMap> </attrMap>` , puoi definire uno o più blocchi di configurazioni da convertire. A seconda del contenuto, come file convertiti potrebbero essere presenti un file .dita e un file .ditamap.

## Migrare qualsiasi altro documento strutturato {#id1949B0590YK}

Le guide AEM consentono di convertire i documenti strutturati esistenti in documenti DITA validi. È necessario specificare i percorsi delle cartelle di input e di output, il percorso del file di trasformazione, l&#39;estensione con cui viene salvato l&#39;output finale e se è necessaria o meno una nuova versione del documento.

Per convertire i documenti strutturati esistenti in formato DITA, effettuare le seguenti operazioni:

1. Utilizza Gestione pacchetti per scaricare il file /libs/fmdita/config/XSLConfig.xml.

1. Crea una copia del file XSLConfig.xml nel percorso seguente nell’archivio Git di Cloud Manager:

   `/apps/fmdita/config/XSLConfig.xml`

   Il `XSLConfig.xml` Il file contiene i seguenti parametri configurabili:

   - In `inputDir` , specificare il percorso della cartella di input in cui sono disponibili i documenti strutturati di origine. Ad esempio, se i documenti strutturati vengono archiviati in una cartella denominata `xsltodita` in `projects` , quindi specifica il percorso come: `/content/dam/projects/xsltodita/`

   - In`outputDir` , specificare il percorso della cartella di output o mantenere il percorso di output predefinito. Se la cartella di output specificata non esiste in DAM, il flusso di lavoro di conversione crea la cartella di output.

   - In `xslFolder` , specificare il percorso della cartella in cui sono archiviati i file di trasformazione XSL.

   - In ``xslPath`` , specificare la posizione del file XSL primario utilizzato per avviare il processo di conversione.

   - In ``outputExt`` specifica le estensioni del file di output finale creato dal flusso di trasformazione.

   - Per `createRev` , specificare se deve essere creata una nuova versione dell&#39;argomento DITA convertito \(`true`\) o meno \(`false`\).

1. Salva il `XSLConfig.xml` file.

1. Dopo aver configurato i parametri richiesti in `XSLConfig.xml` , accedi all’AEM e apri l’interfaccia utente Assets.

1. Passa alla posizione della cartella di input \(`xsltodita`\).

1. Carica i documenti strutturati di origine in questa cartella. Per informazioni sul caricamento di contenuti in DAM, consulta [Carica contenuto DITA esistente](migrate-content-upload-existing-dita-content.md#).


Utilizzo di `<config> </config>` , puoi definire uno o più blocchi di configurazioni da convertire. Il flusso di lavoro di conversione viene eseguito e l&#39;output finale sotto forma di argomento DITA viene salvato nella posizione specificata in `outputDir` elemento.

**Argomento padre:**[ Migrare i contenuti esistenti](migrate-content.md)
