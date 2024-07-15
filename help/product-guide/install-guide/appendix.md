---
title: Appendice
description: Scopri come preparare i file InDesign per la conversione
exl-id: 02da0e61-7a73-4c4c-9bd7-2664d90fa728
feature: InDesign File Conversion
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2851'
ht-degree: 0%

---

# Appendice {#id195AD0L60Y4}

## Prepara i file InDesign per la conversione {#id195DBF0045Z}

L&#39;InDesign offre agli autori un set completo di funzioni per la creazione di documenti attraenti e complessi. Spesso ciò significa che le varie parti di un documento vengono posizionate sulla pagina visivamente, ma senza alcun tentativo di fornire un flusso tra tali cornici di testo. Se l&#39;ordine di lettura &#39;*1}&#39; delle cornici di testo non è definito, il file IDML conterrà brani che potrebbero non seguire alcun ordine significativo.* Il risultato finale sarà uno o più argomenti DITA con paragrafi, tabelle e immagini in ordine casuale.

Anche se è possibile modificare il contenuto DITA in un ordine ragionevole in un editor DITA, è molto più semplice correggere il file InDesign prima di creare il file IDML. Questa operazione può essere eseguita senza modificare l&#39;aspetto del documento di origine. Ha anche il vantaggio di rendere accessibile il documento di origine definendo correttamente l&#39;ordine di lettura.

***Threading cornici di testo***

L&#39;InDesign utilizza il termine *&#39;threading&#39;* per il processo di collegamento di un frame a un altro. Per ulteriori dettagli sulle cornici di testo di threading, vedi l&#39;argomento *[Threading text](https://helpx.adobe.com/in/indesign/using/threading-text.html)* nella documentazione di InDesign.

***Frame sovrapposti***

Alcuni documenti InDesign utilizzano fotogrammi sovrapposti non filettati per motivi di layout. Potrebbe essere molto difficile unire questo contenuto al thread principale. L&#39;opzione migliore potrebbe essere quella di modificare il risultato nell&#39;ambiente DITA.

***Storie InDesign***

Ogni flusso concatenato di contenuto in un documento InDesign è denominato &quot;*brano*&quot;. Per ottenere i migliori risultati, si consiglia di mantenere limitato il numero di storie. Tuttavia, alcune parti del documento potrebbero non essere necessarie nell&#39;output DITA. Ad esempio, i piè di pagina sono raramente necessari, ma possono essere visualizzati nel mezzo di un argomento se non vengono gestiti con attenzione.

Il modo più semplice per escludere il testo non richiesto nel documento è quello di assegnargli un *Tag paragrafo* speciale che viene utilizzato solo per il contenuto indesiderato. Ad esempio, invece di riutilizzare un *\[Paragrafo base\]* per il piè di pagina, crea un tag *Piè di pagina* dedicato. Quindi nel file MapStyle imposta semplicemente i paragrafi *Piè di pagina* da eliminare in questo modo:

```XML
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Mappatura ai doctype DITA***

È essenziale che il documento di origine disponga di almeno uno stile di paragrafo o un elemento che possa contrassegnare l&#39;inizio di un argomento. Nei documenti viene in genere utilizzato *Titolo1* come nome dei titoli di primo livello del documento. È quindi possibile creare una mappatura da tale stile a un doctype DITA specifico. Se il documento è ben organizzato e l&#39;utilizzo di *Intestazione1* è costante, si otterranno buoni risultati.

***Più tipi di documenti DITA***

Se alcuni dei *paragrafi Heading1* devono essere convertiti in doctype DITA diversi, duplicare lo stile di paragrafo in InDesign. Assegna a questi stili un nome facile da riconoscere, ad esempio *Intestazione1\_genAttività* o *Intestazione1\_risoluzione dei problemi*, a seconda delle necessità. Quindi, impostate il file mapStyle come mostrato di seguito:

```XML
<doctypes>
   <doctypeParaRule style="Heading1" local="0" mapToDoctype="concept">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_genTask" local="0" mapToDoctype=" generalTask">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_troubleshooting" local="0"mapToDoctype=" troubleshooting">
      <attributeRules createID="true"/>
   </doctypeParaRule>
