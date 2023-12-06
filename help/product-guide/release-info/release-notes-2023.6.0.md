---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione di giugno 2023
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione di giugno 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: df17ee33-9f50-4223-ab9f-a57a31097d22
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 0%

---

# Versione di giugno 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di giugno 2023 delle Guide di Adobe Experience Manager (in seguito denominate *Guide AEM as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione di giugno 2023 delle Guide dell’AEM as a Cloud Service](whats-new-2023.6.0.md).

## Aggiornamento alla versione di giugno 2023

Aggiorna l’attuale configurazione as a Cloud Service delle Guide AEM eseguendo i seguenti passaggi:

1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
2. Aggiorna `<dox.version>` proprietà in `/dox/dox.installer/pom.xml` file del codice Git dei tuoi Cloud Service in 2023.6.297.
3. Apporta le modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione di giugno 2023 delle guide AEM as a Cloud Service.

## Passaggi per abilitare l’attivazione di uno script tramite un servlet

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

(Solo se utilizzi una versione precedente alla versione di settembre 2022 delle Guide AEM as a Cloud Service)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Esegui una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate \|\| Ad esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

1. L’API restituirà un jobId. Per verificare lo stato del processo, puoi inviare una richiesta di GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Una volta completato il processo, la richiesta di GET precedente risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di giugno 2023 di AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.06.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.06.0 | 2,9-uuid-2 | 2,9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |


## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Navtitle viene rimosso dal contenuto33 quando si passa dalla vista Layout a quella Author o Source. (12174)
- A volte si verificano errori di applicazione quando si fa clic su una mappa DITA. (11842)
- Editor web | Spazio unificatore aggiunto nell&#39;editor XML durante la modifica di un argomento. (11786)
- Interfaccia utente risorse | Nella vista a elenco, le colonne disponibili sovrapposte non sono unificabili. (11528)
- Keyref non è risolto nella vista mappa. (11490)
- Il menu superiore non viene visualizzato quando si passa da un editor XML all&#39;altro. (10868)
- `conref` nel tag ph | La finestra di dialogo Sfoglia visualizzata non è corretta. (9481)
- I collegamenti locali ad altri elementi non vengono risolti in Editor Web. (8790)
- La funzione Matches() non funziona nella funzione Schematron. (11224)


### Gestione

- Nella scheda Report dell&#39;interfaccia utente dell&#39;Editor Web non viene visualizzato l&#39;elenco degli argomenti delle vecchie mappe DITA create prima dell&#39;aggiornamento 4.2. (11708)

- La funzionalità del pulsante Carica file nell’interfaccia utente di Assets è stata interrotta nella versione 4.2. (11633)

### Pubblicazione

- La pubblicazione sul sito AEM non riesce quando si leggono file temporanei dal pod che potrebbero essere stati aggiornati o riavviati. (12113)
- Native PDF | La pubblicazione di contenuti con una classe di output con parentesi() comporta un blocco della pubblicazione. (11936)
- Output JSON | Mappa metadati con valore proprietà come `"value in spaces and double quotes"` genera un errore di pubblicazione. (11933)
- Editor web | Il percorso di output e il modello non possono essere selezionati nel predefinito AEM. (11530)
- Native PDF | Gli attributi personalizzati non vengono propagati al motore temporaneo HTML o PDF. (DXML-12005)
- Native PDF | Java OutOfMemoryError si verifica quando si pubblicano contenuti di grandi dimensioni. (11789)
- Output JSON | Il `fmUuid` proprietà nel nodo jcr:content di JSON diversa dall’&quot;id&quot; all’interno del JSON. (11564)
- Output JSON | Se sono presenti la mappa e l’argomento con lo stesso nome file, viene rimosso il codice JSON della mappa. (11524)
- Native PDF | Xref sta stampando il contenuto del titolo dell&#39;argomento href invece dell&#39;etichetta Xref. (11322)
- Native PDF | Impossibile salvare le impostazioni del modello PDF. (10751)
- Native PDF | Il testo si estende oltre la larghezza della colonna quando si includono più xref. (10876)
- Native PDF | `<note>``</note>` L&#39;elemento non genera un titolo di estensione aggiuntivo del relativo tipo. (10549)
- Native PDF | Non è possibile impostare i metadati del linguaggio nel PDF generato in modo che siano conformi a WCAG 2.0. (12296)



### Traduzione

- Dopo la versione cloud di febbraio (2302), tutti i contenuti di traduzione vengono visualizzati fuori sincronizzazione o senza copia. (11834)

### Recensione

- Nuova interfaccia di revisione | Le condizioni evidenziano e mostrano il funzionamento di Nascondi in modo diverso rispetto a come funzionano nell’Editor web. (11628)
