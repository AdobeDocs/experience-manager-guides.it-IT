---
title: Creare progetto di traduzione
description: Scopri come creare un progetto di traduzione API
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 41dd3dee5f9d64fb5c58b5b302cc9759e48e3631
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 17%

---

# Creare progetto di traduzione

Un metodo POST che consente di creare un progetto di traduzione accettando i dettagli di progetto richiesti.

## URL richiesta

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/create`

## Tipo di richiesta

POST

## Parametri di richiesta

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `type` | Stringa | newTranslationProject, xliffTranslationProject, newMultiLingualTranslationProject, addToExistingProject, newScopingTranslationProject |
| `versionDetails`, `versionSelector` | Stringa | Baseline, latestVersion, versionAsOfDate |
| `language` | Stringa | Lingue separate da virgola &quot;de&quot;, &quot;fr&quot; |
| `map.id` | Stringa | GUID della mappa di origine da tradurre |
| `map.path` | Stringa | Percorso della mappa sorgente da tradurre |
| `referenceType` | Stringa | Indiretto, diretto |
| `fileType` | Stringa | Mappa, Argomento, Altri |
| `documentState` | Stringa | può essere uno degli elenchi assegnati dall’utente sul profilo della mappa |
| `translationStatus` | Stringa | Non sincronizzato, Sincronizzato, Aggiornato, Non aggiornato, In corso, Copia mancante, NESSUNO, N/D |

>[!NOTE]
>
>È possibile utilizzare `map.id` o `map.path` durante la creazione di un progetto di traduzione.

## Esempio di richiesta

```JSON
{
  "title": "Test Project 1 on Dec 5",
  "type": "newTranslationProject",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en",
      "path": "/content/dam/ajay-test/lang/en/m2.ditamap"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "latestVersion"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
   ]
```

## Valori di risposta

```JSON
{
  "executionId": "5c13c571-3407-46d5-8f45-50ea9e05a212",
  "path": "/content/projects/test_project_1_ondec5"
}
```

**Codici di risposta**

- 200 riuscito
- 400 Input non valido
- 401 Accesso non autorizzato
- Errore interno del server 500

## Richieste di esempio

### Aggiungi a progetto esistente

```json
{
  "title": "Add to existing Project",
  "type": "addToExistingProject",
  "path": "/content/projects/test_project_1_existing",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "versionAsOfDate",
      "version": "2025-12-05T10:30:00+01:30"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

### Aggiungi a progetto esistente con linea di base

```json
{
  "title": "Add to existin project Project with baseline",
  "type": "addToExistingProject",
  "path": "/content/projects/existing_project_path",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "baseline",
      "version": "test1"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": ["Direct"] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

## Stato della creazione del progetto di traduzione

API GET che tiene traccia dello stato di traduzione per un progetto di traduzione appena creato.

## URL richiesta

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/creationstatus`

## Tipo di richiesta

GET

## Parametri di richiesta

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `path` | Stringa | Percorso del progetto |
| `languageStatusMap` | Stringa | Per ogni lingua richiesta, restituisce lo stato di completamento: In corso, Completato, Non riuscito, Ignorato |


## Esempio di richiesta

```json
{
  "path": "/content/projects/test_project_1_ondec5",
  "languageStatusMap": {
    "de": "Completed"
  }
}
```



