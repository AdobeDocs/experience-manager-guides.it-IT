---
title: Aggiornare Adobe Experience Manager Guides
description: Scopri come aggiornare Adobe Experience Manager Guides
exl-id: f058b39f-7408-4874-942b-693e133886cf
feature: Installation
role: Admin
level: Experienced
source-git-commit: a29c27a263a3e06e041ffb5e81892449e64323a3
workflow-type: tm+mt
source-wordcount: '9124'
ht-degree: 0%

---

# Aggiornare Adobe Experience Manager Guides {#id224MBE0M0XA}

>[!NOTE]
>
> Segui le istruzioni di aggiornamento specifiche per la versione con licenza del tuo prodotto.

Puoi aggiornare la versione corrente di Experience Manager Guides alla versione 5.1.0:

- Se utilizzi le versioni 4.6.3, 4.6.4, 5.0.0, 5.0.0 Service Pack 1 o 5.0.0 Service Pack 2, puoi eseguire direttamente l’aggiornamento alla versione 5.1.0.
- Se utilizzi le versioni 4.6.0, 4.6.1, devi effettuare l’aggiornamento alla versione 4.6.3, 4.6.4 o 5.0.0 prima di eseguire l’aggiornamento alla versione 5.1.0.
- Se utilizzi le versioni 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 o 4.1.x, devi effettuare l’aggiornamento alla versione 4.4 prima di eseguire l’aggiornamento alla versione 5.0.0.
- Se utilizzi la versione 4.0, devi effettuare l’aggiornamento alla versione 4.2 prima di passare alla versione 4.3.x.
- Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
- Se utilizzi una versione precedente alla 3.8.5, consulta la sezione Aggiornamento di Experience Manager Guides nella guida all&#39;installazione specifica per il prodotto, disponibile in [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).


>[!NOTE]
>
> È necessario installare AEM Service Pack prima di aggiornare la versione di Experience Manager Guides.

Per ulteriori informazioni, consulta le procedure seguenti:

