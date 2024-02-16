---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione di febbraio 2024
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione di febbraio 2024 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 0%

---

# Versione di febbraio 2024 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di febbraio 2024 di Adobe Experience Manager Guides as a Cloud Service (in seguito denominata *Guide di Experience Manager as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, vedi [Novità della versione di febbraio 2024 di Experience Manager Guides as a Cloud Service](whats-new-2024-02-0.md).

## Aggiornamento alla versione di febbraio 2024

Aggiorna la configurazione as a Cloud Service delle guide di Experience Manager correnti eseguendo i seguenti passaggi:

1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
2. Aggiorna `<dox.version>` proprietà in `/dox/dox.installer/pom.xml` file del codice Git dei Cloud Service in 2024.02.0.15.
3. Apporta le modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione di febbraio 2024 di Experience Manager Guides as a Cloud Service.

## Passaggi per abilitare l’attivazione di uno script tramite un servlet

(Solo se utilizzi una versione precedente alla versione di giugno 2023 di Experience Manager Guides as a Cloud Service)

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

## Passaggi per pubblicare ed elaborare il contenuto esistente per utilizzare il rapporto sui collegamenti interrotti

(Solo se utilizzi una versione precedente alla versione di giugno 2023 di Experience Manager Guides as a Cloud Service)

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

## Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti:

(Solo se utilizzi una versione precedente alla versione di giugno 2023 di Experience Manager Guides as a Cloud Service)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Eseguire una richiesta POST al server (con l’autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`. (Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate|| Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. L’API restituirà un jobId. Per verificare lo stato del processo, puoi inviare una richiesta di GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`Ad esempio: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la richiesta di GET precedente risponde con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristina il valore predefinito o esistente precedente di queryLimitReads se lo hai modificato nel passaggio 1.

## Passaggi per gestire `'fmdita rewriter'` conflitto

Experience Manager Guide ha un [**rewriter sling personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) modulo per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter di sling personalizzato, utilizza un `'order'` valore maggiore di 50, utilizzato dal rewriter sling di Experience Manager Guides `'order'` 50  Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, vedi [Pipeline di riscrittura di output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante questo aggiornamento, dal momento che `'order'` viene modificato da 1000 a 50, è necessario unire l’eventuale rewriter personalizzato esistente con `'fmdita-rewriter'`.


## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di febbraio 2024 di Experience Manager Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Rilascio di Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.02.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Rilascio di Experience Manager Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2024.02.0 | 3.1-uuid.17 | 3.1-uuid.17 | 2,3 | 2,3 |
|  |  |  |  |


### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti dei componenti Experience Manager Guides per il Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Il controllo ortografico nell’editor non consente la selezione di suggerimenti. (15045)
- Il pulsante di navigazione globale non funziona e il dashboard non viene caricato. (14968)
- Nell’editor web, la funzione di download mappa non attiva una notifica pop-up quando è pronto per il download. (14626)
- Nell&#39;editor Web, la funzionalità di download mappa non consente di scaricare una mappa con linea di base. (14622)
- Errore DTD non valido nella versione 2310 as a Cloud Service da Experience Manager Guides. (14482)
- Trascinare un argomento del glossario dal repository in una mappa del glossario crea `topicref`. (10767)
- L&#39;editor Web viene disinstallato dopo la reinstallazione di Adobe Experience Manager Guides versione 4.3.1. (14519)
- Il programma di installazione della versione 4.3.1 rileva un conflitto di filtri che determina l’esclusione di `apps/cq/core/content/projects/properties`. (14517)
- La schermata di anteprima dei frammenti è bloccata. (14840)

### Pubblicazione

- Nella pubblicazione di PDF nativi, gli attributi personalizzati nei predefiniti di condizione non funzionano per la pubblicazione di PDF nativi. (14943)
- Impossibile aggiungere un modello personalizzato da **Uscite** nell&#39;editor. (14846)
- **Sito AEM** il predefinito non funziona a causa di un percorso del modello vuoto. (14804)
- La rigenerazione del sito AEM non riesce per le mappe DITA con argomenti che contengono equazioni MathML. (14790)
- Nella pubblicazione nativa di PDF, la generazione di PDF genera errori nell’ottenere dipendenze per `Node.js` pubblicazione. (14445)
- Il predefinito AEM non consente la selezione di un modello esterno al `/content` gerarchia nell&#39;editor Web. (14260)
- Nell’output di AEM Sites, lo stile o le interruzioni di riga venivano persi per `<lines>` elemento con sottoelementi .(12542)
- I metadati personalizzati non sono disponibili nell’output finale. (12116)
- Quando si esegue l’aggiornamento alla versione 4.3.1, si verificano alcune eccezioni nel nodo PDF nativo. (14492)


### Gestione

- **Filtro linea di base** I file non funzionano con Nome file nell&#39;editor Web. (13486)
- La disattivazione dell&#39;indicizzazione della mappa DITA padre per ottenere prestazioni migliori può influire sulle funzionalità di alcune funzionalità.(12213)
- Etichette da `labels.json` I file vengono visualizzati in ordine casuale nell&#39;editor Web. (10508)

### Rivedi

- Il menu di scelta rapida non funziona per **Accetta** o **Rifiuta** tenere traccia delle modifiche. (14607)
- Per chiudere gli argomenti DITA nella finestra Revisione, attivare o disattivare la versione 4.3.1 delle Guide di Adobe Experience Manager. (14537)
- La personalizzazione dei modelli e-mail per il flusso di lavoro di revisione non funziona con la sovrapposizione. (13954)

## Problema noto

L’Adobe ha identificato il seguente problema noto per la versione di febbraio 2024:

- La versione 1.0 non viene visualizzata nell&#39;interfaccia utente del file DITA duplicato.
