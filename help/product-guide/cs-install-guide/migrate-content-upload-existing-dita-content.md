---
title: Carica contenuto DITA esistente
description: Scopri come caricare contenuto DITA esistente
exl-id: 2b385eef-00a7-4c25-9e78-367a0c9e44ba
feature: Migration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/oVLPpwMXyeRGo-1QO553dthsza05mbnRIedaIYpQ1Vg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 511
ht-degree: 0%

---

# Carica contenuto DITA esistente {#id176FF000JUI}

Probabilmente si dispone di un archivio di contenuti DITA esistenti che si desidera utilizzare con AEM Guides. Per tali contenuti esistenti, puoi utilizzare uno qualsiasi dei metodi supportati illustrati in [Aggiungere risorse digitali ad Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=it).

## Configura pattern nome file UUID

Quando importi il contenuto, non è necessario che i nomi dei file siano basati sull’UUID. In un sistema che utilizza nomi di file basati su UUID, è obbligatorio fare riferimento a tutti i file utilizzando i loro UUID anziché i nomi di file originali. Se un file importato non ha nomi di file basati su UUID, potete configurare il sistema per aggiungere un UUID alle proprietà del file. Questo UUID viene quindi utilizzato per fare riferimento a tali file dove UUID non viene utilizzato per la denominazione dei file.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare il pattern del nome file UUID:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Stringa che specifica il regex per il pattern del nome file UUID. <br> Se un file non segue il pattern specificato, viene aggiunto un UUID alla proprietà del file e tutti i riferimenti al file vengono aggiornati con l’UUID assegnato al file. <br> **Valore predefinito**: `"^GUID-(?<id>.*)"` |

## Usa comandi curl

Puoi anche utilizzare i comandi curl per creare una cartella in DAM, caricare file e aggiungere metadati al contenuto caricato.

**Crea una cartella**

Esegui il seguente comando per creare una cartella nel repository di AEM:

```
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Specifica i seguenti parametri per creare una cartella:

- `<username>:<passowrd>`: specificare il nome utente e la password per accedere all&#39;archivio AEM. Questo utente deve disporre dei privilegi per la creazione della cartella.

- `jcr:primaryType=sling:Folder`: specificare il parametro *in quanto è* per creare una risorsa di tipo cartella.

- `<server folder path>`: percorso completo della cartella, incluso il nome della nuova cartella che si desidera creare nell&#39;archivio AEM. Ad esempio, se si specifica il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, la cartella `AEM-Guides` viene creata all&#39;interno della cartella `projects` in DAM.


**Carica un file**

Esegui il comando seguente per caricare un file nell’archivio AEM:

```
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Specifica i seguenti parametri per caricare un file:

- `<username>:<passowrd>`: specificare il nome utente e la password per accedere all&#39;archivio AEM. Questo utente deve disporre dei privilegi di scrittura su `server folder path`.

- ``local file path``: percorso completo del file nel sistema locale da caricare.

- `<server folder path>`: percorso completo della cartella sul server AEM in cui desideri caricare il file.


**Aggiungi metadati**

Esegui il comando seguente per aggiungere metadati a un file:

```
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Specifica i seguenti parametri per aggiungere informazioni sui metadati:

- `<username>:<passowrd>`: specificare il nome utente e la password per accedere all&#39;archivio AEM. Questo utente deve disporre dei privilegi di scrittura su ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` è il nome dell&#39;attributo di metadati, ad esempio `audience`, e `<value>` potrebbe essere `internal`. È possibile specificare più coppie nome-valore di attributo separate da uno spazio.

- `<metadata node path>`: percorso completo della cartella, incluso il nome del file e il relativo nodo di metadati. Ad esempio, se si specifica il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, le informazioni sui metadati specificate vengono impostate sul file `intro.xml`.


**Argomento padre:**&#x200B;[&#x200B; Esegui migrazione contenuto esistente](migrate-content.md)
