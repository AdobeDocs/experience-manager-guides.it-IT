---
title: Aggiorna Adobe Experience Manager Guides On Premise - Versioni precedenti
description: Scopri come aggiornare Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3159'
ht-degree: 0%

---

# Aggiornare Adobe Experience Manager Guides On Premise (versione 4.4.0 e precedenti)

Questo articolo fornisce istruzioni per aggiornare **Adobe Experience Manager Guides** versioni **precedenti alla versione 4.6.0** (fino a **4.4.0** incluso).

Se utilizzi una versione **precedente alla 3.8.5**, consulta la sezione **Aggiornamento di Experience Manager Guides** nella guida all&#39;installazione specifica per il prodotto, disponibile in [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

Per le istruzioni di aggiornamento per le versioni più recenti, consulta [Aggiornare Adobe Experience Manager Guides per la versione 4.6.0 e successive](./upgrade-aemg-latest-version.md).

## Prima di iniziare

>[!NOTE]
>
> Prima di aggiornare la versione di Experience Manager Guides, è necessario aggiornare le istruzioni specifiche della versione con licenza del prodotto e installare AEM Service Pack.

>[!IMPORTANT]
>
> Prima di iniziare l&#39;aggiornamento, eseguire un **backup completo del sistema** per evitare la perdita di dati.

## Percorsi di aggiornamento descritti in questo articolo

Il presente articolo include procedure per:

