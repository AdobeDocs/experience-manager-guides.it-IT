---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione 2024.2.0
description: Scopri la matrice di compatibilità e come effettuare l’aggiornamento alla versione 2024.2.0 delle guide as a Cloud Service di Adobe Experience Manager.
source-git-commit: 9022b8fbae9ff9eba962ca75e25c1f1137b008f8
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 0%

---

# Istruzioni per l’aggiornamento alla versione 2024.2.0

Questo articolo descrive le istruzioni per l’aggiornamento e la matrice di compatibilità per la versione 2024.2.0 delle guide as a Cloud Service di Adobe Experience Manager.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, vedi [Novità della versione 2024.2.0](whats-new-2024-2-0.md).

Per l’elenco dei problemi risolti in questa versione, visualizza [Sono stati risolti i problemi nella versione 2024.2.0 di](fixed-issues-2024-2-0.md).


## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione 2024.2.0 di Experience Manager Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Rilascio di Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.2.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Rilascio di Experience Manager Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2024.2.0 | 3,5-uuid 1 | 3,5-uuid 1 | 2,3 | 2,3 |
|  |  |  |  |


### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti dei componenti Experience Manager Guides per il Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Aggiornamento alla versione 2024.2.0

Experience Manager Guides viene aggiornato automaticamente dopo l’aggiornamento della versione corrente (più recente) di Experience Manager as a Cloud Service.


Se non lo hai già fatto in precedenza per la versione esistente, effettua le seguenti operazioni, ad Experience Manager Guide as a Cloud Service:

### Passaggi per abilitare l’attivazione di uno script tramite un servlet

(Solo se ti trovi in una versione precedente a quella di giugno 2023 di Experience Manager Guides as a Cloud Service)

Dopo aver completato l’installazione, puoi scegliere di premere il trigger per avviare il processo di traduzione:

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Risposta:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

Nella risposta precedente JSON, la chiave `lockNodePath` contiene il percorso del nodo creato nell’archivio che punta al processo inviato. Verrà eliminato automaticamente una volta completato il processo, quindi puoi fare riferimento a questo nodo per lo stato del processo.

Attendere il completamento del processo prima di procedere ai passaggi successivi.

>[!NOTE]
>
> Verifica se il nodo è ancora presente e lo stato del processo.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Passaggi per pubblicare ed elaborare il contenuto esistente per utilizzare il rapporto sui collegamenti interrotti

(Solo se ti trovi in una versione precedente a quella di giugno 2023 di Experience Manager Guides as a Cloud Service)

Effettua le seguenti operazioni per la post-elaborazione del contenuto esistente e l’utilizzo del nuovo rapporto sui collegamenti interrotti:

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file DITA, aggiornare `queryLimitReads` e `queryLimitInMemory` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` su un valore più grande (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuiscilo.

   - Utilizzare le istruzioni fornite nella *Sostituzioni configurazione* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service, per creare il file di configurazione.
   - Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare `queryLimitReads` e `queryLimitInMemory` opzione:

     | PID | Chiave proprietà | Valore proprietà |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valore: 200000 Valore predefinito: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valore: 200000 Valore predefinito: 100000 |

1. Eseguire una richiesta POST al server (con l’autenticazione corretta) - `http://<server>//bin/guides/reports/upgrade`.

1. L’API restituisce un jobId. Per verificare lo stato del processo, puoi inviare una richiesta di GET con ID processo allo stesso endpoint: `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
Ad esempio: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la richiesta di GET precedente risponde con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristina il valore predefinito o esistente precedente di `queryLimitReads` se è stato modificato nel passaggio 1.

### Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti:

(Solo se ti trovi in una versione precedente a quella di giugno 2023 di Experience Manager Guides as a Cloud Service)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Eseguire una richiesta POST al server (con l’autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`. (Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate|| Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. L’API restituirà un jobId. Per verificare lo stato del processo, puoi inviare una richiesta di GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`Ad esempio: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la richiesta di GET precedente risponde con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristina il valore predefinito o esistente precedente di queryLimitReads se lo hai modificato nel passaggio 1.

### Passaggi per gestire `'fmdita rewriter'` conflitto

Experience Manager Guide ha un [**rewriter sling personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) modulo per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter di sling personalizzato, utilizza un `'order'` valore maggiore di 50, utilizzato dal rewriter sling di Experience Manager Guides `'order'` 50  Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, vedi [Pipeline di riscrittura di output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante questo aggiornamento, dal momento che `'order'` viene modificato da 1000 a 50, è necessario unire l’eventuale rewriter personalizzato esistente con `'fmdita-rewriter'`.



