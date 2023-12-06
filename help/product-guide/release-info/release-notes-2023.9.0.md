---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione di settembre 2023
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione di settembre 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: 795b86a0-e763-404a-a4bb-35d3d2a42672
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 0%

---

# Versione di settembre 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di settembre 2023 delle Guide di Adobe Experience Manager (in seguito denominate *Guide AEM as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione di settembre 2023 delle guide AEM as a Cloud Service](whats-new-2023.9.0.md).

## Aggiornamento alla versione di settembre 2023

Aggiorna l’attuale configurazione as a Cloud Service delle Guide AEM eseguendo i seguenti passaggi:

1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
2. Aggiorna `<dox.version>` proprietà in `/dox/dox.installer/pom.xml` file del codice Git dei tuoi Cloud Service su 2023.9.0.359.
3. Apporta le modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione di settembre 2023 delle guide AEM as a Cloud Service.

## Passaggi per abilitare l’attivazione di uno script tramite un servlet

(Solo se utilizzi una versione precedente al rilascio di Guide AEM as a Cloud Service di giugno 2023)

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

Nella risposta precedente JSON, la chiave `lockNodePath` contiene il percorso del nodo creato nell’archivio che punta al processo inviato. Verrà eliminato automaticamente una volta completato il processo; fino ad allora, puoi fare riferimento a questo nodo per lo stato corrente del processo.

Attendere il completamento del processo prima di procedere ai passaggi successivi.

>[!NOTE]
>
> Verifica se il nodo è ancora presente e lo stato del processo.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Passaggi per pubblicare ed elaborare il contenuto esistente per utilizzare il rapporto sui collegamenti interrotti

(Solo se utilizzi una versione precedente al rilascio di Guide AEM as a Cloud Service di giugno 2023)

