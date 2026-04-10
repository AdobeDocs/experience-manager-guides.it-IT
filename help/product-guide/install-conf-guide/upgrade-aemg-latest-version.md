---
title: Aggiornare Adobe Experience Manager Guides
description: Scopri come aggiornare Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '1661'
ht-degree: 0%

---

# Aggiornare Adobe Experience Manager Guides per versione 4.6.0 e successive

Questo articolo fornisce istruzioni per aggiornare le versioni di Experience Manager Guides per 4.6.0 e successive.

>[!NOTE]
>
> Segui le istruzioni di aggiornamento specifiche per la versione con licenza del tuo prodotto.

È possibile aggiornare la versione corrente di Experience Manager Guides alla versione 5.1.0 Service Pack 3:

- Se utilizzi le versioni 5.1.0 o 5.1.x , puoi eseguire direttamente l’aggiornamento alla versione 5.1.0 Service Pack 3.
- Se utilizzi le versioni 4.6.0, 4.6.x, 5.0.0 o 5.0.x, devi effettuare l’aggiornamento alla versione 5.1.0.
- Se utilizzi una versione precedente alla 4.6.0, consulta [Aggiornare Adobe Experience Manager Guides per la versione 4.4.0 e precedenti](./upgrade-aemg-prev-versions.md) per istruzioni di aggiornamento dettagliate.

>[!NOTE]
>
> È necessario installare AEM Service Pack prima di aggiornare la versione di Experience Manager Guides.

Per ulteriori informazioni, consulta le procedure seguenti:

