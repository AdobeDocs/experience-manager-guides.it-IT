---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di febbraio 2023
description: Versione di febbraio di Adobe Experience Manager Guides as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 0%

---

# Versione di febbraio 2023 di Adobe Experience Manager Guides as a Cloud Service

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione di febbraio 2023 di Adobe Experience Manager Guides (in seguito denominata *AEM Guides as a Cloud Service*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, consulta [Novità della versione di febbraio 2023 di AEM Guides as a Cloud Service](whats-new-2023-2-0.md).

## Aggiornamento alla versione di febbraio 2023

Aggiorna la configurazione corrente di AEM Guides as a Cloud Service eseguendo i seguenti passaggi:
1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
2. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei Cloud Service in 2023.2.235.
3. Apporta le modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione di febbraio 2023 di AEM Guides as a Cloud Service.

## Passaggi per indicizzare il contenuto esistente (solo se utilizzi una versione precedente alla versione di settembre di AEM Guides as a Cloud Service)

Effettua le seguenti operazioni per indicizzare il contenuto esistente e utilizzare il nuovo testo Trova e sostituisci a livello di mappa:

* Eseguire una richiesta POST al server (con autenticazione corretta) - `http://<server:port>/bin/guides/map-find/indexing`.
(Facoltativo: Puoi trasmettere percorsi specifici delle mappe per indicizzarle; per impostazione predefinita, tutte le mappe saranno indicizzate || Esempio: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* L’API restituirà un jobId. Per verificare lo stato del processo, è possibile inviare una richiesta GET con ID processo allo stesso endpoint - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Ad esempio: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Una volta completato il processo, la richiesta di GET di cui sopra risponderà con successo e menzionerà se eventuali mappe non sono riuscite. Le mappe indicizzate correttamente possono essere confermate dai registri del server.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di febbraio 2023 di AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di AEM Guides as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Non compatibile | 2022 o versione successiva |
| | | |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2,8-uuid-8 | 2,8-uuid-8 | 2,3 | 2,3 |
|  |  |  |  |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

* Le modifiche nell&#39;html dell&#39;editor Web causano problemi con `<dl>` e `<dlentry>`. (11024)
* Alcuni attributi non vengono trattati come condizionali e causano problemi. (10895)
* Tre o più livelli nidificati `<indexterm>` non sono nidificati nell&#39;esportazione nativa di PDF. (10799)
* Il contenuto scompare nel corpo di un’attività quando si passa dalla visualizzazione Autore a quella Source. (10735)
* I commenti di revisione non vengono inseriti correttamente in un&#39;attività di revisione. (10625)
* **Annulla** o **Ripristina** non funziona correttamente su alcuni file. (10373)
* I metadati personalizzati non vengono mantenuti durante l’azione di copia e incolla. (10367)
* L&#39;opzione Annulla nell&#39;editor XML consente di portare l&#39;utente nella parte superiore della pagina. (10091)
* Le proprietà del nodo vengono rimosse dopo l’operazione di copia e incolla di una risorsa. (10053)
* mimeType è codificato per la creazione e l’aggiornamento di risorse DITA. (8979)
* Il nome dell’autore della versione nella Cronologia versioni è &quot;fmdita-serviceuser&quot; per i file caricati tramite l’interfaccia utente di Assets. (8910)
* I frammenti di contenuto non possono essere copiati e incollati quando AEM Guides è installato su Cloud. (11315)
* Il browser (Editor Web) non è in grado di caricare contenuti con uno schema personalizzato. (11211)

### Gestione

* Copiare una risorsa mappa DITA (dall’interfaccia utente di Asset ) causa l’esistenza di linee di base errate nella risorsa copiata. (11218)
* Non viene visualizzato alcun messaggio di avvertenza al caricamento di un file che supera il limite consentito dall’AEM (2 GB per impostazione predefinita). (10817)
* Web Editor-Baseline | Il comportamento della colonna Più recente nel dashboard della nuova linea di base all&#39;interno dell&#39;editor Web è diverso. (10808)
* Traduzione | Il processo di traduzione non viene avviato a causa di /libs/fmdita/i18n/ja.json non valido. (10543)
* Traduzione | Si verifica un errore in un progetto di traduzione dell’ambito creato dal dashboard di traduzione (Traduzione umana). (10526)
* Traduzione | L’elaborazione Post è bloccata per l’intera cartella lingua le cui risorse sono presenti in un progetto di traduzione attivo. (10332)
* Se la versione viene modificata e salvata nell’editor della linea di base, per qualsiasi risorsa vengono visualizzati più pop-up. (10399)
* La perdita della sessione si verifica alle `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Pubblicazione

* La rigenerazione dell&#39;argomento non funziona per alcuni scenari. (10635)
* Publishlistener non visualizza i dati richiesti nei registri di informazioni e contiene anche alcuni registri di posta indesiderata.( 10567)
* Native PDF | Quando si crea un predefinito di output con l’opzione &quot;Aggiungi al profilo cartella&quot;, la generazione di PDF non riesce e viene generata un’eccezione Null Pointer. (10950)
* Native PDF | Si verificano dei problemi durante la rotazione dell’intestazione della tabella. (10555)
* Native PDF | `<indexterm>` nidificati non sono nidificati nell&#39;esportazione nativa di PDF. (10521)
* Native PDF | Il topicref nidificato nelle appendici viene trasformato in h1 nel HTML temporaneo. (10454)
* La pubblicazione della linea di base non riesce per PDF generato con FrameMaker Publishing Server 2020. (10551)
* Native PDF | L&#39;aggiunta di `xref` a un&#39;immagine non esegue il rendering dell&#39;immagine sul PDF generato. (11346)
* Native PDF | Il tag immagine aggiunge l’attributo display-inline a tutte le immagini. (10653)
* Native PDF | I commenti bozza sono nascosti per impostazione predefinita nell&#39;output generato. (10560)
* Native PDF | navtitle non è onorato per topichead. (10509)