Effettua le seguenti operazioni per la post-elaborazione del contenuto esistente e l’utilizzo del nuovo rapporto sui collegamenti interrotti:

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file dita, aggiornare `queryLimitReads` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` su un valore più grande (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuiscilo.

   - Utilizzare le istruzioni fornite in *Sostituzioni configurazione* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service, per creare il file di configurazione.
   - Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare l’opzione queryLimitReads:

     | PID | Chiave proprietà | Valore proprietà |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valore: 200000 Valore predefinito: 100000 |

1. Eseguire una richiesta POST al server (con l’autenticazione corretta) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API restituirà un jobId. Per verificare lo stato del processo, puoi inviare una richiesta di GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
Ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la richiesta di GET precedente risponderà con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristina il valore predefinito o esistente precedente di `queryLimitReads` se è stato modificato nel passaggio 1.

## Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti:

(Solo se utilizzi una versione precedente al rilascio di Guide AEM as a Cloud Service di giugno 2023)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Esegui una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate \|\| Ad esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

1. L’API restituirà un jobId. Per verificare lo stato del processo, puoi inviare una richiesta di GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Una volta completato il processo, la richiesta di GET precedente risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di settembre 2023 delle guide AEM as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.09.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.09.0 | 3.1-uuid 17 | 3.1-uuid 17 | 2,3 | 2,3 |
|  |  |  |  |


### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti dei componenti delle guide AEM per il Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Il file dell&#39;argomento non viene sbloccato nell&#39;editor Web, anche se sono selezionate le opzioni Sblocca il file e Non salvare. (12558)
- Impossibile estrarre un file nell&#39;editor Web, nonostante sia stata selezionata l&#39;opzione NO per ignorare le modifiche prima dell&#39;archiviazione. (12557)
- Le descrizioni comandi per le icone Blocca e sblocca file nella barra degli strumenti principale dell&#39;editor Web non sono coerenti con le icone visualizzate nella vista Archivio.(12555)
- L&#39;opzione Annulla estrazione e sblocca viene visualizzata per un file nell&#39;editor Web non ancora estratto in visualizzazione mappa. (12556)
- Impossibile selezionare le risorse PDF nei collegamenti &quot;topicref&quot; esistenti. (12477).
- Nella Vista archivio, gli argomenti o le immagini non possono essere trascinati dopo aver utilizzato la funzionalità Ricerca/Filtro. (12396)
- I risultati della ricerca vengono disattivati nel pannello Trova e sostituisci dopo l’apertura di un file cercato. (12142)
- Il tasto numerico &quot;8&quot; sulla tastiera laterale non funziona nell’editor delle guide AEM. (12106)

- Il prefisso viene duplicato nella modalità di anteprima dell’editor web. (13133)
- `Choicetable` le righe non vengono visualizzate o non possono essere selezionate. (12616)
- L’editor web genera errori di convalida in scenari specifici durante la creazione di un argomento utilizzando uno schema personalizzato. (12576)
- I riferimenti al modello di argomento ditaval non creano una copia nella cartella dei contenuti durante la creazione di una mappa dal modello di mappa. (12150)
- La casella di ricerca nelle mappe DITA non dispone di un pulsante di chiusura. (11867)
- Quando si salvano file lunghi nell&#39;editor Web, `DirtyChecker` genera un&#39;eccezione con una traccia lunga dello stack e riempie i file di registro. (11860)
- La creazione di argomenti DITA richiede l&#39;autorizzazione Elimina sul nodo di cartella corrispondente, anche se la mappa può essere creata con l&#39;autorizzazione di scrittura. (11706)
- L’editor web mostra un titolo errato quando è presente una barra. (10949)


### Gestione

- Il campo &quot;title&quot; nelle proprietà dei metadati della mappa DITA viene sovrascritto da `<title>` per la mappa. (10702)
- Il riferimento al contenuto è interrotto per copiare e incollare file DITA quando l&#39;ID argomento non corrisponde a GUID. (12614)
- Nelle baseline dinamiche, l&#39;elenco delle etichette non viene estratto dai riferimenti diretti della copia di lavoro di una mappa DITA. (11917)

### Pubblicazione

- La pubblicazione non riesce quando si rinomina un predefinito di PDF nativo. (12564)
- La duplicazione di un modello di PDF nativo viene duplicata nel percorso predefinito del modello invece che nel percorso personalizzato fornito. (12563)

- Native PDF | L’inclusione di più xrefs estende il testo oltre la larghezza della colonna. (13004)
- Native PDF | Quando l’argomento e il titolo hanno lo stesso ID, si verifica un errore nella generazione dell’output PDF. (12644)
- Native PDF | Quando si aggiunge una classe di output a un elemento padre `<topicref>` in una mappa DITA e applicando uno stile personalizzato alla classe di output, lo stile viene applicato agli elementi all&#39;interno del corpo dell&#39;argomento, inclusi i titoli di sezione.(12166)
- La pubblicazione incrementale non funziona se una mappa DITA contiene più ditavalref. (12117)
- Sito AEM | Quando si crea una mappa con keydef che punta a un argomento come variabile e si aggiunge processing-role=resource-only, vengono create alcune pagine impreviste. (12099)
- Se vengono utilizzate risorse del DAM dell’AEM in un output diverso dal sito AEM, i metadati &quot;jcr:createdBy&quot; non riflettono il nome dell’editore o dell’utente che ha modificato per ultimo la mappa o l’argomento DITA. (12090)
- AEM Sites La mappa DITA con intestazione di argomento nel titolo della navigazione (con caratteri non supportati) causa la presenza di URL di pagina non validi. (11978)
- Native PDF | Si verificano problemi a sostegno di topichead / topicmeta / navtitle in Frontmatter and Backmatter. (11969)
- Native PDF | La generazione di PDF per documenti di grandi dimensioni richiede molto tempo. (11955)
- Native PDF | Se si rinomina un predefinito, viene generata un’eccezione NullPointerException durante la generazione di un output PDF. (11889)
- Il `<conref>` il contenuto non viene visualizzato nell’output di PDF. (11131)
- Viene aggiunto uno spazio all’interno del `<div>` elementi per l’alternanza tra la vista Author e Source nell’editor di layout di pagina. (10750)
- Il contenuto replicato in AEM Cloud Manager non è visibile nell’istanza Publish. (9564)

### Traduzione

- Il processo di esportazione di una baseline rinominata per una traduzione non riesce. (12993)
- Il titolo del file tradotto viene visualizzato al posto del titolo del file sorgente. (11630)
