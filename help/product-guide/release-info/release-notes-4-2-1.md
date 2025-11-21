---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides versione 4.2.1
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione 4.2.1 di Adobe Experience Manager Guides
exl-id: a75ec83f-564b-4243-b5c5-341049521adb
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Versione 4.2.1 di Adobe Experience Manager Guides (maggio 2023)

Questa nota sulla versione descrive le istruzioni per l&#39;aggiornamento, la matrice di compatibilità e i problemi risolti nella versione 4.2.1 di Adobe Experience Manager Guides (in seguito denominata *AEM Guides*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, vedere [Novità della versione 4.2.1 di Adobe Experience Manager Guides](whats-new-4-2-1-release.md).

## Aggiornamento alla versione 4.2.1 di AEM Guides


Puoi aggiornare facilmente la versione corrente di AEM Guides alla versione 4.2.1 Prima di procedere con l’aggiornamento alla versione 4.2.1 di AEM Guides, tieni presente quanto segue:
Puoi aggiornare la versione corrente di AEM Guides alla versione 4.2.1
* Se utilizzi le versioni 4.1, 4.1.x o 4.2, puoi eseguire direttamente l’aggiornamento alla versione 4.2.1.
* Se utilizzi la versione 4.0, devi effettuare l’aggiornamento alla versione 4.2 prima di passare alla versione 4.2.1.
* Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
* Se utilizzi una versione precedente alla 3.8.5, consulta la sezione Aggiornamento di AEM Guides nella guida all’installazione specifica per il prodotto.

>[!NOTE]
>
>È necessario installare AEM Service Pack prima di aggiornare la versione di AEM Guides.

Per ulteriori dettagli, vedere [Istruzioni per l&#39;aggiornamento](../install-guide/upgrade-xml-documentation.md).

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate da AEM Guides 4.2. Versione 1.

### Adobe Experience Manager

**Non UUID**
Versione 6.5 Service Pack 15, 14, 13 o 12

**UUID**
Versione 6.5 Service Pack 15, 14, 13 o 12

Per ulteriori dettagli, consulta la sezione *Requisiti tecnici* nella guida Installare e configurare Adobe Experience Manager Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2.1 (non UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.3 o versione successiva |
| 4.2.1 (UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.4 o versione successiva |
| | | | |  |

*Le condizioni di base e create in AEM sono supportate nelle versioni FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2.1 (non UUID) | 2.2-regular-3 | 2.2-regular-3 | 1,6 | 1,6 |
| 4.2.1 (UUID) | 2,9-uuid-2 | 2,9-uuid-2 | 2,3 | 2,3 |
|  |  |   |  |  |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

* Navtitle viene rimosso dal contenuto quando si passa dalla vista Layout a quella Author o Source. (12174)
* Il pulsante Chiudi nell’editor web non reindirizza alla pagina di navigazione di AEM. (11948)
* A volte si verificano errori di applicazione quando si fa clic su una mappa DITA. (11842)
* Il problema si verifica quando si sposta (trascina e rilascia) al posto di una voce di elenco esistente con l’opzione Rileva modifiche attivata. (11570)
* Si verifica un problema quando si sposta (trascina e rilascia) come nuova voce di elenco con l’opzione Rileva modifiche attivata. (11569)
* Il rientro o il rientro degli elementi dell&#39;elenco non funziona come previsto con l&#39;opzione Rileva modifiche attivata. (11568)
* L&#39;aggiunta di contenuto su una riga con Revisioni attivate e quindi la disattivazione di Revisioni non ne determina la disattivazione. (11567)
* Difficoltà nel trascinare una voce di elenco, il testo viene spostato al posto della voce di elenco. (11566)
* Durante l’authoring nell’elemento visualizzato in verde (Rileva modifiche), il nuovo contenuto viene visualizzato come revisione anche se la modifica della traccia è disabilitata. (7021)
* Il browser (Editor Web) non è in grado di caricare contenuti con uno schema personalizzato. (11211)
* PDF nativo | Quando si crea un predefinito di output con l’opzione &quot;Aggiungi al profilo cartella&quot;, la generazione di PDF non riesce e viene generata un’eccezione Null Pointer. (10950)
* PDF nativo | Il tag immagine aggiunge l’attributo display-inline a tutte le immagini. (10653)
* L&#39;inserimento di file multimediali audio e video non riesce nel formato YouTube sotto l&#39;icona **Inserisci file multimediali**. (11320)
* Si verifica un errore di convalida quando si crea una mappa utilizzando il modello che ha un elemento titolo specializzato. (11212)
* Editor web | Lo spazio unificatore viene aggiunto nell&#39;editor XML durante la modifica di un argomento. (11786)

### Gestione

* Nella scheda Report dell&#39;interfaccia utente dell&#39;Editor Web non viene visualizzato l&#39;elenco degli argomenti delle vecchie mappe DITA create prima dell&#39;aggiornamento 4.2. (11708)

* La funzionalità del pulsante Carica file nell’interfaccia utente di Assets è stata interrotta nella versione 4.2. (11633)


### Pubblicazione

* PDF nativo | La pubblicazione di contenuti con una classe di output con parentesi() comporta un blocco della pubblicazione. (11936)
* Output JSON | La mappatura dei metadati con valore di proprietà come `"value in spaces and double quotes"` genera un errore di pubblicazione. (11933)
* Il problema si verifica nella ricerca del sito AEM (non funziona oltre i nodi di 2-3 livelli). (11352)
* Editor web | Il percorso e il modello di output non possono essere selezionati nel predefinito di AEM. (11530)
* Quando si esegue l’aggiornamento dalla versione 4.1.x alla versione 4.2, il motore PDF nativo non funziona e viene generata l’eccezione NullPointerException anche per il sistema operativo supportato.(11526)
* Il processo di download di PDF non funziona in modo appropriato nell’editor web. (11496)
* PDF nativo | I commenti bozza sono nascosti per impostazione predefinita nell&#39;output generato. (10560)
* PDF nativo | navtitle non è onorato per topichead. (10509)
* PDF nativo | L&#39;aggiunta di `xref` a un&#39;immagine non esegue il rendering dell&#39;immagine sul PDF generato. (11346)
* PDF nativo | la nota a piè di pagina presente nell’intestazione della tabella porta a un testo in grassetto e allineato al centro nel piè di pagina della pagina corrispondente nell’output di PDF. (10610)

### Traduzione

* Con l’aggiornamento 4.2, tutto il contenuto della traduzione viene visualizzato Fuori sincronizzazione o Senza copia. (11834)

### Rivedere

* La revisione completata non si apre in modalità di sola lettura. (11387)