</doctypes>
```

***Documenti InDesign strutturati***

L&#39;InDesign ha una relazione debole con XML. Sebbene un documento possa includere una DTD XML e il brano principale possa essere valido rispetto a tale DTD, è anche possibile creare documenti ibridi in cui parte del contenuto è XML, ma non è inclusa alcuna DTD. Questi sono i casi indesiderati per una conversione riuscita in DITA. Se un documento contiene parti XML, provare a salvare l&#39;output in formato XML e verificare se i risultati sono accettabili. In caso contrario, il contenuto DITA includerà anche contenuto non valido o potrebbe non riuscire completamente.

***Formattazione tabella***

La conversione dalle regole di formattazione della tabella InDesign alla formattazione della tabella equivalente in DITA è un processo complesso. Ciò è dovuto alle funzioni di formattazione avanzate disponibili nei file di origine rispetto alle opzioni di base fornite dal modello di tabella Oasis \(CALS\) utilizzato in DITA. Viene fornito l&#39;allineamento verticale e orizzontale del testo e fornisce risultati simili, anche se il testo giustificato è sempre giustificato in base alla direzione del testo, mentre l&#39;InDesign consente l&#39;allineamento giustificato a sinistra e a destra.

Anche in questo caso, la gestione InDesign dei separatori di colonna e di riga è molto più efficiente delle opzioni di base del modello di tabella Oasis. InDesign fornisce quattro bordi di cella: tipo di bordo \(solido o motivo\), spessore del bordo, colore del bordo, tinta del bordo, colore di distanza del bordo e tinta di distanza del bordo. È necessario eseguire il mapping di tutti questi elementi ai bordi destro e inferiore di ogni cella \(elemento di immissione\) in cui le uniche opzioni disponibili sono 0 o 1: nascondere il bordo o visualizzarlo.

Le regole di confine in InDesign possono essere applicate ai seguenti livelli:

- Stili tabella
- Stili celle
- Sostituzioni locali su ogni cella

Il processo di conversione da InDesign a DITA applica la regola del bordo nel modo seguente:

- Gli stili di tabella sono mappati all&#39;attributo `colspec/@colsep` per le regole verticali. Le regole orizzontali sono mappate all&#39;attributo `row/@rowsep`. In entrambi i casi, se il bordo non è definito, l&#39;attributo non viene creato.
- Gli stili di cella sono mappati agli attributi `entry/@colsep` e `entry/@rowsep`. Questi valori sovrascriveranno qualsiasi righello di bordo derivato da Stile tabella.
- Le sostituzioni locali applicano la formattazione direttamente alla cella e sostituiscono Stili tabella e Stili cella.

***Modelli alternativi***

Gli stili di tabella InDesign consentono di alternare le regolazioni di colonne e celle. Anche se questa funzione è supportata per la conversione, i risultati saranno evidenti solo quando un gruppo di pattern è mappato per mostrare la regola \(1\) e l&#39;altro gruppo di pattern è mappato per nascondere la regola \(0\).

## Preparare il file di mappatura per la migrazione da InDesign a DITA {#id194AF0003HT}

La conversione DITA corretta richiede un file di mapping corrispondente al contenuto del documento di origine. Per i documenti InDesign non strutturati, è necessario mappare tutti gli stili di paragrafo e di carattere disponibili. Per i documenti InDesign strutturati XML è necessario mappare tutti gli elementi della DTD associata.

I file di mappatura per i documenti InDesign non strutturati e strutturati sono diversi. Ciò è dovuto ai requisiti di elaborazione più complessi per la conversione del contenuto sorgente non strutturato in DITA.

Di seguito è riportato un esempio di file di mappatura:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE styleMap SYSTEM "mapStyle.dtd">
<styleMap xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="mapStyle.xsd" >
   <doctypes>
      <mapDoctypeParaRule root="itpx:stories" mapToDoctype="map">
         <attributeRules createID="true">
            <addNew name="outputclass" value="map"/>
         </attributeRules>
      </mapDoctypeParaRule>
      <doctypeParaRule style="Heading 1" local="0" mapToDoctype="concept">
         <attributeRules createID="true"/>
      </doctypeParaRule>
      <doctypeParaRule style="Heading A" local="0" mapToDoctype="topic">
         <attributeRules createID="true"/>
      </doctypeParaRule>
   </doctypes>
   <wrappingRules>
      <wrap elements="li+" context="number" wrapper="ol">
         <attributeRules createID="true"/>
      </wrap>
      <wrap elements="li+" context="bullet" wrapper="ul">
         <attributeRules createID="true"/>
      </wrap>
   </wrappingRules>
   <paragraphStyleRules>
      <paraRule style="Heading 2" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Heading 3" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|n|-|-]" context="number" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="0" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Title" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
   </paragraphStyleRules>
   <characterStyleRules>
      <charRule style="Bold" local="0" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="Code" local="0" mapTo="codeph">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Bold|-|-|-|-|-|-|-]" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Italic|-|-|-|-|-|-|-]" mapTo="i">
         <attributeRules createID="false"/>
      </charRule>
   </characterStyleRules>
</styleMap>
```

