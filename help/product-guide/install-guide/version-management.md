---
title: Gestione delle versioni
description: Scopri come funziona la gestione delle versioni
exl-id: 24e44618-9c4e-4547-a00d-216ef3fb4854
feature: Version Management
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 0%

---

# Gestione delle versioni {#id181GB000XY4}

Il controllo delle versioni è un aspetto importante di qualsiasi sistema di gestione dei contenuti. Consente di creare un’istantanea della risorsa digitale in un momento specifico. Con una versione di una risorsa digitale installata, puoi ripristinare la versione richiesta della risorsa e aggiornarla. In genere, per creare una versione di una risorsa, si estrae e si archivia la risorsa richiesta.

In qualità di amministratore, è possibile applicare regole che impediscono agli utenti di modificare un file senza estrarlo. Analogamente, è possibile assicurarsi che tutti i file estratti vengano archiviati per evitare perdite di dati.

In un ambiente multiuso, è inoltre importante assicurarsi che gli utenti non eliminino i file dal sistema. Questo requisito è più critico per i file estratti da altri utenti.È possibile consentire o impedire agli utenti di sovrascrivere i file estratti da altri utenti. Per evitare che gli utenti eliminino accidentalmente i file estratti dal sistema, AEM Guides fornisce una configurazione che è possibile utilizzare. Oltre ai file estratti, è possibile controllare l&#39;eliminazione dei file che contengono riferimenti o a cui si fa riferimento da altri file. Inoltre, puoi anche creare una nuova versione per il file caricato.

## Crea una nuova versione per il file caricato

>[!NOTE]
>
> Questa configurazione è applicabile solo durante il caricamento dei file.

Per creare una nuova versione del file caricato, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Selezionare l&#39;opzione **Crea nuova versione per il file caricato**.

   Per impostazione predefinita, questa opzione è disattivata.

   Quando l’opzione è selezionata, si verifica un nuovo meccanismo di gestione della versione e sovrascrive il comportamento di caricamento predefinito per qualsiasi caricamento successivo. I contenuti del file caricato vengono salvati come nuova versione. Se l’opzione è deselezionata, AEM Guides utilizza il meccanismo predefinito di gestione delle versioni dell’AEM.

1. Fai clic su **Salva**.


>[!NOTE]
>
> Se abiliti la proprietà **Crea nuova versione per il file caricato** \(create.ver.new.content\) e utilizzi la **interfaccia utente di Assets** per caricare in blocco le risorse, puoi caricare i file in batch di 70 o meno.

## Configura le impostazioni per consentire la modifica dei file estratti

L&#39;Editor Web di AEM Guides consente di creare e aggiornare argomenti DITA. È possibile configurare l&#39;Editor Web in modo da consentire la modifica solo dei documenti estratti dal repository. In questo modo nessun altro autore sovrascrive accidentalmente un argomento aperto per la modifica da un altro autore. Una volta aperto un argomento per la modifica, un autore può archiviare il file al momento della chiusura.

Un&#39;altra regola importante consiste nel garantire che i file estratti vengano nuovamente archiviati nel sistema. In questo modo gli utenti non potranno chiudere accidentalmente i file senza archiviarli di nuovo.

Per abilitare queste funzioni, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Seleziona l&#39;opzione **Disattiva modifica senza estrazione**.

   ![](assets/xml-editor-config.png){width="650" align="left"}

   Con questa opzione, gli utenti non visualizzeranno l&#39;opzione Modifica nella barra degli strumenti fino a quando non estraggono un file.

1. Selezionare l&#39;opzione **Richiedi archiviazione alla chiusura** per visualizzare un messaggio di avviso ogni volta che un file estratto viene chiuso senza essere salvato o archiviato nuovamente nel repository.

1. Fai clic su **Salva**.


>[!NOTE]
>
> Indipendentemente dal fatto che questa funzione venga attivata o disattivata, le opzioni Estrai e Archivia file sono sempre disponibili nell&#39;anteprima di un argomento.

