---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2025.10.0
description: Scopri le correzioni di bug nella versione 2025.10.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: ff3cf777bd348edded29d780031df59bbb03035d
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 3%

---

# Sono stati risolti i problemi nella versione 2025.10.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2025.10.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2025.10.0](whats-new-2025-10-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.10.0](upgrade-instructions-2025-10-0.md).

## Authoring

- Quando più mappe o argomenti DITA sono aperti e uno degli argomenti è chiuso, il pulsante **>>** che mostra tutte le schede aperte si sovrappone alle altre schede aperte sulla barra delle schede. (GUIDES-31421)
- Con il **flusso di lavoro di approvazione** abilitato, il pulsante **Avvia una nuova versione** non è visibile sulla barra degli strumenti dell&#39;editor se sono aperti sia il pannello Sinistra che il pannello Proprietà contenuto. (GUIDES-29093)
- Quando i nomi dei frammenti superano la larghezza del pannello dei frammenti, vengono disposti in modo errato sulla riga successiva, con conseguente sovrapposizione con frammenti adiacenti e impatto sulla leggibilità. (GUIDES-22685)
- Quando si aggiunge lo stesso riferimento più volte a una mappa DITA, la visualizzazione **Mappa** visualizza il titolo solo per l&#39;ultima occorrenza, mentre quelle precedenti mostrano l&#39;UUID del riferimento. (GUIDES-9699)
- I file DITAVAL rimangono modificabili anche quando sono bloccati da un altro utente o quando il server ha **Disabilita modifica senza bloccare il file** abilitato e il file è aperto in modalità di sola lettura. (GUIDES-27754)
- I registri per i nodi mancanti vengono generati da processi di pulizia interni non necessari e contrassegnati in modo errato come errori, con conseguente file di registro disordinati. (GUIDES-31765)


## Pubblicazione

- Durante la generazione di PDF, le regole di filtro in un file DITAVAL vengono ignorate se qualsiasi nome di proprietà contiene un punto. (GUIDES-33229)
- La pubblicazione di Salesforce non riesce e viene generato un errore di applicazione quando esiste già un argomento con lo stesso nome e URL. (GUIDE - 32390)
- La pubblicazione in Salesforce mostra uno stato di completamento nell&#39;interfaccia utente anche quando una mappa DITA contenente un elemento `topichead` non riesce a pubblicare gli argomenti al suo interno. (GUIDES-32143)
- Per il predefinito di output di HTML5, la funzionalità filtro di ricerca non funziona in AEM Assets per il filtro DITAVAL, in quanto i file corrispondenti non vengono visualizzati quando si seleziona il filtro DITAVAL. (GUIDES-28231)
- Durante la generazione di un PDF nativo per una mappa DITA con più argomenti, se un argomento contiene un elemento `fig` all&#39;interno di un elemento `figgroup` insieme a un elemento `title`, il titolo `figgroup` non viene visualizzato correttamente come titolo del capitolo nel sommario. (GUIDES-23223)
- Quando si duplicano i modelli PDF dall’interfaccia utente, viene duplicato anche l’UUID, causando l’eliminazione dei file dei modelli e la generazione di output PDF errati. (GUIDES-30456)
- Durante la generazione di PDF nativi per una mappa DITA, il titolo dell&#39;elemento `example` viene riprodotto come livello di intestazione `h1`, causando incoerenza visiva e struttura del sommario non corretta. (GUIDES-19958)

## Traduzione

- Quando si ingrandisce la schermata dell&#39;interfaccia utente di traduzione, il pulsante **Invia per traduzione** si sposta sotto i puntini di sospensione e viene attivato anche senza selezionare alcuna risorsa. (GUIDES-33720)
- Quando si selezionano file con stato **Non sincronizzato** nell&#39;interfaccia utente di traduzione e la larghezza dello schermo è limitata a causa dell&#39;apertura dei pannelli Sinistra e Destra, l&#39;etichetta **Invia per traduzione** viene troncata. (GUIDES-33692)

## Rivedere

- Quando un revisore completa un’attività di revisione o l’iniziatore aggiorna un’attività di revisione senza inserire commenti, nell’e-mail di notifica inviata viene visualizzato il commento precedente più recente. (GUIDES-33590)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2025.10.0:

- Quando si apre un URL con un argomento DITA aperto in precedenza o si aggiorna un argomento DITA aperto, l&#39;argomento non viene individuato nell&#39;archivio nonostante l&#39;impostazione **Individua sempre i file nell&#39;archivio** sia abilitata nelle preferenze utente. (GUIDES-35565)<br>**Soluzione**: selezionare la scheda Argomento per individuare il file nell&#39;archivio.

- Quando si crea un nuovo file nella vista Autore con più file già aperti, il pannello a destra non viene aggiornato e vengono visualizzati dati errati se il cursore si trova su un tag elemento in un file diverso. (GUIDES-35450)<br>**Soluzione**: cambia scheda o aggiorna la pagina per risolvere il problema.

- Quando si passa dalla vista Source alla vista Autore per un argomento appena aperto (inizialmente in modalità Source), il contenuto dell’argomento diventa vuoto. (GUIDES-35000)<br>**Soluzione**: aggiorna la pagina o riapri l&#39;argomento per risolvere il problema.

- Il pulsante **Aggiorna navigazione** viene visualizzato per i file di argomenti DITA, anche se dovrebbe essere disponibile solo per le mappe DITA, le mappe dei libri e gli schemi di argomento. (GUIDES-35452)






