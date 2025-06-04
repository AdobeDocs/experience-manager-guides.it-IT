---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2025.06.0
description: Scopri le correzioni di bug nella versione 2025.06.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 0f362ab3-0fae-4eba-bbd6-0b64ae1f2599
source-git-commit: 83be0a1e051bfc524ff2448397d87349f30b4301
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Sono stati risolti i problemi nella versione 2025.06.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2025.06.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2025.06.0](whats-new-2025-06-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.06.0](upgrade-instructions-2025-06-0.md).

## Authoring

- Se non si chiudono le connessioni della sessione JCR durante l’aggiornamento o la creazione di argomenti, si verificano perdite di memoria e tempi di inattività del servizio. (GUIDES-26282)
- Trascinando le colonne, la larghezza cambia da valori percentuali a pixel e vengono generate tabelle distorte o non allineate.(GUIDES-23128)
- Quando il contenuto viene incollato in un `code block` o quando vengono aggiunti spazi in `code block` e la visualizzazione viene cambiata, la spaziatura viene persa. (GUIDES-27478)
- Quando si aggiunge una mappa a `bookmap`, questa viene archiviata in `fmditatopicrefs` anziché in `fmditamaprefs`. (GUIDES-25480)
- La finestra di dialogo **Inserisci immagine** non viene riprodotta correttamente in schermate ad alta risoluzione o ingrandite causando la scomparsa del titolo della figura e dei campi di testo alternativi. (GUIDES-26459)


## Pubblicazione

- La pubblicazione nativa di PDF continua a tempo indeterminato se il contenuto DITA ha un collegamento a Internet senza avere ambito come `external`. (GUIDES-26434)
- La pubblicazione di PDF nativi e di siti AEM si blocca e viene messa in coda, in presenza di errori nel contenuto. (GUIDES-26516)
- Quando si crea una nuova baseline con un numero elevato di etichette, questa impedisce il recupero di tutte le etichette. (GUIDES-16232)
- Durante la generazione di pagine del sito AEM con titoli che includono più parole separate da spazi, il titolo della mappa visualizza i trattini invece degli spazi. (GUIDES-27903)
- Per il PDF nativo, non è stato risolto un nome di proprietà di metadati non valido. Verrà visualizzato come `unresolved property name` in **proprietà documento**. (GUIDES-25680)
- Il testo su più righe all&#39;interno di `codeblock` causa problemi di riversamento del testo durante la generazione di PDF. (GUIDES-15541)
- Quando si aggiungono mappe alla raccolta di mappe, vengono visualizzate risorse diverse dalle mappe (come argomenti, ecc.) e anche le lingue delle mappe tradotte non vengono ordinate correttamente.(GUIDES-25085)


## Rivedi

- La visualizzazione del documento nell’interfaccia utente di revisione non racchiude il contenuto per alcune dimensioni dello schermo, richiedendo agli utenti di scorrere in orizzontale per visualizzare l’intero contenuto. (GUIDES-25292)


## Problemi noti

Adobe ha identificato il seguente problema noto per la versione 2025.06.0:

- Quando si utilizza l&#39;opzione Trova e sostituisci, dopo aver applicato l&#39;operazione Sostituisci occorrenza singola su un file, non è possibile eseguire ulteriori azioni nel pannello Trova e sostituisci. (GUIDES-28930)

- Quando si apre una mappa DITA con la shell unificata abilitata, l&#39;editor viene aggiornato in modo intermittente. (GUIDES-26919)

- In un profilo di cartella, quando una risorsa già indicizzata viene eliminata dall’interfaccia utente, il percorso indicizzato corrispondente non viene rimosso e il tentativo di reindicizzazione non riesce e viene visualizzato un messaggio di errore. (GUIDES-29147) <br>**Soluzione:** Rimuovere il percorso obsoleto che non esiste più prima di avviare la reindicizzazione.

- Se una mappa contiene dipendenze cicliche e apri l’Anteprima mappa, le viste Source, Author e Layout diventano inaccessibili fino a quando la pagina non viene aggiornata. (GUIDES-28334) <br>**Soluzione alternativa:** È necessario aggiornare la pagina per ripristinare l&#39;accesso a queste visualizzazioni.
