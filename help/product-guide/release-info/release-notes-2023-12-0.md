---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione di dicembre 2023
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione di dicembre 2023 di Adobe Experience Manager Guides as a Cloud Service.
feature: Release Notes
role: Leader
exl-id: 63efe42a-b817-49df-8f76-df8d7acf9194
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 1%

---

# Versione di dicembre 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l&#39;aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di dicembre 2023 di Adobe Experience Manager Guides as a Cloud Service (in seguito denominato *Experience Manager Guides as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizzare [Novità della versione di dicembre 2023 di Experience Manager Guides as a Cloud Service](whats-new-2023-12-0.md).

## Aggiornamento alla versione di dicembre 2023

Aggiorna la configurazione corrente di Experience Manager Guides as a Cloud Service eseguendo i seguenti passaggi:

1. Consulta il codice Git dei servizi cloud e passa al ramo configurato nella pipeline dei servizi cloud corrispondente all’ambiente da aggiornare.
2. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei servizi cloud a 2023.12.0.16.
3. Apporta le modifiche ed esegui la pipeline dei servizi cloud per l’aggiornamento alla versione di dicembre 2023 di Experience Manager Guides as a Cloud Service.

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

1. Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server>//bin/guides/reports/upgrade`.

1. L’API restituisce un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(ad esempio: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la precedente richiesta GET risponde con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristinare il valore predefinito o esistente precedente di `queryLimitReads` se è stato modificato nel passaggio 1.

## Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti:

(Solo se utilizzi una versione precedente alla versione di giugno 2023 di Experience Manager Guides as a Cloud Service)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`. (Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate|| Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

1. L’API restituisce un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)


1. Una volta completato il processo, la precedente richiesta GET risponde con successo e indica se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Passaggi per gestire il conflitto `'fmdita rewriter'`

Experience Manager Guides dispone di un modulo [**sling rewriter personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50.  Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante l&#39;aggiornamento, poiché il valore `'order'` viene modificato da 1000 a 50, è necessario unire l&#39;eventuale rewriter personalizzato esistente con `'fmdita-rewriter'`.


## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di dicembre 2023 di Experience Manager Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di Experience Manager Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.12.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Versione di Experience Manager Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.12.0 | 3.3-uuid.5 | 3.3-uuid.5 | 2,3 | 2,3 |
|  |  |  |  |  |


### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti per componenti Experience Manager Guides per Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:



### Authoring

- Il **Titolo** nella scheda Editor Web viene troncato dopo un carattere punto(.). (14372)
- I messaggi di errore per i nomi di mappe duplicati nell’interfaccia utente di Assets non vengono aggiornati. (14320)
- Si verifica un errore nella logica di creazione della versione durante il trascinamento della selezione delle risorse. (14291)
- Il contenuto riutilizzabile ignora gli ID elemento. (14213)
- Manca il controllo impostazione per nascondere il pannello **Variabili di lingua** nella scheda **Output**. (14194)
- L&#39;editor Web genera errori di applicazione quando si aggiunge un nuovo riferimento o argomento utilizzando uno schema specializzato nella visualizzazione Layout. (14094)
- Un collegamento di ancoraggio a un elemento `<dlentry>` o `<dt>` non riesce a visualizzare il testo del collegamento. (13543)
- Impossibile caricare la raccolta **Preferiti** nell&#39;editor Web. (13495)
- Le citazioni visualizzano collegamenti non cliccabili quando vengono create con un ID univoco con spazi. (13447)
- Nella visualizzazione **Layout** per una mappa dei libri, utilizzando **Sposta a destra** per rendere non valido un sottoelemento per un capitolo selezionato. (12567)
- La finestra Anteprima dell&#39;editor XML viene troncata nei browser Google Chrome e Microsoft Edge. (10755)
- Nell’editor web non è possibile racchiudere un elemento all’interno dei possibili elementi principali. (8791)

### Pubblicazione

- I componenti Fmdita hanno un percorso hardcoded di `delegator.jsp`, che impedisce la sovrapposizione dei componenti AEM Sites. (13993)
- La visualizzazione con tag del reattore PDF nell’output di pubblicazione nativo di PDF non funziona come previsto. (13622)
- La pubblicazione di siti AEM rileva un problema quando si esegue il commit nell’archivio dati per mappe di grandi dimensioni con collegamenti peer di ambito. (13531)
- Impossibile attivare un sito utilizzando il dashboard Pubblicazione in blocco di Experience Manager Guides. (13439)
- La localizzazione delle etichette degli elementi non funziona correttamente nell’output di AEM Sites. (12144)
- Opzione **ditaval** mancante nei predefiniti di output a livello di profilo della cartella creati tramite l&#39;interfaccia utente dell&#39;editor Web. (11903)

### Gestione

- Negli ambienti cloud AEM si verifica un’eccezione MongoWrite a causa di nodi di grandi dimensioni. (13509)

### Traduzione

- I pulsanti **Accetta/Rifiuta** non vengono visualizzati correttamente per la traduzione umana approvata automaticamente. (14318)
- I problemi di internazionalizzazione (i18n) si verificano durante la trasformazione di file DITA non inglesi in pagine AEM. (14286)
- I contenuti tradotti non possono essere sincronizzati da progetti di traduzione temporanei e la traduzione guidata dell&#39;editor XML DITA mostra erroneamente lo stato **In corso** per i processi approvati. (9938)

### Accessibilità

- Impossibile spostarsi nell’interfaccia utente dell’area di lavoro per l’authoring poiché lo stato attivo si blocca nell’editor argomenti. (13517)

## Problema noto

Adobe ha identificato il seguente problema noto per la versione di dicembre 2023:
- L’errore &quot;Getting Invalid DTD Error&quot; (Recupero dell’errore DTD non valido) si verifica in modo intermittente durante l’aggiornamento alla versione di dicembre 2023.