## Sovrascrivi file estratto al caricamento

>[!NOTE]
>
> Questa configurazione è applicabile solo quando si creano file dall&#39;interfaccia utente di Assets e non quando si caricano file tramite lo strumento WebDAV.

Per consentire agli utenti di sovrascrivere il file durante il caricamento che è stato estratto da loro o da un altro utente, effettuare le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Selezionare l&#39;opzione **Sovrascrivi file estratto al caricamento**.

   Per impostazione predefinita, questa opzione è attivata. Se questa opzione è selezionata, gli utenti potranno sovrascrivere i file estratti. Se l&#39;opzione non è selezionata, il file non può essere sovrascritto se è stato estratto da un altro utente o da un altro utente.

1. Fai clic su **Salva**.


## Impedisci l&#39;eliminazione dei file estratti

Per impedire agli utenti di eliminare accidentalmente i file estratti da loro o da altri utenti, effettuare le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Selezionare l&#39;opzione **Impedisci eliminazione del contenuto estratto**.

   Per impostazione predefinita, questa opzione è attivata. Se questa opzione è selezionata, gli utenti non potranno eliminare i file estratti.

1. Fai clic su **Salva**.


Per supportare questa funzione, in `oak:index` è stata aggiunta la nuova proprietà `drivelock` dell&#39;indice:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png){width="800" align="left"}

Oltre alla nuova proprietà dell&#39;indice, verificare che le seguenti proprietà siano impostate su `/oak:index/damAssetLucene`:

- `jcr:primaryType`=`"oak:QueryIndexDefinition"`
- `async`=`"async"`
- `compatVersion`=`"{Long}2"`
- `evaluatePathRestrictions`=`"{Boolean}true"`
- `reindex`=`"{Boolean}false"`
- `reindexCount`=`"{Long}3"` *\(questo è il numero di volte in cui viene eseguita la reindicizzazione, viene sostituito con l&#39;installazione del pacchetto\)*
- `type`=`"lucene"`

>[!NOTE]
>
> È possibile modificare il valore di `reindex` in `"{Boolean}true"`. Ciò consente di ottenere risultati di ricerca più rapidi per i file estratti all&#39;interno di una gerarchia di cartelle.

## Impedisci l&#39;eliminazione dei file di riferimento

In qualità di amministratore, puoi controllare chi può eliminare i file dall’archivio AEM. In particolare, se un file contiene riferimenti o vi fa riferimento un altro file, puoi definire chi può eliminare tali file.

Utilizzando questa configurazione, puoi consentire o vietare a tutti gli utenti di eliminare i file, oppure consentire solo a un gruppo di utenti specifico di eliminare i file. Se è consentita l’eliminazione del file, viene seguito il seguente processo:

- Se si elimina una cartella, che contiene tutti i file di riferimento e di riferimento, tutti i file vengono eliminati. Il processo elimina innanzitutto tutti i file che non contengono riferimenti, seguiti dai file che contengono riferimenti o a cui si fa riferimento.

- Se si sta eliminando una cartella e a qualsiasi file all&#39;interno della cartella viene fatto riferimento da un file all&#39;esterno della cartella, verrà richiesto di rimuovere il riferimento prima di eliminare il file.


Per definire chi può eliminare un file che contiene riferimenti o a cui fanno riferimento altri file, effettuare le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Individua l&#39;opzione **Blocca eliminazione per Assets** di riferimento.

1. A seconda degli utenti a cui si desidera concedere l&#39;accesso per l&#39;eliminazione, specificare una delle seguenti costanti:

   - allow\_unsafe\_delete\_for\_all: concedere a tutti gli utenti l’autorizzazione per eliminare i file. In questo caso, se il file\(s\) contiene riferimenti o vi fanno riferimento altri file, potete anche eliminarlo forzatamente. Prima di eliminare il file, viene visualizzato un messaggio con i riferimenti, è possibile annullare l&#39;operazione di eliminazione, rimuovere i riferimenti e infine eliminare il file\(s\). In alternativa, è possibile eliminare forzatamente il file\(s\) senza rimuovere i riferimenti.

     ![](assets/allow_unsafe_delete-force-delete.PNG){width="550" align="left"}

   - allow\_unsafe\_delete\_for\_delete\_assets\_group: un amministratore o un utente appartenente al gruppo *delete-assets* può eliminare dei file. Se un altro utente tenta di eliminare file con qualsiasi riferimento, non potrà eliminare tali file finché non saranno stati rimossi tutti i riferimenti. La schermata seguente viene visualizzata quando un utente che non dispone delle autorizzazioni necessarie tenta di eliminare dei file.

     ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG){width="550" align="left"}

   - block\_unsafe\_delete\_for\_all: non consentire a tutti gli utenti \(inclusi gli amministratori\) di eliminare i file finché i riferimenti a e dal file\(s\) non vengono rimossi.

