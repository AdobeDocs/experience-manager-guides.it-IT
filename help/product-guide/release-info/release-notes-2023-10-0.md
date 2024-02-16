---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione di ottobre 2023
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione di ottobre 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: 536d2ec2-31a0-4533-9c29-16a27525acca
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 1%

---

# Versione di ottobre 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di ottobre 2023 delle Guide di Adobe Experience Manager (in seguito denominate *Guide AEM as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione di ottobre 2023 delle guide AEM as a Cloud Service](whats-new-2023-10-0.md).

## Aggiornamento alla versione di ottobre 2023

Aggiorna l’attuale configurazione as a Cloud Service delle Guide AEM eseguendo i seguenti passaggi:

1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
2. Aggiorna `<dox.version>` proprietà in `/dox/dox.installer/pom.xml` file del codice Git dei tuoi Cloud Service in 2023.10.0.373.
3. Apporta le modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione as a Cloud Service di ottobre 2023 delle guide AEM.

## Passaggi per abilitare l’attivazione di uno script tramite un servlet

(Solo se utilizzi una versione precedente alla versione di giugno 2023 di AEM Guides as a Cloud Service)

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

(Solo se utilizzi una versione precedente alla versione di giugno 2023 di AEM Guides as a Cloud Service)

Effettua le seguenti operazioni per la post-elaborazione del contenuto esistente e l’utilizzo del nuovo rapporto sui collegamenti interrotti:

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file DITA, aggiornare `queryLimitReads` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` su un valore più grande (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuiscilo.

   - Utilizzare le istruzioni fornite nella *Sostituzioni configurazione* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service, per creare il file di configurazione.
   - Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare l’opzione queryLimitReads:

     | PID | Chiave proprietà | Valore proprietà |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valore: 200000 Valore predefinito: 100000 |

1. Eseguire una richiesta POST al server (con l’autenticazione corretta) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API restituisce un jobId. Per verificare lo stato del processo, puoi inviare una richiesta di GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
Ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la richiesta di GET precedente risponde con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristina il valore predefinito o esistente precedente di `queryLimitReads` se è stato modificato nel passaggio 1.

## Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti:

(Solo se utilizzi una versione precedente alla versione di giugno 2023 di AEM Guides as a Cloud Service)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Esegui una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi passare percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate \|\| Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

1. L’API restituisce un jobId. Per verificare lo stato del processo, puoi inviare una richiesta di GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Una volta completato il processo, la richiesta di GET precedente risponde con successo e indica se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di ottobre 2023 delle guide AEM as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.10.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.10.0 | 3,2-uuid 5 | 3,2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |


### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti dei componenti delle guide AEM per il Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Le ore pomeridiane non sono impostate nel **Data** per la creazione di baseline. (12712)
- Impossibile incollare il codice JSON in `<codeblock>` dell&#39;editor Web. (12326)
- Le modifiche delle versioni non salvate e i relativi indicatori non vengono visualizzati per i file di grandi dimensioni. (11784)
- Durante la modifica in coreano, il primo carattere diventa il carattere predefinito. (10049)


### Pubblicazione

- Native PDF | L’ordine degli argomenti non viene corretto durante la generazione dell’output di PDF. (13157)
- PDF nativa| Nessun tag di stile predefinito disponibile per `<p>`elemento. (12559)
- Native PDF | Gli stili in linea applicati all&#39;area del contenuto non vengono applicati agli argomenti davanti e dietro. (13510)
- Il `DeliveryTarget` L&#39;attributo non viene propagato durante la generazione dell&#39;output del sito AEM.  (13132)
- Il **Pubblica** Il flusso di lavoro si blocca durante la generazione dell’output del sito AEM per il contenuto con determinati errori. (12000)

### Gestione

- La cronologia delle versioni non viene visualizzata anche se `dc:format` proprietà non presente per una risorsa. (10463)


### Rivedi

- La revisione di un argomento mostra commenti non corretti. (13453)



### Traduzione

- La linea di base esportata da **Traduzione** il dashboard ha esito negativo e non si apre nella lingua di destinazione. (13466)

- Vengono creati nuovi progetti di traduzione invece di aggiungere nuovi processi ai progetti di traduzione esistenti selezionati.  (10214)

## Problema noto

L’Adobe ha identificato il seguente problema noto per la versione di ottobre 2023.

- Ripubblicazione del frammento di contenuto non riuscita.