- [Aggiornamento alla versione 4.4.0](#upgrade-to-version-440)
- [Aggiorna alla versione 4.3.1.5](#upgrade-to-version-4315)
- [Aggiornamento alla versione 4.3.1](#upgrade-to-version-431)
- [Aggiornamento alla versione 4.3.0](#upgrade-to-version-430)
- [Aggiornamento alla versione 4.2.1](#upgrade-to-version-421)
- [Aggiornamento alla versione 4.2](#upgrade-to-version-42)
- [Aggiornamento da 3.8.5 a versione 4.0](#upgrade-from-version-385-to-version-40)


## Prerequisiti globali (si applica a tutti gli aggiornamenti a meno che una procedura non disponga diversamente)

Prima di eseguire il processo di aggiornamento, completare le seguenti attività:

1. Importa i commenti di revisione negli argomenti aperti per la revisione.
2. Chiudi tutte le recensioni attive.
3. Chiude tutte le attività di traduzione.
4. Disinstalla eventuali aggiornamenti rapidi di Experience Manager Guides installati sopra la versione precedente (versione principale o patch).

Alcuni aggiornamenti richiedono anche l&#39;impostazione del livello di registro su `INFO` per una classe di aggiornamento della traduzione e l&#39;accesso a un file separato; tali requisiti sono descritti nelle procedure di aggiornamento pertinenti.

## Aggiornamento dalla versione 3.8.5 alla versione 4.0

>[!NOTE]
>
> Questo processo di aggiornamento è applicabile **only** da **3.8.5** a **4.0**. Per gli aggiornamenti da **3.4 o versione successiva** a **3.8.5**, fare riferimento alla guida all&#39;installazione specifica del prodotto disponibile nell&#39;archivio di PDF della [Guida di Adobe Experience Manager Guides](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

Se si utilizza Experience Manager Guides versione **3.8.5**, è possibile eseguire l&#39;aggiornamento alla versione **4.0** senza disinstallare la versione precedente.

### Prima di installare la versione 4.0

1. Verificare che la versione di Experience Manager Guides sia **3.8.5**.
2. Scaricare il pacchetto dello script di aggiornamento: cercare **&quot;Pacchetto di aggiornamento della soluzione XML Documentation 4.0&quot;** nel portale di distribuzione software Adobe (download di `.zip`).
3. Carica il pacchetto in AEM tramite **Gestione pacchetti** e installalo.
4. Dopo aver installato il pacchetto di aggiornamento, eseguire gli script nell&#39;ordine descritto di seguito.

**Verifica API compatibilità aggiornamento**

Questa API è progettata per valutare lo stato corrente del sistema e segnalare se l’aggiornamento è possibile o meno. Per eseguire questo script, attiva il seguente endpoint specificato:

| Punto finale | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Tipo di richiesta | **GET** <br> **Nota**: è possibile utilizzare un browser Web, in cui è stato effettuato l&#39;accesso all&#39;istanza di AEM come amministratore. |
| Risposta prevista | -   Nel caso in cui tutti i nodi richiesti possano essere spostati, riceverai un controllo superato. <br>-   Se nella posizione di destinazione è presente un nodo, viene visualizzato un errore rilevante. Pulisci l’archivio \(elimina nodo /var/dxml\) e reinstalla il pacchetto di aggiornamento, quindi attiva di nuovo questo endpoint. <br>**Nota:** non si tratta di un errore comune in quanto il percorso di destinazione non è stato utilizzato in precedenza da Experience Manager Guides 3.x. <br> -   Se questo script non riesce, non procedere e segnalalo al team di successo del cliente. |

**API di migrazione dati di sistema**

Questa API è progettata per migrare i dati di sistema come indicato nella sezione **Mappatura migrazione**.

1. Non eseguire questo script se l’API Verifica compatibilità aggiornamento non riesce \(non procedere\).
1. Una volta che l’API di verifica compatibilità dell’aggiornamento restituisce il risultato positivo, puoi eseguire lo script di aggiornamento.

| Punto finale | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Tipo di richiesta | **POST** <br>**Nota**: questo script è una richiesta POST, quindi deve essere eseguito tramite agenti come Postman. |
| Risposta prevista | -   Una volta completata la migrazione, è possibile installare la soluzione XML Documentation versione 4.0.<br>-   In caso di errori, ripristina l’ultimo punto di controllo e condividi i registri degli errori con l’output API al team di successo del cliente. |


**Mappatura migrazione**

Questa API migra tutti i dati nel percorso di origine al percorso di destinazione.

| Origine | Target |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

### Installa versione 4.0

1. Installa la versione 4.0 solo se i passaggi di aggiornamento hanno avuto esito positivo.
1. Scarica il pacchetto di versione 4.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html):

   - Se utilizzi la versione UUID del software, cerca la soluzione &quot;4.0 UUID Release for XML Documentation per AEM 6.5&quot;.
   - Se utilizzi una versione del software non UUID, cerca la soluzione &quot;4.0 Non-UUID Release for XML Documentation per AEM 6.5&quot;.
Carica il pacchetto nell&#39;istanza del server AEM esistente\(s\) utilizzando Gestione pacchetti CRX e installalo.

     >[!NOTE]
     >
     > Attendere l&#39;avvio di tutti i componenti di sistema.

1. Cancella la cache del browser dopo l’installazione del pacchetto.
1. Se un dispatcher è configurato nell’istanza di AEM Author, effettua le seguenti operazioni:
   - Assicurati che nelle regole del dispatcher vengano gestiti i seguenti elementi:
   - Il pattern URL /home/users/\*/preferences è inserito nella whitelist.
   - Il modello URL /libs/cq/security/userinfo.json non è memorizzato nella cache.
1. Cancella cache del dispatcher \(per cancellare qualsiasi `clientlibs` memorizzato nella cache\).

## Aggiornamento alla versione 4.2

È possibile eseguire direttamente l&#39;aggiornamento alla versione **4.2** se si utilizza la versione **4.0**, **4.1** o **4.1.x**.

### Prima di installare la versione 4.2

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.2, assicurati di disporre di:

1. Aggiornamento a Experience Manager Guides **4.0**, **4.1** o **4.1.x**.
2. Ha chiuso tutte le attività di traduzione.
3. Impostare il livello di log su `INFO` per `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e registrare in un nuovo file di log (ad esempio, `logs/translation_upgrade.log`).

   >[!NOTE]
   > 
   > Chiudere tutte le recensioni attive. Se le revisioni non vengono chiuse durante l’aggiornamento alla versione 4.2, le precedenti attività di revisione in corso possono continuare ad aprire le pagine di revisione precedenti; le nuove attività di revisione create dopo l’aggiornamento visualizzano gli aggiornamenti delle funzionalità più recenti.

### Installare la versione 4.2

1. Scarica il pacchetto **4.2** da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
2. Installa il pacchetto 4.2.
3. Dopo l’installazione, attendi il seguente messaggio nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutte le fasi di installazione sono state completate.

   Se riscontri uno dei seguenti errori, segnalali al Customer Success:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`

4. (Facoltativo) Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione 4.2.
5. Cancella la cache del browser dopo l’installazione del pacchetto.
6. Continua ad aggiornare le personalizzazioni come descritto nella sezione successiva.

### Dopo l’installazione della versione 4.2

>[!IMPORTANT]
>
> Il modello Hi-tech non viene visualizzato sul server aggiornato. Per includere il modello hi-tech nel server è possibile copiarlo: Source: `/libs/fmdita/pdf/Hi-Tech` Destinazione: `/content/dam/dita-templates/pdf`.

Quindi procedere con le attività condivise post-aggiornamento in [Attività comuni post-aggiornamento (tutte le versioni)](#common-postupgrade-tasks-all-versions).

## Aggiornamento alla versione 4.2.1

>[!TIP]
>
> È consigliabile installare **Hotfix4.2.1.3** oltre alla versione **4.2.1**.

È possibile eseguire direttamente l&#39;aggiornamento alla versione **4.2.1** se si utilizza **4.1**, **4.1.x** o **4.2**.

>[!NOTE]
>
> La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Avviare l&#39;aggiornamento durante le ore non di punta.

### Prima di installare la versione 4.2.1

1. Esegui l&#39;aggiornamento a Experience Manager Guides **4.1**, **4.1.x** o **4.2**.
2. Chiude tutte le attività di traduzione.
3. Impostare il livello di log su `INFO` per `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e registrare in un nuovo file (ad esempio, `logs/translation_upgrade.log`).

>[!NOTE]
>
> È necessario chiudere tutte le recensioni attive (stesso comportamento come 4.2).

### Installare la versione 4.2.1

1. Scarica il pacchetto **4.2.1** da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
2. Installa il pacchetto 4.2.1.
3. Facoltativamente, attiva il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet).

4. Dopo l&#39;installazione, attendere: `Completed the post deployment setup script` nei registri.

   Segnala questi errori al Customer Success:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Facoltativo) Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione **4.2**
6. Cancella la cache del browser.
7. Continua con [Attività comuni post-aggiornamento (tutte le versioni)](#common-postupgrade-tasks-all-versions).

### Dopo l’installazione della versione 4.2.1

>[!IMPORTANT]
>
> Il modello Hi-tech non viene visualizzato sul server aggiornato. Per includere il modello hi-tech nel server è possibile copiarlo: Source: `/libs/fmdita/pdf/Hi-Tech` Destinazione: `/content/dam/dita-templates/pdf`.

Procedi con [Attività comuni post-aggiornamento (tutte le versioni)](#common-postupgrade-tasks-all-versions) e (se necessario) [Indicizza il contenuto esistente per trovare e sostituire la mappa](#index-existing-content-for-map-find-and-replace).


## Aggiornamento alla versione 4.3.0

L’aggiornamento alla versione 4.3.0 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi la versione 4.2 o 4.2.x, puoi eseguire direttamente l’aggiornamento alla versione 4.3.0.

>[!NOTE]
>
>La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

### Prima di installare la versione 4.3.0

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.3.0, assicurati di disporre di:

1. Aggiornato a Experience Manager Guides versione 4.2 o 4.2.x e completato il rispettivo passaggio di installazione.
1. Ha chiuso tutte le attività di traduzione.

### Installare la versione 4.3.0

1. Scarica il pacchetto di versione 4.3.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 4.3.0 del pacchetto.
1. Cancella la cache del browser dopo l’installazione del pacchetto.
1. Aggiornare il file `ui_config.json` dalla scheda **Configurazione editor XML** nel Profilo cartella.

### Dopo l’installazione della versione 4.3.0

Procedi con:

- [Attività comuni post-aggiornamento (tutte le versioni)](#common-postupgrade-tasks-all-versions)
- Se applicabile: [Pubblica il contenuto esistente per il report dei collegamenti interrotti](#post-process-existing-content-for-broken-link-report)

## Aggiornamento alla versione 4.3.1

L’aggiornamento alla versione 4.3.1 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi le versioni 4.3.0, 4.2 o 4.2.1, puoi eseguire direttamente l’aggiornamento alla versione 4.3.1.

>[!NOTE]
>
>La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

### Prima di installare la versione 4.3.1

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.3.1, assicurati di disporre di:

1. Aggiornato a Experience Manager Guides versione 4.3.0, 4.2 o 4.2.1 e completato il rispettivo passaggio di installazione.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.

### Installare la versione 4.3.1

1. Scarica il pacchetto di versione 4.3.1 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 4.3.1 del pacchetto.
1. Facoltativamente, attiva il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet).
1. Dopo l&#39;installazione, attendere: `Completed the post deployment setup script` nei registri.
Segnala questi errori al Customer Success:\
   `Error in post deployment setup script`, `Exception while porting the translation MAP`, `Unable to port translation map from v1 to v2 for property`
1. (Facoltativo) Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione **4.2**.
1. Cancella la cache del browser.

### Dopo l’installazione della versione 4.3.1

Procedi con:

- [Attività comuni post-aggiornamento (tutte le versioni)](#common-postupgrade-tasks-all-versions)
- Se applicabile: [Indicizzare il contenuto esistente per trovare e sostituire la mappa](#index-existing-content-for-map-find-and-replace)
- Se applicabile: [Pubblica il contenuto esistente per il report dei collegamenti interrotti](#post-process-existing-content-for-broken-link-report)


## Aggiorna alla versione 4.3.1.5

È possibile eseguire l&#39;aggiornamento a **4.3.1.5** direttamente se si utilizza la versione **4.3.1**.

### Installa versione 4.3.1.5

1. Scarica il pacchetto **4.3.1.5** da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
2. Installa il pacchetto 4.3.1.5.
3. Attendere il completamento del processo di installazione.
4. Continua ad aggiornare le personalizzazioni come descritto nella sezione successiva.

## Dopo l&#39;installazione della versione 4.3.1.5

>[!NOTE]
>
>Se desideri utilizzare il bundle org.apache.velocity, esegui i seguenti passaggi prima di caricare il bundle:
> 1. Vai a `<server>:<port>/system/console/bundles`
> 1. Cerca org.apache.velocity.
> 1. Disinstalla il bundle cercato.
> 1. Installa il bundle Velocity richiesto.

1. Al termine dell’aggiornamento, accertati che le personalizzazioni/sovrapposizioni siano convalidate e aggiornate in modo che corrispondano al nuovo codice dell’applicazione. Di seguito sono riportati alcuni esempi:
   - Tutti i componenti sovrapposti da `/libs/fmdita` o ` /libs` devono essere confrontati con il nuovo codice prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in `/apps`.
   - Tutte le categorie clientlib utilizzate dal prodotto, devono essere riviste per eventuali modifiche. Eventuali configurazioni sostituite \(esempi di seguito\) devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - `elementmapping.xml`
   - `ui\_config.json\` (potrebbe essere stato impostato nei profili cartella\)
   - ha modificato `com.adobe.fmdita.config.ConfigManager`


## Aggiornamento alla versione 4.4.0

È possibile eseguire l&#39;aggiornamento a **4.4.0** direttamente se si utilizza: **4.3.1**, **4.3.0**, **4.2** o **4.2.1 (Hotfix 4.2.1.3)**.

>[!NOTE]
>
>La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

### Prima di installare la versione 4.4.0

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.4.0, assicurati di disporre di:

1. Aggiornamento a Experience Manager Guides versione 4.3.1, 4.3.0 o 4.2.1 (Hotfix 4.2.1.3) e completamento del rispettivo passaggio di installazione.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.

### Installare la versione 4.4.0

1. Scarica il pacchetto di versione 4.4.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
2. Installa il pacchetto 4.4.0.
3. Facoltativamente, attiva il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet).
4. Dopo aver completato l’installazione del pacchetto, attendi il seguente messaggio nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutti i passaggi dell&#39;installazione sono stati completati.

   Se riscontri uno dei seguenti prefissi ERROR, segnalali al team di successo del cliente:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Facoltativo) Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione **4.4.0**.
6. Cancella la cache del browser.
7. Continua con:

   - [Attività comuni post-aggiornamento (tutte le versioni)](#common-ppostupgrade-tasks-all-versions)
   - [Indicizza il contenuto esistente per trovare e sostituire la mappa](#index-existing-content-for-map-find-and-replace) (solo se applicabile)
   - [Contenuto esistente post-elaborazione per report collegamenti interrotti](#post-process-existing-content-for-broken-link-report) (solo se applicabile)
   - [Aggiornamento mappa di traduzione (trigger servlet)](#translation-map-upgrade-servlet-trigger) (solo se applicabile)


## Attività comuni post-aggiornamento (tutte le versioni)

Dopo aver installato Experience Manager Guides, potrebbe essere necessario unire le configurazioni applicabili dalla versione appena installata alla configurazione.

>[!NOTE]
>
> È possibile personalizzare il modello di flusso di lavoro **Risorsa di aggiornamento DAM**. Se disponi di personalizzazioni, sincronizzale con le modifiche di Experience Manager Guides nella copia di lavoro del modello.

### Flusso di lavoro Convalida risorsa di aggiornamento DAM (modifiche di post-elaborazione)

1. Apri l’interfaccia utente dei modelli di flussi di lavoro di AEM (esempio mostrato nell’origine):\
   `http://<host>:4502/libs/cq/workflow/admin/console/content/models.html`
2. Seleziona **Flusso di lavoro Aggiorna risorsa DAM**.
3. Seleziona **Modifica**.
4. Se il componente **DXML Post Process Initiator** è presente, assicurarsi che le personalizzazioni siano sincronizzate.
5. Se il componente è assente, inseriscilo:
   1. Fare clic su **Inserisci componente** (responsabile della post-elaborazione delle guide come passaggio finale).
   2. Configura il **passaggio del processo**:
      **Scheda comune**
- Titolo: `DXML Post Process Initiator`
- Descrizione: `DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset`
      **Scheda Elabora**
- Processo: selezionare `DXML Post Process Initiator`
- Seleziona `Handler Advance`
- Seleziona `Done`
   3. Fai clic su **Sincronizza** in alto a destra dopo aver completato le modifiche. Riceverai una notifica di esito positivo.

>[!NOTE]
>
> Aggiorna e verifica che le modifiche personalizzate e il passaggio di post-elaborazione Experience Manager Guides siano presenti nel modello di flusso di lavoro finale.

### Convalidare le configurazioni del modulo di avvio

1. Vai all&#39;interfaccia di AEM Workflow e apri **Moduli di avvio**.

```http
    http://localhost:4502/libs/cq/workflow/content/console.html
```

1. Trova e apporta le modifiche \(se necessario\) ai seguenti due moduli di avvio \(che dovrebbe essere attivo\) corrispondenti al flusso di lavoro **Aggiorna risorsa DAM**:

1. Modulo di avvio per &quot;*Nodo creato*&quot; per **Flusso di lavoro Aggiorna risorsa DAM**- per la condizione `"jcr:content/jcr:mimeType!=video"`, il valore &#39;Globbing&#39; deve essere:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` deve avere `"event-user-data:changedByWorkflowProcess"`.
   - Modulo di avvio per *Nodo modificato* per **Flusso di lavoro Aggiorna risorsa DAM -** per la condizione &quot;`jcr:content/jcr:mimeType!=video`&quot;, il valore &#39;Globbing&#39; deve essere:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` deve avere `"event-user-data:changedByWorkflowProcess"`.

### Convalidare sovrapposizioni e personalizzazioni

Al termine dell’aggiornamento:

1. Al termine dell’aggiornamento, accertati che le personalizzazioni/sovrapposizioni siano convalidate e aggiornate in modo che corrispondano al nuovo codice dell’applicazione. Di seguito sono riportati alcuni esempi:
   - Tutti i componenti sovrapposti da/libs/fmditaor/libssdevono essere confrontati con il nuovo codice del prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in/apps.
   - Tutte le categorie clientlib utilizzate dal prodotto, devono essere riviste per eventuali modifiche. Eventuali configurazioni sostituite \(esempi di seguito\) devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - elementmapping.xml
   - ui\_config.json\(potrebbe essere stato impostato in profili cartella\)
   - ha modificato `com.adobe.fmdita.config.ConfigManager`

1. Se hai aggiunto delle personalizzazioni in damAssetLucene, potresti dover applicarle nuovamente. Dopo aver apportato tali modifiche, imposta la reindicizzazione su true. In questo modo tutti i nodi esistenti verranno reindicizzati con le personalizzazioni. Al termine, il flag di reindicizzazione verrà impostato di nuovo su false. Questa operazione può richiedere alcune ore a seconda del numero di risorse nel sistema.

## Indicizza il contenuto esistente per trovare e sostituire la mappa

Questa sezione consolida la procedura di **indicizzazione** ripetuta utilizzata per abilitare le nuove funzionalità di ricerca e sostituzione a livello di **mappa**.

**Quando puoi saltare l&#39;indicizzazione**

L’origine include note di salto a seconda del percorso di aggiornamento (ad esempio, &quot;Non è necessario eseguire questi passaggi se esegui l’aggiornamento da 4.3.0 o 4.3.1&quot; e note simili). Segui la nota di salto riportata nella sezione relativa all’aggiornamento.

Effettua le seguenti operazioni per indicizzare il contenuto esistente e utilizzare il nuovo testo Trova e sostituisci a livello di mappa:

1. Eseguire una richiesta POST (con autenticazione):

```http
POST http://<server:port>/bin/guides/map-find/indexing
```

Parametri opzionali supportati nell’origine:

- Indicizza percorsi mappa specifici (per impostazione predefinita, indicizza tutte le mappe):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>
  ```

- Indicizzare le mappe DITA in una cartella principale (e relative sottocartelle):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test
  ```

  >[!NOTE]
  >
  > Se vengono passati sia `paths` che `root`, verrà considerato solo `paths`.

1. L&#39;API restituisce un `jobId`. Per verificare lo stato, invia una richiesta GET:

   ```http
   GET http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}
   ```

   Comportamento di completamento previsto:

   - Al termine, GET risponde con successo e indica se eventuali mappe non sono riuscite.
   - Conferma l’indicizzazione delle mappe nei registri del server.

### Assicurati che l’indicizzazione damAssetLucene sia completa (se applicabile)

L&#39;origine nota che l&#39;indicizzazione damAssetLucene può richiedere ore a seconda della dimensione dei dati. È possibile confermare il completamento quando `reindex` è `false` in:

`http://<server:port>/oak:index/damAssetLucene`

Se sono state aggiunte personalizzazioni in `damAssetLucene`, potrebbe essere necessario applicarle nuovamente al termine della reindicizzazione.

### Soluzione alternativa per &quot;leggere o scorrere più di 100000 nodi&quot; (se il processo non riesce)

Se il processo di indicizzazione non riesce e viene visualizzato un errore:

&quot;La query ha letto o attraversato più di 100000 nodi. Per evitare di influenzare altre attività, l’elaborazione è stata interrotta.&quot;

Prova questa soluzione alternativa dall’origine:

1. Nell&#39;indice OAK `damAssetLucene`, aggiungere la proprietà booleana `indexNodeName=true` in `/oak:index/damAssetLucene/indexRules/dam:Asset`.
2. Aggiungere un nuovo nodo denominato `excerpt` in `/oak:index/damAssetLucene/indexRules/dam:Asset/properties` e impostare le proprietà come mostrato nell&#39;origine:
   - `name=rep:excerpt`
   - `propertyIndex=true`
   - `notNullCheckEnabled=true`
3. Reindicizzare `damAssetLucene` impostando `reindex=true` e attendere che diventi di nuovo `false` (potrebbero essere necessarie ore).
4. Esegui nuovamente lo script di indicizzazione (ripeti il POST e il tracciamento del processo).

## Post-elabora contenuto esistente per report collegamento interrotto

Questa sezione consolida la **procedura di post-elaborazione** ripetuta utilizzata per abilitare il **report dei collegamenti interrotti**.

**Quando puoi saltare la post-elaborazione**

L’origine include note di salto a seconda del percorso di aggiornamento (ad esempio, &quot;Non è necessario eseguire questi passaggi se si esegue l’aggiornamento da 4.3.0&quot; o &quot;da 4.3.0 o 4.3.1&quot;). Segui la nota di salto riportata nella sezione relativa all’aggiornamento.

Per abilitare il rapporto sui collegamenti interrotti, effettua le seguenti operazioni:

1. (Facoltativo) Aumenta queryLimitReads di Oak per archivi di grandi dimensioni

   Se sono presenti più di **100.000 file DITA**, aggiornare `queryLimitReads` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valore maggiore del numero di risorse (ad esempio: `200000`), ridistribuire e continuare.

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Valore: 200000 <br> Valore predefinito: 100000 |

1. Esegui le seguenti API per eseguire la post-elaborazione su tutti i file:

   | Punto finale | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo di richiesta | **POST** Questo script è una richiesta POST, quindi deve essere eseguito tramite agenti come Postman. |
   | Risposta prevista | L’API restituirà un jobId. Per verificare lo stato del processo, puoi inviare una richiesta GET con ID processo allo stesso endpoint.<br> URL di esempio: `http://<server:port>/bin/guides/reports/upgrade` |

   | Punto finale | /bin/guides/reports/upgrade |
   |---|---|
   | Tipo di richiesta | **GET** |
   | Parametro | jobId: passa il jobId ricevuto dalla richiesta post precedente. |
   | Risposta prevista | - Una volta completato il processo, la richiesta GET risponde con successo. <br> - In caso di errori, condividi i registri degli errori con il tuo team Customer Success insieme all&#39;output API.  <br>URL di esempio: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Ripristinare il valore predefinito o esistente precedente di `queryLimitReads` se è stato modificato nel passaggio 1.

## Abilitare l’attivazione dello script tramite un servlet

Diverse versioni includono un passaggio facoltativo per attivare un processo di aggiornamento della mappa di traduzione tramite un servlet. Questa sezione consolida la procedura ripetuta e include tutti i dettagli forniti nella sorgente.


>[!NOTE]
>
> Non è necessario eseguire questi passaggi se si esegue l’aggiornamento da 4.3.0 o 4.3.1.

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

Nella risposta JSON precedente, la chiave `lockNodePath` contiene il percorso del nodo creato nell&#39;archivio che punta al processo inviato. Verrà eliminato automaticamente una volta completato il processo; fino ad allora, puoi fare riferimento a questo nodo per lo stato corrente del processo.

Cercare `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` e `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` prima di procedere ai passaggi successivi.

>[!NOTE]
>
> Verifica se il nodo è ancora presente e lo stato del processo.

**GET**: `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`


### Passaggi per gestire il conflitto &#39;fmdita rewriter&#39;

Experience Manager Guides include un modulo del rewriter Sling personalizzato (`fmditarewriter`) per la gestione dei collegamenti generati per il collegamento tra mappe.

Se nel codebase hai un altro rewriter Sling personalizzato:

- Utilizzare un valore `order` **maggiore di 50** perché le guide utilizzano `order=50`.
- Durante l&#39;aggiornamento, il valore `order` cambia da `1000` a `50`, pertanto è necessario unire l&#39;eventuale rewriter personalizzato esistente con `fmditarewriter`.

