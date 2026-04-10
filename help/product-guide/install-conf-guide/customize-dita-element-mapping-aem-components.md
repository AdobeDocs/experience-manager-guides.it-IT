---
title: Personalizzare la mappatura degli elementi dita con i componenti AEM
description: Scopri come personalizzare la mappatura degli elementi dita con i componenti AEM
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 1%

---


# Personalizzare la mappatura degli elementi DITA con i componenti AEM {#id1679J600HEL}

Gli elementi DITA in AEM Guides vengono mappati sui relativi componenti AEM. AEM Guides utilizza questa mappatura nei flussi di lavoro, ad esempio pubblicazione e revisione, per convertire l’elemento DITA in un componente AEM corrispondente. Il mapping è definito nel file `elementmapping.xml`, a cui è possibile accedere utilizzando Gestione pacchetti per la configurazione di Cloud Service e dall&#39;URL `/libs/fmdita/config/elementmapping.xml` nella modalità CRXDE Lite per la configurazione locale.

>[!NOTE]
>
> Non effettuare personalizzazioni nei file di configurazione predefiniti disponibili nel nodo ``libs``. È necessario creare una sovrapposizione del nodo ``libs`` nel nodo ``apps`` e aggiornare i file richiesti solo nel nodo ``apps``.

È possibile utilizzare le mappature di elementi DITA predefinite oppure mappare gli elementi DITA ai componenti AEM personalizzati. Per utilizzare i componenti AEM personalizzati, è necessario comprendere la struttura del file `elementmapping.xml`.

## struttura elementmapping.xml

Di seguito viene illustrata una panoramica di alto livello della struttura `elementmapping.xml`:

1. Per ogni elemento DITA viene innanzitutto eseguita la ricerca di una mappatura di componente corrispondente in base al nome dell&#39;elemento. Ad esempio:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   Nell&#39;esempio precedente, tutti gli elementi DITA `substeps` vengono sottoposti a rendering utilizzando il componente `dita/components/ditaolist`.

1. Se un elemento DITA non trova una corrispondenza basata sul nome, viene eseguita una corrispondenza sulla base di `class`. Ad esempio:

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   Nell&#39;esempio precedente, se non è stata definita alcuna mappatura per l&#39;elemento `task`, l&#39;elemento `task` viene mappato al componente precedente perché `task` è ereditato dal componente `topic`.

1. Quando a un elemento corrisponde un mapping di componenti, l&#39;ulteriore elaborazione degli elementi figlio è determinata da `type`. Ad esempio:

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` accetta i seguenti valori:

   - COMPOSITE: la mappatura da elemento a componente *continua anche per gli elementi figlio*.

   - STANDALONE: gli elementi secondari dell&#39;elemento corrente sono *non mappati ulteriormente*.

   Nell&#39;esempio precedente, se l&#39;elemento `<title>` include elementi figlio, questi non verranno mappati ad alcun altro componente. Il componente per l&#39;elemento `<title>` è responsabile del rendering di tutti gli elementi figlio all&#39;interno dell&#39;elemento `<title>`.

1. Se sono presenti più componenti mappati a un singolo elemento DITA, viene selezionata la corrispondenza migliore per l’elemento. Per selezionare il componente di corrispondenza migliore, viene considerata la specializzazione del dominio e della struttura degli elementi DITA.

   Se sono presenti elementi DITA con specializzazione di dominio e un componente è mappato per la specializzazione di dominio, a tale componente viene assegnata la priorità alta.

   Analogamente, se esistono elementi DITA con specializzazione strutturale e un componente è mappato per la specializzazione strutturale, a tale componente viene assegnata la priorità alta.

1. È possibile utilizzare `<attributemap>` nella mappatura degli elementi per mappare i valori degli attributi alle proprietà corrispondenti del nodo.
1. `textprop` può essere utilizzato per serializzare il contenuto di testo di un elemento DITA in una proprietà nodo. Inoltre, può essere utilizzato più volte in un tag elemento per serializzare il contenuto di testo in più posizioni nella gerarchia pubblicata. Puoi anche personalizzare la posizione e il nome della proprietà target. Ad esempio:

   ```XML
   <ditaelement>
      <name>title</name>
      <componentpath>foundation/components/title</componentpath>
      <type>STANDALONE</type>
      <target>para</target>
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   La mappatura dell&#39;elemento precedente specifica che il contenuto di testo dell&#39;elemento `<title>` verrà salvato come valore di una proprietà denominata `jcr:title` nel nodo di output.

1. `xmlprop` può essere utilizzato per serializzare l&#39;intero XML di un dato elemento a una proprietà del nodo. Il componente può quindi leggere questa proprietà del nodo ed eseguire il rendering personalizzato. Ad esempio:

   ```XML
   <ditaelement>
       <name>svg-container</name>
      <class>+ topic/foreign svg-d/svg-container</class>
       <componentpath>fmdita/components/dita/svg</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
      <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   Il mapping di elementi sopra riportato specifica che l&#39;intero markup XML per l&#39;elemento `<svg-container>` verrà salvato come valore di una proprietà denominata `data` nel nodo di output.

1. Esiste uno speciale mapping di attributi per gestire la risoluzione del percorso nel processo di generazione dell&#39;output. Ad esempio:

   ```XML
   <attributemap>
      <attribute from="href" to="fileReference" ispath="true" rel="source" />
      <attribute from="height" to="height" />
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Per `attributemap`, l&#39;attributo `href` nell&#39;elemento DITA verrà mappato a una proprietà nodo denominata `fileReference`. Poiché `ispath` è impostato su `true`, il processo di generazione dell&#39;output risolve questo percorso e lo imposta nella proprietà del nodo `fileReference`.

   La modalità di risoluzione viene determinata in base al valore dell&#39;attributo `rel` nella mappatura degli attributi.

   - Se `rel=source`, il valore di `href` viene risolto rispetto al file di origine DITA in fase di elaborazione. Il valore di `href` è risolto e posizionato nel valore della proprietà `fileReference`.

   - Se `rel=target`, il valore di `href` viene risolto rispetto al percorso di pubblicazione principale. Il valore di `href` è risolto e posizionato nel valore della proprietà `fileReference`.

   Se non desideri che si verifichi alcuna pre-elaborazione o risoluzione sugli attributi del percorso, non è necessario specificare l&#39;attributo `ispath`. Il valore viene copiato così come è e il componente può eseguire la risoluzione richiesta.


