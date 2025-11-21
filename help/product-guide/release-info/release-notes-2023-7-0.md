---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione di luglio 2023
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione di luglio 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: f1765c6a-cb8e-4a06-a6f4-f5c225b6bc88
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 1%

---

# Versione di luglio 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di luglio 2023 di Adobe Experience Manager Guides (in seguito denominata *AEM Guides as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, consulta [Novità della versione di luglio 2023 di AEM Guides as a Cloud Service](whats-new-2023-7-0.md).

## Aggiornamento alla versione di luglio 2023

Aggiorna la configurazione corrente di AEM Guides as a Cloud Service eseguendo i seguenti passaggi:

1. Consulta il codice Git dei servizi cloud e passa al ramo configurato nella pipeline dei servizi cloud corrispondente all’ambiente da aggiornare.
2. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei servizi cloud a 2023.7.0.314.
3. Apporta le modifiche ed esegui la pipeline dei servizi cloud per l’aggiornamento alla versione di luglio 2023 di AEM Guides as a Cloud Service.

## Passaggi per abilitare l’attivazione di uno script tramite un servlet

(Solo per le versioni precedenti alla versione di AEM Guides as a Cloud Service di giugno 2023)

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

(Solo per le versioni precedenti alla versione di AEM Guides as a Cloud Service di giugno 2023)

Effettua le seguenti operazioni per la post-elaborazione del contenuto esistente e l’utilizzo del nuovo rapporto sui collegamenti interrotti:

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file dita, aggiornare `queryLimitReads` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valore maggiore (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuire.

   - Utilizza le istruzioni fornite nella sezione *Override della configurazione* in Installare e configurare Adobe Experience Manager Guides
as a Cloud Service, per creare il file di configurazione.
   - Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare l’opzione queryLimitReads:

     | PID | Chiave proprietà | Valore proprietà |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valore: 200000 Valore predefinito: 100000 |

1. Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>//bin/guides/reports/upgrade`.

1. L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Una volta completato il processo, la precedente richiesta GET risponderà con successo. Se il processo non riesce per qualche motivo, l’errore può essere visualizzato dai registri del server.

1. Ripristinare il valore predefinito o esistente precedente di `queryLimitReads` se è stato modificato nel passaggio 1.

## Passaggi per indicizzare il contenuto esistente per utilizzare il nuovo elenco Trova e sostituisci e Argomento nella scheda Rapporti:

(Solo per le versioni precedenti alla versione di AEM Guides as a Cloud Service di giugno 2023)

Effettua i seguenti passaggi per indicizzare il contenuto esistente e utilizza il nuovo testo Trova e sostituisci a livello di mappa e l’elenco degli argomenti nella scheda Rapporti:

1. Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi passare percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate \|\| Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

1. L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Una volta completato il processo, la precedente richiesta GET risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di luglio 2023 di AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.07.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.07.0 | 2,9-uuid-2 | 2,9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |


## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Gli attributi Inline/Display non vengono visualizzati nella visualizzazione Layout dell&#39;editor Web. (12498)
- Caricare i file nel plug-in di ossigeno per AEM Guides non funziona in Cloud Services se si dispone di ! nel nome del file. (12207)
- La pubblicazione di mappe DITA è molto lenta con i modelli modificabili. (12075)
- La configurazione dell’interfaccia utente del profilo globale non corrisponde al profilo cartella. (11970)
- I riferimenti ai contenuti vengono interrotti quando i file DITA vengono copiati e incollati. (11959)
- Impossibile modificare il frammento di contenuto nella vista a colonne se è installato AEM Guides. (7342)
- Il contenuto viene perso quando un riferimento esteso non racchiuso si trova sotto i tag di un elemento secondario. (12532)

### Pubblicazione

- Il flusso di lavoro di approvazione non funziona se docstate viene modificato in &quot;end state&quot; dalle proprietà File del pannello di destra. (11026)
