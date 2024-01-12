---
title: Configurare e personalizzare i flussi di lavoro
description: Scopri come configurare e personalizzare i flussi di lavoro
exl-id: 3be387b9-6ac2-4b61-afdf-fbe9d8b6cc1e
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1744'
ht-degree: 1%

---

# Configurare e personalizzare i flussi di lavoro {#id181AI0OJ0RO}

I flussi di lavoro consentono di automatizzare le attività di Adobe Experience Manager \(AEM\). Un flusso di lavoro è costituito da una serie di passaggi eseguiti in un ordine specifico. Puoi definire un’attività distinta da eseguire in ogni passaggio. Ad esempio, è possibile inviare una notifica e-mail a tutti i revisori di un gruppo quando viene creata una revisione dell&#39;argomento. In alternativa, invia una notifica all’editore al termine di un’attività di generazione dell’output.

Per ulteriori informazioni sui flussi di lavoro in AEM, consulta:

- [Amministrazione dei flussi di lavoro](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/workflows.html)

- Applicazione e partecipazione ai flussi di lavoro: [Utilizzo dei flussi di lavoro](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/workflows.html).

- Creazione di modelli di flusso di lavoro ed estensione delle funzionalità del flusso di lavoro: [Sviluppo ed estensione dei flussi di lavoro](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/workflows.html).

