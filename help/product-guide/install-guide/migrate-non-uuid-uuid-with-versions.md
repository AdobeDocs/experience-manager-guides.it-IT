---
title: Convertire contenuti non UUID con versioni in contenuti UUID
description: Scopri come migrare contenuti non UUID con versioni a contenuti UUID.
source-git-commit: b57364fa52d48791fbab07125f13007c563b7781
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 0%

---

# Migra contenuti con versione

Esegui questi passaggi per migrare il contenuto con versione non UUID al contenuto UID.

>[!NOTE]
>
>Segui le [istruzioni di aggiornamento](./upgrade-xml-documentation.md) specifico per la versione con licenza del prodotto.

## Matrice di compatibilità

| Versione corrente delle guide di Experience Manager (non UUID) | Versione richiesta per la migrazione a UUID | Percorso di aggiornamento supportato |
|---|---|---|
| 3.8.5, 4.0.x o 4.1.x | 4.1 non UUID | Installare 4.1 (UUID) ed eseguire la migrazione |
| 4.2, 4.2.x o 4.3 | 4.3.0 non UUID | Installa 4.3.1 (UUID) ed esegui la migrazione |
| 4.3.1. | ND | ND |

## Installazione del pacchetto

Scarica i pacchetti richiesti da Adobe Software Distribution Portal, in base alla versione:
<details>
<summary>  Pacchetti per il percorso di aggiornamento versione 4.1</summary>

1. **Pre-migrazione**: [com.adobe.guides.pre-uuid-migration-1.0.9.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.pre-uuid-migration-1.0.9.zip)
1. **Migrazione**: [com.adobe.guides.uuid-upgrade-1.0.19.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.uuid-upgrade-1.0.19.zip)
</details>


<details>
<summary> Pacchetti per il percorso di aggiornamento versione 4.3.1</summary>

1. **Pre-migrazione**: [com.adobe.guides.pre-uuid-migration-1.1.3.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.pre-uuid-migration-1.1.3.zip)
1. **Migrazione**: [com.adobe.guides.uuid-upgrade-1.1.15.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.uuid-upgrade-1.1.15.zip)

</details>

## Pre-migrazione

Esegui i seguenti controlli sulla versione non UUID (4.1 non UUID o 4.3.0 non UUID):

1. Installa il pacchetto di pre-migrazione in base alla versione.

   >[!NOTE]
   >
   >* Per eseguire la migrazione è necessaria l’autorizzazione di amministratore.
   >* Si consiglia di correggere i file con errori prima di procedere con la migrazione.

