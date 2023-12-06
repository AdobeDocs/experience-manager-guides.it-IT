---
title: Convertire contenuti non UUID con versioni in contenuti UUID
description: Scopri come migrare i contenuti non UUID con le versioni.
exl-id: 9387e0d1-906c-4e5c-a7a0-0ed1600f5eb6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 1%

---

# Migrare contenuti non UUID con versioni

Per migrare contenuti non UUID con versioni a contenuti UUID, effettua le seguenti operazioni.

## Matrice di compatibilità

| Versione corrente delle guide AEM (non-UUID) | Versione richiesta per la migrazione a UUID | Percorso di aggiornamento supportato |
|---|---|---|
| 3.8.5. | 4.0 non UUID | Installare 4.1 (UUID) ed eseguire la migrazione |
| 4.0, 4.0.x, 4.1 o 4.1.x | Uguale al non UUID corrente | Installare 4.1 (UUID) ed eseguire la migrazione |
| 4.2 o superiore | ND | Non ancora supportato |

## Pacchetti richiesti

1. **Eliminazione versione**: `com.adobe.guides.version-purge-1.0.11.zip` (facoltativo)
1. **Pre-migrazione**: `com.adobe.guides.pre-uuid-migration-1.0.7.zip`
1. **Migrazione**: `com.adobe.guides.uuid-upgrade-1.0.17`
1. **Post-migrazione**: `com.adobe.guides.post-uuid-migration-1.0.2.zip`


## Pre-migrazione

1. (Facoltativo) Esegui la rimozione della versione del contenuto per rimuovere le versioni non necessarie e velocizzare il processo di migrazione. Per eseguire la rimozione della versione 4.1 (NON supportata nella versione 4.0), installa il pacchetto `com.adobe.guides.version-purge-1.0.11.zip`, e vai all’interfaccia utente di utilizzando questo URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Questa utility non rimuove le versioni utilizzate nelle linee di base o nelle revisioni né dispone di etichette.
1. Installare il pacchetto di pre-migrazione (`com.adobe.guides.pre-uuid-migration-1.0.7.zip`).

1. Esegui la seguente query per ottenere un rapporto con un tempo stimato (ETA) di quanto tempo richiederà la migrazione e segnala se sono presenti file con problemi di contenuto che non verrebbero migrati.

>[!NOTE]
>
>Per eseguire la migrazione è necessaria l’autorizzazione di amministratore.


| URL endpoint | Tipo di richiesta | Parametro query | Risultati previsti |
|---|---|---|---|
| `/bin/guides/pre_uuid_upgrade` <br> <br>**Ad esempio**: http://localhost:4502/bin/guides/pre_uuid_upgrade?root=/content/dam | GET | **radice**: cartella principale<br> **Valore**: `/content/dam` per l’intero archivio. | Verrà creato un report di pre-migrazione (.csv) che elenca il numero di file, le versioni totali e gli errori. <br><br> **Output di esempio**:<br>RootFolder: /content/dam <br>File totali: 2697 <br>Versioni totali: 10380 <br>Numero di file con errori: 28 <br>Un rapporto dettagliato sarà disponibile tramite AEM CRX all’indirizzo `/content/uuid-pgrade/UuidMigrationReport_1688400131039.csv` |

Questo passaggio potrebbe non riuscire se nel sistema sono presenti molti file DITA. Per risolvere questo problema, aumenta il limite del numero di file attraversati nella query aumentando il valore di *Limite di lettura in memoria (queryLimitReads)* in Apache Jackrabbit Query Engine Settings Service, 100000 un numero maggiore del numero totale di risorse DITA presenti nel sistema.

## Migrazione

### Passaggio 1: aggiornare la configurazione

