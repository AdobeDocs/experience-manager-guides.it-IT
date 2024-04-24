---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2024.4.0
description: Scopri le correzioni di bug nella versione 2024.04.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 4c7421391922d276ef82515fb4b1cbdc2397e4ce
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---


# Sono stati risolti i problemi nella versione 2024.04.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2024.04.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, vedi [Novità della versione 2024.04.0](whats-new-2024-04-0.md).

Informazioni su [istruzioni di aggiornamento per la versione 2024.04.0](upgrade-instructions-2024-04-0.md).

## Authoring

- Il **Copia** La funzione non riesce a duplicare le cartelle vuote in Adobe Experience Manager as a Cloud Service. (15353)
- L&#39;editor Web non è in grado di caricare i file con estensione pptx. (14837)
- Quando si trova un testo nell&#39;Editor Web, il cursore torna alla prima occorrenza del testo cercato premendo il tasto Invio. (14820)
- Il salvataggio automatico causa più problemi, riposiziona il cursore e richiede clic manuali nel documento. (14253)
- I risultati della ricerca vengono disattivati dopo l’apertura di un file trovato tramite global **Trova e sostituisci**. (12142)
- Nella vista origine, `</conbody>` viene inserito occasionalmente in posizioni non corrette. (11305)
- Nell&#39;editor XML la caratteristica descrizione comando non consente di aggiornare il campo Origine. (15847)
- Il **Condividi collegamento UUID** per le immagini in Adobe Experience Manager. (15598)
- Si verificano problemi di sovrapposizione del testo in `<reltable>` e `<fig>` tag. (15238)
- Si verificano problemi di visualizzazione momentanea di altri contenuti **Attributi** pannello. (15237)
- Quando si elimina un carattere o una parola all’interno del contenuto, il cursore si sposta tra gli elementi del blocco. (15224)
- Il **Attributi** nella visualizzazione Origine dell&#39;editor Web. (14387)
- Gli spazi indesiderati e unificatori vengono aggiunti durante la modifica alla fine di un tag nell’editor web. (11786)
- Il contenuto viene eliminato durante la correzione degli errori ortografici nei file DITA. (11610)


## Pubblicazione

- La generazione dell’output del sito AEM non riesce quando **Elimina sito orfano** l&#39;opzione è abilitata. (15896)
- La funzionalità di modifica non funziona quando si aggiungono file alla raccolta mappa. (15813)
- Nell’output JSON, i metadati della mappa o degli argomenti DITA non vengono propagati ai file di output JSON. (15713)
- La pubblicazione nativa di PDF non riesce quando si rinomina il predefinito. (15662)
- Il **sourcePath** proprietà non corretta nell’output pubblicato del sito AEM. (15502)
- La selezione e la personalizzazione delle variabili di lingua non funzionano correttamente nel predefinito di output di Native PDF. (15399)
- La generazione di PDF nativi ha esito negativo quando si utilizza un modello con un foglio di stile o un layout di grandi dimensioni. (15344)
- Il contenuto non viene riprodotto correttamente nell’output pubblicato se `<conref>` viene utilizzato con un percorso assoluto.
- La riduzione degli URL di AEM Sites non funziona a causa di conflitti tra `fmdita rewriter` e `ResourceResolver`. (14793)
- Il **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;**, e **chunk=&quot;al contenuto&quot;** Gli attributi vengono visualizzati in modo irregolare nell’output di AEM Sites. (14442)
- Se una cartella contenente mappe 2k è impostata nel percorso della cartella all&#39;interno di un profilo di cartella, le modifiche applicate al predefinito di output non vengono eseguite.(14852)

## Gestione

- Non chiuso **Risolutori risorse** causare un aumento del conteggio delle sessioni e degli errori PathNotFoundException dopo la versione di ottobre 2023 di Experience Manager Guides as a Cloud Service. (15604)
- Flag di funzione **fmdita.useapproval** non funziona come previsto. (15310)
- La creazione di una linea di base utilizzando l’API Java non funziona con la versione di giugno 2023 di Experience Manager Guides as a Cloud Service. (14787)
- Il `/bin/fmdita/import` L’API rimane bloccata nella richiesta in sospeso a tempo indefinito quando le risorse in caricamento superano i 500 MB. (14743)

## Rivedi

- L’eliminazione dei nodi di revisione impedisce l’apertura e la visualizzazione di commenti nelle guide di Adobe Experience Manager. (15366)
- Nell&#39;editor Web, il pannello Revisione viene caricato lentamente. (14680)

## Traduzione

- **Accetta traduzione** non completa la traduzione dei file temporanei. (14665)


