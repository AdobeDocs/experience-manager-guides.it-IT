---
title: Gestore eventi di completamento attivazione in blocco
description: Scopri il gestore di eventi di attivazione in blocco e completamento
feature: Bulk Activation Event Handler
role: Developer
level: Experienced
exl-id: 08b153d7-3d13-4804-9e3e-38790dbea1f3
source-git-commit: 9b8971bf7065a94a2e42669094249c822c555718
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 6%

---

# Gestore eventi di completamento attivazione in blocco

Experience Manager Guides espone l&#39;evento `com/adobe/fmdita/replication/complete` utilizzato per eseguire operazioni dopo il completamento di un processo di attivazione in blocco. Questo evento viene attivato ogni volta che viene completato un processo di attivazione in blocco. Ad esempio, se esegui l’attivazione in blocco di un predefinito per sito AEM di una mappa, questo evento viene chiamato al termine del processo di attivazione.

È necessario creare un gestore eventi AEM per leggere le proprietà disponibili in questo evento ed eseguire ulteriori elaborazioni.

I dettagli dell’evento sono spiegati di seguito:

**Nome evento**:

```
com/adobe/fmdita/replication/complete 
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `path` | Stringa | Percorso del file che ha attivato l&#39;evento. <br> Ad esempio, `/content/output/sites/ditamap1-ditamap`. <br> È un elenco di percorsi serializzati come array JSON. |
| `messageType` | Stringa | Tipo di messaggio. <br>Opzione possibile: `REPLICATION` |
| `action` | Stringa | Questa è l’azione eseguita. <br>Opzione possibile: `BulkReplicate` |
| `user` | Stringa | Utente che ha avviato l&#39;operazione. |
| `result` | Stringa | Risultato dell&#39;attivazione in blocco. È un oggetto JSON serializzato: <br>`{"success":boolean,"code":integer,"message":"" }` |
| `agentId` | Stringa | L’agentId utilizzato nella replica. Esempio: `"publish"`. |
| `importMode` | Stringa | Modalità di importazione utilizzata in Activation. Opzioni possibili: <br>`REPLACE, MERGE, UPDATE`. |


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
