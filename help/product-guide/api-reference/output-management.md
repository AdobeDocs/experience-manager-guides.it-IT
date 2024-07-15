---
title: API REST per la gestione dell’output
description: Informazioni sulle API REST per la gestione dell’output
exl-id: dab654f5-555d-4a89-bc94-55b1e938f255
feature: Rest API Output Management
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 0%

---

# API REST per la gestione dell’output {#id175UB30E05Z}

Le seguenti API REST sono disponibili per la gestione dell’output in AEM Guides.

## Ottenere tutti i predefiniti di output per una mappa DITA {#get-output-presets-dita-map}

Metodo POST che recupera tutti i predefiniti di output configurati per una mappa DITA.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/publishlistener

**Parametri**:\
|Nome|Tipo|Obbligatorio|Descrizione|
----|----|--------|-----------|
|`:operation`|Stringa|Sì|Nome dell&#39;operazione chiamata. Il valore di questo parametro è `getalloutputs`.<br> **Nota:** il valore non distingue tra maiuscole e minuscole.|
|`sourcePath`|Stringa|Sì|Percorso assoluto del file mappa DITA.|

**Valori risposta**:
Restituisce una matrice di oggetti Predefinito di output JSON, ognuno dei quali contiene i seguenti elementi:

| Elemento | Descrizione |
|-------|-----------|
| `outputName` | Nome del predefinito di output. I nomi di output sono univoci nell&#39;ambito della mappa DITA in cui sono definiti. |
| `outputType` | Tipo di output generato utilizzando questo predefinito, ad esempio Sito AEM, PDF, EPUB o altro. Opzioni disponibili:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   PERSONALIZZATO |
| `outputTitle` | Nome descrittivo per le impostazioni del predefinito di output. Viene utilizzato per definire il valore della proprietà Nome impostazione per il predefinito di output. |
| `ditaValPathList` | Array di percorsi di file DITAVAL da utilizzare per generare l&#39;output desiderato. |
| `targetPath` | Percorso in cui viene pubblicato o memorizzato l’output. |
| `siteName` | *\(Per output sito AEM\)* Nome del sito AEM. |
| `templatePath` | *\(Per output sito AEM\)* Percorso del nodo del modello da utilizzare per generare l&#39;output desiderato. |
| `searchScope` | Specificare l&#39;ambito dell&#39;operazione di ricerca. Il valore di questo parametro deve essere impostato su `local`. |
| `generateTOC` | *\(Per output sito AEM\)* Specificare se viene generato un sommario \(true\) o meno \(false\). |
| `generateBreadcrumbs` | *\(Per output sito AEM\)* Specificare se le breadcrumb vengono generate \(true\) o meno \(false\). |
| `overwriteStrategy` | *\(Per l&#39;output del sito AEM\)* Specificare se i file di destinazione sono sovrascritti \(true\) o meno \(false\). |
| `pdfGenerator` | Specifica il motore di generazione PDF da utilizzare. I valori possibili sono:<br>-   DITAOT <br>-   FMPS |

>[!NOTE]
>
> `DitaValPath` elemento non più supportato.

## Crea predefinito di output

Metodo POST che crea un nuovo predefinito di output per una mappa DITA.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/publishlistener

**Parametri**:
|Nome|Tipo|Obbligatorio|Descrizione|
----|----|--------|-----------|
|`:operation`|Stringa|Sì|Nome dell&#39;operazione chiamata. Il valore di questo parametro è ``createoutput``.<br> **Nota:** il valore non distingue tra maiuscole e minuscole.|
|`sourcePath`|Stringa|Sì|Percorso assoluto del file mappa DITA.|
|`outputTitle`|Stringa|Sì|Nome descrittivo per le impostazioni del predefinito di output. Utilizzato per definire il valore della proprietà Nome impostazione per il predefinito di output.<br> **Nota:** quando viene creato un nuovo predefinito di output, il sistema back-end utilizza un nome univoco per il predefinito di output dal titolo specificato.|
|`outputType`|Stringa|Sì|Tipo di output generato utilizzando questo predefinito, ad esempio Sito AEM, PDF, EPUB o altro. Opzioni disponibili:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   PERSONALIZZATO|

**Valori risposta**:
|Elemento|Descrizione|
----------- -------
|`outputName`|Nome univoco per il predefinito di output appena creato. Questo nome è derivato dal valore del parametro `outputTitle`.|

## Salva predefinito di output

Metodo POST che salva le modifiche apportate in un predefinito di output.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/publishlistener

**Parametri**:
|Nome|Tipo|Obbligatorio|Descrizione|
----|----|--------|-----------|
|`:operation`|Stringa|Sì|Nome dell&#39;operazione chiamata. Il valore di questo parametro è ``saveoutput``.<br> **Nota:** il valore non distingue tra maiuscole e minuscole.|
|`sourcePath`|Stringa|Sì|Percorso assoluto del file mappa DITA.|
|`outputObj`|Stringa|Sì|Oggetto JSON contenente le proprietà del predefinito di output in fase di aggiornamento. La proprietà `outputObj.outputName` contiene il nome del predefinito di output da aggiornare. Per il formato dell&#39;oggetto JSON, vedere la tabella **Valori di risposta** in [Ottenere tutti i predefiniti di output per una mappa DITA](#get-output-presets-dita-map).|

**Valori risposta**:
Restituisce una risposta HTTP 200 \(Riuscito\).

## Ottieni un predefinito di output specifico

Metodo POST che recupera un predefinito di output esistente.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/publishlistener

**Parametri**:
|Nome|Tipo|Obbligatorio|Descrizione|
----|----|--------|-----------|
|`:operation`|Stringa|Sì|Nome dell&#39;operazione chiamata. Il valore di questo parametro è `getoutput`. <br>**Nota:** il valore non distingue tra maiuscole e minuscole.|
|`sourcePath`|Stringa|Sì|Percorso assoluto del file mappa DITA.|
|`outputName`|Stringa|Sì|Nome del predefinito di output per il quale è necessario recuperare i dettagli.|

**Valori risposta**:
|Elemento|Descrizione|
----------- -------
|`outputName`|Nome del predefinito di output. I nomi di output sono univoci nell&#39;ambito della mappa DITA in cui sono definiti.|
|`outputType`|Tipo di output generato utilizzando questo predefinito, ad esempio Sito AEM, PDF, EPUB o altro. Opzioni disponibili:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   PERSONALIZZA <br>|
|`outputTitle`|Nome descrittivo per le impostazioni del predefinito di output. Viene utilizzato per definire il valore della proprietà Nome impostazione per il predefinito di output.|
|`ditaValPathList`|Array di percorsi di file DITAVAL da utilizzare per generare l&#39;output desiderato.|
|`targetPath`|Percorso in cui l&#39;output viene pubblicato o archiviato.|
|`siteName`|\(Per output sito AEM\) Nome del sito AEM.|
|`siteTitle`|\(Per output sito AEM\) Titolo del sito AEM.|
|`templatePath`|\(Per output sito AEM\) Percorso del nodo del modello da utilizzare per generare l&#39;output desiderato.|
|`searchScope`|Specificare l&#39;ambito dell&#39;operazione di ricerca. Il valore di questo parametro deve essere impostato su `local`.|
|`generateTOC`|\(Per output sito AEM\) Specificare se viene generato un sommario \(true\) o meno \(false\).|
|`generateBreadcrumbs`|\(Per output sito AEM\) Specifica se le breadcrumb vengono generate \(true\) o meno \(false\).|
|`overwriteFiles`|\(Per l&#39;output del sito AEM\) Specificare se i file nella destinazione vengono sovrascritti \(true\) o meno \(false\).|
|`pdfGenerator`|Specificare il motore di generazione PDF da utilizzare. I valori possibili sono:<br>-   DITAOT <br>-   FMPS|

>[!NOTE]
>
> `DitaValPath` elemento non più supportato.

## Genera output

Metodo di GET che genera output utilizzando uno o più predefiniti di output.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/publishlistener

**Parametri**:
|Nome|Tipo|Obbligatorio|Descrizione|
----|----|--------|-----------|
|`operation`|Stringa|Sì|Nome dell&#39;operazione chiamata. Il valore di questo parametro è `GENERATEOUTPUT`.<br> **Nota:** il valore fa distinzione tra maiuscole e minuscole.|
|`source`|Stringa|Sì|Percorso assoluto del file mappa DITA.|
|`outputName`|Stringa|Sì|Nome del predefinito di output\(s\) da utilizzare per generare l&#39;output. È possibile specificare più predefiniti di output utilizzando un delimitatore pipe \(&quot;\|&quot;\), ad esempio `aemsite|pdfoutput`.|

**Valori risposta**:
Restituisce una risposta HTTP 200 \(Riuscito\).

## Genera output incrementale

Metodo di GET che genera un output incrementale per un sito AEM utilizzando uno o più predefiniti di output.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/publishlistener

**Parametri**:
|Nome|Tipo|Obbligatorio|Descrizione|
----|----|--------|-----------|
|`operation`|Stringa|Sì|Nome dell&#39;operazione chiamata. Il valore di questo parametro è `INCREMENTALPUBLISH`. <br>**Nota:** il valore fa distinzione tra maiuscole e minuscole.|
|`contentPath`|JSON|Sì|Percorso assoluto del file mappa DITA e dei file di argomento insieme al nome dei predefiniti di output. Utilizza l’esempio seguente come blocco predefinito:|

```XML
{
   {   
   "ditamap": 
      "/content/dam/sample/sample.ditamap",   
   "topics": [     
      "/content/dam/sample/topic1.xml",     
      "/content/dam/sample/topic2.xml"   
         ],   
   "fullMaps": [     
      "/content/dam/sample/submap.ditamap"   
      ],   
   "maps": [     
      "/content/dam/sample/keyspace.ditamap"   
      ],   
   "outputs": [     
      "aemsite"   
      ] 
   }
}
```

- L&#39;attributo `ditamap` utilizza il percorso assoluto della mappa DITA utilizzata per generare l&#39;output.
- L&#39;attributo `topics` accetta un array di argomenti che vengono aggiornati e devono essere ripubblicati.
- L&#39;attributo `fullMaps` contiene il percorso dei file di mappa \(come submaps a blocchi\) necessari insieme ai relativi argomenti per la generazione dell&#39;output incrementale.
- L&#39;attributo `maps` contiene il percorso dei file di mappa \(per la risoluzione dei riferimenti dello spazio chiave\) estratti sul disco senza argomenti.
- L&#39;attributo `outputs` accetta una matrice di nomi di predefiniti di output utilizzati per generare l&#39;output.

**Valori risposta**:
Restituisce una risposta HTTP 200 \(Riuscito\).

## Elimina predefinito di output

Metodo POST che elimina un predefinito di output.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/publishlistener

**Parametri**:
|Nome|Tipo|Obbligatorio|Descrizione|
----|----|--------|-----------|
|`:operation`|Stringa|Sì|Nome dell&#39;operazione chiamata. Il valore di questo parametro è `deleteoutput`.<br> **Nota:** il valore non distingue tra maiuscole e minuscole.|
|`sourcePath`|Stringa|Sì|Percorso assoluto del file mappa DITA.|
|`outputName`|Stringa|Sì|Nome del predefinito di output da eliminare.|

**Valori risposta**:
Restituisce una risposta HTTP 200 \(Riuscito\).
