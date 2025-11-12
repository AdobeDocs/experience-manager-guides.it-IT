---
title: API per avviare l’elaborazione in blocco delle risorse
description: Scopri l’API per avviare l’elaborazione in blocco delle risorse
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: e2eca63a5dd56e358aeea047b37f4b0f88dc720b
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 8%

---

# API per avviare l’elaborazione in blocco delle risorse

Metodo POST che avvia l&#39;elaborazione in blocco delle risorse per un percorso specificato. Questa API supporta sia l’elaborazione delle risorse basata su JCR che quella basata su database. Avvia un processo asincrono che elabora tutte le risorse sotto il percorso specificato e i relativi percorsi secondari. Al momento dell’avvio, l’API restituisce un processingID univoco che può essere utilizzato per monitorare lo stato del processo.

**URL richiesta**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process`

**Parametri richiesta**

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `path` | Stringa | Sì | Percorso assoluto della cartella o risorsa nell’archivio AEM da elaborare. |
| `excludedPaths` | Stringa | No | Elenco dei percorsi da escludere dall’elaborazione |
| `type` | Stringa | Sì | Tipo di elaborazione da eseguire. Ad esempio: ASSET_PROCESSING. |

**Esempio di richiesta**

```JSON
{
  "path": "/content/dam/status-fetch1",
  "excludedPaths": [
    "content/dam/status-fetch1/excluded-folder"
  ],
  "type": "ASSET_PROCESSING"
}
```

**Valori risposta**

processingId per il polling e ottenere lo stato del processo asincrono.

```JSON
{
  "processingId": "akjhdfalkj1132"
}
```

**Codici di risposta**

- 200 riuscito
- 400 Input non valido
- 401 Accesso non autorizzato
- Errore interno del server 500

## Verifica stato processo

Metodo GET che recupera lo stato corrente di un processo di elaborazione di risorse avviato in precedenza.

**URL richiesta**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/status`

**Parametri richiesta**

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `processingId` | Stringa | Sì | ID univoco del processo di cui viene eseguito il query sullo stato. |

**Esempio di risposta**

```JSON
{
  "processingId": "string",
  "path": "string",
  "excludedPaths": ["string"],
  "status": "WAITING",
  "triggeredCount": 0,
  "startedAt": 0,
  "completedAt": 0,
  "hasLogs": true,
  "createdBy": "string",
  "type": "ASSET_PROCESSING",
  "migrationSet": {
    "totalFiles": 0,
    "calculationStatus": "WAITING"
  },
  "eta": {
    "value": 0,
    "unit": "string"
  },
  "comments": "string",
  "restartable": true,
  "resumable": true,
  "cancellable": true
}
```

**Codici di risposta**

- 200 riuscito
- 400 Input non valido
- 401 Accesso non autorizzato
- Errore interno del server 500

## Visualizza registri di processo

Un metodo GET che recupera i registri per un determinato ID processo. Questa API recupera i registri del processo di elaborazione delle risorse. L’ID elaborazione è obbligatorio. L’API fornisce parametri di offset e limite, nonché una strategia di code.

**URL richiesta**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs`

**Parametri richiesta**

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `processingId` | Stringa | Sì | ID univoco del processo di cui devono essere visualizzati i registri. |
| `offset` | Numero intero | No | Punto iniziale (numero di riga) da cui leggere i registri. Utilizzato per l’impaginazione per saltare le prime N righe. |
| `limit` | Numero intero | No | Numero massimo di righe di registro da recuperare. |
| `tail` | Numero intero | No | Numero di righe di registro da recuperare dalla fine. |


**Esempio di risposta**

```JSON
{
  "lines": [
    "string"
  ],
  "limit": 0,
  "offset": 0,
  "hasMore": true
}
```

**Codici di risposta**

- 200 riuscito
- 400 Input non valido
- 401 Accesso non autorizzato
- 500 Errore interno del server


## Scarica registri di processo

Un metodo GET che scarica il file di registro per un determinato processo come file ZIP.

**URL richiesta**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs/download`

**Parametri richiesta**

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `processingId` | Stringa | Sì | ID univoco del processo di cui deve essere scaricato il file di registro. |


**Esempio di risposta**

```JSON
{
  "logFilePaths": [
    "string"
  ]
}
 
```

**Codici di risposta**

- 400 Input non valido
- 401 Accesso non autorizzato
- 500 Errore interno del server

## Annulla processo

API POST che annulla una richiesta di elaborazione in blocco di risorse in corso. Se il processo non viene trovato, l’API restituisce un errore.

**URL richiesta**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/cancel`

**Parametri richiesta**

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `processingId` | Stringa | Sì | ID univoco del processo di cui viene eseguito il query sullo stato. |


**Codici di risposta**

- 200 riuscito
- 400 Input non valido
- 401 Accesso non autorizzato
- 500 Errore interno del server


## Riprendi processo

API POST che riavvia una richiesta di elaborazione in blocco di risorse precedentemente annullata o non riuscita. Riprende l’elaborazione dall’ultimo punto di controllo. Se il processo non viene trovato o è attualmente in esecuzione, l’API restituisce un errore.

**URL richiesta**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/resume`

**Parametri richiesta**

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `processingId` | Stringa | Sì | ID univoco del processo di cui viene eseguito il query sullo stato. |


**Codici di risposta**

- 200 riuscito
- 400 Input non valido
- 401 Accesso non autorizzato
- 500 Errore interno del server

## Visualizza cronologia processo

Un’API GET che restituisce le ultime &quot;N&quot; esecuzioni del post-elaborazione delle risorse.

**URL richiesta**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/history`

**Parametri richiesta**

Nessuno. Questa richiesta GET recupera la cronologia dei processi senza richiedere parametri di input.

**Esempio di risposta**

```JSON
{
  "executionHistory": [
    {
      "processingId": "165f1de6-68c4-4dcd-9223-2b7242b62306",
      "path": "/content/dam/22858",
      "status": "SUCCESS",
      "triggeredCount": 6,
      "startedAt": 1761291362776,
      "completedAt": 1761291364026,
      "hasLogs": true,
      "createdBy": "user",
      "type": "ASSET_PROCESSING",
      "migrationSet": {
        "totalFiles": 6,
        "calculationStatus": "SUCCESS"
      },
      "eta": {
        "value": 0,
        "unit": "SECONDS"
      },
      "comments": "",
      "filter": {
        "fileTypes": [],
        "filterProcessedAssets": false
      },
      "cancellable": false,
      "resumable": false,
      "restartable": true
    }
  ]
}
```



