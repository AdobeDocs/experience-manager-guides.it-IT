---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione di novembre 2023
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione di novembre 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: 80839890-075f-4187-a167-444c73215496
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1673'
ht-degree: 1%

---

# Versione di novembre 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l&#39;aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di novembre 2023 di Adobe Experience Manager Guides as a Cloud Service (in seguito denominato *Experience Manager Guides as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizzare [Novità della versione di novembre 2023 di Experience Manager Guides as a Cloud Service](whats-new-2023-11-0.md).

## Aggiornamento alla versione di novembre 2023

Aggiorna la configurazione corrente di Experience Manager Guides as a Cloud Service eseguendo i seguenti passaggi:

1. Consulta il codice Git dei servizi cloud e passa al ramo configurato nella pipeline dei servizi cloud corrispondente all’ambiente da aggiornare.
2. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei servizi cloud a 2023.11.0.406.
3. Apporta le modifiche ed esegui la pipeline dei servizi cloud per l’aggiornamento alla versione di novembre 2023 di Experience Manager Guides as a Cloud Service.

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

Nella risposta precedente JSON, la chiave `lockNodePath` contiene il percorso del nodo creato nell&#39;archivio che punta al processo inviato. Verrà eliminato automaticamente una volta completato il processo, quindi puoi fare riferimento a questo nodo per lo stato del processo.

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

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file DITA, aggiornare `queryLimitReads` e `queryLimitInMemory` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valore maggiore (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuire.

   - Per creare il file di configurazione, segui le istruzioni fornite nella sezione *Sostituzioni configurazione* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.
   - Nel file di configurazione, fornire i seguenti dettagli (proprietà) per configurare l&#39;opzione `queryLimitReads` e `queryLimitInMemory`:

     | PID | Chiave proprietà | Valore proprietà |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valore: 200000 Valore predefinito: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Valore: 200000 Valore predefinito: 100000 |

1. Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API restituisce un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la precedente richiesta GET risponde con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristinare il valore predefinito o esistente precedente di `queryLimitReads` se è stato modificato nel passaggio 1.

## Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti:

(Solo se utilizzi una versione precedente alla versione di giugno 2023 di Experience Manager Guides as a Cloud Service)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`. (Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate || Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

1. L’API restituisce un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`)


1. Una volta completato il processo, la precedente richiesta GET risponde con successo e indica se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Passaggi per gestire il conflitto `'fmdita rewriter'`