Il file di mapping è un file XML con una struttura semplice che elenca tutti gli stili di paragrafo di origine e i codici di stile dei caratteri. Di seguito sono illustrati i contenuti del file:

**Mappatura stili**

Nell&#39;elemento `styleMap` è possibile specificare due attributi facoltativi: `@map_date` e `@map_version` per la registrazione della versione del file di mapping.

**Tipo di documento**

L&#39;elemento `doctypes` elenca le mappature di argomenti e mappe DITA supportate.

**Mappa le regole di paragrafo del tipo di documento**

Elemento `mapDoctypeParaRule` obbligatorio. Gli attributi di questo elemento non devono essere modificati perché l&#39;elemento radice dell&#39;XML di origine è sempre mappato all&#39;elemento radice `map` della mappa DITA.

**Regola paragrafo tipo documento**

Elemento `doctypeParaRule` obbligatorio. Questo offre al processo di conversione un modo per identificare l’inizio di un nuovo argomento. Normalmente l&#39;attributo `@style` viene utilizzato da solo con l&#39;attributo `@local` impostato su 0. Tuttavia, se sono sempre presenti sostituzioni di formattazione locali per lo stile scelto, dovrai aggiungere una regola per ogni stile e le relative sostituzioni locali. Questo è semplice da riconoscere nel file di mappatura generato dove sarebbe possibile trovarlo o simile:

```XML
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

Nell&#39;esempio precedente sono presenti due elementi `paraRule` per `@style` = &quot;Heading1&quot;. È sufficiente creare un elemento `doctypeParaRule` equivalente con l&#39;attributo `@mapToDoctype` impostato come richiesto.

Gli attributi utilizzati in `doctypeParaRule` sono illustrati di seguito:

- `@style`: nome di uno stile nel documento InDesign di origine.
- `@local`: Vedere [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype`: nome di un tipo di argomento DITA da un elenco enumerato di tutti i `doctypes` validi.

**Regole di wrapping degli elementi**

Le regole di ritorno a capo degli elementi definiscono i modi in cui gli elementi del documento in ingresso vengono racchiusi o spostati in un elemento predefinito in base a un insieme di valori di attributo.

***`wrap`elemento***

Questo è un elemento facoltativo. L&#39;elemento `wrap` elenca gli elementi che verranno racchiusi o spostati. Il wrapping viene in genere utilizzato quando a una serie di elementi deve essere assegnato un elemento padre comune. Ad esempio, più elementi `li` sono racchiusi in un elemento `ol`. Inoltre, `wrap` può essere utilizzato per spostare elementi quali titoli per figure e tabelle.

Gli attributi utilizzati in `wrap` sono illustrati di seguito:

- `@element`: un segno più dopo il nome di un elemento indica che tutti gli elementi adiacenti con lo stesso nome verranno racchiusi nell&#39;elemento denominato nell&#39;attributo `@wrapper`.
- `@wrapper`: nome dell&#39;elemento di wrapping.
- `@context`: fornisce un modo per perfezionare ulteriormente la modalità di disposizione di un determinato elemento. L&#39;esempio seguente mostra un modo per mappare una serie di elementi `li` in un elenco ordinato `ol` o in un elenco non ordinato `ul` in base al valore `@context` \(il contesto è definito sull&#39;elemento `paraRule`\):

  ```XML
  <wrap elements="li+" context="number" wrapper="ol">
     <attributeRules createID="true"/>
  </wrap>
  <wrap elements="li+" context="bullet" wrapper="ul">
     <attributeRules createID="true"/>
  </wrap>
  ```


Nell&#39;esempio seguente viene illustrato come creare un elemento `fig` da un elemento `title` e un elemento `image`:

