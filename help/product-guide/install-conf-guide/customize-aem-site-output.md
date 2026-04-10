---
title: Configurare le impostazioni di generazione dell’output
description: Scopri come configurare le impostazioni di generazione dell’output
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3098'
ht-degree: 0%

---


# Personalizzare l’output del sito AEM {#id166TG0B30WR}

AEM Guides supporta la creazione di output nei seguenti formati:

- Sito AEM
- PDF
- HTML5
- EPUB
- Output personalizzato tramite DITA-OT

Per l’output Sito di AEM, puoi assegnare diversi modelli di progettazione con diverse attività di output. Questi modelli di progettazione possono eseguire il rendering del contenuto DITA in layout diversi. Ad esempio, puoi specificare diversi modelli di progettazione per il pubblico interno ed esterno.

È inoltre possibile utilizzare plug-in personalizzati DITA Open Toolkit \(DITA-OT\) con AEM Guides. È possibile caricare questi plug-in DITA-OT personalizzati per generare l&#39;output di PDF in un modo specifico.

>[!TIP]
>
> Consulta la sezione *Pubblicazione del sito AEM* nella [Guida alle best practice](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-mar-22/Adobe-Experience-Manager-Guides_Best-Practices_EN.pdf) per le best practice sulla creazione dell&#39;output del sito AEM.


## Personalizza modello struttura per generare output {#customize_xml-add-on}

AEM Guides utilizza un set di modelli di progettazione predefiniti per generare l’output del sito AEM. Puoi personalizzare i modelli di progettazione di AEM Guides per generare l’output conforme al tuo branding aziendale. Un modello di progettazione è una raccolta di vari stili \(CSS\), script \(lato server e lato client\), risorse \(immagini, loghi e altre risorse\) e nodi JCR che collegano tutte queste risorse. Un modello di progettazione può essere semplice come un singolo script lato server con solo un paio di nodi JCR o una combinazione complessa di stili, risorse e nodi JCR. I modelli di progettazione vengono utilizzati dal sottosistema di pubblicazione di AEM Guides durante la generazione dell’output del sito AEM e controllano la struttura, l’aspetto dell’output generato.

Non esiste alcuna restrizione relativa alla posizione delle risorse del modello di progettazione nel server, ma in genere sono organizzate in modo logico in base alla loro funzione. Ad esempio, tutti i file JavaScript e CSS del modello predefinito sono memorizzati nella cartella `/etc/designs/fmdita/clientlibs/siteoutput/default`. Ovunque si trovino questi file, sono collegati tra loro da una raccolta di nodi JCR. Insieme, questi nodi JCR e i file costituiscono l’intero modello di progettazione.

Il modello struttura predefinito fornito con AEM Guides consente di personalizzare i componenti della pagina di destinazione, dell’argomento e della ricerca. Potete creare una copia del progetto di default e delle maschere di riferimento corrispondenti e specificare componenti diversi per generare l&#39;output desiderato.

Le schede seguenti forniscono istruzioni per specificare il modello di progettazione da utilizzare per la generazione dell’output del sito AEM in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Utilizzare Gestione pacchetti per scaricare il modello di progettazione predefinito dal percorso seguente:

   /libs/fmdita/config/templates

1. Crea una copia dei file scaricati nella seguente posizione nell’archivio Git del Cloud Manager:

   /apps/fmdita/config/templates

1. È inoltre necessario scaricare e copiare i modelli a cui si fa riferimento dal nodo del modello predefinito. I modelli a cui si fa riferimento si trovano in:

   /libs/fmdita/templates/default/cqtemplates

>[!TAB On-Premise]

1. Accedi ad AEM e apri la modalità CRXDE Lite.

1. Passare al nodo predefinito del modello struttura. La posizione del nodo predefinito del modello struttura è:

   `/libs/fmdita/config/templates/`

   ![](assets/templates-node.png){width="300" align="left"}

   >[!NOTE]
   >
   > Creare una copia dei modelli struttura predefiniti dalla cartella `libs` alla cartella `apps` e apportare le modifiche nella cartella `apps`. È inoltre necessario apportare modifiche ai modelli a cui si fa riferimento dal nodo del modello predefinito. I modelli a cui si fa riferimento si trovano sotto il nodo `/libs/fmdita/templates/default/cqtemplates`. Creare una copia dei modelli a cui si fa riferimento nella cartella `apps` prima di apportare qualsiasi modifica.

