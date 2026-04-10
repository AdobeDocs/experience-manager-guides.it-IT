---
title: Usa comandi curl
description: Scopri come utilizzare i comandi curl sui contenuti caricati in Experience Manager Guides.
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 1%

---

# Usa comandi curl

Puoi anche utilizzare i comandi curl per creare una cartella in DAM, caricare file e aggiungere metadati al contenuto caricato.

## Crea una cartella

Esegui il seguente comando per creare una cartella nel repository di AEM:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Specifica i seguenti parametri per creare una cartella:

- `<username>:<passowrd>`: specificare il nome utente e la password per accedere all&#39;archivio AEM. Questo utente deve disporre dei privilegi per la creazione della cartella.

- `jcr:primaryType=sling:Folder`: specificare il parametro *in quanto è* per creare una risorsa di tipo cartella.

- `<server folder path>`: percorso completo della cartella, incluso il nome della nuova cartella che si desidera creare nell&#39;archivio AEM. Ad esempio, se si specifica il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, la cartella `AEM-Guides` viene creata all&#39;interno della cartella `projects` in DAM.


## Carica un file

Esegui il comando seguente per caricare un file nell’archivio AEM:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Specifica i seguenti parametri per caricare un file:

- `<username>:<passowrd>`: specificare il nome utente e la password per accedere all&#39;archivio AEM. Questo utente deve disporre dei privilegi di scrittura su `server folder path`.

- ``local file path``: percorso completo del file nel sistema locale da caricare.

- `<server folder path>`: percorso completo della cartella sul server AEM in cui desideri caricare il file.


## Aggiungi metadati

Esegui il comando seguente per aggiungere metadati a un file:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Specifica i seguenti parametri per aggiungere informazioni sui metadati:

- `<username>:<passowrd>`: specificare il nome utente e la password per accedere all&#39;archivio AEM. Questo utente deve disporre dei privilegi di scrittura su ``metadata node path``.

- ``-F<attribute name>=<value>``: `<attribute name>` è il nome dell&#39;attributo di metadati, ad esempio `audience`, e `<value>` potrebbe essere `internal`. È possibile specificare più coppie nome-valore di attributo separate da uno spazio.

- `<metadata node path>`: percorso completo della cartella, incluso il nome del file e il relativo nodo di metadati. Ad esempio, se si specifica il percorso come `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, le informazioni sui metadati specificate vengono impostate sul file `intro.xml`.