## Schema elemento DITA

Di seguito è riportato un esempio dello schema dell&#39;elemento DITA nel file `elementmapping.xml`:

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

Nella tabella seguente vengono descritti gli elementi dello schema di elementi DITA:

| Elemento | Descrizione |
|-------|-----------|
| `<ditaelement>` | Nodo di primo livello per ogni elemento di mappatura. |
| `<class>` | Attributo di classe dell&#39;elemento DITA di destinazione per il quale si sta scrivendo il componente.<br> Ad esempio, l&#39;attributo di classe per l&#39;argomento DITA è: <br> `- topic/topic` |
| `<componentpath>` | Percorso CRXDE del componente AEM mappato. |
| `<type>` | Valori possibili:<br> -   **COMPOSITO**: Elabora anche elementi figlio <br> -   **STANDALONE**: ignora l&#39;elaborazione degli elementi figlio |
| `<attributeprop>` | Utilizzato per la mappatura di attributi e valori DITA serializzati ai nodi AEM come proprietà. Ad esempio, se si dispone dell&#39;elemento `<note type="Caution">` e il componente mappato per questo elemento ha `<attributeprop>attr_t</ attributeprop>`, l&#39;attributo e il valore del nodo vengono serializzati nella proprietà `attr_t` del nodo AEM corrispondente \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Salva l&#39;output `getTextContent()` nella proprietà definita da `propname_t.` <br> **Nota:** questa è una proprietà ottimizzata. |
| `<xmlprop>propname_x </xmlprop>` | Salva il codice XML serializzato di questo nodo nella proprietà definita da `propname_x.<br> `**Nota:** Si tratta di una proprietà ottimizzata. |
| `<xpath>` | Se l&#39;elemento XPath viene fornito nel mapping di elementi, insieme al nome e alla classe dell&#39;elemento deve essere soddisfatta anche la condizione XPath affinché venga utilizzato il mapping di componenti. |
| `<target>` | Posizionare l&#39;elemento DITA nell&#39;archivio crx nella posizione specificata.<br> Valori possibili: <br> - **head**: Sotto il nodo head <br> - **text**: Sotto il nodo paragrafo |
| `<wrapelement>` | L’elemento HTML in cui racchiudere il contenuto. |
| `<wrapclass>` | Il valore dell&#39;elemento alla proprietà `wrapclass.` |
| `<attributemap>` | Nodo contenitore contenente uno o più nodi `<attribute>`. |
| `<attribute from="attrname" to="propname" ispath="true\|false" rel="source\|target" />` | Associa gli attributi DITA alle proprietà di AEM: <br> -   **`from`**: nome attributo DITA <br> -   **`to`**: nome proprietà componente AEM <br> -   **`ispath`**: se l&#39;attributo è un valore di percorso \(ad esempio: *immagine*\) <br> -   **`rel`**: se il percorso è l&#39;origine o la destinazione <br> **Nota:** Se `attrname` inizia con `%`, mappare `attrname minus '%'` a prop &#39; `propname`&#39;. |

**Note aggiuntive**

- Se si prevede di ignorare la mappatura degli elementi predefinita, è consigliabile non apportare le modifiche nel file `elementmapping.xml` predefinito. Devi creare un nuovo file XML di mappatura e posizionarlo in un’altra posizione, preferibilmente all’interno della cartella delle app personalizzate che crei.

- Nel file `elementmapping.xml` sono presenti molte voci di mapping che fanno riferimento al componente fmdita/components/dita/wrapper. Wrapper è un componente generico che esegue il rendering di costrutti DITA relativamente semplici utilizzando le proprietà sul nodo del sito per generare HTML rilevanti. Utilizza la proprietà `wrapelement` per generare tag di inclusione e delega il rendering secondario ai componenti corrispondenti. Ciò è utile nei casi in cui desideri solo un componente contenitore. Invece di creare un nuovo componente che esegue il rendering di un tag contenitore specifico come `div` o `p`, è possibile utilizzare il componente Wrapper con le proprietà `wrapelement` e `wrapclass` per ottenere lo stesso effetto.

- Si sconsiglia di salvare grandi quantità di testo nelle proprietà String JCR. Il calcolo del tipo di proprietà ottimizzato nella generazione dell’output assicura che il contenuto di testo di grandi dimensioni non venga salvato come tipo di stringa. Quando invece è necessario salvare un contenuto superiore a una determinata soglia, il tipo della proprietà viene modificato in binario. Per impostazione predefinita, questa soglia è configurata a 512 byte, ma può essere modificata in Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) modificando l&#39;impostazione **Salva come soglia binaria**.

- Se si prevede di ignorare alcuni \(e non tutti\) dei mapping degli elementi, non è necessario replicare l&#39;intero file `elementmapping.xml`. È necessario creare un nuovo file di mapping XML e definire solo gli elementi sovrascritti.

- Dopo aver creato il file XML nel percorso personalizzato, aggiornare l&#39;impostazione `Override Element Mapping` nel bundle `com.adobe.fmdita.config.ConfigManager`.