- Miglioramento delle prestazioni dei flussi di lavoro che utilizzano risorse server significative: [Elaborazione flusso di lavoro simultaneo](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/configuring-performance.html#ConfiguringforPerformance).


Le sezioni in questo argomento descrivono le varie personalizzazioni che è possibile effettuare nei flussi di lavoro predefiniti forniti nelle guide AEM.

## Personalizza flusso di lavoro di revisione {#id176NE0C00HS}

Il team di authoring dei contenuti di ogni organizzazione lavora in modo specifico per soddisfare i requisiti aziendali. In alcune organizzazioni è presente un editor dedicato, mentre in altre potrebbe essere presente un sistema di revisione editoriale automatizzato. Ad esempio, in un’organizzazione, un flusso di lavoro tipico per l’authoring e la pubblicazione può includere attività come: ogni volta che un autore esegue l’authoring di contenuti, questo passa automaticamente ai revisori e, al termine della revisione, passa all’editore per generare l’output finale. In AEM, le attività che esegui sui contenuti e sulle risorse possono essere combinate sotto forma di un processo e mappate a un flusso di lavoro AEM. Per ulteriori informazioni sui flussi di lavoro in AEM, consulta [Amministrazione dei flussi di lavoro](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/workflows.html) nella documentazione AEM.

Le guide AEM consentono di personalizzare il flusso di lavoro di revisione predefinito. Con gli altri flussi di lavoro di authoring o pubblicazione, puoi utilizzare i quattro processi personalizzati seguenti relativi alla revisione.

- **Crea revisione**: questo processo prepara i metadati necessari per creare un’attività di revisione. Ad esempio, assegnerà l&#39;autorizzazione di revisione ai revisori, imposterà lo stato degli argomenti su in revisione, imposterà le timeline di revisione e altro ancora. Tra i quattro processi, questo è l’unico processo obbligatorio che deve essere incluso nel flusso di lavoro personalizzato. Nel flusso di lavoro è possibile scegliere di includere o escludere gli altri tre processi.

- **Assegna attività di revisione**: questo processo crea l&#39;attività di revisione e invia la notifica all&#39;iniziatore e ai revisori.

- **Invia e-mail di revisione**: questo processo invia l’e-mail di revisione all’iniziatore e ai revisori.

- **Pianifica processo per chiudere la revisione**: questo processo assicura che il processo di revisione sia completato non appena viene raggiunta la scadenza.


Quando crei un flusso di lavoro di revisione personalizzato, la prima attività consiste nell’impostare i metadati richiesti dal processo Crea revisione. A tale scopo, è possibile creare uno script ECMA. Di seguito è riportato un esempio dello script ECMA che assegna i metadati:

```json
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
```

Puoi creare questo script in `/etc/workflows/scripts` nodo. La tabella seguente descrive le proprietà assegnate da questo script ECMA:

| Proprietà | Tipo | Descrizione |
|--------|----|-----------|
| `initiator` | Stringa | ID utente dell&#39;utente che avvia l&#39;attività di revisione. |
| `operation` | Stringa | Un valore statico impostato come `AEM_REVIEW`. |
| `orgTopics` | Stringa | Percorso degli argomenti condivisi per la revisione. Specifica più argomenti separati da virgole. |
| `payloadJson` | Oggetto JSON | Specifica i seguenti valori:<br> - `base`: percorso della cartella principale contenente l’argomento inviato per la revisione.<br>- `asset`: percorso dell’argomento inviato per la revisione. <br>- `referrer`: lascia vuoto il campo. |
| `deadline` | Stringa | Specifica l’ora in `yyyy-MM-dd'T'HH:mm:ss.SSSXXX` formato. |
| `title` | Stringa | Immettere un titolo per l&#39;attività di revisione. |
| `description` | Stringa | Immettere una descrizione per il task di revisione. |
| `assignee` | Stringa | ID utente degli utenti a cui desideri inviare l&#39;argomento\(s\) per la revisione. |
| `status` | Intero | Un valore statico impostato come 1. |
| `startTime` | Lungo | Utilizza il `System.currentTimeMillis()` per ottenere l&#39;ora di sistema corrente. |

Dopo aver creato lo script, chiamalo prima del processo Crea revisione nel flusso di lavoro. Quindi, a seconda delle tue esigenze, puoi chiamare gli altri processi del flusso di lavoro di revisione.

### Rimuovi il flusso di lavoro di revisione dalla configurazione di eliminazione

Per migliorare le prestazioni del motore del flusso di lavoro, puoi eliminare regolarmente le istanze del flusso di lavoro completate dall’archivio AEM. Se utilizzi le configurazioni AEM predefinite, tutte le istanze di flusso di lavoro completate vengono pulite dopo un periodo di tempo specifico. Questo determina anche l’eliminazione di tutti i flussi di lavoro di revisione dall’archivio AEM.

È possibile impedire la rimozione automatica dei flussi di lavoro di revisione rimuovendo il modello di flusso di lavoro di revisione \(informazioni\) dalla configurazione di rimozione automatica. È necessario utilizzare il **Adobe configurazione eliminazione flusso di lavoro Granite** per rimuovere i modelli del flusso di lavoro di revisione dall&#39;elenco di rimozione automatica.

In **Adobe configurazione eliminazione flusso di lavoro Granite**, accertati di elencare almeno un flusso di lavoro che puoi eliminare in modo sicuro. Ad esempio, puoi utilizzare uno dei seguenti flussi di lavoro creati da Guide AEM:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Aggiunta di un flusso di lavoro in **Adobe configurazione eliminazione flusso di lavoro Granite** assicura che l’AEM elimini solo i flussi di lavoro elencati nella configurazione. Questo impedisce all’AEM di eliminare le informazioni del flusso di lavoro di revisione.

Per ulteriori dettagli sulla configurazione di **Adobe configurazione eliminazione flusso di lavoro Granite**, vedi *Amministrazione delle istanze dei flussi di lavoro* nella documentazione AEM.

### Personalizzare i modelli e-mail

Diversi flussi di lavoro delle guide dell’AEM utilizzano le notifiche e-mail. Ad esempio, se avvii un’attività di revisione, viene inviata una notifica e-mail ai revisori. Tuttavia, per assicurarsi che la notifica e-mail venga inviata, devi abilitare questa funzionalità in AEM. Per abilitare le notifiche e-mail in AEM, consulta l’articolo [Configurazione delle notifiche e-mail](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=it) nella documentazione AEM.

Le guide AEM contengono un set di modelli e-mail che puoi personalizzare. Per personalizzare questi modelli, effettua le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Nella scheda Navigator, passare alla posizione seguente:

   `/libs/fmdita/mail`

   >[!NOTE]
   >
   > Non rendere disponibili personalizzazioni nei file di configurazione predefiniti in ``libs`` nodo. È necessario creare una sovrapposizione del ``libs`` nodo in ``apps`` e aggiorna i file richiesti nel ``apps`` solo nodo.

1. La cartella e-mail contiene i seguenti modelli personalizzabili:

   | Nome file modello | Descrizione |
   |-----------------|-----------|
   | closereview.html | Questo modello e-mail viene utilizzato quando un’attività di revisione viene chiusa. |
   | createreview.html | Questo modello e-mail viene utilizzato quando viene creata una nuova attività di revisione. |
   | reviewapproval.css | Questo file CSS contiene lo stile dei modelli e-mail. |


## Personalizzare il flusso di lavoro di generazione post-output {#id17A6GI004Y4}

Le guide AEM offrono la flessibilità di specificare un flusso di lavoro per la generazione post-output. Puoi eseguire alcune attività di post-elaborazione sull’output generato utilizzando le guide AEM. Ad esempio, potrebbe essere utile applicare alcuni tag CQ all’output del sito AEM generato, impostare determinate proprietà all’output del PDF o inviare un’e-mail a un set di utenti una volta generato l’output.

Puoi creare un nuovo modello di flusso di lavoro da utilizzare come flusso di lavoro di generazione post-output. Quando viene attivato un flusso di lavoro di generazione post-output, il flusso di lavoro di generazione dell&#39;output condivide informazioni contestuali tramite la mappa metadati del flusso di lavoro, che è possibile utilizzare per eseguire l&#39;elaborazione sull&#39;output generato. La tabella seguente descrive le informazioni contestuali condivise come metadati:

| Proprietà | Tipo | Descrizione |
|--------|----|-----------|
| ``outputName`` | Stringa | Nome del predefinito di output utilizzato per generare l’output. |
| `generatedPath` | Stringa | Percorso in DAM in cui viene memorizzato l’output generato. |
| `outputType` | com.adobe.fmdita.output.OutputType | Tipo del predefinito di output. |
| `outputTitle` | Stringa | Titolo del predefinito di output. |
| `outputHistoryPath` | Stringa | Percorso dell’archivio del nodo della cronologia. |
| `isSuccess` | Booleano | Flag che rappresenta lo stato finale del processo di generazione dell’output, ovvero esito positivo o negativo. |
| `logPath` | Stringa | Percorso in DAM in cui vengono salvati i registri di generazione dell’output. |
| `generatedTime` | Lungo | Ora in cui è stato attivato il processo di generazione dell&#39;output. |
| `initiator` | Stringa | ID utente dell’utente che ha attivato il flusso di lavoro di generazione dell’output. |

Per utilizzare i metadati di generazione dell’output, puoi creare uno script ECMA o un bundle OSGi. Di seguito è riportato un esempio dello script ECMA che utilizza i metadati:

>[!NOTE]
>
> Puoi creare questo script in ``/etc/workflows/scripts`` nodo.

```json
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

Dopo aver creato lo script, chiama lo script personalizzato nel flusso di lavoro. Quindi, a seconda delle tue esigenze, puoi chiamare gli altri processi del flusso di lavoro. Dopo aver progettato il flusso di lavoro personalizzato, chiama *Finalizza post-generazione* come ultimo passaggio del processo di workflow. Il *Finalizza post-generazione* Il passaggio assicura che lo stato dell&#39;attività di generazione dell&#39;output venga aggiornato a *Completato* al completamento del processo di generazione dell’output. Dopo aver creato un flusso di lavoro di generazione post-output personalizzato, puoi configurarlo con uno qualsiasi dei predefiniti di generazione di output. Seleziona il flusso di lavoro richiesto in *Esegui flusso di lavoro di post-generazione* del predefinito richiesto. Quando si esegue un&#39;attività di generazione output utilizzando il predefinito di output configurato, lo stato dell&#39;attività \(nella scheda Output\) diventa *Post-elaborazione*.

## Personalizza flusso di lavoro Aggiorna risorsa {#id18C3D0I0B5Z}

Per impostazione predefinita, il *Aggiorna risorsa DAM* Il flusso di lavoro viene attivato quando si crea o si aggiorna una risorsa AEM \(XML o non XML\). Ad esempio, quando si crea o si aggiorna un argomento, *Aggiorna risorsa DAM* workflow viene eseguito. Il *Aggiorna risorsa DAM* Il flusso di lavoro tenta di estrarre i metadati rilevanti dalle risorse. La soluzione preconfigurata *Flusso di lavoro di aggiornamento risorse* non prevede alcun passaggio per estrarre metadati rilevanti da un file DITA e *Aggiorna risorsa DAM* al momento dell’esecuzione, il flusso di lavoro genera molti registri. Se desideri evitare i registri aggiuntivi, puoi configurare il flusso di lavoro in modo da saltare tutti i file XML dall’elaborazione.

Per personalizzare il *Aggiorna risorsa DAM* workflow:

1. apri **Moduli di avvio dei flussi di lavoro** pagina.

   L’URL predefinito per accedere alla pagina Moduli di avvio dei flussi di lavoro è:

   ```http
   http://<server name>:<port>/libs/cq/workflow/admin/console/content/launchers.html
   ```

1. Dall’elenco dei moduli di avvio dei flussi di lavoro, apri le proprietà del **Aggiorna risorsa DAM** flusso di lavoro.

1. Aggiungi una condizione con la seguente espressione:

   ```json
   jcr:content/metadata/dc:format!=application/xml
   ```

1. Clic **Salva e chiudi**


## Configurare il flusso di lavoro XML di post-elaborazione {#id18CJB03J0Y4}

Le guide AEM creano una serie di flussi di lavoro che consentono di lavorare con contenuti DITA nell’AEM. Alcuni flussi di lavoro, ad esempio, vengono eseguiti quando si caricano contenuti DITA o si aggiornano contenuti esistenti. Questi flussi di lavoro analizzano i documenti DITA ed eseguono varie attività, ad esempio l&#39;impostazione dei metadati, l&#39;aggiunta di predefiniti di output alle nuove mappe DITA e altre attività correlate.

>[!NOTE]
>
> Per personalizzare o estendere i flussi di lavoro di post-elaborazione predefiniti, puoi utilizzare il gestore di eventi di post-elaborazione descritto in *Riferimento API per le guide di Adobe Experience Manager*.

Le seguenti proprietà determinano il modo in cui AEM Guides esegue i flussi di lavoro di post-elaborazione:

>[!NOTE]
>
> Le seguenti proprietà sono accessibili tramite la console web: http://&lt;server name=&quot;&quot;>:&lt;port>/system/console/configMgr.

| Proprietà | Nome bundle | Descrizione |
|--------|-----------|-----------|
| Outref dinamici | `com.adobe.fmdita.postprocess.PostProcessObservation` | Per tutti i file su cui non è stata eseguita la post-elaborazione, recupera i riferimenti in uscita analizzando i file dell’argomento. Si consiglia di mantenere questa opzione disabilitata in quanto ha la possibilità di sovraccaricare il sistema se il numero di file da elaborare è elevato. |
| Threads post-elaborazione | `com.adobe.fmdita.config.ConfigManager` | Imposta il numero di thread di post-elaborazione da utilizzare per il flusso di lavoro di post-elaborazione. <br>Il valore predefinito è 1. |
