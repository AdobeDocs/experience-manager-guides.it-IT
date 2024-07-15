---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2024.06.0
description: Scopri le correzioni di bug nella versione 2024.06.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 608e5b2c-72af-4498-9b63-935e698231d4
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 3%

---

# Sono stati risolti i problemi nella versione 2024.06.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2024.06.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2024.06.0](whats-new-2024-06-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2024.06.0](upgrade-instructions-2024-06-0.md).

## Authoring

- L&#39;operazione di copia e incolla di argomenti di dimensioni superiori a 15 KB non riesce e si verifica un errore imprevisto. (17171)
- La funzionalità per modificare lo stato del documento dal pannello **Proprietà file** non funziona correttamente e cambia allo stato *Bozza*. (17088)
- Quando si modificano le impostazioni dell&#39;editor XML utilizzando un profilo di cartella personalizzato, `ui_config.json` viene aggiornato con un file non corretto. (17011)
- Nel pannello **Archivio**, la ricerca **Filtro** non mantiene il valore del campo **Estratto da** quando si riapre la finestra di dialogo **Filtro avanzato**. (16935)
- Le immagini collegate degli argomenti non vengono visualizzate nella linea di base dopo la creazione della versione. (16931)
- I pannelli del contenuto riutilizzabili non elencano gli elementi quando **Preferenze utente** è impostato per visualizzare i file in base a **Nome file**. (16896)
- I sottoelementi all&#39;interno dell&#39;elemento titolo della tabella non vengono riprodotti nella modalità **Anteprima** di Experience Manager Guides. (16691)
- Esecuzione dello script postprocess non riuscita a causa dell&#39;eccezione **FileNotFoundException**. (16517)
- I video Vimeo non supportano la funzionalità a schermo intero in Experience Manager Guides. (15996)
- Se si incollano lunghe sequenze di testo preformattato in `<pre>` o `<codeblock>` elementi, il testo risulterà troncato. (15859)
- L’eliminazione del contenuto si verifica a causa di GUID duplicati quando i modelli vengono installati tramite codice ma non vengono elaborati. (15858)
- Experience Manager Guides non rispetta l&#39;attributo **Ruolo di elaborazione** in modalità **Anteprima**. (15787)
- L&#39;editor elimina in modo intermittente il testo in eccesso oltre l&#39;area selezionata.  (15708)
- Impossibilità di copiare e incollare tabelle di grandi dimensioni da documenti di Word o HTML nell&#39;editor Web. (15369)
- La funzione **Copia** non riesce per le cartelle vuote in Experience Manager Guides as a Cloud Service. (15353)
- Mancanza di API o eventi per acquisire l’aggiunta di attributi a un elemento o l’inserimento di un nuovo elemento. (15351)
- Impossibile aggiungere il tag `<data>` nel tag `<ol>` nell&#39;editor Web. (15161)
- Quando Unified Shell è abilitato, la finestra di dialogo **Gestione etichette versione** visualizza erroneamente **Contenuto principale** per le versioni senza etichette. (15039)
- I file di grandi dimensioni vengono caricati lentamente nell’editor web, con un ritardo di alcuni secondi. (14958)
- Premendo il tasto **Invio** in una cella di tabella all&#39;interno del testo, il paragrafo non viene diviso come previsto. (14251)
- La Guida DITA di Experience Manager non riesce ad attivare la funzione **Salva** dopo aver utilizzato la funzione di rientro automatico. (16482)
- Gli argomenti della revisione non vengono visualizzati nell&#39;ordine corretto. (16319)
- Nella visualizzazione **Autore** si verifica un problema di copia e incolla quando si utilizzano spazi unificatori e provoca l&#39;overflow del testo. (15541)

- Nell&#39;elemento `<othermeta>` all&#39;interno di `<topicmeta>`, quando si aggiunge un elemento `<conref>` a un&#39;altra mappa DITA, anche l&#39;ID della mappa viene aggiunto insieme all&#39;ID dell&#39;elemento. (15226)
- Impossibile aggiornare `<conref>` dal pannello **Attributi** quando si apportano modifiche. (15209)
- Quando selezionate un&#39;immagine all&#39;interno di una cella di tabella, viene selezionata l&#39;intera cella. (15188)

## Pubblicazione


- Il collegamento di una mappa incrociata non riesce a visualizzare tutte le mappe padre nelle impostazioni del contesto di pubblicazione per un collegamento con `peer @scope`. (16700)
- Quando si aggiungono nuovi attributi o si rimuovono attributi esistenti, i vecchi attributi vengono mantenuti nei **Predefiniti condizione**. (15890)
- Il contenuto della lingua RTL non viene gestito correttamente nell&#39;output di pubblicazione di PDF nativi. (15709)
- Quando viene generato un output di PDF nativo, il primo PDF non dispone di una versione. (10305)
- In Native PDF gli argomenti DITA nidificati non vengono visualizzati correttamente nel sommario. (16742)
- Le miniature generate da Dynamic Medie per i file video non persistono nell’output pubblicato. (15656)
- La generazione dell&#39;output non riesce per la pubblicazione di PDF nativi su un processore ARM64. (16968)

## Gestione

- La modifica di una baseline esistente e la selezione di una versione specifica attivano errori di applicazione. (14451)

## Traduzione

- Con la versione di ottobre 2023 di Experience Manager Guides, i progetti di traduzione non aggiungono nuovi processi linguistici a Adobe Experience Manager 6.5 SP18. (15398)

## Cloud Service

- La navigazione degli strumenti di Adobe Experience Manager non risponde. (17118)
- La fase di trasformazione della build nella distribuzione dei Cloud Service non riesce e genera errori dalla base di codice DITA. (14432)

## Rapporti

- I conteggi imprecisi di **Elenco argomenti** nell&#39;interfaccia utente di Experience Manager Guides a causa di proprietà senza patch durante la copia di risorse DITA influiscono sui rapporti generati per una mappa DTIA. (15529)
- Gli argomenti contenenti riferimenti esterni con *%20* nell&#39;URL visualizzano riferimenti a file interrotti. (15347)


## Problemi noti

L’Adobe ha identificato i seguenti problemi noti per la versione 2024.06.0:

- La pubblicazione nativa di PDF ha esito negativo quando il contenuto Vimeo viene aggiunto all’argomento.
- Le **proprietà argomento** non vengono visualizzate nel formato selezionato nei campi metadati di un layout di pagina.
- Impossibile fare clic su `xrefs` nella visualizzazione **Assets** quando Dynamic Medie è abilitato.