Experience Manager Guides dispone di un modulo [**sling rewriter personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50.  Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante l&#39;aggiornamento, poiché il valore `'order'` viene modificato da 1000 a 50, è necessario unire l&#39;eventuale rewriter personalizzato esistente con `'fmdita-rewriter'`.


## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di novembre 2023 di Experience Manager Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Rilascio di Experience Manager Guides Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.11.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Versione di Experience Manager Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.11.0 | 3,2-uuid 5 | 3,2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |  |


### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti per componenti Experience Manager Guides per Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:



### Authoring

- Lo spazio dopo l&#39;elemento conref `<ph>` scompare quando si salva l&#39;argomento. (13642)
- Si verifica un errore di applicazione quando si tenta di salvare file DITA prima del completamento della post-elaborazione. (13571)
- Se il titolo di un argomento contiene una barra `/`, nella scheda dell&#39;editor verranno visualizzate solo le lettere successive. (13455)
- L’anteprima dell’immagine non scompare dopo averla visualizzata nell’editor. (13454)
- La finestra a comparsa Inserisci parola chiave non viene visualizzata quando si utilizzano i tasti definiti dalla mappa principale in altri argomenti. (12950)
- Le icone di chiusura non sono visibili quando nel pannello Cronologia versioni vengono visualizzate in anteprima immagini molto alte. (12867)
- Impossibile modificare il fuso orario della colonna **Versione creata il** per le linee di base. (12711)
- Il pannello **Cronologia versioni** nell&#39;interfaccia utente di Assets mostra una marca temporale non corretta per il campo **Corrente**. (12624)
- La creazione di un file DITA da un modello con un nome file che inizia con caratteri numerici genera un errore relativo allo spazio dei nomi. (12188)
- Nell&#39;editor Web viene visualizzata la finestra **Riferimenti chiave** quando si inserisce il tag `varname`. (10940)
- I file ZIP non vengono riconosciuti nell&#39;editor Web e non è possibile trascinarli. (12709)
- Il contenuto con alcuni attributi applicati non viene evidenziato in modalità Creazione o Anteprima. (11063)
- Quando si chiude un argomento dopo averlo modificato, si viene reindirizzati alla home page di AEM invece di tornare alla vista cartelle. (13306)
- Si verifica un ritardo nella post-elaborazione dei file copiati e incollati nei servizi cloud. (12457)
- L&#39;impostazione della rootmap viene mantenuta nell&#39;editor Web anche se l&#39;utente non l&#39;ha impostata in modo esplicito nelle preferenze utente. (11551)


### Pubblicazione

- La funzionalità Pubblica come frammento di contenuto non funziona per i file elencati nei risultati di ricerca. (14090)
- Nella pubblicazione nativa in PDF, la selezione del colore di sfondo nel layout del modello richiede il ricaricamento della pagina quando si torna a `None`. (13621)
- Si è verificato un problema durante il commit nell’archivio dati per una mappa DITA di grandi dimensioni con collegamenti peer per l’ambito nella pubblicazione di siti AEM. (13530)
- Nella pubblicazione nativa in PDF, l’accessibilità è compromessa in quanto le immagini nell’intestazione e nel piè di pagina non visualizzano testo alternativo. (12829)
- La duplicazione del layout di pagina in PDF nativo non funziona con nessuna estensione aggiunta automaticamente. (12534)
- Quando si genera l’output di PDF con la pubblicazione PDF nativa, il nome del file viene troncato dopo un punto. (13620)
- L&#39;icona e la descrizione comandi non sono corrette per l&#39;opzione **Modifica contenuto** nella barra degli strumenti Layout di pagina dei modelli utilizzati nella pubblicazione nativa di PDF. (13492)
- I metadati personalizzati non sono disponibili nell’output finale. (12116)
- Il rewriter fmdita è in conflitto con la configurazione del rewriter dell’utente e porta alla visualizzazione di URL lunghi invece dei collegamenti. (12076)
- Nel predefinito per sito AEM, l&#39;opzione per **Generare un PDF separato per ogni argomento** non funziona. (11555)
- La pubblicazione nativa su PDF non supporta la conversione dello spazio colore CMYK. (10754)
- Le chiamate della linea di base dinamica utilizzano il nome invece del titolo, il che si traduce in un errore di esportazione dell’API mappa DITA. (14268)

### Gestione

- Il riferimento al contenuto viene interrotto quando si copiano e incollano i file DITA con collegamenti di riferimento automatico senza GUID. (13540)
- Nell&#39;editor Web, la baseline mostra il titolo della versione precedente anziché della versione selezionata del file DITA. (13444)
- La scheda **Rapporti** nell&#39;interfaccia utente dell&#39;editor Web non visualizza l&#39;elenco degli argomenti per le mappe DITA precedenti create prima dell&#39;aggiornamento di luglio 2023 di Experience Manager Guides as a Cloud Service. (11852)
- Non vengono creati predefiniti di condizione per mappe DITA di grandi dimensioni. (10936)
- Nell’elenco Collegamenti interrotti dei report viene visualizzato un collegamento di riferimento autonomo. (13539)

### Rivedere

- I pannelli di revisione affiancata delle versioni precedenti e correnti nell’editor web non sono corretti nella versione di ottobre 2023 di Experience Manager Guides as a Cloud Service. (14156)
- La personalizzazione del modello e-mail per il flusso di lavoro **Revisione** non funziona con la sovrapposizione dei nodi. (13954)
- Il pulsante **Chiudi** nella pagina Revisione di Experience Manager Guides porta gli utenti alla home page di AEM. (13535)
- I caratteri interrotti vengono visualizzati durante la creazione dei frammenti in lingua coreana. (13489)
- Gli allegati coreani nella schermata Experience Manager Guides Review non sono selezionabili. (13436)
- Il titolo della mappa viene tagliato nella schermata di revisione e collaborazione, senza opzione per visualizzare il titolo completo. (13012)

### Traduzione

- L&#39;approvazione automatica a volte non funziona e si verificano eccezioni se in **Stato traduzione** è impostato un valore non corretto. (13607)
- La linea di base esportata dal dashboard di traduzione non riesce e non si apre nella lingua di destinazione. (12993)

## Problema noto

Adobe ha identificato il seguente problema noto per la versione di novembre 2023.

- La rigenerazione selettiva degli argomenti per l’output del sito AEM non riesce.
