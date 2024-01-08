---
title: Gestore eventi di completamento attivazione in blocco
description: Scopri il gestore di eventi di attivazione in blocco e completamento
source-git-commit: 8f1bb12a92ab9a63aef1765e51159644242683a0
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# Gestore eventi di completamento attivazione in blocco

Experience Manager Guide espone `com/adobe/fmdita/replication/complete` evento utilizzato per eseguire operazioni dopo il completamento di un processo di attivazione in blocco. Questo evento viene attivato ogni volta che viene completato un processo di attivazione in blocco. Ad esempio, se esegui l’attivazione in blocco di un predefinito per sito AEM di una mappa, questo evento viene chiamato al termine del processo di attivazione.

È necessario creare un gestore eventi AEM per leggere le proprietà disponibili in questo evento ed eseguire ulteriori elaborazioni.

I dettagli dell’evento sono spiegati di seguito:

**Nome evento**:

```
com/adobe/fmdita/replication/complete 
```

**Parametri**: |Nome|Tipo|Descrizione| ----|----|-----------| |`path`|String|Percorso del file che ha attivato l&#39;evento. <br> Ad esempio: `/content/output/sites/ditamap1-ditamap`. <br> Si tratta di un elenco di percorsi serializzati come array JSON.| |`messageType`|Stringa|Tipo di messaggio. <br>Possibile opzione: `REPLICATION`| |`action`|Stringa|Questa è l&#39;azione eseguita. <br>Possibile opzione: `BulkReplicate`| |`user`|String|Utente che ha avviato l&#39;operazione.| |`result`|Stringa|Risultato dell&#39;attivazione in blocco. È un oggetto JSON serializzato: <br>`{"success":boolean,"code":integer,"message":"" }`| |`agentId`|String|L&#39;agentId utilizzato nella replica. Esempio: `"publish"`.| |`importMode`|Stringa|Modalità di importazione utilizzata in Activation. Le opzioni possibili sono: <br>`REPLACE, MERGE, UPDATE`.|


**Listener di eventi di esempio**:

```XML
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/fmdita/replication/complete",
        })
 
public class SampleEventHandler implements EventHandler {
 
    protected final Logger log = LoggerFactory.getLogger(this.getClass());
 
    @Override
    public void handleEvent(final Event event) {
        Map<String, String> properties = new HashMap<>();
        properties.put("paths", (String) event.getProperty("paths"));
        properties.put("messageType", (String) event.getProperty("messageType"));
        properties.put("action", (String) event.getProperty("action"));
        properties.put("result", (String) event.getProperty("result"));
        properties.put("user", (String) event.getProperty("user"));
        properties.put("agentId", (String) event.getProperty("agentId"));
        properties.put("importMode", (String) event.getProperty("importMode"));
 
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
 
    }
}
```
