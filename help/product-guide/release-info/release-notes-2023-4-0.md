---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di aprile 2023
description: Versione di aprile 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: fa339eab-d3d0-4763-adbf-6411e39aa213
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# Versione di aprile 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di aprile 2023 di Adobe Experience Manager Guides (in seguito denominata *AEM Guides as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, consulta [Novità della versione di aprile 2023 di AEM Guides as a Cloud Service](whats-new-2023-4-0.md).

## Aggiornamento alla versione di aprile 2023

Aggiorna la configurazione corrente di AEM Guides as a Cloud Service eseguendo i seguenti passaggi:

1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
2. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei Cloud Service in 2023.4.249.
3. Apporta le modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione di aprile 2023 di AEM Guides as a Cloud Service.

## Passaggi per indicizzare il contenuto esistente (solo se utilizzi una versione precedente alla versione di settembre di AEM Guides as a Cloud Service)

Per indicizzare il contenuto esistente e utilizzare il nuovo testo di ricerca e sostituzione a livello di mappa, effettua le seguenti operazioni:

* Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate || Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Ad esempio: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Una volta completato il processo, la richiesta di GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

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
|  |  |  |  |



## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

* Native PDF | La pubblicazione di contenuti con una classe di output con parentesi() comporta un blocco della pubblicazione. (11596)
* Il problema si verifica quando si sposta (trascina e rilascia) al posto di una voce di elenco esistente con l’opzione Rileva modifiche attivata. (11570)
* Si verifica un problema quando si sposta (trascina e rilascia) come nuova voce di elenco con l’opzione Rileva modifiche attivata. (11569)
* Il rientro o il rientro degli elementi dell&#39;elenco non funziona come previsto con l&#39;opzione Rileva modifiche attivata. (11568)
* L&#39;aggiunta di contenuto su una riga con Revisioni attivate e quindi la disattivazione di Revisioni non ne determina la disattivazione. (11567)
* Difficoltà nel trascinare una voce di elenco, il testo viene spostato al posto della voce di elenco. (11566)
* La revisione completata non si apre in modalità di sola lettura. (11387)
* Il problema si verifica nella ricerca del sito AEM (non funziona oltre i nodi di 2-3 livelli). (11352)
* Durante l’authoring nell’elemento visualizzato in verde (Rileva modifiche), il nuovo contenuto viene visualizzato come revisione anche se la modifica della traccia è disabilitata. (7021)

### Problema noto con la soluzione alternativa

L’Adobe ha identificato il seguente problema noto per la versione di AEM Guides as a Cloud Service di aprile 2023.

* Native PDF | I vecchi metadati vengono compilati solo dopo l’apertura esplicita del predefinito di output.