1. Assicurati che lo spazio disponibile sia almeno 10 volte superiore allo spazio occupato da AEM (directory crx-quickstart) durante la migrazione. Dopo aver completato la migrazione, è possibile recuperare la maggior parte dello spazio su disco eseguendo la compattazione (fare riferimento a [Pulizia revisioni](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Abilita *Abilita moduli di avvio dei flussi di lavoro di post-elaborazione* in `com.adobe.fmdita.config.ConfigManager` e *Abilita postelaborazione versione* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installa la versione UUID della versione supportata su quella non UUID. Ad esempio, se utilizzi una build 4.0 non UUID o una build 4.1 non UUID, devi installare UUID versione 4.1.

1. Installare il nuovo pacchetto per la migrazione UUID (`com.adobe.guides.uuid-upgrade-1.0.17`).

1. Disattiva i seguenti flussi di lavoro e qualsiasi altro flusso di lavoro in esecuzione su `/content/dam` utilizzo dei moduli di avvio in `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Flusso di lavoro Aggiorna risorsa DAM
   * Flusso di lavoro Writeback di metadati DAM

1. Disattiva *Abilita moduli di avvio dei flussi di lavoro di post-elaborazione* in `com.adobe.fmdita.config.ConfigManager` e disattiva *Abilita postelaborazione versione* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Disabilita la proprietà Abilita convalida (`validation.enabled`) nel servizio di assegnazione tag Day CQ.

1. Assicurati che `uuid.regex` la cartella delle proprietà è impostata correttamente in `com.adobe.fmdita.config.ConfigManager`. Se è vuoto, impostalo sul valore predefinito - `^GUID-(?<id>.*)`.
1. Aggiungi un logger separato per `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` La risposta del browser è disponibile anche all’indirizzo `/content/uuid-upgrade/logs`.

### Passaggio 2: eseguire lo script e convalidare

Esegui la query specificata su una cartella con dati più piccoli prima di eseguirla su `/content/dam`.

>[!TIP]
>
>È possibile verificare se tutti i file della cartella sono aggiornati correttamente e se tutte le funzionalità funzionano solo per tale cartella.

| URL endpoint | Tipo di richiesta | Parametro query | Risultati previsti |
|---|---|---|---|
| `/bin/guides/uuid_upgrade`<br><br> **Ad esempio**: `http://localhost:4502/bin/guides/uuid_upgrade?root=/content/dam/test` | GET | **radice**: cartella principale <br>**Valore**: /content/dam per l’intero archivio.<br><br>**ignoreImageVersions**<br> **Valore**: true/false (ignora l’elaborazione delle versioni delle immagini. Il valore predefinito è false) | Rapporto di migrazione con elenco dei file migrati correttamente, aggiornamento non riuscito, aggiornamento con errori e tempo totale impiegato. <br><br> **Output di esempio**: <br> [INFO] Elenco dei file non riuscito:0 <br>[INFO] No. di file aggiornati correttamente: 2241 <br>[INFO] No. di file aggiornati con errori: 28 <br>[INFO] No. aggiornamento di file non riuscito: 0 <br> [INFO] Tempo totale impiegato: 0:37:03,131 |

>[!NOTE]
>
> La migrazione dei contenuti può essere eseguita a livello di cartella o `/content/dam` o sulla stessa cartella (esegui nuovamente la migrazione).

Inoltre, è importante assicurarsi che la migrazione dei contenuti venga eseguita anche per tutte le risorse multimediali, come immagini e grafici utilizzati nel contenuto DITA.

#### Migrazione linea di base

Esegui la query sulla cartella di cui hai già eseguito la migrazione per migrare le linee di base.

| URL endpoint | Tipo di richiesta | Parametro query | Risultati previsti |
|---|---|---|---|
| `/bin/guides/baseline_uuid_upgrade`<br><br> **Ad esempio**: ` http://localhost:4502/bin/guides/baseline_uuid_upgrade?root=/content/dam/test` | GET | **radice**: cartella principale <br> **Valore**: /content/dam per l’intero archivio. <br><br> **ignoreImageVersions**<br> **Valore**: true/false <br>(Ignora l&#39;elaborazione delle versioni delle immagini. Il valore predefinito è false) <br><br> **doReviews** <br> **Valore**: true/false <br> (Se le recensioni devono essere aggiornate o meno. Il valore predefinito è false.) Rapporto di migrazione con elenco dei file migrati correttamente, aggiornamento non riuscito, aggiornamento con errori e tempo totale impiegato. <br> <br> **Output di esempio**:<br>[INFO] Elenco dei file non riuscito <br> [INFO] No. di file aggiornati correttamente 2241<br> [INFO] No. di file aggiornati con errori 28<br>[INFO] No. impossibile aggiornare 0<br>[INFO] Tempo totale impiegato: 0:37:03,131 |


### Passaggio 3: ripristinare la configurazione

Una volta completata la migrazione del server, abilita la post-elaborazione, l’assegnazione di tag e i seguenti flussi di lavoro (inclusi tutti gli altri flussi di lavoro inizialmente disabilitati durante la migrazione) per continuare a lavorare sul server.

* Flusso di lavoro Aggiorna risorsa DAM
* Flusso di lavoro per metadati DAM

>[!NOTE]
>
>Se alcuni file non vengono elaborati o danneggiati prima della migrazione, verrebbero danneggiati prima della migrazione e rimarrebbero danneggiati anche dopo la migrazione.

## Convalida della migrazione

1. Installare il pacchetto di migrazione post-uuid (`com.adobe.guides.post-uuid-migration-1.0.2.zip`).

1. Esegui la query seguente per verificare che non vi siano stati errori durante la migrazione che abbiano causato l’interruzione di eventuali collegamenti. Questo script identificherà se vi sono stati collegamenti non interrotti in precedenza ma interrotti ora per qualsiasi motivo.

   | URL endpoint | Tipo di richiesta | Parametro query | Risultati previsti |
   |---|---|---|---|
   | `/bin/guides/get_broken_links` <br> <br> **Ad esempio**:<br>`http://localhost:4502/bin/guides/get_broken_links` | GET | ND | Rapporto di migrazione con il numero totale di file con UUID interrotti e i rispettivi percorsi dei file. <br> <br> **Output di esempio**:<br>[DEBUG] Verifica dell&#39;utilizzo di tutti questi GUID nel contenuto.<br>[DEBUG] Numero totale di file che potrebbero aver danneggiato UUID: 0 <br>[DEBUG] Percorsi che potrebbero aver interrotto gli UUID:0 |

1. Al termine della migrazione, è possibile recuperare la maggior parte dello spazio su disco eseguendo la compattazione (fare riferimento a `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

## Migrazione dei contenuti Delta

1. Per migrare il contenuto delta dal server attivo (non UUID) al server UUID corrente, installa lo script di pre-migrazione sul server non UUID.

1. Esegui la seguente query sull’intero set di dati (o sottocartella) per identificare ed esportare tutti i file modificati dopo il timestamp specificato: Il timestamp utilizza il formato ISO8601 per date e ore ( AAAA-MM-GGTHH:mm:ss.SSSZ) e consente anche rappresentazioni parziali, come AAAA-MM-GG.

   | URL endpoint | Tipo di richiesta | Parametro query | Risultati previsti |
   |---|---|---|---|
   | `/bin/guides/data_export`<br><br>**Ad esempio**: <br> `http://localhost:4502/bin/guides/data_export?timestamp=2023-07-11&root=/content/dam` | GET | **timestamp** <br> **Valore**: AAAA-MM-GG<br><br> **radice**: cartella principale <br> **Valore**: `/content/dam` per l’intero archivio. | Un file zip con contenuti delta viene creato in /var/dxml/exports. <br> <br>**Esempio**: dataexport_1689761491218.zip (il file viene creato) |

1. Scarica il file zip esportato dallo script. L’ultima riga della risposta deve fornire il percorso del file zip generato (memorizzato in /var/dxml/exports nel sistema).

1. Carica il file zip sul server uuid nel percorso desiderato nell’interfaccia utente di Assets.

1. Verificare che il pacchetto di post-migrazione sia installato nel server UUID.

1. Esegui la seguente query per importare nel sistema il contenuto delta dal file zip caricato. Per identificare ed elaborare correttamente i dati, la query deve includere il percorso del file zip caricato.

   | URL endpoint | Tipo di richiesta | Parametro query | Risultati previsti |
   |---|---|---|---|
   | `/bin/guides/data_import`<br> **Ad esempio**:`http://localhost:4502/bin/guides/data_import?path=/content/dam/dataexport_1689344927551.zip&createVersion=true` | POST | **percorso**<br> **Valore**: `/content/dam/filename.zip`(Percorso file caricato) **createVersion** <br> **Valore**: true/false<br>Il valore predefinito di createVersion è false. | Il file viene caricato nel percorso di contenuto desiderato.<br><br>**Esempio**: `dataexport_1689761491218.zip`<br><br> (Lo stesso file esportato nel passaggio precedente viene caricato nel percorso desiderato in `/content/dam`). |

1. Se non esiste, lo script creerà un nuovo file o sostituirà il file esistente se è stato modificato.

>[!NOTE]
>
> La cronologia delle versioni e tutte le altre modifiche apportate sul server (come flussi di lavoro e revisioni ) devono essere aggiornate manualmente.