1. Fai clic sul componente *default* nel nodo *templates* per accedere alle relative proprietà.

>[!ENDTABS]

Nella tabella seguente sono descritte le proprietà del modello di progettazione AEM Guides.

| Proprietà | Descrizione |
|--------|-----------|
| `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Specifica il nodo `cq:Template` per le pagine corrispondenti \(destinazione, ricerca e argomento\). Per impostazione predefinita, il nodo `cq:Template` per queste pagine si trova nel nodo `/libs/fmdita/templates/default/cqtemplates`. Questo nodo definisce la struttura e le proprietà delle pagine di destinazione, ricerca e argomento.<br> `shadowPageTemplate` viene utilizzato per ottimizzare il contenuto a blocchi. Impostare il valore di questa proprietà su: `fmdita/templates/default/cqtemplates/shadowpage` <br> **Nota:** è necessario specificare un valore per `topicPageTemplate`. `landingPageTemplate` e `searchPageTemplate` sono proprietà facoltative. Se non desideri che le pagine di ricerca e di destinazione vengano generate, non specificare queste proprietà. |
| `title` | Nome descrittivo del modello di progettazione. |
| `topicContentNode` | Posizione del nodo che conterrà il contenuto DITA in una pagina dell&#39;argomento. Il percorso è relativo alla pagina dell&#39;argomento. |
| `topicHeadNode` | Posizione del nodo che conterrà i valori head \(o metadati\) derivati dal contenuto DITA. Il percorso è relativo alla pagina dell&#39;argomento. |
| `tocNode` | Posizione del nodo che conterrà il sommario. Percorso relativo alla pagina di destinazione o al percorso di destinazione. |
| `basePathProp` | Nome della proprietà per la memorizzazione del percorso della directory principale del sito pubblicato. |
| `indexPathProp` | Nome della proprietà per la memorizzazione del percorso della pagina di destinazione/indice del sito pubblicato. |
| `pdfPathProp` | Nome della proprietà per l&#39;archiviazione del percorso PDF dell&#39;argomento, se è abilitata la generazione PDF dell&#39;argomento. |
| `pdfTypeProp` | Nome della proprietà per l’archiviazione del tipo della generazione PDF. Attualmente questa proprietà contiene sempre &quot;Argomento&quot;. |
| `searchPathProp` | Il nome della proprietà per memorizzare il percorso della pagina di ricerca, se il modello include una pagina di ricerca. |
| `siteTitleProp` | Nome della proprietà per memorizzare il titolo del sito da pubblicare. Questo titolo è in genere lo stesso del titolo della mappa pubblicata. |
| `sourcePathProp` | Nome della proprietà per la memorizzazione del percorso dell&#39;argomento DITA di origine per la pagina corrente. |
| `tocPathProp` | Nome della proprietà per la memorizzazione del percorso della directory principale del sommario per il sito pubblicato. |


>[!NOTE]
>
> Dopo aver creato un nodo del modello di progettazione personalizzato, è necessario aggiornare l’opzione Progettazione nei predefiniti di output del sito AEM per utilizzare il nodo del modello di progettazione personalizzato.

Per ulteriori informazioni, consulta [Creazione del primo sito Web Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=en) e [Nozioni di base](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/develop-wknd-tutorial.html?lang=en) sullo sviluppo del tuo sito Web su AEM.

## Usa il titolo del documento per generare l&#39;output del sito AEM

Durante la generazione dell’output del sito AEM, il modo in cui vengono generati gli URL svolge un ruolo importante nella reperibilità dei contenuti. Se utilizzi nomi di file basati su UUID, la generazione di URL basati su UUID dei file non sarà semplice da cercare. In qualità di amministratore o di editore, hai il controllo su come generare gli URL per l’output del sito AEM. AEM Guides offre una configurazione attraverso la quale puoi scegliere di generare gli URL dell’output del sito AEM utilizzando il titolo del file invece dei nomi di file basati su UUID. Per impostazione predefinita, per i file system basati su UUID questa opzione è attivata. Ciò implicava che quando si genera l&#39;output del sito AEM per file system basati su UUID, i titoli del file vengono utilizzati per generare gli URL e non gli UUID dei file.

Per la configurazione on-premise con file system non basati su UUID, l’output del sito AEM viene generato utilizzando i nomi dei file e non i titoli dei file. Per impostazione predefinita, questa opzione è disattivata. Ciò implicava che quando si genera l’output del sito AEM, i nomi dei file vengono utilizzati per generare gli URL e non il titolo del file. Abilitando questa opzione, puoi scegliere di generare gli URL in base ai titoli dei file.

Le schede seguenti forniscono istruzioni per configurare la generazione di URL nell’output del sito AEM in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!NOTE]
>
> Puoi configurare ulteriormente le regole in modo da consentire solo un set di caratteri negli URL dell’output di un sito AEM. Per ulteriori dettagli, vedere [Configurare le regole di bonifica del nome file per la creazione di argomenti e la pubblicazione dell&#39;output del sito AEM](#id2164D0KD0XA).

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare la generazione di URL nell’output del sito AEM:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `aemsite.pagetitle` | Booleano \(true/false\). Se desideri generare l’output utilizzando il titolo della pagina, imposta questa proprietà su true. Per impostazione predefinita, è impostato per utilizzare il nome file.<br> **Valore predefinito**: false |


>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Selezionare l&#39;opzione **Usa titolo per i nomi delle pagine del sito AEM**.

   >[!NOTE]
   >
   > Se desideri generare l’output utilizzando i nomi dei file, deseleziona questa opzione.

1. Fai clic su **Salva**.

>[!ENDTABS]

## Configura l’URL dell’output del sito AEM in modo che utilizzi il titolo del documento (solo per Cloud Service)

Puoi utilizzare i titoli dei documenti nell’URL dell’output del sito AEM. Se il nome del file non esiste o contiene tutti i caratteri speciali, puoi configurare il sistema per sostituire i caratteri speciali con un separatore nell’URL dell’output del sito AEM. È inoltre possibile configurarlo per sostituirli con il nome del primo argomento figlio.


Per configurare i nomi delle pagine, effettuare le seguenti operazioni:

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione.
1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare i nomi delle pagine per gli argomenti.

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeName` | `nodename.systemDefinedPageName` | Booleano (`true/false`). **Valore predefinito**: `false` |

