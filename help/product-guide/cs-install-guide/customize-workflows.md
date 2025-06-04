---
title: Configurare e personalizzare i flussi di lavoro
description: Scopri come configurare e personalizzare i flussi di lavoro
exl-id: a5742082-cc0b-49d9-9921-d0da1b272ea5
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 026d75e69ef002607ac375cf1af7d055fcc22b38
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 2%

---

# Configurare e personalizzare i flussi di lavoro {#id181AI0OJ0RO}

I flussi di lavoro consentono di automatizzare le attività di Adobe Experience Manager \(AEM\). Un flusso di lavoro è costituito da una serie di passaggi eseguiti in un ordine specifico. Puoi definire un’attività distinta da eseguire in ogni passaggio. Ad esempio, è possibile inviare una notifica e-mail a tutti i revisori di un gruppo quando viene creata una revisione dell&#39;argomento. In alternativa, invia una notifica all’editore al termine di un’attività di generazione dell’output.

Per ulteriori informazioni sui flussi di lavoro in AEM, consulta:

- [Amministrazione istanze flusso di lavoro](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html?lang=it)

- Applicazione e partecipazione ai flussi di lavoro: [Utilizzo dei flussi di lavoro dei progetti](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/projects/workflows.html?lang=it).


Le sezioni in questo argomento descrivono le varie personalizzazioni che è possibile effettuare nei flussi di lavoro predefiniti forniti in AEM Guides.

## Personalizza flusso di lavoro di revisione {#id176NE0C00HS}

Il team di authoring dei contenuti di ogni organizzazione lavora in modo specifico per soddisfare i requisiti aziendali. In alcune organizzazioni è presente un editor dedicato, mentre in altre potrebbe essere presente un sistema di revisione editoriale automatizzato. Ad esempio, in un’organizzazione, un flusso di lavoro tipico per l’authoring e la pubblicazione può includere attività come: ogni volta che un autore esegue l’authoring di contenuti, questo passa automaticamente ai revisori e, al termine della revisione, passa all’editore per generare l’output finale. In AEM, le attività che esegui sui contenuti e sulle risorse possono essere combinate sotto forma di un processo e mappate a un flusso di lavoro AEM. Per ulteriori informazioni sui flussi di lavoro in AEM, consulta [Amministrazione dei flussi di lavoro](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html?lang=it) nella documentazione di AEM.

AEM Guides consente di personalizzare il flusso di lavoro di revisione predefinito. Con gli altri flussi di lavoro di authoring o pubblicazione, puoi utilizzare i quattro processi personalizzati seguenti relativi alla revisione.

- **Crea revisione**: questo processo prepara i metadati necessari per creare un&#39;attività di revisione. Ad esempio, assegnerà l&#39;autorizzazione di revisione ai revisori, imposterà lo stato degli argomenti su in revisione, imposterà le timeline di revisione e altro ancora. Tra i quattro processi, questo è l’unico processo obbligatorio che deve essere incluso nel flusso di lavoro personalizzato. Nel flusso di lavoro è possibile scegliere di includere o escludere gli altri tre processi.

- **Assegna attività di revisione**: questo processo crea l&#39;attività di revisione e invia la notifica all&#39;iniziatore e ai revisori.

- **Invia e-mail di revisione**: questo processo invia l&#39;e-mail di revisione all&#39;iniziatore e ai revisori.

- **Pianifica processo per chiudere la revisione**: questo processo assicura che il processo di revisione venga completato quando viene raggiunta la scadenza.


Quando crei un flusso di lavoro di revisione personalizzato, la prima attività consiste nell’impostare i metadati richiesti dal processo Crea revisione. A tale scopo, è possibile creare uno script ECMA. Di seguito è riportato un esempio dello script ECMA che assegna i metadati sia per l&#39;argomento che per la mappa.

