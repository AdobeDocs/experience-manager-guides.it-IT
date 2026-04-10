---
title: Configurazione aggiuntiva per l’aggiornamento di Cloud Service
description: Scopri la configurazione aggiuntiva per l’aggiornamento di Cloud Service
exl-id: 3d60d06b-ce50-4948-b50d-bd373051d055
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Configurazione aggiuntiva per l’aggiornamento di AEM Guides as Cloud Service

>[!INFO]
>
>Questo articolo si applica se sono state configurate le impostazioni del profilo di cartella personalizzato (`ui_config.json`). Dopo ogni aggiornamento, rivedi e modifica le impostazioni in base alle esigenze per garantire la compatibilità con le modifiche più recenti.

A seconda della versione da cui stai effettuando l’aggiornamento, potrebbero essere necessari ulteriori passaggi di configurazione per integrare le modifiche introdotte nelle versioni più recenti di Cloud Service.

Alcune configurazioni sono valide solo per versioni specifiche. Fai riferimento alle sezioni di configurazione riportate di seguito e applica le configurazioni richieste applicabili alla configurazione.

## Passaggi per applicare filtri di ricerca ai file DITAVAL per tutti i predefiniti di output

Per garantire il corretto funzionamento dei filtri, aggiorna ui_config.json. Modifica le proprietà elencate in **browseFilters** > **File non DITA** > **File Ditaval** come illustrato di seguito:

```
{
  "title": "Ditaval Files",
  "property": "LOWER_NAME",
  "operation": "like",
  "value": ".ditaval"
}
```

## Passaggi per eseguire la migrazione della struttura B per i frammenti di contenuto

Se non vengono visualizzati riferimenti per i frammenti di contenuto, puoi scegliere di eseguire il processo di migrazione:

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

## Passaggi per gestire il conflitto `'fmdita rewriter'`

Experience Manager Guides dispone di un modulo [**sling rewriter personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50. Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante l&#39;aggiornamento, poiché il valore `'order'` viene modificato da 1000 a 50, è necessario unire l&#39;eventuale rewriter personalizzato esistente con `fmdita-rewriter`.

## Configurazioni applicabili alle versioni precedenti a giugno 2023

Le seguenti configurazioni sono necessarie solo se utilizzi una versione di Experience Manager Guides as a Cloud Service rilasciata prima di giugno 2023. Espandi le sezioni pertinenti di seguito per applicare le impostazioni necessarie e garantire la compatibilità con gli aggiornamenti necessari.

+++Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti
Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`. (Facoltativo: è possibile passare percorsi specifici delle mappe per indicizzarle; per impostazione predefinita tutte le mappe sono indicizzate|| Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

1. L’API restituisce un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (ad esempio: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la precedente richiesta GET risponde con successo e indica se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

+++

+++Passaggi per pubblicare ed elaborare il contenuto esistente per utilizzare il rapporto sui collegamenti interrotti 
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

+++

+++Passaggi per abilitare l’attivazione di uno script tramite un servlet
Dopo aver completato l’installazione, puoi scegliere di avviare il processo di traduzione:

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

+++