Se ad esempio il *@navtitle* in `<topichead>` contiene tutti i caratteri speciali e si imposta la proprietà `aemsite.pagetitle` su true, per impostazione predefinita viene utilizzato un separatore. Se si imposta la proprietà `nodename.systemDefinedPageName` su true, verrà visualizzato il nome del primo argomento secondario.


## Configurare le regole di bonifica del nome file per la creazione di argomenti e la pubblicazione dell’output in AEM Sites e altri formati {#id2164D0KD0XA}

In qualità di amministratore, puoi definire un elenco di caratteri speciali validi consentiti nei nomi dei file, che alla fine formeranno l’URL di un output del sito AEM. Nelle versioni precedenti, gli utenti potevano definire nomi di file contenenti caratteri speciali come `@`, `$`, `>` e altri. Questi caratteri speciali hanno generato un URL codificato nella generazione di pagine del sito AEM.

A partire dalla versione 3.8, sono state aggiunte configurazioni per definire un elenco di caratteri speciali consentiti nei nomi dei file. Per impostazione predefinita, la configurazione del nome file valida contiene &quot;`a-z A-Z 0-9 - _`&quot;. Ciò implica che durante la creazione di un file, è possibile inserire qualsiasi carattere speciale nel titolo del file, ma internamente verrà sostituito con un trattino \(`-`\) nel nome del file. Ad esempio, puoi assegnare al file il titolo Introduzione 1 o Introduction@1; il nome file corrispondente generato in entrambi i casi sarà Introduzione-1.

Quando definisci un elenco di caratteri validi, ricorda che questi caratteri &quot;`*/:[\]|#%{}?&<>"/+`&quot; e `a space` verranno sempre sostituiti da un trattino \(`-`\).

