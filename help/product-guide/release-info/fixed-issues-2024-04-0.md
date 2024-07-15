---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2024.4.0
description: Scopri le correzioni di bug nella versione 2024.04.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 35351d71-7739-4ad3-a063-67adf64906bf
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 3%

---

# Sono stati risolti i problemi nella versione 2024.04.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2024.04.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2024.04.0](whats-new-2024-04-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2024.04.0](upgrade-instructions-2024-04-0.md).

## Authoring

- La funzione **Copia** non riesce a duplicare le cartelle vuote in Adobe Experience Manager as a Cloud Service. (15353)
- L&#39;editor Web non è in grado di caricare i file con estensione pptx. (14837)
- Quando si trova un testo nell&#39;Editor Web, il cursore torna alla prima occorrenza del testo cercato premendo il tasto Invio. (14820)
- Il salvataggio automatico causa più problemi, riposiziona il cursore e richiede clic manuali nel documento. (14253)
- I risultati della ricerca sono disabilitati dopo l&#39;apertura di un file trovato tramite **Trova e sostituisci** globale. (12142)
- Nella vista origine, `</conbody>` viene inserito occasionalmente in posizioni non corrette. (11305)
- Nell&#39;editor XML la caratteristica descrizione comando non consente di aggiornare il campo Source. (15847)
- La funzionalità **Condividi collegamento UUID** non funziona per le immagini in Adobe Experience Manager. (15598)
- Problemi di testo sovrapposti si verificano in `<reltable>` e `<fig>` tag. (15238)
- Si verificano problemi di visualizzazione momentanea di altri contenuti nel pannello **Attributi**. (15237)
- Quando si elimina un carattere o una parola all’interno del contenuto, il cursore si sposta tra gli elementi del blocco. (15224)
- Il pannello **Attributi** non viene visualizzato nella visualizzazione Source dell&#39;editor Web. (14387)
- Gli spazi indesiderati e unificatori vengono aggiunti durante la modifica alla fine di un tag nell’editor web. (11786)
- Il contenuto viene eliminato durante la correzione degli errori ortografici nei file DITA. (11610)


## Pubblicazione

- La generazione dell&#39;output del sito AEM non riesce se l&#39;opzione **Elimina sito orfano** è abilitata. (15896)
- La funzionalità di modifica non funziona quando si aggiungono file alla raccolta mappa. (15813)
- Nell’output JSON, i metadati della mappa o degli argomenti DITA non vengono propagati ai file di output JSON. (15713)
- La pubblicazione nativa di PDF non riesce quando si rinomina il predefinito. (15662)
- La proprietà **sourcePath** non è corretta nell&#39;output del sito AEM pubblicato. (15502)
- La selezione e la personalizzazione delle variabili di lingua non funzionano correttamente nel predefinito di output di Native PDF. (15399)
- La generazione di PDF nativi ha esito negativo quando si utilizza un modello con un foglio di stile o un layout di grandi dimensioni. (15344)
- Il rendering del contenuto nell&#39;output pubblicato non viene eseguito correttamente se `<conref>` viene utilizzato con un percorso assoluto.
- La riduzione degli URL di AEM Sites non funziona a causa di conflitti tra `fmdita rewriter` e `ResourceResolver`. (14793)
- Gli attributi **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** e **chunk=&quot;to-content&quot;** vengono visualizzati nell&#39;output di AEM Sites in modo indipendente. (14442)
- Se una cartella contenente mappe 2k è impostata nel percorso della cartella all&#39;interno di un profilo di cartella, le modifiche applicate al predefinito di output non vengono eseguite.(14852)

## Gestione

- I **Resource Resolver** non chiusi causano un aumento del conteggio delle sessioni e errori PathNotFoundException dopo la versione di ottobre 2023 di Experience Manager Guides as a Cloud Service. (15604)
- Il flag di funzionalità **fmdita.useapproval** non funziona come previsto. (15310)
- La creazione di una linea di base utilizzando l’API Java non funziona con la versione di giugno 2023 di Experience Manager Guides as a Cloud Service. (14787)
- L&#39;API `/bin/fmdita/import` rimane bloccata nella richiesta in sospeso a tempo indefinito quando le risorse in caricamento superano i 500 MB. (14743)

## Rivedi

- L’eliminazione dei nodi di revisione impedisce l’apertura e la visualizzazione di commenti in Adobe Experience Manager Guides. (15366)
- Nell&#39;editor Web, il pannello Revisione viene caricato lentamente. (14680)

## Traduzione

- **Accetta traduzione** non completa la traduzione dei file temporanei. (14665)
