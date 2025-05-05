---
title: Architettura dell’integrazione delle origini dati esterne in AEM Guides
description: Scopri l’architettura dell’integrazione delle origini dati esterne in AEM Guides.
source-git-commit: b0cf652023770eda24ea27ff105ed6dc2cdd1f08
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# Integrazione di origini dati esterne

I dati provenienti da sistemi esterni possono essere facilmente integrati nell’istanza Experience Manager Guides. La connessione a origini dati esterne può migliorare in modo significativo la funzionalità e l&#39;usabilità del sistema di gestione dei contenuti.


Puoi collegare e recuperare dati in modo efficiente da origini esterne utilizzando l’integrazione dei dati. Con questa funzione, non è necessario dipendere dal team IT per ottenere i dati e poi copiarli e incollarli manualmente o aggiornare costantemente le modifiche nel sistema esterno.

Questa funzione garantisce la sincronizzazione con la sorgente originale e consente aggiornamenti armoniosi della documentazione senza ricorrere a operazioni manuali di copia e incolla. Consente inoltre di mantenere la coerenza dei dati tra Experience Manager Guides e l’origine dati esterna.

Inoltre, dopo aver recuperato il contenuto da origini dati esterne, puoi crearlo in formato DITA e riutilizzare il contenuto integrato.


## Framework di integrazione delle origini dati

Il framework di integrazione di un’origine dati include principalmente due componenti principali: le origini dati esterne e la loro integrazione nell’istanza Experience Manager Guides.

### Origini dati esterne

Alcune delle origini dati che è possibile connettere da Experience Manager Guides sono le seguenti:

- Database relazionali (RDBMS)
   - PostgreSQL, MySQL, Microsoft SQL Server, MariaDB e SQLite
- Database non relazionali
   - MongoDB, Apache Cassandra, Apache CouchDB e Redis
- Product Information Management (PIM) / Product Lifecycle Management (PLM)
   - Pimcore, Salsify, Akeneo e Informatica
- Sistemi di gestione dei prodotti
   - Bacheche DevOps di JIRA e Microsoft Azure (ADO)
- Sistemi OLAP (Online Analytical Processing) e Analytics

### Integrazione in Experience Manager Guides



Utilizzando un connettore autenticato, i dati vengono trasferiti da un sistema esterno e generati all’interno di Experience Manager Guides.
![Architettura](assets/konnect-architecture.png)


### Integrazione in Experience Manager Guides

Per integrare il contenuto in Experience Manager Guides, effettua le seguenti operazioni:

1. **Configurare il connettore dell&#39;origine dati**
   - Il connettore dell’origine dati funge da interfaccia per stabilire la connettività con le origini dati esterne. È necessario configurare il connettore per stabilire la connessione e includere i metodi di autenticazione, ad esempio `Basic Auth` o `API key Auth`. Tutti i dettagli di configurazione, comprese le informazioni crittografate, vengono archiviati in modo sicuro in Adobe Experience Manager.
   - Il livello del connettore è progettato per essere estensibile, consentendo di creare implementazioni per la connessione a vari sistemi che non sono forniti come preconfigurati da Experience Manager Guides.

     ![Livello connettore](assets/data-source-connector-layer.jpg)
   >[!NOTE]
   >
   > Accedi al modulo di definizione Konnect e implementa l’interfaccia del connettore per creare un connettore personalizzato. Ulteriori informazioni su come [configurare i connettori di origini dati personalizzati](./conf-custom-data-source-connector.md).

1. **Personalizzare i modelli Velocity**

   - Experience Manager Guides supporta Velocity (https://velocity.apache.org/), un motore di creazione di modelli altamente affidabile per trasformare i dati dai file JSON in contenuti DITA. Velocity offre la flessibilità di navigare tra le strutture JSON con qualsiasi livello di nidificazione.
   - L’esempio seguente illustra come integrare modelli Velocity e dati provenienti da Jira per generare facilmente tabelle o elenchi ordinati.
      - Risposta Jira

        ```
        {
            "expand": "schema,names",
            "total": 5,
            "hostname": "https://jira.corp.adobe.com",
            "maxResults": "200",
            "issues": [
                {
                    "key": "DXML-12756",
                    "fields": {
                        "description": "Implement the snippet generator in External Data Source integration",
                        "summary": "Implement the snippet generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12755",
                    "fields": {
                        "description": "Implement the topic generator in External Data Source integration",
                        "summary": "Implement the topic generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12745",
                    "fields": {
                        "description": "Implement the ability to register a new connector",
                        "summary": "Implement the ability to register a new connector"
                    }
                }
            ],
            "startAt": 0
        }
        ```

      - Modelli

        ![Motore di modelli](assets/data-source-TemplatingEngine.png){width="800" align="left"}
      - Dati generati dalla stessa origine dati ma da modelli diversi

        ![Dati generati](assets/data-source-templates-topics.png){width="800" align="left"}

1. **Genera contenuto utilizzando i modelli**
   - Puoi generare il contenuto dai modelli creati.
   - Puoi generare vari tipi di contenuto:
      - Snippet: contenuto utilizzabile una tantum. Puoi generare i dati dal connettore nel modello definito e quindi incorporarli nel tag desiderato.
      - Argomento DITA: consente di generare vari argomenti da utilizzare così come sono nel contenuto o possono essere riutilizzati come *Componente riutilizzabile*.
      - Argomento DITA + mappa: è inoltre possibile generare una mappa completa anche con l&#39;argomento e quindi utilizzare i dati per la pubblicazione diretta o utilizzarli come *Componente riutilizzabile* in altri dati.


1. **Publish del contenuto integrato**
   - La pubblicazione è la funzione OOTB di Experience Manager Guides e puoi pubblicare direttamente tutti i dati generati dal sistema esterno come output PDF o del sito AEM.

>[!MORELIKETHIS]
>
> I documenti seguenti forniscono ulteriori dettagli sulla configurazione dei connettori e sul loro utilizzo nell’istanza.
> - [Configurare un connettore origine dati](../../../install-guide/conf-data-source-connector-tools.md)
> - [Genera contenuto utilizzando snippet o argomenti](../../../user-guide/web-editor-content-snippet.md)