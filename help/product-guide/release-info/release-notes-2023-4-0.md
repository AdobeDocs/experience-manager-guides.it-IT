---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di aprile 2023
description: Versione di aprile 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: fa339eab-d3d0-4763-adbf-6411e39aa213
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/tGOV1IcAL8f2B5ziGWPOMfkkPZGPlxcXSerTtAO3LW0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 602
ht-degree: 2%

---

# Versione di aprile 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di aprile 2023 di Adobe Experience Manager Guides (in seguito denominata *AEM Guides as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, consulta [Novità della versione di aprile 2023 di AEM Guides as a Cloud Service](whats-new-2023-4-0.md).

## Aggiornamento alla versione di aprile 2023

Aggiorna la configurazione corrente di AEM Guides as a Cloud Service eseguendo i seguenti passaggi:

1. Consulta il codice Git dei servizi cloud e passa al ramo configurato nella pipeline dei servizi cloud corrispondente all’ambiente da aggiornare.
2. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei servizi cloud a 2023.4.249.
3. Apporta le modifiche ed esegui la pipeline dei servizi cloud per l’aggiornamento alla versione di aprile 2023 di AEM Guides as a Cloud Service.

## Passaggi per indicizzare il contenuto esistente (solo se utilizzi una versione precedente alla versione di settembre di AEM Guides as a Cloud Service)

Per indicizzare il contenuto esistente e utilizzare il nuovo testo di ricerca e sostituzione a livello di mappa, effettua le seguenti operazioni:

* Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API restituirà un jobId. Per verificare lo stato del processo, puoi inviare una richiesta GET con ID processo allo stesso endpoint: `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Ad esempio: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di AEM Guides as a Cloud Service di aprile 2023.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2,9-uuid-2 | 2,9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |



## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

* PDF nativo | La pubblicazione di contenuti con una classe di output con parentesi() comporta un blocco della pubblicazione. (11596)
* Il problema si verifica quando si sposta (trascina e rilascia) al posto di una voce di elenco esistente con l’opzione Rileva modifiche attivata. (11570)
* Si verifica un problema quando si sposta (trascina e rilascia) come nuova voce di elenco con l’opzione Rileva modifiche attivata. (11569)
* Il rientro o il rientro degli elementi dell&#39;elenco non funziona come previsto con l&#39;opzione Rileva modifiche attivata. (11568)
* L&#39;aggiunta di contenuto su una riga con Revisioni attivate e quindi la disattivazione di Revisioni non ne determina la disattivazione. (11567)
* Difficoltà nel trascinare una voce di elenco, il testo viene spostato al posto della voce di elenco. (11566)
* La revisione completata non si apre in modalità di sola lettura. (11387)
* Il problema si verifica nella ricerca del sito AEM (non funziona oltre i nodi di 2-3 livelli). (11352)
* Durante l’authoring nell’elemento visualizzato in verde (Rileva modifiche), il nuovo contenuto viene visualizzato come revisione anche se la modifica della traccia è disabilitata. (7021)

### Problema noto con la soluzione alternativa

Adobe ha identificato il seguente problema noto per la versione di AEM Guides as a Cloud Service di aprile 2023.

* PDF nativo | I vecchi metadati vengono compilati solo dopo l’apertura esplicita del predefinito di output.
