---
title: Note sulla versione | Adobe Experience Manager Guides versione 4.2
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alle versioni 4.2 delle guide di Adobe Experience Manager
exl-id: 8a7fef77-63af-462f-89c5-054ab31e079b
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 1%

---

# Versione 4.2 delle guide di Adobe Experience Manager (febbraio 2023)

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione 4.2 delle Guide di Adobe Experience Manager (in seguito denominate *Guide AEM*).

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 4.2 delle guide di Adobe Experience Manager](whats-new-4.2-release.md).

## Aggiornamento alla versione 4.2 delle guide AEM

Puoi aggiornare facilmente la versione corrente delle guide AEM alla versione 4.2. Prima di procedere con l’aggiornamento alla versione 4.2 delle Guide AEM, è necessario considerare i seguenti punti:
* Se utilizzi le versioni 4.0, 4.1 o 4.1.x, puoi eseguire direttamente l’aggiornamento alla versione 4.2.
* Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
* Se utilizzi una versione precedente alla 3.8.5, consulta *Aggiornamento delle guide AEM* nella guida all’installazione specifica per il prodotto.

>[!NOTE]
>
>È necessario installare il service pack per l’AEM prima di aggiornare la versione delle guide AEM.

Per ulteriori informazioni, consulta [Istruzioni per l’aggiornamento](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate dalla versione 4.2 delle guide AEM.

### Adobe Experience Manager

**Non UUID**
Versione 6.5 Service Pack 15, 14, 13 o 12

**UUID**
Versione 6.5 Service Pack 15, 14, 13 o 12

Per ulteriori dettagli, vedi *Requisiti tecnici* nella guida Installare e configurare Adobe Experience Manager Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2 (non UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.3 o versione successiva |
| 4.2 (UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.4 o versione successiva |
| | | | |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2 (non UUID) | 2.1-regular-4 | 2.1-regular-4 | 1,6 | 1,6 |
| 4.2 (UUID) | 2,8-uuid-8 | 2,8-uuid-8 | 2,3 | 2,3 |
|  |  |   |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

* Il pannello sinistro si interrompe quando si aggiunge una scheda. (11126)
* Le modifiche nell’HTML dell’editor web causano problemi con `<dl>` e `<dlentry>`. (11024)
* Alcuni attributi non vengono trattati come condizionali e causano problemi. (10895)
* Tre o più livelli nidificati `<indexterm>` non sono nidificati nell’esportazione nativa di PDF. (10799)
* Il contenuto scompare nel corpo di un’attività quando si passa dalla vista Creazione alla vista Origine. (10735)
* I commenti di revisione non vengono inseriti correttamente in un&#39;attività di revisione. (10625)
* `<conref>` la nota all’interno di un tag para non viene visualizzata nella modalità di anteprima. (10559)
* Se si preme backspace alla fine di una voce di elenco, l’intero elenco viene rimosso. (10540)
* Lo schermo viene visualizzato come vuoto in Chrome v106 sul trascinamento della selezione su qualsiasi elemento dall’interfaccia utente (ad esempio, dal pannello Condizioni). (10524)
* Il pulsante Rientro automatico non è presente nella barra degli strumenti di **Sorgente** visualizzazione. (10448)
* Il primo carattere di una voce di elenco viene perso a volte quando l’elenco viene creato nell’editor.( 10447)
* **Annulla** o **Ripeti** non funziona correttamente su alcuni file. (10373)
* I metadati personalizzati non vengono mantenuti durante l’azione di copia e incolla. (10367)
* Si verifica un errore quando si esegue una copia (Ctrl+C) e si incolla (Ctrl+V) del contenuto. (10304)
* Il pannello Struttura non visualizza il contenuto quando si passa dalla modalità Autore alla modalità Sorgente. (10296)
* La mappa secondaria non viene creata quando si riferisce a una mappa principale in Modelli DITA. (10231)
* Si verificano problemi di navigazione nell’editor web dopo l’aggiornamento 4.0. (10159)
* L&#39;opzione Annulla nell&#39;editor XML consente di portare l&#39;utente nella parte superiore della pagina. (10091)
* Le proprietà del nodo vengono rimosse dopo l’operazione di copia e incolla di una risorsa. (10053)
* I file SVG aggiunti agli argomenti DITA non vengono visualizzati nella modalità di anteprima dell&#39;editor. (10010)
* I risultati della ricerca per trovare e sostituire nell’editor web non sono leggibili in modalità scura. (9978)
* Non esiste alcun caricatore durante la creazione di una mappa dal modello di mappa. (9891)
* Conref nel modello di argomento non funziona e l&#39;ID hash copiato non viene aggiornato nella copia del contenuto. (9890)
* Non viene visualizzata alcuna opzione per sfogliare gli argomenti o mappare il modello all&#39;interno delle sottocartelle della cartella degli argomenti o delle mappe. (9889)
* Nessuna opzione per creare un nuovo modello nelle sottocartelle di argomenti o mappe. (9888)
* XML Editor non aggiorna le immagini degli argomenti. (9500)
* mimeType è codificato per la creazione e l’aggiornamento di risorse DITA. (8979)
* Quando si seleziona Trattino unificatore in, viene inserito un trattino normale **Inserisci carattere speciale** . (8919)
* Il nome dell’autore della versione nella Cronologia versioni è &quot;fmdita-serviceuser&quot; per i file caricati tramite l’interfaccia utente di Assets. (8910)
* L’opzione Modifica non funziona per le immagini utilizzate nella vista a colonne dell’interfaccia utente Assets. (8758)
* L&#39;argomento DITA non viene aggiornato automaticamente con le modifiche apportate il **Proprietà** pagina. (8745)
* Durante lo spostamento di elementi all’interno dell’argomento nell’Editor web, gli ID assegnati sugli elementi vengono sovrascritti dagli ID assegnati automaticamente. (7895)

### Gestione

* Copiare una risorsa mappa DITA (dall’interfaccia utente di Asset ) causa l’esistenza di linee di base errate nella risorsa copiata. (11218)
* Non viene visualizzato alcun messaggio di avvertenza al caricamento di un file che supera il limite consentito dall’AEM (2 GB per impostazione predefinita). (10817)
* Web Editor-Baseline | Il comportamento della colonna Più recente nel dashboard della nuova linea di base all&#39;interno dell&#39;editor Web è diverso. (10808)
* Traduzione | Il processo di traduzione non viene avviato perché /libs/fmdita/i18n/ja.json non è valido. (10543)
* Traduzione | Si verifica un errore in un progetto di traduzione dell’ambito creato dal dashboard di traduzione (Traduzione umana). (10526)
* Traduzione | La post-elaborazione è bloccata per l’intera cartella della lingua le cui risorse sono presenti in un progetto di traduzione attivo. (10332)
* Traduzione| I metadati e i tag non vengono propagati alle copie tradotte. (4696)
* Se la versione viene modificata e salvata nell’editor della linea di base, per qualsiasi risorsa vengono visualizzati più pop-up. (10399)
* La perdita di sessione si verifica in com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210). (10279)
* Il file video non è presente nella baseline se la cartella principale contiene spazio nel nome. (10031)

### Pubblicazione

* La rigenerazione dell&#39;argomento non funziona per alcuni scenari. (10635)
* La pubblicazione PDF non riesce quando si genera l’output di un predefinito duplicato (di un predefinito esistente). (10584)
* Il pulsante Visualizza registro non funziona se la generazione PDF non riesce per un predefinito. (10576)
* Publishlistener non visualizza i dati richiesti nei registri di informazioni e contiene anche alcuni registri di posta indesiderata.( 10567)
* Native PDF | La generazione di PDF non riesce con un’eccezione Null Pointer. (10950)
* Native PDF | conkeyref non viene risolto nell&#39;output generato. (10564)
* Native PDF | Si verificano problemi con i metadati di una mappa a cui è necessario fare riferimento nell’output PDF.( 10556)
* Native PDF | Si verificano problemi durante la rotazione dell’intestazione della tabella. (10555)
* Native PDF | Si verificano problemi durante la rimozione di argomenti con ruolo di elaborazione=&#39;solo risorsa&#39;. (10554)
* Native PDF | I tasti vuoti vengono visualizzati nell’output PDF. (10553)
* Native PDF | Nidificato `<indexterm>` non sono nidificati nell’esportazione nativa di PDF. (10521)
* Native PDF | Native PDF utilizza lo stile in linea anziché il nome della classe per i tag generati. (10498)
* Native PDF | Il topicref nidificato nelle appendici viene trasformato in h1 nella HTML temporanea.( 10454)
* Native PDF | Impossibile nascondere gli argomenti relativi al frontespizio dal sommario. (10355)
* Native PDF | Attributo frame tabella non propagato al HTML temporaneo (come classe). (10353)
* Native PDF | File HTML temporanei aggiungere le classi colsep e rowsep a <td> e <th> anche se il loro valore è 0 nel DITA di origine. (10352)
* Native PDF | Se si riavviano i numeri di pagina nel layout del capitolo, la numerazione inizia in modo casuale dalla fine del capitolo precedente. (10154)
* Native PDF | I riferimenti chiave per i keydefs con immagine o collegamenti esterni non vengono risolti. (10063)
* Native PDF | L&#39;appendice viene visualizzata come un capitolo in PDF generato. (9829)
* La scheda Modello nell’editor XML non viene visualizzata dagli amministratori dei profili delle cartelle. (10266)
* La pubblicazione della linea di base non riesce per PDF generato con FrameMaker Publishing Server 2020. (10551)
* Si verifica un errore di applicazione quando si fa clic sul pulsante Modifica dopo aver selezionato tutti i predefiniti tramite la casella di controllo Predefiniti di output nella finestra a comparsa Generazione rapida. (10388)
* Se la scheda Output dell&#39;Editor Web contiene più predefiniti, la sezione dei predefiniti non è scorrevole in verticale e non visualizza tutti i predefiniti disponibili. (9787)
* Impossibile eliminare i predefiniti dal flusso di lavoro di output durante la pubblicazione tramite l’editor. (9100)
* Il rendering del collegamento tra pari viene eseguito come testo normale invece di un collegamento nella pagina generata. (7774)

## Problema noto

L’Adobe ha identificato il seguente problema noto per la versione 4.2 delle Guide AEM:

* Gli utenti possono eseguire le operazioni di revisione anche dopo il completamento dell&#39;attività di revisione.