**Per Argomento**

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
workflowdata.getMetaDataMap().put("reviewType", "AEM");
workflowdata.getMetaDataMap().put("versionJson", "[{\"path\":\"GUID-ca6ae229-889a-4d98-a1c6-60b08a820bb3.dita\",\"review\":true,\"version\":\"1.0\",\"reviewers\":[\"projects-samplereviewproject-owner\"]}]");
workflowdata.getMetaDataMap().put("isDitamap","false");
```

**Per La Mappa**

```javascript
var workflowdata = workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator", "admin");
workflowdata.getMetaDataMap().put("operation", "AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics", "GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita|GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita|GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita|");
var payloadJson = "{\"referrer\":\"\",\"rootMap\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"asset\":[\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\"],\"base\":\"/content/dam\"}";
workflowdata.getMetaDataMap().put("payloadJson", payloadJson);
workflowdata.getMetaDataMap().put("deadline", "2047-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title", "Review task via workflow with map");
workflowdata.getMetaDataMap().put("description", "Review task via workflow with map Description");
workflowdata.getMetaDataMap().put("assignee", "user-one");
workflowdata.getMetaDataMap().put("status", "1");
workflowdata.getMetaDataMap().put("projectPath", "/content/projects/review_project_via_workflow");
workflowdata.getMetaDataMap().put("startTime", new Date().getTime());
var versionJson = "[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]}]";
workflowdata.getMetaDataMap().put("versionJson", versionJson);
workflowdata.getMetaDataMap().put("notifyViaEmail", "true");
workflowdata.getMetaDataMap().put("allowAllReviewers", "false");
workflowdata.getMetaDataMap().put("isDitamap", "true");
workflowdata.getMetaDataMap().put("ditamap", "GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap");
var ditamapHierarchy = "[{\"path\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"items\":[{\"path\":\"GUID-db5787bb-5467-4dc3-b3e5-cfde562ee745.ditamap\",\"items\":[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"items\":[],\"title\":\"\"},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"items\":[],\"title\":\"\"}],\"title\":\"\"},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"items\":[],\"title\":\"\"}]}]";
workflowdata.getMetaDataMap().put("ditamapHierarchy", ditamapHierarchy);
```

È possibile creare questo script nel nodo `/etc/workflows/scripts`. Nella tabella seguente vengono descritte le proprietà assegnate da entrambi gli script ECMA sopra indicati.

| Proprietà | Tipo | Descrizione |
|--------|----|-----------|
| `initiator` | Stringa | ID utente dell&#39;utente che avvia l&#39;attività di revisione. |
| `operation` | Stringa | Un valore statico impostato come `AEM_REVIEW`. |
| `orgTopics` | Stringa | Percorso degli argomenti condivisi per la revisione. Specifica più argomenti separati da virgole. |
| `payloadJson` | Oggetto JSON | Specifica i seguenti valori: -   `base`: percorso della cartella padre contenente l&#39;argomento inviato per la revisione. <br> -   `asset`: percorso dell&#39;argomento inviato per la revisione. <br> -   `referrer`: lasciare vuoto il campo. |
| `deadline` | Stringa | Specificare l&#39;ora nel formato `yyyy-MM-dd'T'HH:mm:ss.SSSXXX`. |
| `title` | Stringa | Immettere un titolo per l&#39;attività di revisione. |
| `description` | Stringa | Immettere una descrizione per il task di revisione. |
| `assignee` | Stringa | ID utente degli utenti a cui desideri inviare l&#39;argomento\(s\) per la revisione. |
| `status` | Numero intero | Un valore statico impostato come 1. |
| `startTime` | Lungo | Utilizzare la funzione `System.currentTimeMillis()` per ottenere l&#39;ora di sistema corrente. |
| `projectPath` | Stringa | Percorso del progetto di revisione a cui verrà assegnata l’attività di revisione. Esempio: /content/projects/samplereviewproject. |
| `reviewType` | Stringa | Valore statico &quot;AEM&quot;. |
| `versionJson` | Oggetto JSON | versionJson è un elenco di argomenti inclusi nella revisione in cui ogni oggetto argomento ha la seguente struttura { &quot;path&quot;: &quot;/content/dam/1-topic.dita&quot;, &quot;version&quot;: &quot;1.1&quot;, &quot;review&quot;: true, &quot;reviewers&quot;: [&quot;projects-we_retail-editor&quot;] } |
| `isDitamap` | Booleano | false/true |
| `ditamapHierarchy` | Oggetto JSON | Se la mappa viene inviata per la revisione, il valore qui dovrebbe essere simile a:[ { &quot;path&quot;: &quot;GUID-f0df1513-fe07-473f-9960-477d4df29c87.ditamap&quot;, &quot;items&quot;: [ { &quot;path&quot;: &quot;GUID-9747e8ab-8cf1-45dd-9e20-d47d482f667d.dita&quot;, &quot;title&quot; &quot;&quot;, &quot;elementi&quot;: [] } ] } ]. |
| `ditamap` | Stringa | Specifica il percorso della mappa dei tag dell&#39;attività di revisione |
| `allowAllReviewers` | Booleano | false/true |
| `notifyViaEmail` | Booleano | false/true |


Dopo aver creato lo script, chiamalo prima del processo Crea revisione nel flusso di lavoro. Quindi, a seconda delle tue esigenze, puoi chiamare gli altri processi del flusso di lavoro di revisione.

### Rimuovi il flusso di lavoro di revisione dalla configurazione di eliminazione

Per migliorare le prestazioni del motore del flusso di lavoro, puoi eliminare regolarmente le istanze del flusso di lavoro completate dall’archivio di AEM. Se utilizzi le configurazioni di AEM predefinite, tutte le istanze di flusso di lavoro completate vengono pulite dopo un periodo di tempo specifico. Questo determina anche l’eliminazione di tutti i flussi di lavoro di revisione dall’archivio AEM.

È possibile impedire la rimozione automatica dei flussi di lavoro di revisione rimuovendo il modello di flusso di lavoro di revisione \(informazioni\) dalla configurazione di rimozione automatica. È necessario utilizzare la **Configurazione di eliminazione del flusso di lavoro di Adobe Granite** per rimuovere i modelli del flusso di lavoro di revisione dall&#39;elenco di rimozione automatica.

Nella **Configurazione eliminazione flusso di lavoro di Adobe Granite**, accertati di elencare almeno un flusso di lavoro che puoi eliminare in modo sicuro. Ad esempio, puoi utilizzare uno dei seguenti flussi di lavoro creati da AEM Guides:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

L&#39;aggiunta di un flusso di lavoro nella **configurazione eliminazione flusso di lavoro di Adobe Granite** garantisce che AEM elimini solo i flussi di lavoro elencati nella configurazione. Questo impedisce ad AEM di eliminare le informazioni del flusso di lavoro di revisione.

Per ulteriori dettagli sulla configurazione della **configurazione di Adobe Granite Workflow Purge**, vedi *Amministrazione delle istanze del flusso di lavoro* nella documentazione di AEM.

### Personalizzare i modelli e-mail

Alcuni flussi di lavoro di AEM Guides utilizzano le notifiche e-mail. Ad esempio, se avvii un’attività di revisione, viene inviata una notifica e-mail ai revisori. Tuttavia, per garantire l’invio della notifica e-mail, devi abilitare questa funzionalità in AEM. Per abilitare le notifiche e-mail in AEM, consulta l&#39;articolo [Invio di e-mail](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html?lang=it#sending-email) nella documentazione di AEM.

L’AEM Guides contiene un set di modelli e-mail che puoi personalizzare. Per personalizzare questi modelli, effettua le seguenti operazioni:

1. Utilizzare Gestione pacchetti per scaricare il file `/libs/fmdita/mail`.

   >[!NOTE]
   >
   > Non effettuare personalizzazioni nei file di configurazione predefiniti disponibili nel nodo ``libs``. È necessario creare una sovrapposizione del nodo ``libs`` nel nodo ``apps`` e aggiornare i file richiesti solo nel nodo ``apps``.

1. La cartella e-mail contiene i seguenti modelli personalizzabili:

   | Nome file modello | Descrizione |
   |-----------------|-----------|
   | closereview.html | Questo modello e-mail viene utilizzato quando un’attività di revisione viene chiusa. |
   | createreview.html | Questo modello e-mail viene utilizzato quando viene creata una nuova attività di revisione. |
   | reviewapproval.css | Questo file CSS contiene lo stile dei modelli e-mail. |


## Personalizzare il flusso di lavoro di generazione post-output {#id17A6GI004Y4}

AEM Guides offre la flessibilità di specificare un flusso di lavoro per la generazione post-output. Puoi eseguire alcune attività di post-elaborazione sull’output generato utilizzando AEM Guides. Ad esempio, puoi applicare alcuni tag CQ all’output del sito AEM generato, impostare determinate proprietà all’output di PDF o inviare un’e-mail a un set di utenti una volta generato l’output.

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
> È possibile creare questo script nel nodo ``/etc/workflows/scripts``.

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

Dopo aver creato lo script, chiama lo script personalizzato nel flusso di lavoro. Quindi, a seconda delle tue esigenze, puoi chiamare gli altri processi del flusso di lavoro. Dopo aver progettato il flusso di lavoro personalizzato, chiama *Finalize Post Generation* come ultimo passaggio del processo del flusso di lavoro. Il passaggio *Finalize Post Generation* assicura che lo stato dell&#39;attività di generazione dell&#39;output venga aggiornato a *Finished* al completamento del processo di generazione dell&#39;output. Dopo aver creato un flusso di lavoro di generazione post-output personalizzato, puoi configurarlo con uno qualsiasi dei predefiniti di generazione di output. Selezionare il flusso di lavoro richiesto nella proprietà *Esegui flusso di lavoro di post-generazione* del predefinito richiesto. Quando esegui un&#39;attività di generazione output utilizzando il predefinito di output configurato, lo stato dell&#39;attività \(nella scheda Output\) diventa *Post-elaborazione*.
