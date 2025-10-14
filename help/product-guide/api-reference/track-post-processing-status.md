---
title: API per tenere traccia della post-elaborazione per una cartella o una risorsa
description: Scopri l’API per tenere traccia della post-elaborazione di una cartella o di una risorsa
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 558108650aeeeda440895972e460fa523b804bb2
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 10%

---

# API per tenere traccia dello stato di post-elaborazione di una cartella o di una risorsa

Di seguito è riportato un metodo POST che avvia un processo asincrono per ottenere lo stato delle risorse.

## Trovare lo stato delle risorse nelle guide

**URL richiesta**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status `

**Parametri**

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `path` | Stringa | Sì | Percorso della cartella o della risorsa per cui è necessario recuperare lo stato. |
| `excludedPaths` | Stringa | No | Percorsi di cartelle da escludere dall’elenco precedente. |

```JSON
{ 

    "paths": [ 

        "/content/dam/status-fetch1", 

        "/content/dam/status-fetch2" 

    ], 

    "excludedPaths": [ 

        "content/dam/status-fetch1/excluded-folder" 

    ] 

} 
```

**Valori risposta**
jobId su cui eseguire il polling per ottenere lo stato del processo asincrono.

```JSON
{ 

  "jobId": "akjhdfalkj1132", 

  "status": "WAITING", 

 

} 
```

## API poller

Un metodo GET che ottiene lo stato del processo asincrono eseguito dall’API precedente.

**URL richiesta**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status`

**Parametri**

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `jobId` | Stringa | Sì | ID processo restituito dall&#39;API precedente. |

**Valori risposta**

Elenco delle risorse e relativo stato.

```JSON
{ 

  "jobId": " akjhdfalkj1132", 

  "status": "SUCCESS", 

  "assets": [ 

    { 

      "path": "/content/dam/status-fetch1/a.dita", 

      "uuid": "GUID-1293914ansd", 

      "status": "SUCCESS", 

      "exists": true 

    }, 

    { 

      "path": "/content/dam/status-fetch1/b.dita", 

      "uuid": "GUID-1883241", 

      "status": "FAILURE", 

      "exists": true 

    } 

 

  ] 

} 
```

**Valori di stato:** OPERAZIONE RIUSCITA, ERRORE, ELABORAZIONE, IN SOSPESO
