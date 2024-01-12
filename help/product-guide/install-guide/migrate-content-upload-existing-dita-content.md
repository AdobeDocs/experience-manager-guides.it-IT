---
title: Carica contenuto DITA esistente
description: Scopri come caricare contenuto DITA esistente
exl-id: 1dde8a29-301f-461e-b598-2a8cab61bf3d
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1201'
ht-degree: 0%

---

# Carica contenuto DITA esistente {#id176FF000JUI}

È probabile che si disponga di un archivio di contenuti DITA esistenti che si desidera utilizzare con le guide AEM. Per tali contenuti esistenti, puoi utilizzare uno dei seguenti approcci per caricare in blocco i contenuti nell’archivio AEM.

## Utilizzare uno strumento WebDAV

Se si creano argomenti e mappe in qualsiasi altro editor DITA, è possibile utilizzare qualsiasi strumento WebDAV per caricare i file. La procedura descritta in questa sezione utilizza WinSCP come strumento WebDAV per caricare contenuti.

Per utilizzare WinSCP per caricare i file, effettuare le seguenti operazioni:

1. Scarica e installa WinSCP sul computer.

1. Avvia l&#39;app WinSCP.

   Viene visualizzata la finestra di dialogo Login (Accesso).

1. Nella finestra di dialogo Accesso, specificare un&#39;impostazione Nuovo sito scegliendo WebDAV come **Protocollo file** e fornendo altri dettagli di connessione come:

   - l’URL in cui è ospitato il server AEM,

   - il numero di porta \(il valore predefinito è 4502\) e

   - il nome utente e la password per accedere al server AEM.

1. Fai clic su **Accedi**.

   Una volta stabilita la connessione, nell&#39;interfaccia utente WinSCP verranno visualizzati i contenuti di AEM Assets. È possibile sfogliare, creare, aggiornare o eliminare facilmente il contenuto utilizzando Esplora file WinSCP.


## Usa FrameMaker

Adobe FrameMaker viene fornito con un potente connettore AEM che consente di caricare facilmente in AEM i documenti DITA e di altro FrameMaker esistenti \(.book e .fm\). Puoi utilizzare varie funzionalità di caricamento dei file, ad esempio il caricamento di un singolo file e di una cartella completa con o senza dipendenze \(come riferimenti a contenuti, riferimenti incrociati e elementi grafici\).

Per utilizzare il connettore AEM del FrameMaker per caricare il contenuto, effettua le seguenti operazioni:

1. Avvia FrameMaker.

