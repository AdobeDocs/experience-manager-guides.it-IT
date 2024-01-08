---
title: Convertire contenuti non UUID con versioni in contenuti UUID dall’interfaccia utente
description: Scopri come migrare contenuti non UUID con le versioni 4.3.x.
source-git-commit: f18c19eb493cd4d2003f68b082e71ebe7b3e6b7a
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Migrare contenuti non UUID con versioni dall’interfaccia utente

Se utilizzi la versione 4.3.x o successiva, esegui questi passaggi per migrare il contenuto non UUID con le versioni al contenuto UUID.

## Matrice di compatibilità

| Versione corrente delle guide AEM (non-UUID) | Versione richiesta per la migrazione a UUID | Percorso di aggiornamento supportato |
|---|---|---|
| 4.3.x o superiore | 4.3.0 non UUID | Installare 4.3.1 (UUID) |

## Pacchetti richiesti

1. **Eliminazione versione**: `com.adobe.guides.version-purge-1.0.11.zip` (facoltativo)
1. **Pre-migrazione**: `com.adobe.guides.pre-uuid-migration-1.1.2 .zip`
1. **Migrazione**: `com.adobe.guides.uuid-upgrade-1.1.13.zip`



## Pre-migrazione

1. (Facoltativo) Esegui la rimozione della versione del contenuto per rimuovere le versioni non necessarie e velocizzare il processo di migrazione. Per eseguire la rimozione della versione 4.1 (NON supportata nella versione 4.0), installa il pacchetto `com.adobe.guides.version-purge-1.0.11.zip`, e vai all’interfaccia utente di utilizzando questo URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Questa utility non rimuove le versioni utilizzate nelle linee di base o nelle revisioni né dispone di etichette.
1. Installare il pacchetto di pre-migrazione (`ccom.adobe.guides.pre-uuid-migration-1.1.2 .zip`).

   >[!NOTE]
   >
   >* Per eseguire la migrazione è necessaria l’autorizzazione di amministratore.
   >* Si consiglia di correggere i file con errori prima di procedere con la migrazione.

1. Seleziona **Valutazione della compatibilità**  dal pannello a sinistra e sfoglia il percorso di una cartella.
1. Controlla la compatibilità per elencare le seguenti informazioni:
   * File totali
   * Versioni totali
   * Tempo stimato per la migrazione
   * Numero di file con errori



![scheda valutazione della compatibilità in migrazione](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Seleziona **Configurare le convalide** dal pannello a sinistra. Then **Seleziona mappa** e **Seleziona predefinito** della mappa per configurarli. L’elenco di convalida dell’output corrente visualizza i file di output presenti prima della migrazione e può essere convalidato in base ai file di output generati successivamente alla migrazione.

![Configurare la scheda Convalide in migrazione](assets/migration-configure-validation.png){width="800" align="left"}




## Migrazione

### Passaggio 1: aggiornare la configurazione

1. Assicurati che lo spazio disponibile sia almeno 10 volte superiore allo spazio occupato da AEM (directory crx-quickstart) durante la migrazione. Dopo aver completato la migrazione, è possibile recuperare la maggior parte dello spazio su disco eseguendo la compattazione (fare riferimento a [Pulizia revisioni](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Abilita *Abilita moduli di avvio dei flussi di lavoro di post-elaborazione* in `com.adobe.fmdita.config.ConfigManager` e *Abilita postelaborazione versione* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installa la versione UUID della versione supportata su quella non UUID. Ad esempio, se utilizzi una build 4.0 non UUID o una build 4.1 non UUID, devi installare UUID versione 4.1.

1. Installare il nuovo pacchetto per la migrazione UUID (`com.adobe.guides.uuid-upgrade-1.1.13`).

1. Disattiva i seguenti flussi di lavoro e qualsiasi altro flusso di lavoro in esecuzione su `/content/dam` utilizzo dei moduli di avvio in `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Flusso di lavoro Aggiorna risorsa DAM
   * Flusso di lavoro Writeback di metadati DAM

1. Disattiva *Abilita moduli di avvio dei flussi di lavoro di post-elaborazione* in `com.adobe.fmdita.config.ConfigManager` e disattiva *Abilita postelaborazione versione* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Disabilita la proprietà Abilita convalida (`validation.enabled`) nel servizio di assegnazione tag Day CQ.

1. Assicurati che `uuid.regex` la cartella delle proprietà è impostata correttamente in `com.adobe.fmdita.config.ConfigManager`. Se è vuoto, impostalo sul valore predefinito - `^GUID-(?<id>.*)`.
1. Aggiungi un logger separato per `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` La risposta del browser è disponibile anche all’indirizzo `/content/uuid-upgrade/logs`.

### Passaggio 2: eseguire la migrazione e convalidare

#### Installare il pacchetto di migrazione

![Scheda Aggiornamento del sistema in migrazione](assets/migration-system-upgrade.png){width="800" align="left"}

* Seleziona **Aggiornamento del sistema** dal pannello a sinistra per eseguire la migrazione. Iniziare su una cartella con dati più piccoli prima di eseguirla su `/content/dam`.

* Seleziona **Scarica rapporto** durante l&#39;esecuzione della migrazione per verificare se tutti i file della cartella sono aggiornati correttamente e se tutte le funzionalità funzionano solo per tale cartella.


>[!NOTE]
>
> La migrazione dei contenuti può essere eseguita a livello di cartella o `/content/dam` o sulla stessa cartella (esegui nuovamente la migrazione).

Inoltre, è importante assicurarsi che la migrazione dei contenuti venga eseguita anche per tutte le risorse multimediali, come immagini e grafici utilizzati nel contenuto DITA.

#### Migrazione di base e revisione

Seleziona **Aggiornamento della linea di base/revisione** dal pannello a sinistra per migrare le linee di base e rivederle a livello di cartella.

![Scheda Baseline e Revisione in migrazione](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Passaggio 3: ripristinare la configurazione

Una volta completata la migrazione del server, abilita la post-elaborazione, l’assegnazione di tag e i seguenti flussi di lavoro (inclusi tutti gli altri flussi di lavoro inizialmente disabilitati durante la migrazione) per continuare a lavorare sul server.

* Flusso di lavoro Aggiorna risorsa DAM
* Flusso di lavoro per metadati DAM

>[!NOTE]
>
>Se alcuni file non vengono elaborati o danneggiati prima della migrazione, verrebbero danneggiati prima della migrazione e rimarrebbero danneggiati anche dopo la migrazione.

## Convalida della migrazione

Al termine della migrazione, seleziona **Convalidare l’aggiornamento del sistema** dal pannello a sinistra e convalida i file di output prima e dopo la migrazione per garantire che questa abbia esito positivo.

![Convalidare la scheda di aggiornamento del sistema nella migrazione](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Al termine della migrazione, è possibile recuperare la maggior parte dello spazio su disco eseguendo la compattazione (fare riferimento a `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