- [Aggiornamento alla versione 5.1.0](#upgrade-to-version-510)
- [Aggiornamento alla versione 5.0.0](#upgrade-to-version-500)
- [Aggiornamento alla versione 4.6.0](#upgrade-to-version-460)
- [Aggiornamento alla versione 4.4.0](#upgrade-to-version-440)
- [Aggiorna alla versione 4.3.1.5](#upgrade-to-version-4315)
- [Aggiornamento alla versione 4.3.1](#upgrade-to-version-431)
- [Aggiornamento alla versione 4.3.0](#upgrade-to-version-430)
- [Aggiornamento alla versione 4.2.1](#upgrade-to-version-421)
- [Aggiornamento alla versione 4.2](#upgrade-to-version-42)
- [Aggiornamento da 3.8.5 a versione 4.0](#upgrade-from-version-385-to-version-40)


>[!IMPORTANT]
>
> Prima di iniziare l&#39;aggiornamento, eseguire un backup completo del sistema per evitare la perdita di dati.

## Aggiornamento dalla versione 3.8.5 alla versione 4.0

Se utilizzi Experience Manager Guides versione 3.8.5, puoi effettuare l’aggiornamento alla versione 4.0 di Experience Manager Guides. Con la funzione di aggiornamento, non è necessario disinstallare la versione precedente di Experience Manager Guides.

Prima di eseguire il processo è necessario completare alcune attività. Le seguenti sottosezioni ti guideranno attraverso i prerequisiti, la generazione di rapporti e il processo di migrazione. Inoltre, dopo aver installato Experience Manager Guides versione 4.0 è possibile personalizzare varie configurazioni, in base alle impostazioni del cliente.

>[!NOTE]
>
> Questo processo di aggiornamento è applicabile solo dalla versione 3.8.5 alla versione 4.0. Per il processo di aggiornamento dalla versione 3.4 o successiva alla versione 3.8.5, fare riferimento alla sezione *Aggiornamento di Experience Manager Guides* nella guida all&#39;installazione specifica del prodotto disponibile nell&#39;archivio di PDF della Guida di Adobe Experience Manager Guides [&#128279;](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).



**&#x200B;**&#x200B;Prerequisiti&#x200B;**&#x200B;**

Prima di avviare il processo di aggiornamento di Experience Manager Guides, verificare di disporre di:

1. Importazione dei commenti di revisione negli argomenti aperti per la revisione.
1. Chiuse tutte le recensioni attive.
1. Ha chiuso tutte le attività di traduzione.
1. Disinstalla eventuali aggiornamenti rapidi di Experience Manager Guides installati nella parte superiore della versione precedente \(principale o patch\) di Experience Manager Guides.

**Prima di installare la versione 4.0**

Prima di installare la versione 4.0, effettuare le seguenti operazioni:

1. A questo punto, assicurati che Experience Manager Guides sia nella versione 3.8.5.
1. Scarica il pacchetto dello script di aggiornamento. Per eseguire questa operazione, cercare &quot;Pacchetto di aggiornamento della soluzione XML Documentation 4.0&quot; nel [portale di distribuzione software Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html) che scaricherà un file zip.
1. Carica questo pacchetto in AEM tramite Gestione pacchetti e installa il pacchetto.
1. Una volta installato il pacchetto di aggiornamento, esegui i seguenti script specificati nello stesso ordine e segui le istruzioni fornite:

**Verifica API compatibilità aggiornamento**

Questa API è progettata per valutare lo stato corrente del sistema e segnalare se l’aggiornamento è possibile o meno. Per eseguire questo script, attiva il seguente endpoint specificato:

| Punto finale | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Tipo di richiesta | **GET** Puoi utilizzare un browser Web, in cui hai effettuato l&#39;accesso all&#39;istanza AEM come amministratore. |
| Risposta prevista | -   Nel caso in cui tutti i nodi richiesti possano essere spostati, riceverai un controllo superato. <br>-   Se nella posizione di destinazione è presente un nodo, viene visualizzato un errore rilevante. Pulisci l’archivio \(elimina nodo /var/dxml\) e reinstalla il pacchetto di aggiornamento, quindi attiva di nuovo questo endpoint. <br>**Nota:** non si tratta di un errore comune in quanto il percorso di destinazione non è stato utilizzato in precedenza da Experience Manager Guides 3.x. <br> -   Se questo script non riesce, non procedere e segnalalo al team di successo del cliente. |

**API di migrazione dati di sistema**

Questa API è progettata per migrare i dati di sistema come indicato nella sezione **Mappatura migrazione**.

1. Non eseguire questo script se l’API Verifica compatibilità aggiornamento non riesce \(non procedere\).
1. Una volta che l’API di verifica compatibilità dell’aggiornamento restituisce il risultato positivo, puoi eseguire lo script di aggiornamento.

| Punto finale | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Tipo di richiesta | **POST** Questo script è una richiesta POST, quindi deve essere eseguito tramite agenti come Postman. |
| Risposta prevista | -   Una volta completata la migrazione, è possibile installare la soluzione XML Documentation versione 4.0.<br>-   In caso di errori, ripristina l’ultimo punto di controllo e condividi i registri degli errori con l’output API al team di successo del cliente. |

**Mappatura migrazione**: l&#39;API precedente esegue la migrazione di tutti i dati nel percorso di origine nel percorso di destinazione.

| Origine | Target |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Installa versione 4.0 {#id23598G006XA}

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

L’aggiornamento alla versione 4.2 dipende dalla versione corrente di Experience Manager Guides.

Se utilizzi le versioni 4.0, 4.1 o 4.1.x, puoi eseguire direttamente l’aggiornamento alla versione 4.2.

**&#x200B;**&#x200B;Prerequisiti&#x200B;**&#x200B;**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.2, assicurati di disporre di:

1. Aggiornato a Experience Manager Guides versione 4.0, 4.1 o 4.1.x.
1. Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log.`

>[!NOTE]
>
> Chiudere tutte le recensioni attive. Se le attività di revisione non vengono chiuse durante l’aggiornamento alla versione 4.2, le precedenti attività di revisione in corso continuano a coinvolgere gli utenti nelle pagine di revisione precedenti e le attività di revisione create dopo l’aggiornamento visualizzano gli ultimi aggiornamenti della funzionalità.

## Installare la versione 4.2 {#id2245IK0E0EV}

1. Scarica il pacchetto di versione 4.2 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 4.2 del pacchetto.
1. Dopo aver completato l’installazione del pacchetto, attendi i seguenti messaggi\(s\) nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutti i passaggi dell&#39;installazione sono stati completati.

   Se riscontri uno dei seguenti prefissi ERROR, segnalali al team di successo del cliente:

   - Errore nello script di installazione post-distribuzione
   - Eccezione durante il porting del MAP di traduzione
   - Impossibile trasferire la mappa di traduzione dalla versione 1 alla versione 2 per la proprietà
1. Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione 4.2 (se necessario).
1. Cancella la cache del browser dopo l’installazione del pacchetto.
1. Continua ad aggiornare le personalizzazioni come descritto nella sezione successiva.

## Dopo aver installato la versione 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> Il modello Hi-tech non viene visualizzato sul server aggiornato. Per includere il modello hi-tech sul tuo server puoi copiarlo: Source: /libs/fmdita/pdf/Hi-Tech Destinazione: /content/dam/dita-templates/pdf

Dopo aver installato Experience Manager Guides, è possibile unire le varie configurazioni applicabili dalla versione appena installata alla configurazione.

>[!NOTE]
>
> Il modello dam-update-asset può essere personalizzato. Pertanto, se sono state apportate personalizzazioni, è necessario sincronizzare le personalizzazioni e Experience Manager Guides nella copia di lavoro del modello.

1. **Flusso di lavoro Aggiorna risorsa DAM \(Modifiche post-elaborazione\):**

1. Apri URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Seleziona **Flusso di lavoro Aggiorna risorsa DAM**.
1. Fai clic su **Modifica**.
1. Se il componente **DXML Post Process Initiator** è presente, verificare che le personalizzazioni siano sincronizzate.
1. Se il componente **DXML Post Process Initiator** è assente, eseguire la procedura seguente per inserirlo:

1. Fare clic su **Inserisci componente** \(Responsabile della post-elaborazione di Experience Manager Guides come fase finale del processo\).
1. Configura il **passaggio del processo** con i dettagli seguenti:

   **Scheda comune**

   **Titolo:** iniziatore post-elaborazione DXML

   **Descrizione**: passaggio iniziatore post-elaborazione DXML che attiverà un processo sling per la post-elaborazione DXML della risorsa modificata/creata

   **Scheda Elabora**

   - Seleziona **DXML Post Process Initiator** dal menu a discesa **Process**

   - Seleziona **Avanzamento gestore**

   - Seleziona **Fine**

1. Fai clic su **Sincronizza** in alto a destra dopo aver completato le modifiche. Riceverai una notifica di esito positivo.

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
   - Modulo di avvio per &quot;*Node Modified*&quot; per **Flusso di lavoro Aggiorna risorsa DAM -** per la condizione &quot;`jcr:content/jcr:mimeType!=video`&quot;,
   - il valore &#39;Globbing&#39; deve essere:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; deve avere `"event-user-data:changedByWorkflowProcess"`.
1. Al termine dell’aggiornamento, accertati che le personalizzazioni/sovrapposizioni siano convalidate e aggiornate in modo che corrispondano al nuovo codice dell’applicazione. Di seguito sono riportati alcuni esempi:
   - Tutti i componenti sovrapposti da/libs/fmditaor/libssdevono essere confrontati con il nuovo codice del prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in/apps.
   - Tutte le categorie clientlib utilizzate dal prodotto, devono essere riviste per eventuali modifiche. Eventuali configurazioni sostituite \(esempi di seguito\) devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - elementmapping.xml
   - ui\_config.json\(potrebbe essere stato impostato in profili cartella\)
   - ha modificato `com.adobe.fmdita.config.ConfigManager`
   - Verifica se uno dei codici personalizzati utilizzava percorsi precedenti \(come indicato nella sezione [Mappatura migrazione](#id2244LE040XA)\) - deve essere aggiornato ai nuovi percorsi in modo che anche le personalizzazioni funzionino come previsto.
1. Leggi le informazioni sulle nuove configurazioni introdotte nella versione corrente \(controlla [Note sulla versione](../release-info/release-notes-4-3.md)\) e scopri se sono interessate eventuali funzionalità, quindi adotta le misure appropriate. Un esempio potrebbe essere quello di utilizzare &quot;Gestione migliorata dei file e delle versioni&quot; introdotta nella versione 4.0, per la quale è necessario abilitare una configurazione.

## Passaggi per indicizzare il contenuto esistente per utilizzare la nuova funzione Trova e sostituisci:

Effettua le seguenti operazioni per indicizzare il contenuto esistente e utilizzare il nuovo testo Trova e sostituisci a livello di mappa:

- Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Facoltativo: È possibile passare percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate \|\| Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- L’API restituirà un jobId. Per verificare lo stato del processo, puoi inviare una richiesta GET con ID processo allo stesso endpoint:

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

Se il processo di aggiornamento non riesce e il registro degli errori mostra il seguente errore:

&quot;La *query* ha letto o attraversato più di *100000 nodi*. Per evitare di influenzare altre attività, l’elaborazione è stata interrotta.&quot;

Ciò potrebbe verificarsi perché l’indice non è configurato correttamente per la query utilizzata nell’aggiornamento. È possibile provare la seguente soluzione alternativa:

1. Nell&#39;indice oak damAssetLucene aggiungere la proprietà booleana `indexNodeName` come `true` nel nodo.
   `/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Aggiungi un nuovo nodo con il nome estratto sotto il nodo.

   `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
e imposta le seguenti proprietà nel nodo:

   ```
   name - rep:excerpt
   propertyIndex - {Boolean}true
   notNullCheckEnabled - {Boolean}true
   ```

   La struttura di `damAssetLucene` deve essere simile a:

   ```
   <damAssetLucene compatVersion="{Long}2" async="async, nrt" jcr:primaryType="oak:QueryIndexDefinition" evaluatePathRestrictions="{Boolean}true" type="lucene">
   <indexRules jcr:primaryType="nt:unstructured">
     <dam:Asset indexNodeName="{Boolean}true" jcr:primaryType="nt:unstructured">
       <properties jcr:primaryType="nt:unstructured">
         <excerpt name="rep:excerpt" propertyIndex="{Boolean}true" jcr:primaryType="nt:unstructured" notNullCheckEnabled="{Boolean}true"/>
       </properties>
       </dam:Asset>
     </indexRules>
   </damAssetLucene>    
   ```


   (insieme ad altri nodi e proprietà esistenti)

1. Reindicizzare l&#39;indice `damAssetLucene` (impostando il flag di reindicizzazione come `true` in
e attendi che sia di nuovo `false` (questo indica che la reindicizzazione è completa). Tieni presente che potrebbero essere necessarie alcune ore a seconda delle dimensioni dell’indice.
1. Esegui nuovamente lo script di indicizzazione eseguendo i passaggi precedenti.


## Aggiornamento alla versione 4.2.1

>[!TIP]
>
>Si consiglia di installare l&#39;Hotfix 4.2.1.3 oltre alla versione 4.2.1.

L’aggiornamento alla versione 4.2.1 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi le versioni 4.1 o 4.1.x o 4.2, puoi eseguire direttamente l’aggiornamento alla versione 4.2.1.

>[!NOTE]
>
>La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

**&#x200B;**&#x200B;Prerequisiti&#x200B;**&#x200B;**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.2.1, assicurati di disporre di:

1. Aggiornamento a Experience Manager Guides versione 4.1, 4.1.x o 4.2.
1. Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log.`

>[!NOTE]
>
> Chiudere tutte le recensioni attive. Se le attività di revisione non vengono chiuse durante l’aggiornamento alla versione 4.2, le precedenti attività di revisione in corso continuano a coinvolgere gli utenti nelle pagine di revisione precedenti e le attività di revisione create dopo l’aggiornamento visualizzano gli ultimi aggiornamenti della funzionalità.

## Installare la versione 4.2.1

1. Scarica il pacchetto di versione 4.2.1 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 4.2.1 del pacchetto.
1. Puoi scegliere di premere il trigger per avviare il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet-for-421).


1. Dopo aver completato l’installazione del pacchetto, attendi i seguenti messaggi\(s\) nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutti i passaggi dell&#39;installazione sono stati completati.

   Se riscontri uno dei seguenti prefissi ERROR, segnalali al team di successo del cliente:

   - Errore nello script di installazione post-distribuzione
   - Eccezione durante il porting del MAP di traduzione
   - Impossibile trasferire la mappa di traduzione dalla versione 1 alla versione 2 per la proprietà
1. Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione 4.2 (se necessario).
1. Cancella la cache del browser dopo l’installazione del pacchetto.
1. Continua ad aggiornare le personalizzazioni come descritto nella sezione successiva.

### Abilitare l’attivazione dello script tramite un servlet (per 4.2.1)

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

Registro di esempio:
Di seguito è riportato un esempio di registri che verranno visualizzati nel file di registro dopo l&#39;attivazione dello script.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Cercare `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` e `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` prima di procedere ai passaggi successivi.



## Dopo aver installato la versione 4.2.1

>[!IMPORTANT]
>
> Il modello Hi-tech non viene visualizzato sul server aggiornato. Per includere il modello hi-tech sul tuo server puoi copiarlo: Source: /libs/fmdita/pdf/Hi-Tech Destinazione: /content/dam/dita-templates/pdf

Dopo aver installato Experience Manager Guides, è possibile unire le varie configurazioni applicabili dalla versione appena installata alla configurazione.

>[!NOTE]
>
> Il modello dam-update-asset può essere personalizzato. Pertanto, se sono state apportate personalizzazioni, è necessario sincronizzare le personalizzazioni e Experience Manager Guides nella copia di lavoro del modello.

1. **Flusso di lavoro Aggiorna risorsa DAM \(Modifiche post-elaborazione\):**

1. Apri URL:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Seleziona **Flusso di lavoro Aggiorna risorsa DAM**.
1. Fai clic su **Modifica**.
1. Se il componente **DXML Post Process Initiator** è presente, verificare che le personalizzazioni siano sincronizzate.
1. Se il componente **DXML Post Process Initiator** è assente, eseguire la procedura seguente per inserirlo:

1. Fare clic su **Inserisci componente** \(Responsabile della post-elaborazione di Experience Manager Guides come fase finale del processo\).
1. Configura il **passaggio del processo** con i dettagli seguenti:

   **Scheda comune**

   **Titolo:** iniziatore post-elaborazione DXML

   **Descrizione**: passaggio iniziatore post-elaborazione DXML che attiverà un processo sling per la post-elaborazione DXML della risorsa modificata/creata

   **Scheda Elabora**

   - Seleziona **DXML Post Process Initiator** dal menu a discesa **Process**

   - Seleziona **Avanzamento gestore**

   - Seleziona **Fine**

1. Fai clic su **Sincronizza** in alto a destra dopo aver completato le modifiche. Riceverai una notifica di esito positivo.

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
   - Tutti i componenti sovrapposti da/libs/fmditaor/libssdevono essere confrontati con il nuovo codice del prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in/apps.
   - Tutte le categorie clientlib utilizzate dal prodotto, devono essere riviste per eventuali modifiche. Eventuali configurazioni sostituite \(esempi di seguito\) devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - elementmapping.xml
   - ui\_config.json\(potrebbe essere stato impostato in profili cartella\)
   - ha modificato `com.adobe.fmdita.config.ConfigManager`
   - Verifica se uno dei codici personalizzati utilizzava percorsi precedenti \(come indicato nella sezione [Mappatura migrazione](#id2244LE040XA)\) - deve essere aggiornato ai nuovi percorsi in modo che anche le personalizzazioni funzionino come previsto.
1. Leggi le informazioni sulle nuove configurazioni introdotte nella versione corrente \(controlla [Note sulla versione](../release-info/release-notes-4-2-1.md)\) e scopri se sono interessate eventuali funzionalità, quindi adotta le misure appropriate. Un esempio potrebbe essere quello di utilizzare &quot;Gestione migliorata dei file e delle versioni&quot; introdotta nella versione 4.0, per la quale è necessario abilitare una configurazione.

## Passaggi per indicizzare il contenuto esistente per utilizzare la nuova funzione Trova e sostituisci:

Effettua le seguenti operazioni per indicizzare il contenuto esistente e utilizzare il nuovo testo Trova e sostituisci a livello di mappa:

- Verificare che l&#39;indicizzazione `damAssetLucene` sia stata completata. Può richiedere alcune ore, a seconda della quantità di dati presenti sul server. Puoi confermare che la reindicizzazione è stata completata verificando che il campo di reindicizzazione sia impostato su false in
  `http://<server:port>/oak:index/damAssetLucene`.  Inoltre, se hai aggiunto delle personalizzazioni in `damAssetLucene`, potrebbe essere necessario applicarle nuovamente.

- Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi passare percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate \|\| Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- È inoltre possibile passare una cartella principale per indicizzare le mappe DITA di una cartella specifica (e delle relative sottocartelle). Ad esempio, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Si noti che se vengono passati sia il parametro paths che il parametro root, viene considerato solo il parametro paths.

- L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.


## Aggiornamento alla versione 4.3.0

L’aggiornamento alla versione 4.3.0 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi la versione 4.2 o 4.2.x, puoi eseguire direttamente l’aggiornamento alla versione 4.3.0.

>[!NOTE]
>
>La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

**&#x200B;**&#x200B;Prerequisiti&#x200B;**&#x200B;**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.3.0, assicurati di disporre di:

1. Aggiornato a Experience Manager Guides versione 4.2 o 4.2.x e completato il rispettivo passaggio di installazione.
1. Ha chiuso tutte le attività di traduzione.



## Installare la versione 4.3.0

1. Scarica il pacchetto di versione 4.3.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 4.3.0 del pacchetto.
1. Cancella la cache del browser dopo l’installazione del pacchetto.
1. Aggiornare il file `ui_config.json` dalla scheda **Configurazione editor XML** nel Profilo cartella.


## Dopo aver installato la versione 4.3.0

Dopo aver installato Experience Manager Guides, è possibile unire le varie configurazioni applicabili dalla versione appena installata alla configurazione.

## Passaggi per pubblicare ed elaborare il contenuto esistente per utilizzare il rapporto sui collegamenti interrotti


Effettua le seguenti operazioni per la post-elaborazione del contenuto esistente e l’utilizzo del nuovo rapporto sui collegamenti interrotti:

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file dita, aggiornare `queryLimitReads` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valore maggiore (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuire.

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



## Aggiornamento alla versione 4.3.1

L’aggiornamento alla versione 4.3.1 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi le versioni 4.3.0, 4.2 o 4.2.1, puoi eseguire direttamente l’aggiornamento alla versione 4.3.1.

>[!NOTE]
>
>La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

**&#x200B;**&#x200B;Prerequisiti&#x200B;**&#x200B;**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.3.1, assicurati di disporre di:

1. Aggiornato a Experience Manager Guides versione 4.3.0, 4.2 o 4.2.1 e completato il rispettivo passaggio di installazione.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.


## Installare la versione 4.3.1

1. Scarica il pacchetto di versione 4.3.1 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 4.3.1 del pacchetto.
1. Puoi scegliere di premere il trigger per avviare il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet-for-431).


1. Dopo aver completato l’installazione del pacchetto, attendi i seguenti messaggi\(s\) nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutti i passaggi dell&#39;installazione sono stati completati.

   Se riscontri uno dei seguenti prefissi ERROR, segnalali al team di successo del cliente:

   - Errore nello script di installazione post-distribuzione
   - Eccezione durante il porting del MAP di traduzione
   - Impossibile trasferire la mappa di traduzione dalla versione 1 alla versione 2 per la proprietà
1. Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione 4.2 (se necessario).
1. Cancella la cache del browser dopo l’installazione del pacchetto.
1. Continua ad aggiornare le personalizzazioni come descritto nella sezione successiva.

### Abilitare l’attivazione dello script tramite un servlet (per 4.3.1)

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

Registro di esempio:
Di seguito è riportato un esempio di registri che verranno visualizzati nel file di registro dopo l&#39;attivazione dello script.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Cercare `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` e `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` prima di procedere ai passaggi successivi.

## Dopo aver installato la versione 4.3.1



Dopo aver installato Experience Manager Guides, è possibile unire le varie configurazioni applicabili dalla versione appena installata alla configurazione.

>[!NOTE]
>
> Il modello dam-update-asset può essere personalizzato. Pertanto, se sono state apportate personalizzazioni, è necessario sincronizzare le personalizzazioni e Experience Manager Guides nella copia di lavoro del modello.

1. **Flusso di lavoro Aggiorna risorsa DAM \(Modifiche post-elaborazione\):**

1. Apri URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleziona **Flusso di lavoro Aggiorna risorsa DAM**.
1. Fai clic su **Modifica**.
1. Se il componente **DXML Post Process Initiator** è presente, verificare che le personalizzazioni siano sincronizzate.
1. Se il componente **DXML Post Process Initiator** è assente, eseguire la procedura seguente per inserirlo:

1. Fare clic su **Inserisci componente** \(Responsabile della post-elaborazione di Experience Manager Guides come fase finale del processo\).
1. Configura il **passaggio del processo** con i dettagli seguenti:

   **Scheda comune**

   **Titolo:** iniziatore post-elaborazione DXML

   **Descrizione**: passaggio iniziatore post-elaborazione DXML che attiverà un processo sling per la post-elaborazione DXML della risorsa modificata/creata

   **Scheda Elabora**

   - Seleziona **DXML Post Process Initiator** dal menu a discesa **Process**

   - Seleziona **Avanzamento gestore**

   - Seleziona **Fine**

1. Fai clic su **Sincronizza** in alto a destra dopo aver completato le modifiche. Riceverai una notifica di esito positivo.

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
   - Tutti i componenti sovrapposti da/libs/fmditaor/libssdevono essere confrontati con il nuovo codice del prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in/apps.
   - Tutte le categorie clientlib utilizzate dal prodotto, devono essere riviste per eventuali modifiche. Eventuali configurazioni sostituite \(esempi di seguito\) devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - elementmapping.xml
   - ui\_config.json\(potrebbe essere stato impostato in profili cartella\)
   - ha modificato `com.adobe.fmdita.config.ConfigManager`


## Passaggi per indicizzare il contenuto esistente

>[!NOTE]
>
> Non è necessario eseguire questi passaggi se si esegue l’aggiornamento da 4.3.0 o 4.2.1.

Effettua le seguenti operazioni per indicizzare il contenuto esistente e utilizzare il nuovo testo Trova e sostituisci a livello di mappa:


- Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi passare percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate \|\| Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Passaggi per pubblicare ed elaborare il contenuto esistente per utilizzare il rapporto sui collegamenti interrotti

>[!NOTE]
>
> Non è necessario eseguire questi passaggi se si esegue l’aggiornamento da 4.3.0

Effettua le seguenti operazioni per la post-elaborazione del contenuto esistente e l’utilizzo del nuovo rapporto sui collegamenti interrotti:

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file dita, aggiornare `queryLimitReads` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valore maggiore (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuire.

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



## Aggiorna alla versione 4.3.1.5

L&#39;aggiornamento alla versione 4.3.1.5 dipende dalla versione corrente di Experience Manager Guides. Se si utilizza la versione 4.3.1, è possibile eseguire direttamente l&#39;aggiornamento alla versione 4.3.1.5.



## Installa versione 4.3.1.5

1. Scarica il pacchetto di versione 4.3.1.5 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione del pacchetto 4.3.1.5.

1. Attendere il completamento del processo di installazione.
1. Continua ad aggiornare le personalizzazioni come descritto nella sezione successiva.


## Dopo aver installato la versione 4.3.1.5


>[!NOTE]
>
>Se desideri utilizzare il bundle org.apache.velocity, esegui i seguenti passaggi prima di caricare il bundle:
> 1. Passa a `<server>:<port>/system/console/bundles`.
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

L’aggiornamento alla versione 4.4.0 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi le versioni 4.3.1, 4.3.0, 4.2 o 4.2.1 (Hotfix 4.2.1.3), puoi eseguire direttamente l’aggiornamento alla versione 4.4.0

>[!NOTE]
>
>La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

**&#x200B;**&#x200B;Prerequisiti&#x200B;**&#x200B;**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.4.0, assicurati di disporre di:

1. Aggiornamento a Experience Manager Guides versione 4.3.1, 4.3.0 o 4.2.1 (Hotfix 4.2.1.3) e completamento del rispettivo passaggio di installazione.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.


## Installare la versione 4.4.0

1. Scarica il pacchetto di versione 4.4.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 4.4.0 del pacchetto.
1. Puoi scegliere di premere il trigger per avviare il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet).

1. Dopo aver completato l’installazione del pacchetto, attendi i seguenti messaggi\(s\) nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutti i passaggi dell&#39;installazione sono stati completati.

   Se riscontri uno dei seguenti prefissi ERROR, segnalali al team di successo del cliente:

   - Errore nello script di installazione post-distribuzione
   - Eccezione durante il porting del MAP di traduzione
   - Impossibile trasferire la mappa di traduzione dalla versione 1 alla versione 2 per la proprietà
1. Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione 4.4.0 \(se necessario\).
1. Cancella la cache del browser dopo l’installazione del pacchetto.
1. Continua ad aggiornare le personalizzazioni come descritto nella sezione successiva.


## Dopo aver installato la versione 4.4.0

Dopo aver installato Experience Manager Guides, è possibile unire le varie configurazioni applicabili dalla versione appena installata alla configurazione.

>[!NOTE]
>
> Il modello dam-update-asset può essere personalizzato. Pertanto, se sono state apportate personalizzazioni, è necessario sincronizzare le personalizzazioni e Experience Manager Guides nella copia di lavoro del modello.

1. **Flusso di lavoro Aggiorna risorsa DAM \(Modifiche post-elaborazione\):**

1. Apri URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleziona **Flusso di lavoro Aggiorna risorsa DAM**.
1. Fai clic su **Modifica**.
1. Se il componente **DXML Post Process Initiator** è presente, verificare che le personalizzazioni siano sincronizzate.
1. Se il componente **DXML Post Process Initiator** è assente, eseguire la procedura seguente per inserirlo:

1. Fare clic su **Inserisci componente** \(Responsabile della post-elaborazione di Experience Manager Guides come fase finale del processo\).
1. Configura il **passaggio del processo** con i dettagli seguenti:

   **Scheda comune**

   **Titolo:** iniziatore post-elaborazione DXML

   **Descrizione**: passaggio iniziatore post-elaborazione DXML che attiverà un processo sling per la post-elaborazione DXML della risorsa modificata/creata

   **Scheda Elabora**

   - Seleziona **DXML Post Process Initiator** dal menu a discesa **Process**

   - Seleziona **Avanzamento gestore**

   - Seleziona **Fine**

1. Fai clic su **Sincronizza** in alto a destra dopo aver completato le modifiche. Riceverai una notifica di esito positivo.

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
   - Tutti i componenti sovrapposti da/libs/fmditaor/libssdevono essere confrontati con il nuovo codice del prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in/apps.
   - Tutte le categorie clientlib utilizzate dal prodotto, devono essere riviste per eventuali modifiche. Eventuali configurazioni sostituite \(esempi di seguito\) devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - elementmapping.xml
   - ui\_config.json\(potrebbe essere stato impostato in profili cartella\)
   - ha modificato `com.adobe.fmdita.config.ConfigManager`

1. Se hai aggiunto delle personalizzazioni in damAssetLucene, potresti dover applicarle nuovamente. Dopo aver apportato tali modifiche, imposta la reindicizzazione su true. In questo modo tutti i nodi esistenti verranno reindicizzati con le personalizzazioni. Al termine, il flag di reindicizzazione verrà impostato di nuovo su false. Questa operazione può richiedere alcune ore a seconda del numero di risorse nel sistema.

## Passaggi per indicizzare il contenuto esistente

>[!NOTE]
>
> Non è necessario eseguire questi passaggi se si esegue l’aggiornamento da 4.3.0 o 4.3.1.

Effettua le seguenti operazioni per indicizzare il contenuto esistente e utilizzare il nuovo testo Trova e sostituisci a livello di mappa:

- Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi passare percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate \|\| Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (ad esempio: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Passaggi per pubblicare ed elaborare il contenuto esistente per utilizzare il rapporto sui collegamenti interrotti

>[!NOTE]
>
> Non è necessario eseguire questi passaggi se si esegue l’aggiornamento da 4.3.0 o 4.3.1.

Effettua le seguenti operazioni per la post-elaborazione del contenuto esistente e l’utilizzo del nuovo rapporto sui collegamenti interrotti:

1. (Facoltativo) Se nel sistema sono presenti più di 100.000 file dita, aggiornare `queryLimitReads` in `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` a un valore maggiore (qualsiasi valore maggiore del numero di risorse presenti, ad esempio 200.000) e quindi ridistribuire.

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

### Abilitare l’attivazione dello script tramite un servlet

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



## Passaggi per gestire il conflitto `'fmdita rewriter'`

Experience Manager Guides dispone di un modulo [**sling rewriter personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50.  Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante l&#39;aggiornamento, poiché il valore `'order'` viene modificato da 1000 a 50, è necessario unire l&#39;eventuale rewriter personalizzato esistente con `'fmdita-rewriter'`.


**Argomento padre:**&#x200B;[&#x200B; Scarica e installa](download-install.md)


## Aggiornamento alla versione 4.6.0

>[!TIP]
>
> Si consiglia di installare 4.6.0 Service Pack 4 oltre alle versioni 4.6.0, 4.6.0 Service Pack 1 o 4.6.0 Service Pack 3. Il processo di aggiornamento per la versione 4.6.0 Service Pack 4 segue gli stessi passaggi della versione 4.6.0.

L’aggiornamento alla versione 4.6.0 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi le versioni 4.4.0, 4.3.1, 4.3.0, 4.2 o 4.2.1 (Hotfix 4.2.1.3), puoi eseguire direttamente l&#39;aggiornamento alla versione 4.6.0.

>[!NOTE]
>
> La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

**&#x200B;**&#x200B;Prerequisiti&#x200B;**&#x200B;**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 4.6.0, assicurati di disporre di:

1. Aggiornamento a Experience Manager Guides versione 4.3.1, 4.3.0 o 4.2.1 (Hotfix 4.2.1.3) e completamento del rispettivo passaggio di installazione.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.


## Installare la versione 4.6.0

1. Scarica il pacchetto di versione 4.6.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 4.6.0 del pacchetto.
1. Puoi scegliere di premere il trigger per avviare il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet).

1. Dopo aver completato l’installazione del pacchetto, attendi i seguenti messaggi\(s\) nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutti i passaggi dell&#39;installazione sono stati completati.

   Se riscontri uno dei seguenti prefissi ERROR, segnalali al team di successo del cliente:

   - Errore nello script di installazione post-distribuzione
   - Eccezione durante il porting del MAP di traduzione
   - Impossibile trasferire la mappa di traduzione dalla versione 1 alla versione 2 per la proprietà
1. Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione 4.6.0 \(if needed\).
1. Cancella la cache del browser dopo l’installazione del pacchetto.

## Dopo aver installato la versione 4.6.0

Dopo aver installato Experience Manager Guides, è possibile unire le varie configurazioni applicabili dalla versione appena installata alla configurazione.

>[!NOTE]
>
> Il modello dam-update-asset può essere personalizzato. Pertanto, se sono state apportate personalizzazioni, è necessario sincronizzare le personalizzazioni e Experience Manager Guides nella copia di lavoro del modello.

1. **Flusso di lavoro Aggiorna risorsa DAM \(Modifiche post-elaborazione\):**

1. Apri URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleziona **Flusso di lavoro Aggiorna risorsa DAM**.
1. Fai clic su **Modifica**.
1. Se il componente **DXML Post Process Initiator** è presente, verificare che le personalizzazioni siano sincronizzate.
1. Se il componente **DXML Post Process Initiator** è assente, eseguire la procedura seguente per inserirlo:

1. Fare clic su **Inserisci componente** \(Responsabile della post-elaborazione di Experience Manager Guides come fase finale del processo\).
1. Configura il **passaggio del processo** con i dettagli seguenti:

   **Scheda comune**

   **Titolo:** iniziatore post-elaborazione DXML

   **Descrizione**: passaggio iniziatore post-elaborazione DXML che attiverà un processo sling per la post-elaborazione DXML della risorsa modificata/creata

   **Scheda Elabora**

   - Selezionare **DXML Post Process Initiator** dal menu a discesa **Process**

   - Seleziona **Avanzamento gestore**

   - Seleziona **Fine**

1. Fai clic su **Sincronizza** in alto a destra dopo aver completato le modifiche. Riceverai una notifica di esito positivo.

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
   - Tutti i componenti sovrapposti da/libs/fmditaor/libssdevono essere confrontati con il nuovo codice del prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in/apps.
   - Tutte le categorie clientlib utilizzate dal prodotto, devono essere riviste per eventuali modifiche. Eventuali configurazioni sostituite \(esempi di seguito\) devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - elementmapping.xml
   - ui\_config.json\(potrebbe essere stato impostato in profili cartella\)
   - ha modificato `com.adobe.fmdita.config.ConfigManager`

1. Se hai aggiunto delle personalizzazioni in damAssetLucene, potresti dover applicarle nuovamente. Dopo aver apportato tali modifiche, imposta la reindicizzazione su true. In questo modo tutti i nodi esistenti verranno reindicizzati con le personalizzazioni. Al termine, il flag di reindicizzazione verrà impostato di nuovo su false. Questa operazione può richiedere alcune ore a seconda del numero di risorse nel sistema.

## Passaggi per reindicizzare gli indici Experience Manager Guides

1. Apri `crx/de` e passa al percorso indice: `/oak:index/guidesAssetProperties`
2. Impostare la proprietà di reindicizzazione come `true` (`false` per impostazione predefinita) e fare clic su **Salva tutto**.
3. Una volta completata la reindicizzazione, la proprietà di reindicizzazione viene nuovamente impostata su `false` e il conteggio di reindicizzazione viene incrementato di 1.

   >[!NOTE]
   >
   > Questa operazione può richiedere alcuni minuti, a seconda della quantità di dati presenti.
4. Seguire la stessa procedura per gli altri indici aggiunti o modificati: `guidesBulkActivation`, `guidesPeerLinkIndex` e `guidesKonnectTemplateIndex`.

## Passaggi per indicizzare il contenuto esistente



Per indicizzare il contenuto esistente, effettua le seguenti operazioni:

- Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate || Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (ad esempio: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.


>[!NOTE]
>
> Se si utilizza lo schema personalizzato, è necessario definire il percorso dei file DTD e XSD catalog.xml personalizzati nell&#39;archivio di AEM nell&#39;opzione **Integrate Catalog**.




## Passaggi per gestire il conflitto `'fmdita rewriter'`

Experience Manager Guides dispone di un modulo [**sling rewriter personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50.  Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante l&#39;aggiornamento, poiché il valore `'order'` viene modificato da 1000 a 50, è necessario unire l&#39;eventuale rewriter personalizzato esistente con `'fmdita-rewriter'`.


## Aggiornamento alla versione 5.0.0

>[!TIP]
>
> L’aggiornamento alla versione 5.0.0 del Service Pack 2 dipende dalla versione corrente di Experience Manager Guides. Se utilizzi la versione 5.0.0 di Service Pack 1 o 5.0.0, puoi eseguire direttamente l’aggiornamento alla versione 5.0.0 di Service Pack 2.

>[!NOTE]
>
> La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

**&#x200B;**&#x200B;Prerequisiti&#x200B;**&#x200B;**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 5.0.0, verificare di disporre dei seguenti elementi:

1. Aggiornato a Experience Manager Guides versione 4.6.3, 4.6.1, 4.6.0 o 4.4 e completato il rispettivo passaggio di installazione.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.


## Installare la versione 5.0.0

1. Scarica il pacchetto della versione 5.0.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 5.0.0 del pacchetto.
1. Puoi scegliere di premere il trigger per avviare il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet).

1. Dopo aver completato l’installazione del pacchetto, attendi i seguenti messaggi\(s\) nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutti i passaggi dell&#39;installazione sono stati completati.

   Se riscontri uno dei seguenti prefissi ERROR, segnalali al team di successo del cliente:

   - Errore nello script di installazione post-distribuzione
   - Eccezione durante il porting del MAP di traduzione
   - Impossibile trasferire la mappa di traduzione dalla versione 1 alla versione 2 per la proprietà
1. Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione 5.0.0 \(se necessario\).
1. Cancella la cache del browser dopo l’installazione del pacchetto.

## Dopo aver installato la versione 5.0.0

Dopo aver installato Experience Manager Guides, è possibile unire le varie configurazioni applicabili dalla versione appena installata alla configurazione.

>[!NOTE]
>
> Il modello dam-update-asset può essere personalizzato. Pertanto, se sono state apportate personalizzazioni, è necessario sincronizzare le personalizzazioni e Experience Manager Guides nella copia di lavoro del modello.

1. **Flusso di lavoro Aggiorna risorsa DAM \(Modifiche post-elaborazione\):**

1. Apri URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleziona **Flusso di lavoro Aggiorna risorsa DAM**.
1. Fai clic su **Modifica**.
1. Se il componente **DXML Post Process Initiator** è presente, verificare che le personalizzazioni siano sincronizzate.
1. Se il componente **DXML Post Process Initiator** è assente, eseguire la procedura seguente per inserirlo:

1. Fare clic su **Inserisci componente** \(Responsabile della post-elaborazione di Experience Manager Guides come fase finale del processo\).
1. Configura il **passaggio del processo** con i dettagli seguenti:

   **Scheda comune**

   **Titolo:** iniziatore post-elaborazione DXML

   **Descrizione**: passaggio iniziatore post-elaborazione DXML che attiverà un processo sling per la post-elaborazione DXML della risorsa modificata/creata

   **Scheda Elabora**

   - Selezionare **DXML Post Process Initiator** dal menu a discesa **Process**

   - Seleziona **Avanzamento gestore**

   - Seleziona **Fine**

1. Fai clic su **Sincronizza** in alto a destra dopo aver completato le modifiche. Riceverai una notifica di esito positivo.

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
   - Tutti i componenti sovrapposti da/libs/fmditaor/libssdevono essere confrontati con il nuovo codice del prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in/apps.
   - Tutte le categorie clientlib utilizzate dal prodotto, devono essere riviste per eventuali modifiche. Eventuali configurazioni sostituite \(esempi di seguito\) devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - elementmapping.xml
   - ui\_config.json\(potrebbe essere stato impostato in profili cartella\)
   - ha modificato `com.adobe.fmdita.config.ConfigManager`

1. Se hai aggiunto delle personalizzazioni in damAssetLucene, potresti dover applicarle nuovamente. Dopo aver apportato tali modifiche, imposta la reindicizzazione su true. In questo modo tutti i nodi esistenti verranno reindicizzati con le personalizzazioni. Al termine, il flag di reindicizzazione verrà impostato di nuovo su false. Questa operazione può richiedere alcune ore a seconda del numero di risorse nel sistema.

## Passaggi per reindicizzare gli indici Experience Manager Guides

1. Apri `crx/de` e passa al percorso indice: `/oak:index/guidesAssetProperties`
2. Impostare la proprietà di reindicizzazione come `true` (`false` per impostazione predefinita) e fare clic su **Salva tutto**.
3. Una volta completata la reindicizzazione, la proprietà di reindicizzazione viene nuovamente impostata su `false` e il conteggio di reindicizzazione viene incrementato di 1.

   >[!NOTE]
   >
   > Questa operazione può richiedere alcuni minuti, a seconda della quantità di dati presenti.
4. Seguire la stessa procedura per gli altri indici aggiunti o modificati: `guidesBulkActivation`, `guidesPeerLinkIndex` e `guidesKonnectTemplateIndex`.

## Passaggi per indicizzare il contenuto esistente



Per indicizzare il contenuto esistente, effettua le seguenti operazioni:

- Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate || Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (ad esempio: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.


>[!NOTE]
>
> Se si utilizza lo schema personalizzato, è necessario definire il percorso dei file DTD e XSD catalog.xml personalizzati nell&#39;archivio di AEM nell&#39;opzione **Integrate Catalog**.




## Passaggi per gestire il conflitto `'fmdita rewriter'`

Experience Manager Guides dispone di un modulo [**sling rewriter personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50.  Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante l&#39;aggiornamento, poiché il valore `'order'` viene modificato da 1000 a 50, è necessario unire l&#39;eventuale rewriter personalizzato esistente con `'fmdita-rewriter'`.



## Passaggi per reindicizzare damAssetLucene

La definizione dell’indice viene aggiornata per damAssetLucene con Guide. Fai riferimento a [questo articolo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) per reindicizzare damAssetLucene dopo l&#39;aggiornamento alla versione 5.0.0.

>[!NOTE]
>
> Seguendo la documentazione, assicurati che entrambe le proprietà (reindex=true e reindex-async=true per /oak:index/damAssetLucene) vengano aggiornate contemporaneamente tramite l&#39;operazione di salvataggio.

## Aggiornamento alla versione 5.1.0

>[!IMPORTANT]
>
> Se al momento utilizzi AEM 6.5 e prevedi di passare ad AEM 6.5 LTS, assicurati di completare l’aggiornamento ad AEM prima di procedere con l’aggiornamento a Experience Manager Guides 5.1.0. Per informazioni dettagliate, visualizzare [Aggiornamento a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

**&#x200B;**&#x200B;Prerequisiti&#x200B;**&#x200B;**

Prima di avviare il processo di aggiornamento di Experience Manager Guides 5.1.0, verificare di disporre dei seguenti elementi:

1. Aggiornamento a Experience Manager Guides versione 4.6.3, 4.6.4, 5.0.0 o 5.0.0 Service Pack 1 e completamento del rispettivo passaggio di installazione.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.

>[!NOTE]
>
> La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

## Installare la versione 5.1.0

1. Scarica il pacchetto di versione 5.1.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa la versione 5.1.0 del pacchetto.
1. Puoi scegliere di premere il trigger per avviare il processo di aggiornamento della mappa di traduzione. Per ulteriori dettagli, vedere [Abilitare il trigger dello script tramite un servlet](#enable-trigger-of-script-via-a-servlet).

1. Dopo aver completato l’installazione del pacchetto, attendi i seguenti messaggi\(s\) nei registri:

   `Completed the post deployment setup script`

   Il messaggio sopra riportato indica che tutti i passaggi dell&#39;installazione sono stati completati.

   Se riscontri uno dei seguenti prefissi ERROR, segnalali al team di successo del cliente:

   - Errore nello script di installazione post-distribuzione
   - Eccezione durante il porting del MAP di traduzione
   - Impossibile trasferire la mappa di traduzione dalla versione 1 alla versione 2 per la proprietà
1. Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione 5.1.0 \(se necessario\).
1. Cancella la cache del browser dopo l’installazione del pacchetto.

## Dopo aver installato la versione 5.1.0

Dopo aver installato Experience Manager Guides, è possibile unire le varie configurazioni applicabili dalla versione appena installata alla configurazione.

>[!NOTE]
>
> Il modello dam-update-asset può essere personalizzato. Pertanto, se sono state apportate personalizzazioni, è necessario sincronizzare le personalizzazioni e Experience Manager Guides nella copia di lavoro del modello.

1. **Flusso di lavoro Aggiorna risorsa DAM \(Modifiche post-elaborazione\):**

1. Apri URL:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Seleziona **Flusso di lavoro Aggiorna risorsa DAM**.
1. Seleziona **Modifica**.
1. Se il componente **DXML Post Process Initiator** è presente, verificare che le personalizzazioni siano sincronizzate.
1. Se il componente **DXML Post Process Initiator** è assente, eseguire la procedura seguente per inserirlo:

1. Selezionare **Inserisci componente** \(Responsabile della post-elaborazione di Experience Manager Guides come fase finale del processo\).
1. Configura il **passaggio del processo** con i dettagli seguenti:

   **Scheda comune**

   **Titolo:** iniziatore post-elaborazione DXML

   **Descrizione**: passaggio iniziatore post-elaborazione DXML che attiverà un processo sling per la post-elaborazione DXML della risorsa modificata/creata

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
   - Tutti i componenti sovrapposti da/libs/fmditaor/libssdevono essere confrontati con il nuovo codice del prodotto e gli aggiornamenti devono essere eseguiti in file sovrapposti in/apps.
   - Tutte le categorie clientlib utilizzate dal prodotto, devono essere riviste per eventuali modifiche. Eventuali configurazioni sostituite \(esempi di seguito\) devono essere confrontate con quelle più recenti in modo da ottenere le funzioni più recenti:
   - elementmapping.xml
   - ui\_config.json\(potrebbe essere stato impostato in profili cartella\)
   - ha modificato `com.adobe.fmdita.config.ConfigManager`

1. Se hai aggiunto delle personalizzazioni in damAssetLucene, potresti dover applicarle nuovamente. Dopo aver apportato tali modifiche, imposta la reindicizzazione su true. In questo modo tutti i nodi esistenti verranno reindicizzati con le personalizzazioni. Al termine, il flag di reindicizzazione verrà impostato di nuovo su false. Questa operazione può richiedere alcune ore a seconda del numero di risorse nel sistema.

## Passaggi per reindicizzare gli indici Experience Manager Guides

1. Apri `crx/de` e passa al percorso indice: `/oak:index/guidesAssetProperties`
2. Impostare la proprietà di reindicizzazione come `true` (`false` per impostazione predefinita) e fare clic su **Salva tutto**.
3. Una volta completata la reindicizzazione, la proprietà di reindicizzazione viene nuovamente impostata su `false` e il conteggio di reindicizzazione viene incrementato di 1.

   >[!NOTE]
   >
   > Questa operazione può richiedere alcuni minuti, a seconda della quantità di dati presenti.
4. Seguire la stessa procedura per gli altri indici aggiunti o modificati: `guidesBulkActivation`, `guidesPeerLinkIndex` e `guidesKonnectTemplateIndex`.

## Passaggi per indicizzare il contenuto esistente



Per indicizzare il contenuto esistente, effettua le seguenti operazioni:

- Eseguire una richiesta POST al server \(con autenticazione corretta\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate || Esempio: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (ad esempio: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.


>[!NOTE]
>
> Se si utilizza lo schema personalizzato, è necessario definire il percorso dei file DTD e XSD catalog.xml personalizzati nell&#39;archivio di AEM nell&#39;opzione **Integrate Catalog**.




## Passaggi per gestire il conflitto `'fmdita rewriter'`

Experience Manager Guides dispone di un modulo [**sling rewriter personalizzato**](../cs-install-guide/conf-output-generation.md#custom-rewriter) per la gestione dei collegamenti generati in caso di mappe incrociate (collegamenti tra gli argomenti di due mappe diverse).

Se nel codebase è presente un altro rewriter sling personalizzato, utilizza un valore `'order'` maggiore di 50, in quanto il rewriter sling di Experience Manager Guides utilizza `'order'` 50.  Per evitare questo problema, è necessario un valore > 50. Per ulteriori dettagli, visualizza [Pipeline di riscrittura output](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Durante l&#39;aggiornamento, poiché il valore `'order'` viene modificato da 1000 a 50, è necessario unire l&#39;eventuale rewriter personalizzato esistente con `'fmdita-rewriter'`.



## Passaggi per reindicizzare damAssetLucene

La definizione dell’indice viene aggiornata per damAssetLucene con Guide. Fai riferimento a [questo articolo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) per reindicizzare damAssetLucene dopo l&#39;aggiornamento alla versione 5.1.0.

>[!NOTE]
>
> Seguendo la documentazione, assicurati che entrambe le proprietà (reindex=true e reindex-async=true per /oak:index/damAssetLucene) vengano aggiornate contemporaneamente tramite l&#39;operazione di salvataggio.



**Argomento padre:** [Scarica e installa](download-install.md)