- [Aggiornamento alla versione 5.1.0](#upgrade-to-version-510)
- [Aggiornamento alla versione 5.0.0](#upgrade-to-version-500)
- [Aggiornamento alla versione 4.6.0](#upgrade-to-version-460)

>[!IMPORTANT]
>
> Prima di iniziare l&#39;aggiornamento, eseguire un backup completo del sistema per evitare la perdita di dati.


## Aggiornamento alla versione 5.1.0


>[!IMPORTANT]
>
> Se al momento utilizzi AEM 6.5 e prevedi di passare ad AEM 6.5 LTS, assicurati di completare l’aggiornamento ad AEM prima di procedere con l’aggiornamento a Experience Manager Guides 5.1.0. Per informazioni dettagliate, visualizzare [Aggiornamento a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/it/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

**Prerequisiti**

>[!NOTE]
>
>Se stai eseguendo l’aggiornamento a 5.1.0 Service Pack 3, devi utilizzare la versione 5.1.0 o 5.1.x di Experience Manager Guides. Il processo di aggiornamento per la versione 5.1.0 Service Pack 3 segue gli stessi passaggi della versione 5.1.0.

Prima di avviare il processo di aggiornamento di Experience Manager Guides 5.1.0, verificare di disporre dei seguenti elementi:

1. Aggiornamento a Experience Manager Guides versione 4.6.3, 4.6.4, 5.0.0 o 5.0.0 Service Pack 1.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.

>[!NOTE]
>
> La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

**Installa versione 5.1.0**

Scarica il pacchetto della versione 5.1.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html) e segui le istruzioni fornite in [Flusso di lavoro di installazione e aggiornamento post-installazione](#installation-and-post-installation-upgrade-workflow) per completare il processo di aggiornamento.


## Aggiornamento alla versione 5.0.0

>[!TIP]
>
> L’aggiornamento alla versione 5.0.0 del Service Pack 3 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi le versioni 5.0.0 Service Pack 2, 5.0.0 Service Pack 1 o 5.0.0, puoi eseguire direttamente l’aggiornamento alla versione 5.0.0 Service Pack 3. I passaggi di aggiornamento sono gli stessi della versione 5.0.0.

>[!NOTE]
>
> La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

**Prerequisiti**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 5.0.0, verificare di disporre dei seguenti elementi:

1. Aggiornamento a Experience Manager Guides versione 4.6.3, 4.6.1, 4.6.0 o 4.4.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.


**Installa versione 5.0.0**

Scarica il pacchetto della versione 5.0.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html) e segui le istruzioni fornite in [Flusso di lavoro di installazione e aggiornamento post-installazione](#installation-and-post-installation-upgrade-workflow) per completare il processo di aggiornamento.

## Aggiornamento alla versione 4.6.0

>[!TIP]
>
> Si consiglia di installare 4.6.0 Service Pack 4 oltre alle versioni 4.6.0, 4.6.0 Service Pack 1 o 4.6.0 Service Pack 3. Il processo di aggiornamento per la versione 4.6.0 Service Pack 4 segue gli stessi passaggi della versione 4.6.0.

L’aggiornamento alla versione 4.6.0 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi le versioni 4.4.0, 4.3.1, 4.3.0, 4.2 o 4.2.1 (Hotfix 4.2.1.3), puoi eseguire direttamente l&#39;aggiornamento alla versione 4.6.0.

>[!NOTE]
>
> La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

**Prerequisiti**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.6.0, assicurati di disporre di:

1. Aggiornamento a Experience Manager Guides versione 4.3.1, 4.3.0 o 4.2.1 (Hotfix 4.2.1.3).
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.

**Installa versione 4.6.0**

Scarica il pacchetto di versione 4.6.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html) e segui le istruzioni fornite in [Flusso di lavoro di installazione e aggiornamento post-installazione](#installation-and-post-installation-upgrade-workflow) per completare il processo di aggiornamento.

## Flusso di lavoro di aggiornamento per installazione e post-installazione

### Installare il pacchetto della versione

Per installare il pacchetto di versione, effettua le seguenti operazioni:

1. Installa il pacchetto di versione su cui desideri eseguire l’aggiornamento.
1. Puoi scegliere di premere il trigger per avviare il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet).

1. Dopo aver completato l’installazione del pacchetto, attendi il seguente messaggio nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutti i passaggi dell&#39;installazione sono stati completati.

   Se riscontri uno dei seguenti errori, segnalali al team di successo del cliente:

   - Errore nello script di installazione post-distribuzione
   - Eccezione durante il porting del MAP di traduzione
   - Impossibile trasferire la mappa di traduzione dalla versione 1 alla versione 2 per la proprietà
1. (Facoltativo) Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione che si sta aggiornando.
1. Cancella la cache del browser dopo l’installazione del pacchetto.

### Processo post-installazione

Dopo aver installato Experience Manager Guides, è possibile unire le varie configurazioni applicabili dalla versione appena installata alla configurazione.

>[!NOTE]
>
> Il modello dam-update-asset può essere personalizzato. Pertanto, se sono state apportate personalizzazioni, è necessario sincronizzare le personalizzazioni e Experience Manager Guides nella copia di lavoro del modello.

**Flusso di lavoro Aggiorna risorsa DAM \(Modifiche post-elaborazione\):**

1. Apri URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleziona **Flusso di lavoro Aggiorna risorsa DAM**.
1. Seleziona **Modifica**.
1. Se il componente **DXML Post Process Initiator** è presente, verificare che le personalizzazioni siano sincronizzate.
1. Se il componente **DXML Post Process Initiator** è assente, eseguire la procedura seguente per inserirlo:

   - Selezionare **Inserisci componente** \(Responsabile della post-elaborazione di Experience Manager Guides come fase finale del processo\).
   - Configura il **passaggio del processo** con i dettagli seguenti:

     **Scheda comune:**

      - **Titolo:** iniziatore post-elaborazione DXML

      - **Descrizione**: passaggio iniziatore post-elaborazione DXML che attiverà un processo sling per la post-elaborazione DXML della risorsa modificata/creata

     **Scheda Elabora**

      - Selezionare **DXML Post Process Initiator** dal menu a discesa **Process**
      - Seleziona **Avanzamento gestore**
      - Seleziona **Fine**

1. Seleziona **Sincronizza** in alto a destra dopo aver completato le modifiche. Riceverai una notifica di esito positivo.

   >[!NOTE]
   >
   > Aggiorna e verifica che le modifiche personalizzate e il passaggio di post-elaborazione Experience Manager Guides siano presenti nel modello di flusso di lavoro finale.

1. Una volta convalidato il flusso di lavoro **Aggiorna risorsa DAM**, controlla le configurazioni del modulo di avvio corrispondenti. Per farlo, vai all’interfaccia di AEM Workflow e apri i moduli di avvio.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Trova e apporta le modifiche \(se necessario\) ai seguenti due moduli di avvio \(che dovrebbe essere attivo\) corrispondenti al flusso di lavoro **Aggiorna risorsa DAM**:

1. Modulo di avvio per &quot;*Nodo creato*&quot; per **Flusso di lavoro Aggiorna risorsa DAM**- per la condizione `"jcr:content/jcr:mimeType!=video"`, il valore &#39;Globbing&#39; deve essere:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; deve avere `"event-user-data:changedByWorkflowProcess"`.
   - Modulo di avvio per &quot;*Node Modified*&quot; per **Flusso di lavoro Aggiorna risorsa DAM -** per la condizione &quot;`jcr:content/jcr:mimeType!=video`&quot;, il valore &#39;Globbing&#39; deve essere:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` deve avere `"event-user-data:changedByWorkflowProcess"`.

1. Al termine dell’aggiornamento, accertati che le personalizzazioni/sovrapposizioni siano convalidate e aggiornate in modo che corrispondano al nuovo codice dell’applicazione. Di seguito sono riportati alcuni esempi:
   - Tutti i componenti sovrapposti da `/libs/fmditaor/libsshould` devono essere confrontati con il nuovo codice prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in/apps.
   - Qualsiasi categoria `clientlib` utilizzata dal prodotto, deve essere rivista per le modifiche. Eventuali configurazioni sostituite `\(examples below\)` devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - elementmapping.xml
   - `ui\_config.json\(may have been set in folder profiles\)`
   - ha modificato `com.adobe.fmdita.config.ConfigManager`

1. Se hai aggiunto delle personalizzazioni in damAssetLucene, potresti dover applicarle nuovamente. Dopo aver apportato tali modifiche, imposta la reindicizzazione su true. In questo modo tutti i nodi esistenti verranno reindicizzati con le personalizzazioni. Al termine, il flag di reindicizzazione verrà impostato di nuovo su false. Questa operazione può richiedere alcune ore a seconda del numero di risorse nel sistema.

### Passaggi per reindicizzare gli indici Experience Manager Guides

1. Apri `crx/de` e passa al percorso indice: `/oak:index/guidesAssetProperties`
2. Impostare la proprietà di reindicizzazione come `true` (`false` per impostazione predefinita) e fare clic su **Salva tutto**.
3. Una volta completata la reindicizzazione, la proprietà di reindicizzazione viene nuovamente impostata su `false` e il conteggio di reindicizzazione viene incrementato di 1.

   >[!NOTE]
   >
   > Questa operazione può richiedere alcuni minuti, a seconda della quantità di dati presenti.
4. Seguire la stessa procedura per gli altri indici aggiunti o modificati: `guidesBulkActivation`, `guidesPeerLinkIndex` e `guidesKonnectTemplateIndex`.

### Passaggi per indicizzare il contenuto esistente

Per indicizzare il contenuto esistente, effettua le seguenti operazioni:

- Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: è possibile passare percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate || Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L&#39;API restituirà `jobId`. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (ad esempio: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.


>[!NOTE]
>
> Se si utilizza lo schema personalizzato, è necessario definire il percorso dei file DTD e XSD catalog.xml personalizzati nell&#39;archivio di AEM nell&#39;opzione **Integrate Catalog**.

### Passaggi per gestire il conflitto `'fmdita rewriter'`

Experience Manager Guides dispone di un modulo [**sling rewriter personalizzato**](../install-conf-guide/conf-output-generation.md#custom-rewriter) per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50.  Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante l&#39;aggiornamento, poiché il valore `'order'` viene modificato da 1000 a 50, è necessario unire l&#39;eventuale rewriter personalizzato esistente con `'fmdita-rewriter'`.


### Passaggi per reindicizzare damAssetLucene

La definizione dell’indice viene aggiornata per damAssetLucene con AEM Guides. Dopo l&#39;aggiornamento alla versione richiesta, fare riferimento a [questo articolo](https://experienceleague.adobe.com/it/docs/experience-cloud-kcs/kbarticles/ka-16460) per reindicizzare damAssetLucene.

>[!NOTE]
>
> Seguendo la documentazione, assicurarsi che entrambe le proprietà (`reindex=true` e `reindex-async=true` per `/oak:index/damAssetLucene`) siano aggiornate contemporaneamente tramite l&#39;operazione Salva.