- `@elements`: gli elementi elencati e separati da una virgola verranno racchiusi nell&#39;elemento denominato nell&#39;attributo `@wrapper`. A causa della pratica comune di includere i titoli delle figure sotto l&#39;immagine, il titolo sarà l&#39;elemento `title` immediatamente dopo `image`.

  La seguente regola di ritorno a capo:

  ```XML
  <wrap elements="title, image" context="FigTitle" wrapper="fig">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Converte il seguente XML intermedio:

  ```XML
  <image href="Links/myImage.png" scale="59">
     <title>IDML2DITA workflow</title>
  ```

  Nella seguente struttura di figure DITA valida:

  ```XML
  <fig id="id397504">
     <title>IDML2DITA workflow</title>
     <image href="Links/myImage.png" scale="59">
  </fig>
  ```

- `@wrapper`: nome dell&#39;elemento di wrapping.
- `@context`: fornisce un modo per perfezionare ulteriormente il modo in cui un dato elemento viene racchiuso \(il contesto è definito sull&#39;elemento `paraRule`\).

Nell&#39;esempio seguente viene illustrato come spostare `title` in `table`:

- `@elements`: l&#39;elemento `title` che si trova immediatamente prima o immediatamente dopo un `table` verrà racchiuso nell&#39;elemento denominato nell&#39;attributo `@wrapper`. Un predicato in stile XPath può identificare la posizione dell&#39;elemento titolo come `[before]` o `[after]`.

  Esempio: la seguente regola di ritorno a capo:

  ```XML
  <wrap elements="title[before]" context="TableTitle" wrapper="table">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Converte il seguente XML intermedio:

  ```XML
  <title>IDML2DITA workflow</title>
  <table id="id289742" outputclass="BasicTable">
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

  In questa struttura di figure DITA valida:

  ```XML
  <table id="id289742" outputclass="BasicTable">
     <title>IDML2DITA workflow</title>
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

- `@wrapper`: nome dell&#39;elemento di wrapping.

