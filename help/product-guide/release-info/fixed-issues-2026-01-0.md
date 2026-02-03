---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2026.01.0
description: Scopri le correzioni di bug nella versione 2026.01.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 8a9a82e79c757e403141e853aafbc64e1618c30a
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 3%

---

# Sono stati risolti i problemi nella versione 2026.01.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2026.01.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2026.01.0](whats-new-2026-01-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.01.0](upgrade-instructions-2026-01-0.md).

## Authoring

- Quando si aggiorna un’equazione in linea di MathML utilizzando l’opzione Modifica MathML dal menu di scelta rapida, il valore aggiornato non viene visualizzato finché la pagina non viene aggiornata. (GUIDES-38198)
- Quando un argomento contiene molti elementi riutilizzabili (quelli con ID) aggiunti nel pannello Riutilizzabile, alcuni elementi potrebbero non essere accessibili a causa dell’altezza fissa del contenitore. (GUIDES-37220)
- Quando si inserisce un riferimento incrociato a un file, le icone per le mappe e gli argomenti sono identiche.(GUIDES-36662)
- Durante la modifica di una mappa, i simboli speciali in `navtitle` non vengono visualizzati per `topichead` nella visualizzazione Autore. (GUIDES-35435)
- Impossibile aggiungere più etichette di versione a un argomento dalla finestra di dialogo **Salva come nuova versione**. (GUIDES-32716)

## Gestione risorse

- Impossibile rimuovere le etichette di versione dal pannello Cronologia versioni nell’interfaccia utente di Assets. (GUIDES-38276)
- Quando si caricano risorse il cui nome file contiene caratteri non validi, la risorsa non viene caricata e viene visualizzato un messaggio non corretto **Il file è bloccato da un altro utente** nonostante la risorsa sia stata sbloccata. (GUIDES-32680)
- Nella ricerca di Assets, le risorse secondarie e i nodi di metadati (come immagini e PDF) non vengono inclusi correttamente nei risultati. Inoltre, per un predefinito di output quando si applicano filtri DITAVAL, la ricerca restituisce file DITAVAL generati internamente e creati da predefiniti condizione. (GUIDES-35418)

## Pubblicazione

- Durante la generazione dell&#39;output di AEM Sites, i titoli delle mappe contenenti parole chiave e titoli di argomenti con l&#39;elemento `<ph>` non vengono inclusi nell&#39;output pubblicato. (GUIDES-36641)
- Quando si pubblica utilizzando un predefinito personalizzato con contenuto che contiene collegamenti a PDF senza l’ambito impostato come esterno, il processo non viene completato. (GUIDES-21708)
- Durante l&#39;attivazione in blocco, la creazione del pacchetto aggiunge filtri per tutti i percorsi elencati nella proprietà `fileReference` di una pagina, inclusi i percorsi esterni e peer. (GUIDES-24887)
- Nell&#39;output del PDF nativo, l&#39;elemento `abbreviated-form` visualizza `glossterm` anziché `glossSurfaceForm` o `glossAcronym` designato. (GUIDES-26393)
- Per l&#39;output PDF nativo, l&#39;elemento `<alt>` per le immagini viene ignorato, impedendo l&#39;applicazione di testo alternativo per l&#39;accessibilità. (GUIDES-29087)
- Quando si scaricano file temporanei per una mappa con una linea di base durante la pubblicazione di un predefinito, il file `metadata.xml` fa erroneamente riferimento a `versionPath` invece che a `dampath`.(GUIDES-29815)
- Durante la creazione o la modifica di un argomento che include una citazione, se il campo Autore non viene aggiunto nella finestra di dialogo della citazione, il PDF non viene generato. (GUIDES-37934)
- Il file CSS (`rhdefault.css`) viene applicato in modo errato al modello PDF nonostante non venga fatto riferimento a alcun CSS, causando la perdita dei registri di errore del file CSS.(GUIDES-31752)

## Platform

- Quando si tenta di salvare un argomento o una mappa, l&#39;operazione potrebbe non riuscire a intermittenza con un errore **Impossibile salvare il file**, in particolare durante l&#39;elaborazione intensiva delle risorse o i flussi di lavoro di traduzione in esecuzione in background. (GUIDES-37837)
- Se si utilizza `scope="external"` come riferimento al contenuto DAM in un argomento o in una mappa, il percorso relativo della risorsa viene sostituito da un GUID. (GUIDES-38783)

## Rapporti

- Il report Elenco interrotto include erroneamente collegamenti esterni, `keyrefs` validi e parole chiave risolti correttamente nell&#39;ambito della mappa corrente. (GUIDES-27774)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2026.01.0:

- Quando un argomento in revisione viene rimosso da un&#39;attività di revisione in corso, lo stato del documento continua a rimanere **In revisione**, anche se l&#39;argomento non fa più parte di alcuna attività di revisione. (GUIDES-38709)<br>**Soluzione**: modificare lo stato del documento dell&#39;argomento da **In revisione** allo stato appropriato dalla pagina Proprietà o dal pannello Proprietà file.
- Quando si esegue una ricerca utilizzando **Trova e sostituisci**, se si apre un file dai risultati della ricerca, lo si chiude e si tenta di riaprirlo selezionando il risultato elencato, il file non viene riaperto. (GUIDES-39050)<br>**Soluzione**: aprire prima qualsiasi altro file dai risultati della ricerca, quindi riaprire il file precedentemente chiuso dall&#39;elenco per risolvere il problema.
- Quando si utilizzano le guide con il server DB, per il contenuto che include riferimenti automatici, il rapporto Elenco argomenti visualizza voci non valide per ogni riferimento autonomo, con conseguente conteggio di file non accurato. (GUIDES-39420)












