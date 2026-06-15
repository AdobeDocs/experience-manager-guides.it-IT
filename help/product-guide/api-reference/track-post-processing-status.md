---
title: API per tenere traccia della post-elaborazione per una cartella o una risorsa
description: Scopri l’API per tenere traccia della post-elaborazione di una cartella o di una risorsa
feature: Post-Processing Event Handler
role: Developer
level: Experienced
exl-id: f902fac1-2717-4696-a835-c4b0bb8add3d
TQID: https://experienceleague.adobe.com/Lyv-S5o-Z40bMqqIHhbxKrsmn9CCqHRnqnpiq91EjGU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 1d80ca88a3a6637a118657367b86b499675f6d0e
workflow-type: tm+mt
source-wordcount: 150
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

**Valori di risposta**
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
