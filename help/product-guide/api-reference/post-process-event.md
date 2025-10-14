---
title: Gestore di eventi di post-elaborazione
description: Scopri il gestore di eventi di post-elaborazione
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 8e57d4048f4aa13d7f77f25082d4e7aa329ee355
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 5%

---

# Gestore di eventi di post-elaborazione {#id175UB30E05Z}

## UUID e CLOUD SERVICE

Adobe Experience Manager Guides espone l&#39;evento `com/adobe/guides/postprocess/complete` utilizzato per eseguire eventuali operazioni di post-elaborazione. Questo evento viene attivato ogni volta che si esegue un&#39;operazione su un file DITA. Le seguenti operazioni su un file DITA attivano questo evento:

- Carica
- Creare
- Modificare

>[!NOTE]
>
> L&#39;evento di post-elaborazione viene attivato abilitando il flag `fire.processing.events` che è un parametro di configurazione in `fmdita config manager`. Se è impostato su true, attiva degli eventi (com/adobe/guides/postprocess/complete) per tenere traccia del completamento della post-elaborazione. Per impostazione predefinita, è impostato su false (disabilitato).

È necessario creare un gestore eventi di Adobe Experience Manager per leggere le proprietà disponibili in questo evento ed eseguire ulteriori elaborazioni.

I dettagli dell’evento sono spiegati di seguito:

**Nome evento**:

```
com/adobe/guides/postprocess/complete 
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `path` | Stringa | Percorso del file che ha attivato l&#39;evento. In genere si tratta del file su cui è stata eseguita un&#39;operazione. |
| `eventType` | Stringa | Il tipo di evento, ad esempio CREATE o MODIFY. |
| `status` | Stringa | Stato di ritorno per l&#39;operazione eseguita. Le opzioni possibili sono: - <br>- OPERAZIONE RIUSCITA: l&#39;operazione di post-elaborazione è stata completata. <br>- NON RIUSCITO: operazione di post-elaborazione non riuscita a causa di un errore. |
| `errorMsg` | Stringa | Il messaggio di errore in caso di errore dell’operazione di post-elaborazione. |
| `uuid` | Stringa | L’UUID del file che ha attivato questo evento. In genere si tratta del file su cui è stata eseguita un&#39;operazione. |

**Listerner eventi di esempio**


```
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/guides/postprocess/complete",
        })
public class PostProcessCompleteEventHandler implements EventHandler {

    protected final Logger log = LoggerFactory.getLogger(this.getClass());

    @Override
    public void handleEvent(final Event event) {
        Set<String> propertyNames = new HashSet<>(Arrays.asList(event.getPropertyNames()));
        Map<String, String> properties = new HashMap<>();
        properties.put("path", (String) event.getProperty("path"));
        properties.put("eventType", (String) event.getProperty("eventType"));
        properties.put("status", (String) event.getProperty("status"));
        if(propertyNames.contains("errorMsg")) {
            properties.put("errorMsg", (String) event.getProperty("errorMsg"));
        }
        if (propertyNames.contains("uuid")) {
            properties.put("uuid", (String) event.getProperty("uuid"));
        }
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
    }
}
```

## Non UUID


Adobe Experience Manager Guides espone com/adobe/fmdita/postprocess/complete event utilizzato per eseguire eventuali operazioni di post-elaborazione. Questo evento viene attivato ogni volta che si esegue un&#39;operazione su un file DITA. Le seguenti operazioni su un file DITA attivano questo evento:

>[!NOTE]
>
> Questo evento non viene attivato per l’operazione di eliminazione in AEM 6.1.

- Carica
- Creazione
- Modifiche
- Eliminazione

È necessario creare un gestore eventi di Adobe Experience Manager per leggere le proprietà disponibili in questo evento ed eseguire ulteriori elaborazioni.

I dettagli dell’evento sono spiegati di seguito:

**Nome evento**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `path` | Stringa | Percorso del file che ha attivato l&#39;evento. In genere si tratta del file su cui è stata eseguita un&#39;operazione. |
| `status` | Stringa | Stato di ritorno per l&#39;operazione eseguita. Le opzioni possibili sono: - <br>- OPERAZIONE RIUSCITA: l&#39;operazione di post-elaborazione è stata completata. <br>- COMPLETATO CON ERRORI: operazione di post-elaborazione completata, ma con alcuni errori. <br>- NON RIUSCITO: operazione di post-elaborazione non riuscita a causa di un errore. |
| `message` | Stringa | Nel caso in cui lo stato sia COMPLETATO CON ERRORI o NON RIUSCITO, questo parametro contiene i dettagli sull’errore o sul motivo dell’errore. |
| `operation` | Stringa | Operazione di post-elaborazione eseguita sul file. Le opzioni possibili sono:<br>- Aggiunta <br>- Aggiornamento <br>- Eliminazione |
