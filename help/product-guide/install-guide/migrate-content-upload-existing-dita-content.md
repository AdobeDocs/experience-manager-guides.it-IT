---
title: Carica contenuto DITA esistente
description: Scopri come caricare contenuto DITA esistente
exl-id: 1dde8a29-301f-461e-b598-2a8cab61bf3d
feature: Migration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/pO-gEvrIl6z-bKvz7IKEW49YXDi6tFE-8CUxxDULH0c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1209
ht-degree: 0%

---

# Carica contenuto DITA esistente {#id176FF000JUI}

Probabilmente si dispone di un archivio di contenuti DITA esistenti che si desidera utilizzare con AEM Guides. Per tali contenuti esistenti, puoi utilizzare uno dei seguenti approcci per caricare in blocco i contenuti nell’archivio AEM.

## Utilizzare uno strumento WebDAV

Se si creano argomenti e mappe in qualsiasi altro editor DITA, è possibile utilizzare qualsiasi strumento WebDAV per caricare i file. La procedura descritta in questa sezione utilizza WinSCP come strumento WebDAV per caricare contenuti.

Per utilizzare WinSCP per caricare i file, effettuare le seguenti operazioni:

1. Scarica e installa WinSCP sul computer.

1. Avvia l&#39;app WinSCP.

   Viene visualizzata la finestra di dialogo Login (Accesso).

1. Nella finestra di dialogo Accesso specificare un&#39;impostazione Nuovo sito scegliendo WebDAV come **File Protocol** e fornendo altri dettagli di connessione, ad esempio:

   - l’URL in cui è ospitato il server AEM,

   - il numero di porta \(il valore predefinito è 4502\) e

   - il nome utente e la password per accedere al server AEM.

1. Fai clic su **Accedi**.

   Una volta stabilita la connessione, nell&#39;interfaccia utente WinSCP verranno visualizzati i contenuti di AEM Assets. È possibile sfogliare, creare, aggiornare o eliminare facilmente il contenuto utilizzando Esplora file WinSCP.


## Usa FrameMaker

Adobe FrameMaker viene fornito con un potente connettore AEM che consente di caricare facilmente in AEM i documenti DITA e FrameMaker esistenti \(.book e .fm\). Puoi utilizzare varie funzionalità di caricamento dei file, ad esempio il caricamento di un singolo file e di una cartella completa con o senza dipendenze \(come riferimenti a contenuti, riferimenti incrociati e elementi grafici\).

Per utilizzare il connettore AEM di FrameMaker per caricare il contenuto, effettua le seguenti operazioni:

1. Avvia FrameMaker.

1. Aprire la finestra di dialogo **Connection Manager**.

   ![](assets/fm-aem-connector.png){width="550"}

