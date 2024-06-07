---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2024.06.0
description: Scopri le correzioni di bug nella versione 2024.06.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: dff625a841ea9fc758de83b1d830ddffa15646cd
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 3%

---


# Sono stati risolti i problemi nella versione 2024.06.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2024.06.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2024.06.0](whats-new-2024-06-0.md).

Informazioni su [istruzioni di aggiornamento per la versione 2024.06.0](upgrade-instructions-2024-06-0.md).

## Authoring

- L&#39;operazione di copia e incolla di argomenti di dimensioni superiori a 15 KB non riesce e si verifica un errore imprevisto. (17171)
- Funzionalità per modificare lo stato del documento da  **Proprietà file** il pannello non funziona correttamente e cambia in *Bozza* stato. (17088)
- Quando si modificano le impostazioni dell&#39;editor XML utilizzando un profilo di cartella personalizzato, `ui_config.json` viene aggiornato con un file errato. (17011)
- In **Archivio** pannello, il **Filtro** la ricerca non mantiene il valore di **Ritirato da** quando si riapre il **Filtro avanzato** . (16935)
- Le immagini collegate degli argomenti non vengono visualizzate nella linea di base dopo la creazione della versione. (16931)
- I pannelli di contenuto riutilizzabili non elencano gli elementi quando **Preferenze utente** sono impostati per la visualizzazione dei file **Nome file**. (16896)
- I sottoelementi all’interno dell’elemento titolo della tabella non vengono riprodotti in **Anteprima** modalità di Experience Manager Guides. (16691)
- Esecuzione dello script post-elaborazione non riuscita a causa di **FileNotFoundException** eccezione. (16517)
- I video Vimeo non supportano la funzionalità a schermo intero in Experience Manager Guides. (15996)
- Incollare sequenze di testo preformattate lunghe in `<pre>` o `<codeblock>` Gli elementi generano testo troncato. (15859)
- L’eliminazione del contenuto si verifica a causa di GUID duplicati quando i modelli vengono installati tramite codice ma non vengono elaborati. (15858)
- Le guide Experienci Manager non aderiscono al **Ruolo di elaborazione** attributo in **Anteprima** modalità. (15787)
- L&#39;editor elimina in modo intermittente il testo in eccesso oltre l&#39;area selezionata.  (15708)
- Impossibilità di copiare e incollare tabelle di grandi dimensioni da documenti di Word o HTML nell&#39;editor Web. (15369)
- Il **Copia** la funzione non riesce per le cartelle vuote in Experience Manager Guides as a Cloud Service. (15353)
- Mancanza di API o eventi per acquisire l’aggiunta di attributi a un elemento o l’inserimento di un nuovo elemento. (15351)
- Impossibilità di aggiungere `<data>` tag in `<ol>` nell&#39;editor Web. (15161)
- Quando Unified Shell è abilitato, il **Gestione etichette versione** viene visualizzata in modo errato **Contenuto principale** per le versioni senza etichette. (15039)
- I file di grandi dimensioni vengono caricati lentamente nell’editor web, con un ritardo di alcuni secondi. (14958)
- Premendo il tasto **Invio** in una cella di tabella all’interno del testo non divide il paragrafo come previsto. (14251)
- La Guida DITA di Experience Manager non riesce ad attivare **Salva** dopo l&#39;utilizzo della funzione di rientro automatico. (16482)
- Gli argomenti della revisione non vengono visualizzati nell&#39;ordine corretto. (16319)
- In **Autore** visualizzazione, si verifica un problema di copia e incolla quando si utilizzano spazi unificatori e provoca l’overflow del testo. (15541)

- In entrata `<othermeta>` elemento in `<topicmeta>`, all’aggiunta di un `<conref>`a un&#39;altra mappa DITA, insieme all&#39;ID dell&#39;elemento viene aggiunto anche l&#39;ID mappa. (15226)
- Il `<conref>` non può essere aggiornato da **Attributi** quando si apportano modifiche. (15209)
- Quando selezionate un&#39;immagine all&#39;interno di una cella di tabella, viene selezionata l&#39;intera cella. (15188)

## Pubblicazione


- Il collegamento della mappa incrociata non visualizza tutte le mappe principali nelle impostazioni del contesto di pubblicazione per un collegamento che presenta `peer @scope`. (16700)
- Quando si aggiungono nuovi attributi o si rimuovono attributi esistenti, i vecchi attributi vengono mantenuti nel **Predefiniti condizione**. (15890)
- Il contenuto della lingua RTL non viene gestito correttamente nell&#39;output di pubblicazione di PDF nativi. (15709)
- Quando viene generato un output di PDF nativo, il primo PDF non dispone di una versione. (10305)
- In Native PDF gli argomenti DITA nidificati non vengono visualizzati correttamente nel sommario. (16742)
- Le miniature generate da Dynamic Medie per i file video non persistono nell’output pubblicato. (15656)
- La generazione dell&#39;output non riesce per la pubblicazione di PDF nativi su un processore ARM64. (16968)

## Gestione

- La modifica di una baseline esistente e la selezione di una versione specifica attivano errori di applicazione. (14451)

## Traduzione

- Con la versione di ottobre 2023 di Adobe Experience Manager Guides, i progetti di traduzione non aggiungono nuovi processi linguistici a Experience Manager 6.5 SP18. (15398)

## Cloud Service

- La navigazione degli strumenti di Adobe Experience Manager non risponde. (17118)
- La fase di trasformazione della build nella distribuzione dei Cloud Service non riesce e genera errori dalla base di codice DITA. (14432)

## Rapporti

- L&#39;inaccurato **Elenco argomenti** I conteggi nell’interfaccia utente di Experience Manager Guides dovuti a proprietà senza patch durante la copia di risorse DITA influiscono sui rapporti generati per una mappa DTIA. (15529)
- Argomenti contenenti riferimenti esterni con *%20* nell’URL vengono visualizzati i riferimenti ai file interrotti. (15347)


## Problemi noti

L’Adobe ha identificato i seguenti problemi noti per la versione 2024.06.0:

- La pubblicazione nativa di PDF ha esito negativo quando il contenuto Vimeo viene aggiunto all’argomento.
- Il **Proprietà argomento** non vengono visualizzati nel formato selezionato nei campi di metadati del layout di una pagina.
- `xrefs` non sono selezionabili in **Risorse** visualizzare quando Dynamic Medie è abilitato.
