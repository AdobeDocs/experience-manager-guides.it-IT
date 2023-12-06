---
title: API basata su Java per la creazione e l’attivazione di pacchetti
description: Scopri l’API basata su Java per la creazione e l’attivazione dei pacchetti
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# API basata su Java per la creazione e l’attivazione di pacchetti {#id175UB30E05Z}

La seguente API basata su Java consente di creare e attivare pacchetti CRX. Questa API è disponibile sotto forma di bundle. Per utilizzare queste API, devi includere questo bundle nel codice.

Dettagli bundle:

- ID gruppo: **com.adobe.fmdita**

- ID artefatto: **api**

- Versione: **3,3**

- Pacchetto **com.adobe.fmdita.api.crxactivate**

- Dettagli classe:

  ```JAVA
  public class CRXActivator
  ```

  Il **`CRXActivator`** La classe contiene un metodo per creare pacchetti CRX e replicarli nell’istanza Publish.


## Creare e attivare pacchetti

Il `activate` Il metodo crea un pacchetto CRX nell’istanza di authoring e lo replica nell’istanza di pubblicazione, se necessario. Si presume che i parametri di replica AEM siano già stati impostati nell’istanza di authoring. Questo metodo crea il pacchetto CRX in base a un elenco di regole fornite come parametri di input in una stringa JSON.
>[!NOTE]
>
> Gli errori riscontrati durante il processo di creazione o attivazione vengono scritti nel `outputstream`.

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

**Parametri**: |Nome|Tipo|Descrizione| ----|----|-----------| |`json`Stringa|Stringa JSON che determina il pacchetto CRX da generare. Utilizza il seguente formato per creare la stringa JSON: <br>- `activate`: è di tipo booleano \(`true`/`false`\). Determina se il pacchetto CRX creato nell’istanza di authoring viene replicato nell’istanza di pubblicazione. <br> - `rules`: è di tipo array JSON. Un array di regole JSON che vengono elaborate in sequenza per generare il pacchetto CRX. <br> - `rootPath`: è di tipo String. Percorso di base su cui vengono eseguite le query nodo/proprietà. Se non sono presenti query nodo/proprietà, il percorso radice e tutti i nodi presenti nel percorso radice vengono inclusi nel pacchetto CRX. <br> - `nodeQueries`: è di tipo Regex Array. Array di espressioni regolari utilizzate per includere file specifici nel percorso principale. <br> - `propertyQueries`: è di tipo array JSON. Array di oggetti JSON con ogni oggetto JSON costituito da una query XPath da eseguire sul percorso principale e dal nome di una proprietà presente in ogni nodo JCR dopo l’esecuzione della query. Il valore della proprietà in ciascun nodo JCR deve essere un percorso o un array di percorsi. I percorsi presenti in questa proprietà vengono aggiunti al pacchetto CRX.| |`outputstream`|java.io.OutputStream|Viene utilizzato per scrivere il risultato di varie fasi, come l’esecuzione di query, l’inclusione di file, la creazione di pacchetti CRX o l’attivazione. Eventuali errori riscontrati durante il processo di creazione o attivazione vengono scritti nel `outputstream`. Questa opzione è utile per il debug.| |`session`|Stringa|Sessione JCR valida con autorizzazione di attivazione.|

**Eccezione**: proiezioni ``java.io.IOException``.

**Esempio**: l’esempio seguente mostra come creare una query JSON:

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
- I percorsi presenti nel `fileReference` proprietà dei nodi in /content/output/sites/hierarchy\_ditamap sono inclusi nel pacchetto.