- `@context`: fornisce un modo per perfezionare ulteriormente il modo in cui un dato elemento viene racchiuso \(il contesto è definito sull&#39;elemento `paraRule`\).


**Regole di stile paragrafo**

Gli elementi `<paragraphStyleRule>` sono descritti di seguito:

***`paraRule`elemento***

Elemento `paraRule` obbligatorio. Specifica le regole di mapping per tutti gli stili di paragrafo. In un documento InDesign, tutto il testo è contenuto all&#39;interno di una sottostruttura di Stili di paragrafo, anche i paragrafi senza alcuno stile sono denominati `[No paragraph style]`. Le parentesi quadre indicano un nome di stile InDesign incorporato.

>[!NOTE]
>
> Le parentesi quadre indicano un nome di stile InDesign incorporato.

Gli attributi utilizzati in `paraRule` sono illustrati di seguito:

- `@style`: nome di uno stile nel documento InDesign di origine.
- `@local`: Vedere [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: nome di un elemento destinazione DITA.

- `@context`: questo attributo viene utilizzato per il collegamento a una regola **wrap** specifica quando è disponibile più di una scelta wrapper. Esempio: l&#39;elemento `li` può essere racchiuso in un elemento `ol` o `ul`. Per identificare i diversi tipi di elenco, è possibile utilizzare un nome di stile specifico o l&#39;attributo `@local` che può mostrare quanto segue:
   - `local="p[-|-|-|-|-|b|-|-]"` Dove &#39;`b`&#39; nel campo 6 indica una voce di elenco puntato. In questo caso, impostare `@context` su &#39;`bullet`&#39;.
   - `local="p[-|-|-|-|-|n|-|-]"` Dove &#39;`n`&#39; nel campo 6 indica una voce di elenco numerata. In questo caso, impostare `@context` su &#39;`number`&#39;.

- `@commentOut`: questo attributo consente il wrapping dell&#39;elemento di destinazione nei commenti XML in modo che le informazioni non vadano perse ma possano essere gestite manualmente dall&#39;utente. Ciò è utile se il contenuto sorgente non può essere forzato a conformarsi alle regole della struttura DITA.

- `@refactor`: questo attributo facoltativo può scegliere tra due valori:

- `unwrap`: l&#39;elemento corrispondente viene rimosso mantenendo il relativo contenuto.

- `drop`: l&#39;elemento corrispondente e tutto il relativo contenuto vengono rimossi.


**Regole stile carattere**

Gli elementi `charRule` sono descritti di seguito:

>[!NOTE]
>
> Non verrà eseguita alcuna mappatura per lo stile di carattere predefinito `[No character style]` quando `local="0"`, perché vengono rimossi durante la preelaborazione.

***`charRule`elemento***

Questo è un elemento facoltativo.

Regole di mappatura per tutti gli stili di carattere. In un documento InDesign tutto il testo è contenuto all&#39;interno di elementi figlio di Stili di carattere.

Gli attributi utilizzati in `charRule` sono illustrati di seguito:

- `@style`: nome di uno stile nel documento InDesign di origine.
- `@local`: Vedere [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: nome di un elemento destinazione DITA.
- `@refactor`: questo attributo facoltativo può scegliere tra due valori:
   - `unwrap`: l&#39;elemento corrispondente viene rimosso mantenendo il relativo contenuto.

   - `drop`: l&#39;elemento corrispondente e tutto il relativo contenuto vengono rimossi.


**Regole attributo**

Questo elemento può essere figlio dei contesti di elemento seguenti:

- `mapDoctypeParaRule`
- `mapDoctypeElemRule`
- `doctypeParaRule`
- `doctypeElemRule`
- `paraRule`
- `charRule`
- `elementRule`

Lo scopo delle regole di attributo è quello di gestire gli attributi per gli elementi corrispondenti.

A seconda del contesto, nell&#39;elemento `attributeRules` sono disponibili i seguenti attributi:

- `@createID`: genera un ID univoco per gli elementi corrispondenti. Valori consentiti `true` o `false`. Disponibile in tutti i contesti.
- `@copyAll`: copia tutti gli attributi dal contenuto XML di origine solo per i file di origine strutturati. I valori consentiti sono `true` o `false`. Disponibile per i contesti `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` e `elementRule`.


Gli attributi utilizzati in `attributeRules` sono illustrati di seguito:

>[!NOTE]
>
> Questo elemento può contenere più elementi figlio.

- `addNew`: aggiunge un nuovo attributo all&#39;elemento corrispondente. Disponibile per tutti i contesti. Ha due attributi:
   - `@name`: deve essere un nome XML valido, preferibilmente valido per il contesto DITA.
   - `@value`: può essere un testo letterale o una semplice espressione XPath.
- `copyAtt`: copia un singolo attributo nella destinazione mentre è possibile rinominarlo nel processo. Il valore non viene modificato. Disponibile per i contesti `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` e `elementRule`. Quando questo elemento è presente, il valore `@copyAllAtts` è considerato `false`. Ha due attributi:
   - `@name`: deve essere il nome di un attributo presente nell&#39;elemento XML di origine.
   - `@mapTo`: deve essere un nome XML valido, preferibilmente valido per il contesto DITA.

**Codici di formattazione locali**

In qualsiasi documento InDesign, gli stili di paragrafo e di carattere possono avere diverse centinaia di sostituzioni di formattazione. La maggior parte di queste proprietà non fornisce alcun ruolo utile nel processo di conversione. Tuttavia, abbiamo identificato un set principale di funzioni di formattazione che influiscono sulla semantica del documento e devono influenzare il processo di conversione.

Gli attributi `@local` vengono presentati come un formato delimitato speciale in cui otto campi vengono forniti insieme a un prefisso per mostrare il tipo di sostituzione della formattazione. I campi dei codici di formattazione sono elencati di seguito:

- Prefisso **p** per sostituzione locale stile para o **c** per sostituzione locale stile carattere.
- **Stile carattere** che è il nome della famiglia e le proprietà, ad esempio &#39;***Grassetto corsivo ridotto***&#39;.
- **Dimensione font** in punti.
- **Posizione carattere** per apice o pedice.
- **Sotto** per il carattere di sottolineatura.
- **Barrato** per barrato.
- **Codice elenco** per identificare il tipo di elenco come puntato o numerato, non sempre utilizzato dall&#39;InDesign.
- **Il codice punto elenco** elenca tutti i tipi di punto elenco definiti nel documento.
- **Codice numero** elenca tutti gli stili di numerazione definiti nel documento.

L&#39;uso attento di questa funzione consente di perdere la formattazione locale e può contribuire a migliorare la qualità di un trasferimento da contenuti formattati a DITA. Questo esempio può essere risolto in corsivo, testo 16 pt in un elenco puntato: `p[Italic|16|-|-|-|b|-|-]`.

**Mappatura struttura**

Il file di mapping della struttura è simile al file di mapping degli stili con una struttura semplice che elenca tutti gli elementi di origine e i tipi di attributi rilevanti. Per la registrazione della versione del file di mapping da utilizzare vengono forniti due attributi, `@map_date` e `@map_version`.

**Tipo di documento**

L&#39;elemento `doctypes` elenca le mappature di argomenti e mappe DITA supportate.

**Mappa le regole degli elementi di tipo documento**

Elemento `mapDoctypeElemRule` obbligatorio. Gli attributi di questo elemento non devono essere modificati perché l&#39;elemento radice dell&#39;XML di origine è sempre mappato all&#39;elemento radice `map` della mappa DITA.

**Regole di wrapping degli elementi**

**`elementRules`elemento** Elenca tutti gli elementi.

**`elementRule`elemento** L&#39;elemento `elementRule` è obbligatorio. Si tratta delle regole di mappatura per tutti gli elementi sorgente. Sebbene un documento InDesign contenga elementi di stile non strutturati, questi vengono ignorati per i contenuti strutturati a meno che l&#39;elaborazione &#39;***modalità ibrida***&#39; non sia abilitata.

Gli attributi utilizzati in `elementRule` sono illustrati di seguito:

- `@elementName`: nome di un elemento nel documento InDesign di origine.

- `@local`: Vedere [\#id194CG0V005Z](#id194CG0V005Z). \(Utile solo per i documenti ibridi\).

- `@mapTo`: nome di un elemento destinazione DITA.

- `@refactor`: questo attributo facoltativo può scegliere tra due valori:

   - `unwrap`: l&#39;elemento corrispondente viene rimosso mantenendo il relativo contenuto.

   - `drop`: l&#39;elemento corrispondente e tutto il relativo contenuto vengono rimossi.

- `@context`: questo attributo viene utilizzato per il collegamento a una regola di wrapper specifica quando sono disponibili più opzioni di wrapper. Esempio: l&#39;elemento `li` può essere racchiuso in un elemento `ol` o `ul`.

- `@commentOut`: questo attributo consente il wrapping dell&#39;elemento di destinazione nei commenti XML in modo che le informazioni non vadano perse ma possano essere gestite manualmente dall&#39;utente. Ciò è utile se il contenuto sorgente non può essere forzato a conformarsi alle regole della struttura DITA.


## Risoluzione dei problemi di AEM Guides

Dopo aver installato e configurato AEM Guides, puoi risolvere i problemi.

## Convalida riferimenti

Puoi eseguire gli script forniti per convalidare i riferimenti. Questi script possono essere utili per identificare i riferimenti interrotti e quindi applicarvi patch o correggerli.

- `/bin/fmdita/validatebtree?operation=validate` - segnala eventuali riferimenti a contenuti interrotti, ma non li corregge.
- `/bin/fmdita/validatebtree?operation=patch`- elenca i riferimenti ai contenuti interrotti e le patch o le corregge.

**Convalida script**

Per controllare i riferimenti, esegui i seguenti passaggi utilizzando lo script di convalida disponibile nel pacchetto di prodotto:

1. Esegui lo script di convalida \[`/bin/fmdita/validatebtree?operation=validate`\] per verificare se sono presenti nuovi riferimenti interrotti.
1. Se lo script di convalida riporta errori, è possibile applicarvi la patch utilizzando lo script di patch.
1. Registra i dettagli forniti di seguito e, se necessario, condividili con il team di successo del cliente:
1. 
   - Registri stampati dallo script di convalida
- Package di &quot;`/content/fmdita/references`&quot;
- Qualsiasi altro dettaglio richiesto a seconda dello scenario segnalato

**Script patch**

Per applicare la patch ai riferimenti interrotti, esegui i passaggi seguenti utilizzando lo script di patch disponibile nel pacchetto del prodotto:

1. Eseguire lo script di patch `[/bin/fmdita/validatebtree?operation=patch]` per correggere i riferimenti interrotti. L’esecuzione dello script richiede alcuni minuti e stampa i registri mentre procede. Al termine dell&#39;esecuzione, verrà stampato &quot;`Done`&quot;.

   **Nota:* si consiglia di copiare e salvare i registri a scopo di riferimento.

1. Una volta eseguito correttamente lo script di patch, è possibile eseguire i seguenti controlli:
1. 
   - Verificare che sia stato creato un nuovo nodo &quot;`references_backup_<timestamp>"` in `/content/fmdita`
- Verifica che i riferimenti siano stati corretti

**Logger**

Puoi anche creare un logger separato per questa esecuzione dello script, in base ai dettagli riportati di seguito:

- Aggiungi un logger alla classe &quot;`adobe.fmdita.common.BTreeReferenceValidator`&quot;
- Imposta su `DEBUG`

Il file di registro creato registra tutte le informazioni relative all’esecuzione dello script ed è utile nel caso in cui si verifichino timeout nella sessione del browser, durante l’attivazione dello script dal browser.