1. Fai clic su **Salva**.


## Rimuovi versioni precedenti di file DITA

Quando si aggiorna il contenuto e si creano nuove versioni, le versioni precedenti dei file DITA vengono mantenute nell&#39;archivio. Molte versioni potrebbero essere create per i file DITA in un periodo di tempo e, collettivamente, occupano una grande quantità di spazio nell&#39;archivio. AEM Guides consente di configurare le versioni precedenti da eliminare dall’archivio.

Puoi accedere a questa utility utilizzando l’URL specificato se disponi di diritti di amministratore:

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

La versione di un file DITA che soddisfa uno qualsiasi dei criteri specificati viene mantenuta e non eliminata:

- È la prima versione di un file
- È incluso in una baseline
- È incluso in qualsiasi flusso di lavoro di traduzione o revisione
- Ha un’etichetta applicata
- Soddisfa l’età o il numero di criteri di versione definiti

Per eliminare le versioni precedenti, effettua le seguenti operazioni:

1. Immetti i seguenti dettagli sui file da eliminare:

   ![](assets/preview-purge-report.png){width="350" align="left"}

1. 
   - **Numero di versioni da mantenere dall&#39;ultima versione**: immettere il numero di versioni da conservare e non eliminare. Ad esempio, se si immette 5, le ultime 5 versioni vengono mantenute e le versioni precedenti vengono qualificate per l&#39;eliminazione nel caso in cui vengano soddisfatte altre condizioni di rimozione.
- **Mantieni versioni create entro l&#39;intervallo di tempo \(In giorni\)**: immettere l&#39;età massima di una versione in giorni. Le versioni precedenti al numero di giorni specificato possono essere eliminate nel caso in cui siano soddisfatte altre condizioni di eliminazione. Ad esempio, se si immette 100, tutte le versioni create prima di 100 giorni vengono qualificate per l&#39;eliminazione nel caso in cui vengano soddisfatte altre condizioni di rimozione.
- **Percorso**: selezionare il percorso del file o della cartella di cui si desidera eliminare i file.

  >[!NOTE]
  >
  > È possibile eliminare solo i file DITA.

1. Fare clic su **Anteprima report di rimozione**.

   >[!NOTE]
   >
   > Può essere presente una sola attività di eliminazione alla volta. Non è possibile avviare un&#39;altra operazione di eliminazione della versione se una è in corso di elaborazione.

   Viene generato il rapporto di eliminazione della versione.

1. Scarica il rapporto di eliminazione della versione e controlla i file e le versioni che verranno eliminati.
1. Puoi scegliere di **Annullare la rimozione** o **Avviare la rimozione**.

   ![](assets/download-purge-report.png){width="350" align="left"}

   Viene visualizzato lo stato di rimozione.

   Fare clic su **Scarica rapporto di eliminazione versione** per visualizzare le versioni eliminate. Questo rapporto fornisce lo stato di rimozione su tutte le versioni insieme ai motivi per cui una particolare versione è stata mantenuta o eliminata.


>[!NOTE]
>
> Il report viene scaricato nella posizione seguente: /var/dxml/versionpurge