1. (Facoltativo) Esegui la rimozione della versione del contenuto per rimuovere le versioni non necessarie e velocizzare il processo di migrazione. Per eseguire la rimozione delle versioni, selezionare l&#39;opzione
   **Pulizia versione** dalla schermata di migrazione e passa all’interfaccia utente utilizzando l’URL `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
   >[!NOTE]
   >
   >Questa utility non rimuove le versioni utilizzate nelle linee di base o nelle revisioni né dispone di etichette.
1. Launch `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
1. Seleziona **Valutazione della compatibilità**  dal pannello a sinistra e sfoglia il percorso di una cartella.
1. Controlla la compatibilità per elencare le seguenti informazioni:
   * File totali
   * Versioni totali
   * Tempo stimato per la migrazione
   * Numero di file con errori

   ![scheda valutazione della compatibilità in migrazione](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Seleziona **Configurare le convalide** dal pannello a sinistra. Allora, **Seleziona mappa** e **Seleziona predefinito** della mappa per configurarli. L’elenco di convalida dell’output corrente visualizza i file di output presenti prima della migrazione e può essere convalidato in base ai file di output generati successivamente alla migrazione.

   ![Configurare la scheda Convalide in migrazione](assets/migration-configure-validation.png){width="800" align="left"}




## Migrazione

### Passaggio 1: aggiornare la configurazione

1. Assicurati che lo spazio disponibile sia almeno dieci volte superiore a quello occupato da AEM (directory crx-quickstart) durante la migrazione. Una volta completata la migrazione, è possibile recuperare la maggior parte dello spazio su disco eseguendo la compattazione (fare riferimento a [Pulizia revisioni](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Abilita *Abilita moduli di avvio dei flussi di lavoro di post-elaborazione* in `com.adobe.fmdita.config.ConfigManager` e *Abilita postelaborazione versione* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installa la versione UUID della versione supportata su quella non UUID. Ad esempio, se utilizzi la build 4.1 non UUID, devi installare UUID versione 4.1 ed eseguire la migrazione.

1. Installa il nuovo pacchetto per la migrazione UUID.

1. Disattiva i seguenti flussi di lavoro e qualsiasi altro flusso di lavoro in esecuzione su `/content/dam` utilizzo dei moduli di avvio in `http://<server-name>/libs/cq/workflow/content/console.html`.

   * Flusso di lavoro Aggiorna risorsa DAM
   * Flusso di lavoro Writeback di metadati DAM

1. Disattiva *Abilita moduli di avvio dei flussi di lavoro di post-elaborazione* in `com.adobe.fmdita.config.ConfigManager` e disattiva *Abilita postelaborazione versione* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Disabilita la proprietà Abilita convalida (`validation.enabled`) nel servizio di assegnazione tag Day CQ.

1. Assicurati che `uuid.regex` la cartella delle proprietà è impostata correttamente in `com.adobe.fmdita.config.ConfigManager`. Se è vuoto, impostalo sul valore predefinito - `^GUID-(?<id>.*)`.
1. Aggiungi un logger separato per `com.adobe.fmdita.uuid` La risposta del browser è disponibile anche all’indirizzo `/content/uuid-upgrade/logs`.

### Passaggio 2: eseguire la migrazione e convalidare

#### Installare il pacchetto di migrazione

1. Launch `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

   ![Scheda Aggiornamento del sistema in migrazione](assets/migration-system-upgrade.png){width="800" align="left"}

1. Seleziona **Aggiornamento del sistema** dal pannello a sinistra per eseguire la migrazione. Iniziare su una cartella con dati più piccoli prima di eseguirla su `/content/dam`.

1. Seleziona **Scarica rapporto** durante l&#39;esecuzione della migrazione per verificare se tutti i file della cartella sono aggiornati correttamente e se tutte le funzionalità funzionano solo per tale cartella.


>[!NOTE]
>
> La migrazione dei contenuti può essere eseguita a livello di cartella, la `/content/dam`o la stessa cartella (esegui nuovamente la migrazione).

Inoltre, è importante assicurarsi che la migrazione dei contenuti venga eseguita per tutte le risorse multimediali, come immagini e grafici utilizzati nel contenuto DITA.

#### Migrazione di base e revisione

Seleziona **Aggiornamento della linea di base/revisione** dal pannello a sinistra per migrare le linee di base e rivederle a livello di cartella.

![Scheda Baseline e Revisione in migrazione](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Passaggio 3: ripristinare la configurazione

Dopo aver eseguito correttamente la migrazione del server, abilita la post-elaborazione, l’assegnazione di tag e i seguenti flussi di lavoro (inclusi tutti gli altri flussi di lavoro inizialmente disabilitati durante la migrazione) per continuare a lavorare sul server.

* Flusso di lavoro Aggiorna risorsa DAM
* Flusso di lavoro per metadati DAM

>[!NOTE]
>
>Se alcuni file non vengono elaborati o danneggiati prima della migrazione, verranno danneggiati prima della migrazione e rimarranno danneggiati anche dopo la migrazione.

## Convalida della migrazione

1. Al termine della migrazione, seleziona **Convalidare l’aggiornamento del sistema** dal pannello a sinistra e convalida i file di output prima e dopo la migrazione per garantire che questa abbia esito positivo.

   ![Convalidare la scheda di aggiornamento del sistema nella migrazione](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Al termine della convalida, è possibile recuperare la maggior parte dello spazio su disco eseguendo la compattazione (fare riferimento a `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