1. Apri **Gestione connessioni** .

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Immettere i dettagli seguenti per connettersi all&#39;archivio AEM:

   - **Nome**: immetti un nome descrittivo per identificare la connessione al server AEM.
   - **Server**: immetti l’URL e il numero di porta del server AEM.

   - **Nome utente**/**Password**: immetti il nome utente e la password per accedere al server AEM.

1. Clic **Connetti**.

   Una volta stabilita la connessione, le risorse dell’archivio AEM vengono visualizzate nella finestra Gestione archivio.

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Facendo clic con il pulsante destro del mouse su un file o una cartella è possibile eseguire operazioni correlate. Ad esempio, se fai clic con il pulsante destro del mouse su una cartella, ottieni le opzioni per caricare un file, caricare un file con dipendenze, caricare un’intera cartella e così via.


## Configura pattern nome file UUID

Quando importi il contenuto, non è necessario che i nomi dei file siano basati sull’UUID. In un sistema che utilizza nomi di file basati su UUID, è obbligatorio fare riferimento a tutti i file utilizzando i loro UUID anziché i nomi di file originali. Se un file importato non ha nomi di file basati su UUID, potete configurare il sistema per aggiungere un UUID alle proprietà del file. Questo UUID viene quindi utilizzato per fare riferimento a tali file dove UUID non viene utilizzato per la denominazione dei file.

Effettua le seguenti operazioni per controllare i nomi dei file in base a un pattern UUID e assegnare UUID ai file a cui non è stato assegnato un UUID:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su *com.adobe.fmdita.config.ConfigManager* pacchetto.

1. In **Pattern per nome file UUID** , specificare un pattern per verificare i nomi dei file importati.

   Se un file non segue il pattern specificato, viene aggiunto un UUID alla proprietà del file e tutti i riferimenti al file vengono aggiornati con l’UUID assegnato al file.

1. Fai clic su **Salva**.


## Caricare contenuti con UUID utilizzando uno strumento WebDav {#id201MI0I04Y4}

Per caricare il contenuto con UUID, puoi utilizzare uno dei seguenti metodi:

- Trascinare i contenuti dal sistema locale.
- Utilizza il **Crea** \> **File** flusso di lavoro dall’interfaccia utente di AEM Assets.
- Utilizza uno strumento come WinSCP.

Se si utilizza uno strumento come WinSCP, è possibile definire l&#39;azione da eseguire su un file duplicato impostando **Sposta il vecchio file con lo stesso UUID in una nuova cartella** in configMgr. Questa opzione definisce l’azione eseguita su un file disponibile in un’altra posizione nell’archivio AEM. Questa impostazione è disponibile in *com.adobe.fmdita.config.ConfigManager* nel file configMgr.

Per impostazione predefinita, il **Sposta il vecchio file con lo stesso UUID in una nuova cartella** è attivata. Ciò implica che quando il file che viene caricato è presente in un’altra cartella nell’archivio, il file esistente viene spostato nella posizione corrente e sovrascritto con il file che viene caricato. Se non si seleziona questa opzione, il file viene sovrascritto nella posizione esistente.

**Note aggiuntive sull&#39;utilizzo dei file basati su UUID**:

Durante lo spostamento o la copia di contenuti all’interno dell’archivio AEM devono essere considerati i seguenti punti:

- Quando si copiano uno o più file da una posizione a un’altra, viene generato un nuovo UUID per i file privi di UUID. Questo UUID viene aggiunto nei metadati del file.

- Se un file presenta un conflitto o un duplicato, viene generato un nome di file univoco per il nuovo file da copiare o spostare.

- Non ci sono due file con lo stesso UUID. A tutti i nuovi file viene assegnato un UUID univoco.


Durante lo spostamento o la copia dei contenuti dal sistema locale all’archivio AEM, è necessario tenere in considerazione i seguenti punti:

- Se un file viene caricato contemporaneamente da due utenti diversi, il file elaborato successivamente sovrascrive quello precedente. Tuttavia, tale pratica è rara e deve essere evitata.

- Quando estrai il contenuto dall’archivio AEM e apporti modifiche sul sistema locale, assicurati che il nome del file non venga modificato al momento del caricamento.


## Usa comandi curl

Puoi anche utilizzare i comandi curl per creare una cartella in DAM, caricare file e aggiungere metadati al contenuto caricato.

**Creare una cartella**

Esegui il comando seguente per creare una cartella nell’archivio AEM:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Specifica i seguenti parametri per creare una cartella:

- `<username>:<passowrd>`: specifica il nome utente e la password per accedere all’archivio AEM. Questo utente deve disporre dei privilegi per la creazione della cartella.

- `jcr:primaryType=sling:Folder`: specifica questo parametro *così com’è* per creare una risorsa di tipo cartella.

- `<server folder path>`: percorso completo della cartella che include il nome della nuova cartella da creare nell’archivio AEM. Ad esempio, se specificate il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, quindi la cartella `AEM-Guides` viene creato all&#39;interno di `projects` cartella in DAM.


**Carica un file**

Esegui il comando seguente per caricare un file nell’archivio AEM:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Specifica i seguenti parametri per caricare un file:

- `<username>:<passowrd>`: specifica il nome utente e la password per accedere all’archivio AEM. Questo utente deve disporre dei privilegi di scrittura su `server folder path`.

- ``local file path``: percorso completo del file sul sistema locale da caricare.

- `<server folder path>`: percorso completo della cartella sul server AEM in cui desideri caricare il file.


**Aggiungi metadati**

Esegui il comando seguente per aggiungere metadati a un file:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Specifica i seguenti parametri per aggiungere informazioni sui metadati:

- `<username>:<passowrd>`: specifica il nome utente e la password per accedere all’archivio AEM. Questo utente deve disporre dei privilegi di scrittura su ``metadata node path``.

- ``-F<attribute name>=<value>``: Il `<attribute name>` è il nome dell’attributo di metadati, ad esempio `audience` e `<value>` potrebbe essere `internal`. È possibile specificare più coppie nome-valore di attributo separate da uno spazio.

- `<metadata node path>`: percorso completo della cartella con il nome del file e il relativo nodo di metadati. Ad esempio, se specificate il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, quindi le informazioni sui metadati specificate vengono impostate su `intro.xml` file.


**Argomento padre:**[ Migrare i contenuti esistenti](migrate-content.md)
