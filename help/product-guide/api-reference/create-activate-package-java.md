---
title: API basata su Java per la creazione e l’attivazione di pacchetti
description: Scopri l’API basata su Java per la creazione e l’attivazione dei pacchetti
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
feature: Java-Based API Packages
role: Developer
level: Experienced
source-git-commit: ed0b0e6124a8656e711a8e64b290b805569fbd48
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# API basata su Java per la creazione e l’attivazione di pacchetti {#id175UB30E05Z}

>[!NOTE]
>
> Puoi utilizzare le API basate su Java disponibili in Experience Manager Guides per creare plug-in personalizzati ed estendere flussi di lavoro preconfigurati. Questo articolo verrà archiviato a novembre 2024.
> Visualizza [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) per la documentazione più recente e dettagliata sull&#39;utilizzo dell&#39;API basata su Java.


La seguente API basata su Java consente di creare e attivare pacchetti CRX. Questa API è disponibile sotto forma di bundle. Per utilizzare queste API, devi includere questo bundle nel codice.

Dettagli bundle:

- ID gruppo: **com.adobe.fmdita**

- ID artefatto: **api**

- Versione: **3.3**

- Pacchetto: **com.adobe.fmdita.api.crxactivate**

- Dettagli classe:

  ```JAVA
  public class CRXActivator
  ```

  La classe **`CRXActivator`** contiene un metodo per creare pacchetti CRX e replicarli nell&#39;istanza Publish.


## Creare e attivare pacchetti

Il metodo `activate` crea un pacchetto CRX nell&#39;istanza di authoring e lo replica nell&#39;istanza di pubblicazione, se necessario. Si presume che i parametri di replica AEM siano già stati impostati nell’istanza di authoring. Questo metodo crea il pacchetto CRX in base a un elenco di regole fornite come parametri di input in una stringa JSON.
>[!NOTE]
>
> Gli errori rilevati durante il processo di creazione o attivazione vengono scritti in `outputstream`.

### Esempio con due parametri

**Sintassi**:


```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream, 
  Session session
) 
throws GuidesApiException
```

### Esempio con terzo parametro opzionale

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream,
  String activationTarget, 
  Session session
) 
throws GuidesApiException
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `json` | Stringa | Stringa JSON che determina il pacchetto CRX da generare. Utilizzare il formato seguente per creare la stringa JSON: <br>- `activate`: è di tipo booleano \(`true`/`false`\). Determina se il pacchetto CRX creato nell’istanza di authoring viene replicato nell’istanza di pubblicazione. <br> - `rules`: è di tipo array JSON. Array di regole JSON, elaborate in sequenza per generare il pacchetto CRX. <br> - `rootPath`: è di tipo String. Percorso di base su cui vengono eseguite le query nodo/proprietà. Se non sono presenti query nodo/proprietà, il percorso radice e tutti i nodi presenti nel percorso radice vengono inclusi nel pacchetto CRX. <br> - `nodeQueries`: è di tipo Regex Array. Array di espressioni regolari utilizzate per includere file specifici nel percorso principale. <br> - `propertyQueries`: è di tipo array JSON. Array di oggetti JSON con ogni oggetto JSON costituito da una query XPath da eseguire sul percorso principale e dal nome di una proprietà presente in ogni nodo JCR dopo l’esecuzione della query. Il valore della proprietà in ciascun nodo JCR deve essere un percorso o un array di percorsi. I percorsi presenti in questa proprietà vengono aggiunti al pacchetto CRX. |
| `outputstream` | java.io.OutputStream | Viene utilizzato per scrivere il risultato di varie fasi, come l’esecuzione di query, l’inclusione di file, la creazione di pacchetti CRX o l’attivazione. Qualsiasi errore riscontrato durante il processo di creazione o attivazione viene scritto in `outputstream`. Questa opzione è utile per il debug. |
| `session` | Stringa | Una sessione JCR valida con autorizzazione di attivazione. |
| `activationTarget` | Stringa | (*Facoltativo*) `preview` o `publish` per il Cloud Service e `publish` per il software locale <br>. Per il Cloud Service, se il parametro contiene un valore non valido, l&#39;attivazione del pacchetto non riesce. <br> - Per il software locale, se il parametro contiene un valore non valido, l&#39;errore viene registrato e la pubblicazione viene eseguita utilizzando il valore predefinito `publish`. |

**Eccezione**:

Genera `java.io.IOException` e `java.io.IllegalArgumentException`


Se non si definisce il parametro opzionale `activationTarget`, verrà attivato utilizzando l&#39;agente di pubblicazione predefinito sia per il software di Cloud Service che per quello locale.


**Esempio**:
L’esempio seguente mostra come creare una query JSON:

```JSON
{
  "activate": true,
  "rules": [
    {
      "rootPath": "/content/dam/nested",
      "nodeQueries": [
        ".*\\.jpg",
        ".*\\.png",
        ".*\\.gif"        
      ]
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap"
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap",
      "propertyQueries": [
        {
          "query": "//*[@fileReference]",
          "property": "fileReference"
        }
      ]
    }
  ]
}
```

La query JSON di esempio è costituita dalle regole seguenti:

- Solo le immagini .png, .jpg e .gif nel percorso /content/dam/nested sono incluse nel pacchetto.
- Tutti i nodi in /content/output/sites/hierarchy\_ditamap sono inclusi nel pacchetto.
- I percorsi presenti nella proprietà `fileReference` dei nodi in /content/output/sites/hierarchy\_ditamap sono inclusi nel pacchetto.
