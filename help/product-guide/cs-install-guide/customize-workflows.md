---
title: Configurare e personalizzare i flussi di lavoro
description: Scopri come configurare e personalizzare i flussi di lavoro
exl-id: a5742082-cc0b-49d9-9921-d0da1b272ea5
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1362'
ht-degree: 1%

---

# Configurare e personalizzare i flussi di lavoro {#id181AI0OJ0RO}

I flussi di lavoro consentono di automatizzare le attività di Adobe Experience Manager \(AEM\). Un flusso di lavoro è costituito da una serie di passaggi eseguiti in un ordine specifico. Puoi definire un’attività distinta da eseguire in ogni passaggio. Ad esempio, è possibile inviare una notifica e-mail a tutti i revisori di un gruppo quando viene creata una revisione dell&#39;argomento. In alternativa, invia una notifica all’editore al termine di un’attività di generazione dell’output.

Per ulteriori informazioni sui flussi di lavoro in AEM, consulta:

- [Amministrazione delle istanze dei flussi di lavoro](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html)

- Applicazione e partecipazione ai flussi di lavoro: [Utilizzo dei flussi di lavoro per i progetti](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/projects/workflows.html).


Le sezioni in questo argomento descrivono le varie personalizzazioni che è possibile effettuare nei flussi di lavoro predefiniti forniti nelle guide AEM.

## Personalizza flusso di lavoro di revisione {#id176NE0C00HS}

Il team di authoring dei contenuti di ogni organizzazione lavora in modo specifico per soddisfare i requisiti aziendali. In alcune organizzazioni è presente un editor dedicato, mentre in altre potrebbe essere presente un sistema di revisione editoriale automatizzato. Ad esempio, in un’organizzazione, un flusso di lavoro tipico per l’authoring e la pubblicazione può includere attività come: ogni volta che un autore esegue l’authoring di contenuti, questo passa automaticamente ai revisori e, al termine della revisione, passa all’editore per generare l’output finale. In AEM, le attività che esegui sui contenuti e sulle risorse possono essere combinate sotto forma di un processo e mappate a un flusso di lavoro AEM. Per ulteriori informazioni sui flussi di lavoro in AEM, consulta [Amministrazione dei flussi di lavoro](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html) nella documentazione AEM.

Le guide AEM consentono di personalizzare il flusso di lavoro di revisione predefinito. Con gli altri flussi di lavoro di authoring o pubblicazione, puoi utilizzare i quattro processi personalizzati seguenti relativi alla revisione.

- **Crea revisione**: questo processo prepara i metadati necessari per creare un’attività di revisione. Ad esempio, assegnerà l&#39;autorizzazione di revisione ai revisori, imposterà lo stato degli argomenti su in revisione, imposterà le timeline di revisione e altro ancora. Tra i quattro processi, questo è l’unico processo obbligatorio che deve essere incluso nel flusso di lavoro personalizzato. Nel flusso di lavoro è possibile scegliere di includere o escludere gli altri tre processi.

- **Assegna attività di revisione**: questo processo crea l&#39;attività di revisione e invia la notifica all&#39;iniziatore e ai revisori.

- **Invia e-mail di revisione**: questo processo invia l’e-mail di revisione all’iniziatore e ai revisori.

- **Pianifica processo per chiudere la revisione**: questo processo assicura che il processo di revisione sia completato non appena viene raggiunta la scadenza.


Quando crei un flusso di lavoro di revisione personalizzato, la prima attività consiste nell’impostare i metadati richiesti dal processo Crea revisione. A tale scopo, è possibile creare uno script ECMA. Di seguito è riportato un esempio dello script ECMA che assegna i metadati:

```javascript
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
| `payloadJson` | Oggetto JSON | Specifica i seguenti valori: -   `base`: percorso della cartella principale contenente l’argomento inviato per la revisione. <br> -   `asset`: percorso dell’argomento inviato per la revisione. <br> -   `referrer`: lascia vuoto il campo. |
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

Diversi flussi di lavoro delle guide dell’AEM utilizzano le notifiche e-mail. Ad esempio, se avvii un’attività di revisione, viene inviata una notifica e-mail ai revisori. Tuttavia, per assicurarsi che la notifica e-mail venga inviata, devi abilitare questa funzionalità in AEM. Per abilitare le notifiche e-mail in AEM, consulta l’articolo [Invio e-mail](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#sending-email) nella documentazione AEM.

Le guide AEM contengono una serie di modelli e-mail che puoi personalizzare. Per personalizzare questi modelli, effettua le seguenti operazioni:

1. Utilizzare Gestione pacchetti per scaricare `/libs/fmdita/mail` file.

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

```javascript
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