>[!NOTE]
>
> Se non configuri l’elenco dei caratteri speciali validi, il processo di creazione del file potrebbe fornire risultati imprevisti.

Le schede seguenti forniscono istruzioni per configurare i caratteri speciali validi nei nomi di file e nell’output del sito AEM in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare i caratteri speciali validi nei nomi dei file e nell’output del sito AEM:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Verificare che la proprietà sia impostata su ``'<>`@$``. Puoi aggiungere altri caratteri speciali a questo elenco. |

>[!NOTE]
> 
> La configurazione precedente si applica a tutti i formati di output. Ciò significa che durante la generazione di un output PDF, HTML o personalizzato, l’output finale seguirà le regole di bonifica del nome file configurate.

Puoi anche configurare le altre proprietà, ad esempio l’utilizzo di lettere minuscole nei nomi dei file, di un separatore per la gestione dei caratteri non validi e del numero massimo di caratteri consentiti nei nomi dei file. Per configurare queste proprietà, aggiungi le seguenti coppie di valori chiave nel file di configurazione:

| Chiave proprietà | Valore proprietà |
|------------|--------------|
| `nodename.uselower` | Booleano \(true/false\).<br> **Valore predefinito**: true |
| `nodename.separator` | Qualsiasi carattere. <br> **Valore predefinito**: \_ *\(trattino basso\)* |
| `nodename.maxlength` | Valore intero.<br> **Valore predefinito**: 50 |

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle *com.adobe.fmdita.common.SanitizeNodeNameImpl*.

