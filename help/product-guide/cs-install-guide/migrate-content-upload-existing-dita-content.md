---
title: Carica contenuto DITA esistente
description: Scopri come caricare contenuto DITA esistente
exl-id: 2b385eef-00a7-4c25-9e78-367a0c9e44ba
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Carica contenuto DITA esistente {#id176FF000JUI}

È molto probabile che si disponga di un archivio di contenuti DITA esistenti che si desidera utilizzare con le guide AEM. Per tali contenuti esistenti, puoi utilizzare uno qualsiasi dei metodi supportati descritti in [Aggiungere risorse digitali alle risorse Adobe Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html).

## Configura pattern nome file UUID

Quando importi il contenuto, non è necessario che i nomi dei file siano basati sull’UUID. In un sistema che utilizza nomi di file basati su UUID, è obbligatorio fare riferimento a tutti i file utilizzando i loro UUID anziché i nomi di file originali. Se un file importato non ha nomi di file basati su UUID, potete configurare il sistema per aggiungere un UUID alle proprietà del file. Questo UUID viene quindi utilizzato per fare riferimento a tali file dove UUID non viene utilizzato per la denominazione dei file.

Utilizzare le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare il pattern del nome file UUID:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Stringa che specifica il regex per il pattern del nome file UUID. <br> Se un file non segue il pattern specificato, viene aggiunto un UUID alla proprietà del file e tutti i riferimenti al file vengono aggiornati con l’UUID assegnato al file. <br> **Valore predefinito**: `"^GUID-(?<id>.*)"` |

## Usa comandi curl

Puoi anche utilizzare i comandi curl per creare una cartella in DAM, caricare file e aggiungere metadati al contenuto caricato.

**Creare una cartella**

Esegui il comando seguente per creare una cartella nell’archivio AEM:

```
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Specifica i seguenti parametri per creare una cartella:

- `<username>:<passowrd>`: specifica il nome utente e la password per accedere all’archivio AEM. Questo utente deve disporre dei privilegi per la creazione della cartella.

- `jcr:primaryType=sling:Folder`: specifica questo parametro *così com’è* per creare una risorsa di tipo cartella.

- `<server folder path>`: percorso completo della cartella che include il nome della nuova cartella da creare nell’archivio AEM. Ad esempio, se specificate il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, quindi la cartella `AEM-Guides` viene creato all&#39;interno di `projects` cartella in DAM.


**Carica un file**

Esegui il comando seguente per caricare un file nell’archivio AEM:

```
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Specifica i seguenti parametri per caricare un file:

- `<username>:<passowrd>`: specifica il nome utente e la password per accedere all’archivio AEM. Questo utente deve disporre dei privilegi di scrittura su `server folder path`.

- ``local file path``: percorso completo del file sul sistema locale da caricare.

- `<server folder path>`: percorso completo della cartella sul server AEM in cui desideri caricare il file.


**Aggiungi metadati**

Esegui il comando seguente per aggiungere metadati a un file:

```
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Specifica i seguenti parametri per aggiungere informazioni sui metadati:

- `<username>:<passowrd>`: specifica il nome utente e la password per accedere all’archivio AEM. Questo utente deve disporre dei privilegi di scrittura su ``metadata node path``.

- ``-F<attribute name>=<value>``: Il `<attribute name>` è il nome dell’attributo di metadati, ad esempio `audience` e `<value>` potrebbe essere `internal`. È possibile specificare più coppie nome-valore di attributo separate da uno spazio.

- `<metadata node path>`: percorso completo della cartella con il nome del file e il relativo nodo di metadati. Ad esempio, se specificate il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, quindi le informazioni sui metadati specificate vengono impostate su `intro.xml` file.


**Argomento padre:**[ Migrare i contenuti esistenti](migrate-content.md)
