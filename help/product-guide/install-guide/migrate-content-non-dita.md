---
title: Migrare contenuti non DITA
description: Scopri come eseguire la migrazione di contenuti non DITA
exl-id: 4597d1be-5426-4eba-8490-e42d0e565427
feature: Migration
role: Admin
level: Experienced
source-git-commit: 1644bfba3332b0f023aa8d70aefd2680d4220d8a
workflow-type: tm+mt
source-wordcount: '2802'
ht-degree: 0%

---

# Migrare contenuti non DITA {#id181AH0R02HT}

In questa sezione viene illustrato il processo di migrazione dei documenti non DITA in formato DITA. AEM Guides fornisce la migrazione dalle seguenti origini:

- [Microsoft Word](#id1949B040Z5Z)

- [Documenti InDesign](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Documenti di FrameMaker non strutturati](#id1949B050VUI)

- [Qualsiasi altro documento strutturato](#id1949B0590YK)


## Migrazione di documenti di Microsoft Word {#id1949B040Z5Z}

AEM Guides consente di migrare i documenti Word esistenti \(`.docx`\) nei documenti di tipo argomento DITA. È necessario specificare i percorsi delle cartelle di input e di output insieme ad altri parametri e il documento viene convertito in documento DITA. A seconda del contenuto, è possibile disporre di un file .dita e di un file .ditamap.

Per convertire un documento di Word in modo corretto, è necessario che il documento sia ben strutturato. Ad esempio, il documento deve avere un Titolo, seguito da Titolo 1, Titolo 2 e così via. Ciascuna intestazione deve avere un certo contenuto. Se il documento non è ben strutturato, il processo potrebbe non funzionare come previsto.

Per impostazione predefinita, AEM Guides utilizza il framework di trasformazione [da Word a DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Questa trasformazione dipende dal file di configurazione [mapping stile-tag](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html). Per poter utilizzare correttamente la trasformazione Word2DITA, è necessario prendere in considerazione le seguenti linee guida per la preparazione del documento di Word per la conversione:

>[!NOTE]
>
> Se si apportano modifiche al file di configurazione della mappatura stile-tag predefinito, è necessario aggiornare e utilizzare le linee guida di conferma per la mappatura stile aggiornata.

- Assicurarsi che il documento inizi con un Titolo, che deve essere mappato al titolo della mappa DITA. Inoltre, il Titolo deve essere seguito da alcuni contenuti regolari.

- Dopo il titolo, dovrebbero essere presenti titolo 1, titolo 2 e così via. Ogni intestazione deve contenere del contenuto. Le intestazioni vengono convertite in nuovi argomenti di tipo Concetto. La gerarchia degli argomenti generati corrisponde ai livelli Titolo nel documento. Ad esempio, Titolo 1 precede Titolo 2 e Titolo 2 precede Titolo 3.

- Il documento deve avere almeno un contenuto di tipo Titolo.

- Verificare di non disporre di immagini raggruppate. Se nel documento sono presenti immagini raggruppate, separarle.

- Rimuovere tutte le intestazioni e i piè di pagina.

- Gli stili in linea come grassetto, corsivo e sottolineato vengono convertiti in `b`, `i` e `u` elementi.

- Tutti gli elenchi ordinati e non ordinati vengono convertiti in `ol` e `ul` elementi. Questo vale anche per elenchi nidificati, elenchi all’interno di tabelle, note o note a piè di pagina.

- Tutti i collegamenti ipertestuali vengono convertiti in `xref`.

- Il nome del file convertito si basa sul testo dell&#39;intestazione seguito da un numero di file. Il numero di file è un numero sequenziale basato sulla posizione del testo dell&#39;intestazione nel documento. Ad esempio, se il testo di un titolo è &quot;Titolo di esempio&quot; ed è il decimo titolo del documento, il nome file risultante per questo argomento sarà simile a Sample\_Heading\_10.dita.


Per convertire i documenti di Word esistenti in documenti di tipo argomento DITA, effettuare le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passare al file di configurazione predefinito disponibile nella posizione seguente:

   `/libs/fmdita/config/w2d_io.xml`

1. Creare un nodo di sovrapposizione della cartella `config` all&#39;interno del nodo `apps`.

1. Passare al file di configurazione disponibile nel nodo `apps`:

   `/apps/fmdita/config/w2d_io.xml`

   Il file `w2d_io.xml` contiene i seguenti parametri configurabili:

   - Nell&#39;elemento `inputDir` specificare il percorso della cartella di input in cui sono disponibili i documenti di Word di origine. Se ad esempio i documenti di Word sono archiviati in una cartella denominata `wordtodita` nella cartella `projects`, specificare il percorso come: `/content/dam/projects/wordtodita/`

   - Nell&#39;elemento `outputDir` specificare il percorso della cartella di output oppure mantenere il percorso di output predefinito per salvare il documento DITA convertito. Se la cartella di output specificata non esiste in DAM, il flusso di lavoro di conversione crea la cartella di output.

   - Per l&#39;elemento `createRev`, specificare se creare una nuova versione dell&#39;argomento DITA convertito \(`true`\) o meno \(`false`\).

   - Nell&#39;elemento `s2tMap` specificare la posizione del file di mapping contenente i mapping degli stili di documento di Word agli elementi DITA. La mappatura predefinita viene memorizzata nel file che si trova in:

     ```XML
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Per ulteriori informazioni sulla struttura del file `word-builtin-styles-style2tagmap.xml` e su come personalizzarlo, vedere [Style to Tag Mapping](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) nella *Guida utente di DITA For Publishers*.

   - Nell&#39;elemento props2Propagate specificare le proprietà da passare alla mappa DITA. Questa proprietà è necessaria per passare i metadati predefiniti come dc:title,dc:subject,dam:keywords,dam:category dai metadati del documento alle risorse DITA convertite.

1. Salva il file `w2d_io.xml`.

1. Dopo aver configurato i parametri richiesti nel file `w2d_io.xml`, accedere all&#39;AEM e aprire l&#39;interfaccia utente di Assets.

1. Passare alla cartella di input \(`wordtodita`\).

1. Caricare i documenti Word di origine in questa cartella. Per informazioni sul caricamento di contenuto in DAM, vedere [Caricare contenuto DITA esistente](migrate-content-upload-existing-dita-content.md#).


Utilizzando il blocco `config` `/config`, puoi definire uno o più blocchi di configurazioni per la conversione. Il flusso di lavoro di conversione viene eseguito e l&#39;output finale sotto forma di argomento DITA viene salvato nella posizione specificata nell&#39;elemento `outputDir`.

## Migrazione di documenti Adobe InDesign {#id195AD0B0K5Z}

AEM Guides consente di convertire i documenti InDesign. Analogamente a FrameMaker, InDesign consente anche di creare documenti non strutturati e strutturati. I documenti non strutturati utilizzano gli stili di paragrafo e di carattere per formattare il contenuto. Il documento strutturato utilizza gli elementi e gli attributi corrispondenti.

Il processo di conversione richiede la mappatura dei formati di paragrafo e stile di carattere agli elementi DITA pertinenti. Analogamente, in caso di documenti strutturati, il file di mappatura conterrà la mappatura uno-a-uno di elementi e attributi InDesign con elementi e attributi DITA.

Il processo di conversione prevede le seguenti azioni nel back-end:

- Il file *IDML\ (InDesign Markup Language*) è stato decompresso in una directory di lavoro.
- Il file designmap.xml viene letto per individuare i singoli brani InDesign.
- Tutti i brani vengono uniti in un&#39;unica istanza XML. I brani &quot;vuoti&quot; vengono eliminati.
- Tutti gli elementi grafici incorporati vengono esportati.
- Preconversione di strutture standard quali tabelle e immagini in formato DITA.
- Mappatura di stili o strutture all’output finale in base al file di mappatura.
- Creazione e convalida di singoli argomenti e file di mappe DITA.
- Eliminazione dei file temporanei.

In generale, il processo di conversione richiede di [preparare i file InDesign per la conversione](appendix.md#id195DBF0045Z) e [preparare il file di mappatura per la migrazione da InDesign a DITA](appendix.md#id194AF0003HT), quindi è necessario seguire la procedura specificata di esecuzione del processo di conversione.

Per convertire i documenti InDesign esistenti in documenti di tipo argomento DITA, effettuare le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passare al file di configurazione predefinito disponibile nella posizione seguente:

   `/libs/fmdita/config/idml2dita_io.xml`

1. Per creare una configurazione personalizzata in base alle tue esigenze, crea un nodo di sovrapposizione della cartella `config` all&#39;interno del nodo `apps`.

1. Copiare i file o le cartelle seguenti dalla cartella `libs` nella cartella delle app:

   - `/fmdita/config/idml2dita_io.xml`
   - `/fmdita/idml2dita/config`
   - `/fmdita/idml2dita/xsl`

1. Passare al file di configurazione disponibile nel nodo `apps`:

   `/apps/fmdita/config/idml2dita_io.xml`

1. Aggiungere la mappatura delle configurazioni presenti nella cartella `idml12dita` all&#39;interno del file `idml2dita_io.xml`.
1. Aggiungi le seguenti proprietà nel file `idml2dita_io.xml`:

   ```
   <entry key="idml2DitaConfig">/apps/fmdita/idml2dita/config</entry>
   
   <entry key="idml2DitaXsl">/apps/fmdita/idml2dita/xsl</entry>
   ```

Configura i seguenti parametri nel file `idml2dita_io.xml`:

- Nell&#39;elemento `inputDir` specificare il percorso della cartella di input in cui sono disponibili i documenti InDesign di origine. Se ad esempio i documenti InDesign sono archiviati in una cartella denominata `indesigntodita` nella cartella `projects`, specificare il percorso come: `/content/dam/idmlfiles/indesigntodita/`

- Nell&#39;elemento `outputDir` specificare il percorso della cartella di output oppure mantenere il percorso di output predefinito per salvare il documento DITA convertito. Se la cartella di output specificata non esiste in DAM, il flusso di lavoro di conversione crea la cartella di output.

- Nell&#39;elemento `mapStyle` specificare la posizione del file di mapping che contiene i mapping degli stili di documento InDesign agli elementi DITA. La mappatura predefinita viene memorizzata nel file che si trova in:

```XML
    /stmap.adobeidml.xml
```

>[!NOTE]
>
> Per ulteriori informazioni sulla struttura del file `stmap.adobeidml.xml` e su come personalizzarlo, vedere la sezione [Preparare il file di mappatura per la migrazione da InDesign a DITA](appendix.md#id194AF0003HT) in *Appendice*.

1. Salva il file `idml2dita_io.xml`.

1. Dopo aver configurato i parametri richiesti nel file `idml2dita_io.xml`, accedere all&#39;AEM e aprire l&#39;interfaccia utente di Assets.

1. Passare alla cartella di input \(`indesigntodita`\).

1. Carica i documenti InDesign di origine in questa cartella. Per informazioni sul caricamento di contenuto in DAM, vedere [Caricare contenuto DITA esistente](migrate-content-upload-existing-dita-content.md#).


## Migrazione di documenti XHTML {#id1949B04L0Y4}

AEM Guides consente di convertire i documenti XHTML esistenti in documenti di tipo argomento DITA. È necessario specificare i percorsi delle cartelle di input e di output insieme ad altri parametri e i documenti vengono convertiti in formato DITA. Per convertire i documenti HTML strutturati è possibile utilizzare due metodi:

- Carica tutti i documenti nella cartella di input oppure
- Crea un file ZIP di tutti i documenti insieme ai file multimediali e caricalo nella cartella di input. Questo approccio viene generalmente utilizzato per un set di file HTML collegati tra loro ed è disponibile un sommario \(index.html\). Il file index.html contiene collegamenti a tutti i file HTML del set.

Sia che si caricino tutti i file singolarmente che in un pacchetto ZIP, il processo di conversione crea una mappatura uno-a-uno tra i file HTML e i file DITA risultanti. Ciò significa essenzialmente che è presente un file .dita creato per ciascun file .html nella cartella di input.

Per caricare i documenti in un file ZIP, è necessario considerare i seguenti punti:

- Tutti gli argomenti a cui si fa riferimento devono trovarsi all&#39;interno del file ZIP.

- Tutti i file multimediali a cui si fa riferimento devono essere inclusi nei file di argomento utilizzando il collegamento relativo.

- Crea un file index.html e aggiungi i collegamenti agli argomenti che desideri aggiungere nel sommario. Questo file index.html viene utilizzato per creare il file di mapping DITA. Nel file index.html è inoltre possibile creare un elenco di argomenti nidificati, come illustrato nell&#39;esempio di codice seguente:

  ```XML
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

  Ogni tag `ul` deve avere l&#39;attributo `class` impostato su `book`. Analogamente, ogni tag `class` di `li` deve essere impostato su `topicref`.

- Se utilizzi gli stili in linea, converti gli stili in linea in classi di stile basate su CSS nel file XHTML. Utilizzare quindi la mappatura degli attributi di stile per convertire gli stili basati su classi in attributi DITA `outputclass` nel file DITA convertito.

  Durante la generazione dell&#39;output di HTML o del sito AEM da questi file DITA, è possibile utilizzare gli attributi `outputclass` per applicare la classe di stile su HTML o sito AEM generato in modo che corrisponda al contenuto HTML di origine.


Oltre alle considerazioni per la creazione del file ZIP, il documento XHTML deve anche essere ben strutturato. Ad esempio, il documento deve avere un *Titolo*, seguito da *Intestazione 1*, *Intestazione 2* e così via. Ciascuna intestazione deve avere un certo contenuto. Se il documento non è ben strutturato, il processo di migrazione potrebbe non funzionare come previsto.

Per convertire un documento XHTML esistente in argomento DITA, effettuare le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passare al file di configurazione predefinito disponibile nella posizione seguente:

   `/libs/fmdita/config/h2d_io.xml`

1. Creare un nodo di sovrapposizione della cartella `config` all&#39;interno del nodo `apps`.

1. Passare al file di configurazione disponibile nel nodo `apps`:

   `/apps/fmdita/config/h2d_io.xml`

   Il file `h2d_io.xml` contiene i seguenti parametri configurabili:

   - Nell&#39;elemento `inputDir` specificare il percorso della cartella di input in cui sono disponibili i documenti XHTML di origine. Ad esempio, se i documenti XHTML sono archiviati in una cartella denominata `xhtmltodita` nella cartella `projects`, specificare il percorso come: `/content/dam/projects/xhtmltodita/`

   - Nell&#39;elemento `outputDir`, specificare il percorso della cartella di output o mantenere il percorso di output predefinito. Se la cartella di output specificata non esiste in DAM, il flusso di lavoro di conversione crea la cartella di output.

   - Per l&#39;elemento `createRev`, specificare se creare una nuova versione dell&#39;argomento DITA convertito \(`true`\) o meno \(`false`\).

1. Salva il file `h2d_io.xml`.

1. Dopo aver configurato i parametri richiesti nel file `h2d_io.xml`, accedere all&#39;AEM e aprire l&#39;interfaccia utente di Assets.

1. *\(Facoltativo\)* È inoltre possibile aggiungere la sezione dei collegamenti correlati ai documenti convertiti. Per abilitare questa funzione, effettua le seguenti operazioni:

   >[!NOTE]
   >
   > Per impostazione predefinita, la sezione dei collegamenti correlati non viene creata nei documenti convertiti.

   1. Passare al file h2d.xsl nel percorso seguente:

      /libs/fmdita/html2dita/

   2. Cerca il seguente parametro:

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Impostare il valore del parametro precedente su `true()`.
   4. Salva e chiudi il file.
1. Passare alla cartella di input \(`xhtmltodita`\).

1. Carica i documenti XHTML di origine in questa cartella. Per informazioni sul caricamento di contenuto in DAM, vedere [Caricare contenuto DITA esistente](migrate-content-upload-existing-dita-content.md#).


Utilizzando il blocco `<config> </config>`, puoi definire uno o più blocchi di configurazioni per la conversione. Il flusso di lavoro di conversione viene eseguito e l&#39;output finale sotto forma di argomento DITA viene salvato nella posizione specificata nell&#39;elemento `outputDir`.

## Migrazione di documenti di FrameMaker non strutturati {#id1949B050VUI}

AEM Guides consente di convertire i documenti di FrameMaker non strutturati esistenti \(`.fm` e `.book`\) in documenti DITA. Il primo passo è quello di creare mappature di stile utilizzando il FrameMaker e salvare tali impostazioni in un file con estensione sts. Quindi, se si utilizza DITA personalizzato, è possibile associare gli elementi personalizzati ai formati del FrameMaker di origine nel file `ditaElems.xml`. Ad esempio, se hai creato un elemento personalizzato denominato `impnote` per gestire tutte le note importanti, puoi definire tale elemento personalizzato nel file `ditaElems.xml`. Una volta definito questo elemento personalizzato, AEM Guides non genererà un errore durante la conversione del documento di FrameMaker contenente l&#39;elemento `impnote`.

Inoltre, se si desidera specificare alcuni attributi aggiuntivi con l&#39;elemento DITA personalizzato o valido, è possibile definirli nel file style2attrMap.xml. È ad esempio possibile specificare l&#39;attributo `type` con il valore di `important` da passare con l&#39;elemento `impnote`. Queste informazioni aggiuntive possono essere specificate nel file style2attrMap.xml.

Oltre a specificare

Per convertire i documenti di FrameMaker non strutturati esistenti in formato DITA, effettuare le seguenti operazioni:

1. Creare le mappature di stile nel FrameMaker e salvare tali impostazioni in un file con estensione sts.

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Se si dispone di elementi DITA personalizzati, definirli nel file `ditaElems.xml` disponibile nel percorso seguente:

   `/libs/fmdita/config/ditaElems.xml`

1. Creare un nodo di sovrapposizione della cartella `config` all&#39;interno del nodo `apps`.

1. Passare al file di configurazione disponibile nel nodo `apps`:

   `/apps/fmdita/config/ditaElems.xml`

   Il file `ditaElems.xml` contiene un singolo parametro configurabile:

   - Nel parametro `elem` specificare il nome dell&#39;elemento personalizzato che si desidera utilizzare nei documenti DITA convertiti. Questo elemento viene trasmesso così come è nei documenti DITA generati.

1. Se si desidera specificare attributi aggiuntivi, definirli nel file `style2attrMap.xml` disponibile nel percorso seguente:

   `/libs/fmdita/config/style2attrMap.xml`

1. Creare un nodo di sovrapposizione della cartella `config` all&#39;interno del nodo `apps`.

1. Passare al file di configurazione disponibile nel nodo `apps`:

   `/apps/fmdita/config/style2attrMap.xml`

   Il file `style2attrMap.xml` contiene i seguenti parametri configurabili:

   - Nel parametro `fmStyle` specificare il formato di origine utilizzato nel documento di FrameMaker che si desidera mappare.

   - Nell&#39;elemento `ditaAttr` specificare l&#39;attributo DITA che si desidera mappare con il formato di origine.

   - Nell&#39;elemento `ditaVal` specificare il valore per l&#39;attributo mappato. Se non si dispone di alcun valore, è possibile lasciare vuota questa voce.

1. Salva il file `style2attrMap.xml`.

1. Dopo aver configurato i parametri richiesti nel file `style2attrMap.xml`, accedere all&#39;AEM e aprire l&#39;interfaccia utente di Assets.

1. Passare al documento di FrameMaker che si desidera convertire e fare clic su di esso.

   Viene visualizzata la console Mappa DITA con l&#39;elenco dei predefiniti di output disponibili per generare l&#39;output.

1. Selezionate il formato di output DITA e configurate i parametri richiesti.

   >[!NOTE]
   >
   > È necessario utilizzare lo stesso file di impostazioni \(.sts\) creato in FrameMaker. Inoltre, specifica il Nome impostazioni e il Percorso di destinazione.

1. Fai clic sull&#39;icona **Genera** per avviare il processo di generazione dell&#39;output.


Utilizzando il blocco `<attrMap> </attrMap>`, puoi definire uno o più blocchi di configurazioni per la conversione. A seconda del contenuto, come file convertiti potrebbero essere presenti un file .dita e un file .ditamap.

## Migrare qualsiasi altro documento strutturato {#id1949B0590YK}

AEM Guides consente di convertire i documenti strutturati esistenti in documenti DITA validi. È necessario specificare i percorsi delle cartelle di input e di output, il percorso del file di trasformazione, l&#39;estensione con cui viene salvato l&#39;output finale e se è necessaria o meno una nuova versione del documento.

Per convertire i documenti strutturati esistenti in formato DITA, effettuare le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passare al file di configurazione predefinito disponibile nella posizione seguente:

   `/libs/fmdita/config/XSLConfig.xml`

1. Creare un nodo di sovrapposizione della cartella `config` all&#39;interno del nodo `apps`.

1. Passare al file di configurazione disponibile nel nodo `apps`:

   `/apps/fmdita/config/XSLConfig.xml`

   Il file `XSLConfig.xml` contiene i seguenti parametri configurabili:

   - Nell&#39;elemento `inputDir` specificare il percorso della cartella di input in cui sono disponibili i documenti strutturati di origine. Ad esempio, se i documenti strutturati sono archiviati in una cartella denominata `xsltodita` nella cartella `projects`, specificare il percorso come: `/content/dam/projects/xsltodita/`

   - Nell&#39;elemento `outputDir`, specificare il percorso della cartella di output o mantenere il percorso di output predefinito. Se la cartella di output specificata non esiste in DAM, il flusso di lavoro di conversione crea la cartella di output.

   - Nell&#39;elemento `xslFolder` specificare il percorso della cartella in cui sono archiviati i file di trasformazione XSL.

   - Nell&#39;elemento ``xslPath`` specificare il percorso del file XSL primario utilizzato per avviare il processo di conversione.

   - Nell&#39;elemento ``outputExt`` specificare le estensioni del file di output finale creato dal flusso di trasformazione.

   - Per l&#39;elemento `createRev`, specificare se creare una nuova versione dell&#39;argomento DITA convertito \(`true`\) o meno \(`false`\).

1. Salva il file `XSLConfig.xml`.

1. Dopo aver configurato i parametri richiesti nel file `XSLConfig.xml`, accedere all&#39;AEM e aprire l&#39;interfaccia utente di Assets.

1. Passare alla cartella di input \(`xsltodita`\).

1. Carica i documenti strutturati di origine in questa cartella. Per informazioni sul caricamento di contenuto in DAM, vedere [Caricare contenuto DITA esistente](migrate-content-upload-existing-dita-content.md#).


Utilizzando il blocco `<config> </config>`, puoi definire uno o più blocchi di configurazioni per la conversione. Il flusso di lavoro di conversione viene eseguito e l&#39;output finale sotto forma di argomento DITA viene salvato nella posizione specificata nell&#39;elemento `outputDir`.

**Argomento padre:**[ Esegui migrazione contenuto esistente](migrate-content.md)