1. Nel set di caratteri **Non consentito per la pubblicazione nella proprietà AEM Sites**, verificare che la proprietà sia impostata su ```'<>`@$```. È possibile aggiungere altri caratteri speciali all&#39;elenco, tuttavia è necessario che siano presenti i caratteri speciali richiesti.

   >[!NOTE]
   >
   > È inoltre possibile configurare le altre proprietà, ad esempio **Usa caratteri minuscoli** nei nomi dei file, **Separatore** per gestire i caratteri non validi e **Numero massimo di caratteri** consentito nei nomi dei file.

1. Fai clic su **Salva**.

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Nella proprietà **Regex per caratteri validi**, verificare che la proprietà sia impostata su `[-a-zA-Z0-9_]`. È possibile aggiungere altri caratteri all&#39;elenco, tuttavia è necessario che siano presenti questi caratteri di base e l&#39;elenco deve iniziare con un trattino \(`-`\).

   >[!NOTE]
   >
   > Questa proprietà definisce l’elenco dei caratteri validi utilizzati per creare un nuovo file.

1. Fai clic su **Salva**.

>[!ENDTABS]

## Configurare l’appiattimento della struttura dei nodi del sito AEM

Quando si genera l&#39;output di AEM Site, viene creato internamente un nodo per ogni elemento degli argomenti. Per una mappa DITA con migliaia di argomenti, questa struttura di nodi può diventare troppo profonda. Questo tipo di struttura di nodi profondamente nidificata può presentare problemi di prestazioni per siti più grandi. L’istantanea seguente mostra la struttura dei nodi profondamente nidificati per un output di un sito AEM:

![](assets/deep-nested-aem-site-node-structure.png)

Nell&#39;istantanea precedente, si noti che viene creato un nodo per ogni elemento `p` e i relativi sottoelementi successivi e che viene creata una struttura simile per ogni altro elemento utilizzato nell&#39;argomento.

AEM Guides consente di configurare la modalità di creazione interna della struttura dei nodi dell’output del sito AEM. È possibile appiattire la struttura del nodo in corrispondenza di elementi specifici, il che significa che è possibile definire un elemento che verrà considerato come elemento principale e tutti i sottoelementi al suo interno verranno uniti all’elemento principale. Se ad esempio si decide di appiattire l&#39;elemento `p`, qualsiasi elemento visualizzato all&#39;interno dell&#39;elemento `p` verrà unito all&#39;elemento `p` principale. Non verrà creata una nota separata per alcun sottoelemento all&#39;interno dell&#39;elemento `p`. Lo snapshot seguente visualizza la struttura del nodo appiattita in corrispondenza dell&#39;elemento `p`:

![](assets/flattened-aem-site-node-structure.png)

Le schede seguenti forniscono istruzioni per appiattire la struttura dei nodi del sito AEM in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Identifica l’elemento in corrispondenza del quale desideri appiattire la struttura del nodo:

1. Sovrapposizione del nodo `libs` nel nodo `apps` e apertura del file elementmapping.xml.

1. Aggiungere la proprietà `<flatten>true</flatten>` nella definizione dell&#39;elemento in corrispondenza del quale si desidera appiattire la struttura del nodo. Ad esempio, se si desidera appiattire la struttura del nodo in corrispondenza dell&#39;elemento `p`, aggiungere l&#39;attributo appiattire nella definizione dell&#39;elemento `p` come illustrato di seguito:

   ```XML
   <ditaelement>
         <name>p</name>
         <class>- topic/p</class>
         <componentpath>fmdita/components/dita/wrapper</componentpath>
         <type>COMPOSITE</type>
         <target>para</target>
         <flatten>true</flatten>
         <wrapelement>div</wrapelement>
      </ditaelement>
   ```

   >[!NOTE]
   >
   > Per impostazione predefinita, la proprietà del nodo appiattito è stata configurata nell&#39;elemento `p`.

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione.
1. Nel file di configurazione, fornisci i seguenti dettagli di \(property\):

   | PID | Chiave proprietà | Valore proprietà |
   |---|------------|--------------|
   | `com.adobe.dxml.flattening.FlatteningConfigurationService` | `flattening.enabled` | Booleano \(true/false\).<br> **Valore predefinito**: `false` |


Ora, quando si genera l&#39;output del sito AEM, i nodi all&#39;interno dell&#39;elemento `p` vengono appiattiti e memorizzati all&#39;interno dell&#39;elemento `p` stesso. Le nuove proprietà di conversione per l&#39;elemento `p` sono disponibili in CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png)

>[!TAB On-Premise]

1. Specifica l’elemento in corrispondenza del quale desideri appiattire la struttura del nodo.

   1. Sovrapposizione del nodo `libs` nel nodo `apps` e apertura del file elementmapping.xml.

   1. Aggiungere la proprietà `<flatten>true</flatten>` nella definizione dell&#39;elemento in corrispondenza del quale si desidera appiattire la struttura del nodo. Ad esempio, se si desidera appiattire la struttura del nodo in corrispondenza dell&#39;elemento `p`, aggiungere l&#39;attributo appiattire nella definizione dell&#39;elemento `p` come illustrato di seguito:

      ```XML
      <ditaelement>
          <name>p</name>
          <class>- topic/p</class>
          <componentpath>fmdita/components/dita/wrapper</componentpath>
          <type>COMPOSITE</type>
          <target>para</target>
          <flatten>true</flatten>
          <wrapelement>div</wrapelement>
      </ditaelement>
      ```

      >[!NOTE]
      >
      > Per impostazione predefinita, la proprietà del nodo appiattito è stata configurata nell&#39;elemento `p`.

1. Abilitare la configurazione di appiattimento del nodo del sito in configMgr.

   1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

      L&#39;URL predefinito per accedere alla pagina di configurazione è:

      ```http
      http://<server name>:<port>/system/console/configMgr
      ```

   1. Cerca e fai clic sul bundle *com.adobe.dxml.flattening.FlatteningConfigurationService*.

   1. Selezionare l&#39;opzione **Appiattimento proprietà.enabled**.

   1. Fai clic su **Salva**.


>[!IMPORTANT]
>
> Se hai apportato modifiche al file elementmapping.xml, accertati di aprire configMgr e salvare eventuali bundle per rendere effettive le modifiche.

Ora, quando si genera l&#39;output del sito AEM, i nodi all&#39;interno dell&#39;elemento `p` vengono appiattiti e memorizzati all&#39;interno dell&#39;elemento `p` stesso. Le nuove proprietà di conversione per l&#39;elemento `p` sono disponibili in CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png){width="650" align="left"}

>[!ENDTABS]

**Cerca una stringa all&#39;interno del contenuto nell&#39;output del sito AEM (solo per Cloud Service)**

Per impostazione predefinita, è possibile cercare una stringa nei titoli solo all’interno dell’output del sito AEM. Puoi configurare il sistema per la ricerca di una stringa sia nei titoli che nel contenuto o nel corpo dell’output del sito AEM.

>[!NOTE]
>
> A volte la ricerca può funzionare per alcuni elementi nel contenuto, ma puoi configurarla per funzionare per l’intero contenuto.

![](assets/flatten-aem-site-note-props-crxde-search.png)

Per abilitare la ricerca, devi configurare l’appiattimento della struttura dei nodi del sito AEM.

ATTENZIONE:

È possibile cercare fino a 1 MB di contenuto appiattito. Ad esempio, nella schermata precedente, puoi cercare se il contenuto sotto il tag &lt;p\> è &lt;= 1Mb.

>[!NOTE]
>
> La ricerca funziona sugli elementi solo se l&#39;attributo `<flatten>` è impostato su true. Per impostazione predefinita, in AEM Guides l&#39;attributo `<flatten>` è impostato su true per gli elementi di testo comunemente utilizzati, ad esempio &lt;p\> &lt;ul\> &lt;lI\>. Tuttavia, se sono stati creati alcuni elementi personalizzati, è necessario impostare l&#39;attributo `<flatten>` su true nel file elementmapping.xml.

**Impedisci l&#39;appiattimento della struttura dei nodi del sito AEM**

Simile a specificare il nodo da &quot;appiattire&quot; nell’output di AEM Site, puoi anche specificare un elemento da escludere da questa configurazione. Ad esempio, se si desidera appiattire i nodi in corrispondenza dell&#39;elemento `body`, ma non si desidera appiattire alcun elemento `table` in `body`, è possibile aggiungere la proprietà exclude all&#39;interno della definizione dell&#39;elemento `table`.

Per escludere l&#39;elemento `table` dall&#39;appiattimento, aggiungere la seguente proprietà alla definizione dell&#39;elemento `table`:

`<preventancestorflattening>true|false</preventancestorflattening>`

## Configurare il controllo delle versioni per le pagine eliminate nell’output del sito AEM

Quando si genera l&#39;output del sito AEM con l&#39;opzione **Elimina e** Crea **&#x200B;**&#x200B;selezionata per l&#39;impostazione Pagine di output esistenti, viene creata una versione per la pagina\(s\) da eliminare. Puoi configurare il sistema in modo da interrompere la creazione di una versione prima dell’eliminazione.

Le schede seguenti forniscono istruzioni per interrompere la creazione di una versione per le pagine che vengono eliminate in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione.
1. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per configurare l&#39;opzione **Do Not Create Version for Deleted Pages**:

   | PID | Chiave proprietà | Valore proprietà |
   |---|------------|--------------|
   | `com.adobe.fmdita.confi g.ConfigManager` | `no.version.creation.on.deletion` | Booleano \(true/false\).<br> **Valore predefinito**: `true` |

   >[!NOTE]
   >
   > Selezionando questa opzione, gli utenti potranno eliminare direttamente le pagine senza creare alcuna versione. Se l&#39;opzione non è selezionata, viene creata una versione prima che le pagine\(s\) vengano eliminate.

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle *com.adobe.fmdita.config.ConfigManager*.

1. Seleziona **Non creare la versione per le pagine eliminate**.

   >[!NOTE]
   >
   > Selezionando questa opzione, gli utenti potranno eliminare direttamente le pagine senza creare alcuna versione. Se l&#39;opzione non è selezionata, viene creata una versione prima che le pagine\(s\) vengano eliminate.

1. Fai clic su **Salva**.

>[!ENDTABS]

## Configurare il rewriter personalizzato con Experience Manager Guides (solo per Cloud Service) {#custom-rewriter}

Experience Manager Guides dispone di un modulo [**rewriter**](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html) Sling personalizzato per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse). La configurazione del rewriter è installata nel percorso seguente: <br> `/apps/fmdita/config/rewriter/fmdita-crossmap-link-patcher`.

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50.  Per evitare questo problema, è necessario un valore >50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).



