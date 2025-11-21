---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di marzo 2023
description: Versione di marzo di Adobe Experience Manager Guides as a Cloud Service
exl-id: 6a0bba92-7d7d-4b20-ad46-0eacc91268da
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Versione di marzo 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di marzo 2023 di Adobe Experience Manager Guides (in seguito denominata *AEM Guides as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, consulta [Novità della versione di marzo 2023 di AEM Guides as a Cloud Service](whats-new-2023-3-0.md).

## Aggiornamento alla versione di marzo 2023

Aggiorna la configurazione corrente di AEM Guides as a Cloud Service eseguendo i seguenti passaggi:

1. Consulta il codice Git dei servizi cloud e passa al ramo configurato nella pipeline dei servizi cloud corrispondente all’ambiente da aggiornare.
1. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei servizi cloud a 2023.3.242.
1. Apporta le modifiche ed esegui la pipeline dei servizi cloud per l’aggiornamento alla versione di marzo 2023 di AEM Guides as a Cloud Service.

## Passaggi per indicizzare il contenuto esistente (solo se utilizzi una versione precedente alla versione di settembre di AEM Guides as a Cloud Service)

Per indicizzare il contenuto esistente e utilizzare il nuovo testo di ricerca e sostituzione a livello di mappa, effettua le seguenti operazioni:

* Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate || Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
Ad esempio: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678

* Una volta completato il processo, la richiesta GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di marzo 2023 di AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | Non compatibile | 2022 o versione successiva |
| | | |


### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2,9-uuid-2 | 2,9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

* Il processo di download di PDF non funziona in modo appropriato nell’editor web. (11496)
* Output JSON | La mappatura dei metadati con valore di proprietà come `"value in spaces and double quotes"` genera un errore di pubblicazione. (11438)
* L&#39;inserimento di file multimediali audio e video non riesce nel formato YouTube sotto l&#39;icona **Inserisci file multimediali**. (11320)
* Si verifica un errore di convalida quando si crea una mappa utilizzando il modello che ha un elemento titolo specializzato. (11212)
* PDF nativo | la nota a piè di pagina presente nell’intestazione della tabella porta a un testo in grassetto e allineato al centro nel piè di pagina della pagina corrispondente nell’output di PDF. (10610)
>[!NOTE]
>
>Per riflettere la modifica apportata al PDF nativo, elimina la cartella PDF che si trova in /content/dam/dita-templates e quindi effettua l’aggiornamento alla build più recente. (10610)

### Problema noto con la soluzione alternativa

Adobe ha identificato il seguente problema noto per la versione di AEM Guides as a Cloud Service di marzo 2023.

* Gli utenti non possono salvare o creare la versione di una risorsa duplicata.

**Soluzione**: prima di apportare modifiche alla risorsa duplicata, rielaborala dall&#39;interfaccia utente di Assets.
