---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione di ottobre 2023
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione di ottobre 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: 536d2ec2-31a0-4533-9c29-16a27525acca
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/z5F-Y7WSSnFSGU5n6obqNb9bOqp3WQvvpxaQJ9ksOLI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: afb45297-4313-4f67-818e-bc0b03abe086
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: cda0baeb-996e-4aaa-92d1-41032e34fd68
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1047
ht-degree: 2%

---

# Versione di ottobre 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di ottobre 2023 di Adobe Experience Manager Guides (in seguito denominata *AEM Guides as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, consulta [Novità della versione di ottobre 2023 di AEM Guides as a Cloud Service](whats-new-2023-10-0.md).

## Aggiornamento alla versione di ottobre 2023

Aggiorna la configurazione corrente di AEM Guides as a Cloud Service eseguendo i seguenti passaggi:

1. Consulta il codice Git dei servizi cloud e passa al ramo configurato nella pipeline dei servizi cloud corrispondente all’ambiente da aggiornare.
2. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei servizi cloud a 2023.10.0.373.
3. Apporta le modifiche ed esegui la pipeline dei servizi cloud per l’aggiornamento alla versione di ottobre 2023 di AEM Guides as a Cloud Service.

## Passaggi per abilitare l’attivazione di uno script tramite un servlet

(Solo per le versioni precedenti alla versione di giugno 2023 di AEM Guides as a Cloud Service)

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

Nella risposta precedente JSON, la chiave `lockNodePath` contiene il percorso del nodo creato nell&#39;archivio che punta al processo inviato. Verrà eliminato automaticamente una volta completato il processo; fino ad allora, puoi fare riferimento a questo nodo per lo stato corrente del processo.

Attendere il completamento del processo prima di procedere ai passaggi successivi.

>[!NOTE]
>
> Verifica se il nodo è ancora presente e lo stato del processo.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Passaggi per pubblicare ed elaborare il contenuto esistente per utilizzare il rapporto sui collegamenti interrotti

(Solo per le versioni precedenti alla versione di giugno 2023 di AEM Guides as a Cloud Service)

Effettua le seguenti operazioni per la post-elaborazione del contenuto esistente e l’utilizzo del nuovo rapporto sui collegamenti interrotti:

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file DITA, aggiornare `queryLimitReads` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valore maggiore (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuire.

   - Per creare il file di configurazione, segui le istruzioni fornite nella sezione *Sostituzioni configurazione* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.
   - Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare l’opzione queryLimitReads:

     | PID | Chiave proprietà | Valore proprietà |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valore: 200000 Valore predefinito: 100000 |

1. Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API restituisce un jobId. Per verificare lo stato del processo, puoi inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la precedente richiesta GET risponde con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristinare il valore predefinito o esistente precedente di `queryLimitReads` se è stato modificato nel passaggio 1.

## Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti:

(Solo per le versioni precedenti alla versione di giugno 2023 di AEM Guides as a Cloud Service)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: È possibile passare percorsi specifici delle mappe per indicizzarle. Per impostazione predefinita, tutte le mappe saranno indicizzate \|\| Ad esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

1. L’API restituisce un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Una volta completato il processo, la precedente richiesta GET risponde con successo e indica se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di ottobre 2023 di AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.10.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.10.0 | 3,2-uuid 5 | 3,2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |  |


### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti dei componenti di AEM Guides per Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Le ore pomeridiane non sono impostate nella **Data** per la creazione delle linee di base. (12712)
- Impossibile incollare il codice JSON nell&#39;elemento `<codeblock>` dell&#39;editor Web. (12326)
- Le modifiche delle versioni non salvate e i relativi indicatori non vengono visualizzati per i file di grandi dimensioni. (11784)
- Durante la modifica in coreano, il primo carattere diventa il carattere predefinito. (10049)


### Pubblicazione

- PDF nativo | L’ordine degli argomenti non viene corretto durante la generazione dell’output di PDF. (13157)
- PDF nativo| Nessun tag di stile predefinito disponibile per l&#39;elemento `<p>`. (12559)
- PDF nativo | Gli stili in linea applicati all&#39;area contenuto non vengono applicati agli argomenti in primo piano e dietro. (13510)
- L&#39;attributo `DeliveryTarget` non viene propagato durante la generazione dell&#39;output del sito AEM.  (13132)
- Il flusso di lavoro **Pubblica** si blocca durante la generazione dell&#39;output del sito AEM per il contenuto con determinati errori. (12000)

### Gestione

- La cronologia delle versioni non viene visualizzata anche se la proprietà `dc:format` non è presente per una risorsa. (10463)


### Rivedere

- La revisione di un argomento mostra commenti non corretti. (13453)



### Traduzione

- La linea di base esportata dal dashboard **Traduzione** non riesce e non si apre nella lingua di destinazione. (13466)

- Vengono creati nuovi progetti di traduzione invece di aggiungere nuovi processi ai progetti di traduzione esistenti selezionati.  (10214)

## Problema noto

Adobe ha identificato il seguente problema noto per la versione di ottobre 2023.

- Ripubblicazione del frammento di contenuto non riuscita.
