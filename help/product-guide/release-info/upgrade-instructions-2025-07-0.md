---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione 2025.07.0
description: Scopri la matrice di compatibilità e come effettuare l’aggiornamento alla versione 2025.07.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 391b8995-3938-4de6-b402-599a1c8df100
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 3%

---

# Istruzioni per l’aggiornamento alla versione 2025.07.0

Questo articolo descrive le istruzioni per l’aggiornamento e la matrice di compatibilità per la versione 2025.07.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2025.07.0](whats-new-2025-07-0.md).

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2025.07.0](fixed-issues-2025-07-0.md).

## Matrice di compatibilità

Questa sezione descrive la matrice di compatibilità per le applicazioni software supportate dalla versione 2025.07.0 di Experience Manager Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2025.07.0 | Non compatibile | 2022 o versione successiva |


### Connettore ossigeno

| Versione di Experience Manager Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2025.07.0 | 3,8-uuid 1 | 3,8-uuid 1 | 2,3 | 2,3 |


### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti per componenti Experience Manager Guides per Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |


### Nuova versione del modello del sito AEM

| Versione componenti | Versione sito |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |


## Aggiornamento alla versione 2025.07.0

Experience Manager Guides viene aggiornato automaticamente dopo l’aggiornamento della versione corrente (più recente) di Experience Manager as a Cloud Service.

>[!NOTE]
>
> Dopo aver iniziato a utilizzare la versione corrente (più recente), confronta tutte le configurazioni sostituite con quelle più recenti per ottenere le funzioni più recenti:
>- ui_config.json (potrebbe essere stato impostato nei profili cartella)


Se non lo hai già fatto in precedenza per la versione esistente, effettua le seguenti operazioni per Experience Manager Guides as a Cloud Service:

### Passaggi per abilitare l’attivazione di uno script tramite un servlet

(Solo per le versioni precedenti alla versione di giugno 2023 di Experience Manager Guides as a Cloud Service)

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

Nella risposta precedente JSON, la chiave `lockNodePath` contiene il percorso del nodo creato nell&#39;archivio che punta al processo inviato. Viene eliminato automaticamente una volta completato il processo, quindi puoi fare riferimento a questo nodo per lo stato del processo.

Attendere il completamento del processo prima di procedere ai passaggi successivi.

>[!NOTE]
>
> Verifica se il nodo è ancora presente e lo stato del processo.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Passaggi per pubblicare ed elaborare il contenuto esistente per utilizzare il rapporto sui collegamenti interrotti

(Solo per le versioni precedenti alla versione di giugno 2023 di Experience Manager Guides as a Cloud Service)

Effettua le seguenti operazioni per la post-elaborazione del contenuto esistente e l’utilizzo del nuovo rapporto sui collegamenti interrotti:

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file DITA, aggiornare `queryLimitReads` e `queryLimitInMemory` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valore maggiore (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuire.

   - Per creare il file di configurazione, segui le istruzioni fornite nella sezione *Sostituzioni configurazione* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.
   - Nel file di configurazione, fornire i seguenti dettagli (proprietà) per configurare l&#39;opzione `queryLimitReads` e `queryLimitInMemory`:

     | PID | Chiave proprietà | Valore proprietà |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valore: 200000 Valore predefinito: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valore: 200000 Valore predefinito: 100000 |

1. Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server>//bin/guides/reports/upgrade`.

1. L’API restituisce un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(ad esempio: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la precedente richiesta GET risponde con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristinare il valore predefinito o esistente precedente di `queryLimitReads` se è stato modificato nel passaggio 1.

### Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti:

(Solo per le versioni precedenti alla versione di giugno 2023 di Experience Manager Guides as a Cloud Service)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`. (Facoltativo: Puoi passare percorsi specifici delle mappe per indicizzarle; per impostazione predefinita tutte le mappe sono indicizzate|| Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

1. L’API restituisce un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (ad esempio: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la precedente richiesta GET risponde con successo e indica se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

### Passaggi per gestire il conflitto `'fmdita rewriter'`

Experience Manager Guides dispone di un modulo [**sling rewriter personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50. Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante l&#39;aggiornamento, poiché il valore `'order'` viene modificato da 1000 a 50, è necessario unire l&#39;eventuale rewriter personalizzato esistente con `fmdita-rewriter`.

### Passaggi per eseguire la migrazione della struttura B per i frammenti di contenuto

Se non vengono visualizzati i riferimenti per i frammenti di contenuto, puoi scegliere di premere il trigger per avviare il processo di migrazione:

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=cf-reference-store-btree-migration
```


Risposta:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886",
"status": "SCHEDULED"
}
```

Nella risposta precedente, JSON, la chiave `lockNodePath` contiene il percorso del nodo creato nell&#39;archivio, che punta al processo inviato. Verrà eliminato automaticamente al termine del processo. Puoi fare riferimento a questo nodo per lo stato del processo.

Attendere il completamento del processo prima di procedere ai passaggi successivi.

>[!NOTE]
>
>Verifica se il nodo è ancora presente e lo stato del processo.

GET:

```
http://<aem_domain>/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886.json
```