1. Immetti i seguenti dettagli per connetterti al repository di AEM:

   - **Nome**: immetti un nome descrittivo per identificare la connessione al server AEM.
   - **Server**: immettere l&#39;URL e il numero di porta del server AEM.

   - **Nome utente**/**Password**: immettere il nome utente e la password per accedere al server AEM.

1. Fai clic su **Connetti**.

   Una volta stabilita la connessione, Assets dall’archivio AEM viene visualizzato nella finestra Gestione archivio.

   ![](assets/fm-repo-manager.png){width="550"}

   Facendo clic con il pulsante destro del mouse su un file o una cartella è possibile eseguire operazioni correlate. Ad esempio, se fai clic con il pulsante destro del mouse su una cartella, ottieni le opzioni per caricare un file, caricare un file con dipendenze, caricare un’intera cartella e così via.


## Configura pattern nome file UUID

Quando importi il contenuto, non è necessario che i nomi dei file siano basati sull’UUID. In un sistema che utilizza nomi di file basati su UUID, è obbligatorio fare riferimento a tutti i file utilizzando i loro UUID anziché i nomi di file originali. Se un file importato non ha nomi di file basati su UUID, potete configurare il sistema per aggiungere un UUID alle proprietà del file. Questo UUID viene quindi utilizzato per fare riferimento a tali file dove UUID non viene utilizzato per la denominazione dei file.

Effettua le seguenti operazioni per controllare i nomi dei file in base a un pattern UUID e assegnare UUID ai file a cui non è stato assegnato un UUID:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle *com.adobe.fmdita.config.ConfigManager*.

1. Nella proprietà **UUID Filename Patterns**, specifica un pattern per verificare i nomi del file importato.

   Se un file non segue il pattern specificato, viene aggiunto un UUID alla proprietà del file e tutti i riferimenti al file vengono aggiornati con l’UUID assegnato al file.

1. Fai clic su **Salva**.


## Caricare contenuti con UUID utilizzando uno strumento WebDav {#id201MI0I04Y4}

Per caricare il contenuto con UUID, puoi utilizzare uno dei seguenti metodi:

- Trascinare i contenuti dal sistema locale.
- Utilizza il flusso di lavoro **Crea** \> **File** dall&#39;interfaccia utente Assets di AEM.
- Utilizza uno strumento come WinSCP.

Se si utilizza uno strumento come WinSCP, è possibile definire l&#39;azione da eseguire su un file duplicato impostando l&#39;opzione **Sposta il file precedente con lo stesso UUID in una nuova cartella** in configMgr. Questa opzione definisce l’azione eseguita su un file disponibile in un’altra posizione nell’archivio AEM. Questa impostazione è disponibile nel bundle *com.adobe.fmdita.config.ConfigManager* in configMgr.

Per impostazione predefinita, l&#39;opzione **Sposta il vecchio file con lo stesso UUID in una nuova cartella** è attivata. Ciò implica che quando il file che viene caricato è presente in un’altra cartella nell’archivio, il file esistente viene spostato nella posizione corrente e sovrascritto con il file che viene caricato. Se non si seleziona questa opzione, il file viene sovrascritto nella posizione esistente.

**Note aggiuntive sull&#39;utilizzo dei file basati su UUID**:

Durante lo spostamento o la copia di contenuti nell’archivio AEM, è necessario tenere in considerazione i seguenti punti:

- Quando si copiano uno o più file da una posizione a un’altra, viene generato un nuovo UUID per i file privi di UUID. Questo UUID viene aggiunto nei metadati del file.

- Se un file presenta un conflitto o un duplicato, viene generato un nome di file univoco per il nuovo file da copiare o spostare.

- Non ci sono due file con lo stesso UUID. A tutti i nuovi file viene assegnato un UUID univoco.


Durante lo spostamento o la copia del contenuto dal sistema locale all’archivio AEM, è necessario tenere in considerazione i seguenti punti:

- Se un file viene caricato contemporaneamente da due utenti diversi, il file elaborato successivamente sovrascrive quello precedente. Tuttavia, tale pratica è rara e deve essere evitata.

- Quando estrai il contenuto dall’archivio di AEM e apporti modifiche sul sistema locale, assicurati che il nome del file non venga modificato al momento del caricamento.


## Usa comandi curl

Puoi anche utilizzare i comandi curl per creare una cartella in DAM, caricare file e aggiungere metadati al contenuto caricato.

**Crea una cartella**

Esegui il seguente comando per creare una cartella nel repository di AEM:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Specifica i seguenti parametri per creare una cartella:

- `<username>:<passowrd>`: specificare il nome utente e la password per accedere all&#39;archivio AEM. Questo utente deve disporre dei privilegi per la creazione della cartella.

- `jcr:primaryType=sling:Folder`: specificare il parametro *in quanto è* per creare una risorsa di tipo cartella.

- `<server folder path>`: percorso completo della cartella, incluso il nome della nuova cartella che si desidera creare nell&#39;archivio AEM. Ad esempio, se si specifica il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, la cartella `AEM-Guides` viene creata all&#39;interno della cartella `projects` in DAM.


**Carica un file**

Esegui il comando seguente per caricare un file nell’archivio AEM:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Specifica i seguenti parametri per caricare un file:

- `<username>:<passowrd>`: specificare il nome utente e la password per accedere all&#39;archivio AEM. Questo utente deve disporre dei privilegi di scrittura su `server folder path`.

- ``local file path``: percorso completo del file nel sistema locale da caricare.

- `<server folder path>`: percorso completo della cartella sul server AEM in cui desideri caricare il file.


**Aggiungi metadati**

Esegui il comando seguente per aggiungere metadati a un file:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Specifica i seguenti parametri per aggiungere informazioni sui metadati:

- `<username>:<passowrd>`: specificare il nome utente e la password per accedere all&#39;archivio AEM. Questo utente deve disporre dei privilegi di scrittura su ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` è il nome dell&#39;attributo di metadati, ad esempio `audience`, e `<value>` potrebbe essere `internal`. È possibile specificare più coppie nome-valore di attributo separate da uno spazio.

- `<metadata node path>`: percorso completo della cartella, incluso il nome del file e il relativo nodo di metadati. Ad esempio, se si specifica il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, le informazioni sui metadati specificate vengono impostate sul file `intro.xml`.


**Argomento padre:**&#x200B;[&#x200B; Esegui migrazione contenuto esistente](migrate-content.md)
