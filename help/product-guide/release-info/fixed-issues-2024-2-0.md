---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2024.2.0
description: Scopri le correzioni di bug nella versione 2024.2.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 4%

---

# Sono stati risolti i problemi nella versione 2024.2.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2024.2.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2024.2.0](whats-new-2024-2-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2024.2.0](upgrade-instructions-2024-2-0.md).



## Authoring

- Il controllo ortografico nell’editor non consente la selezione di suggerimenti. (15045)
- Il pulsante di navigazione globale non funziona e il dashboard non viene caricato. (14968)
- Nell’editor web, la funzione di download mappa non attiva una notifica pop-up quando è pronto per il download. (14626)
- Nell&#39;editor Web, la funzionalità di download mappa non consente di scaricare una mappa con linea di base. (14622)
- Errore DTD non valido nella versione di ottobre 2023 di Experience Manager Guides as a Cloud Service. (14482)
- Trascinare un argomento del glossario dal repository in una mappa del glossario crea `topicref`. (10767)
- La schermata di anteprima dei frammenti è bloccata. (14840)
- Le etichette del file `labels.json` vengono visualizzate in ordine casuale nell&#39;editor Web. (10508)

## Pubblicazione

- Nella pubblicazione di Native PDF, gli attributi personalizzati all’interno dei predefiniti di condizione non funzionano per la pubblicazione di Native PDF. (14943)
- Nella pubblicazione di PDF nativi, i riferimenti chiave non vengono risolti per la versione di dicembre 2023 di Adobe Experience Manager Guides. (15085)
- La pubblicazione di AEM Sites non riesce e causa errori di ambito per i file con `xref` nel file DITA che iniziano con &quot;HTTP&quot;. (15154)
- Impossibile aggiungere un modello personalizzato dalla scheda **Output** nell&#39;editor. (14846)
- Il predefinito per il sito **AEM** non funziona a causa di un percorso modello vuoto. (14804)
- La rigenerazione del sito AEM non riesce per le mappe DITA con argomenti che contengono equazioni MathML. (14790)
- Nella pubblicazione nativa di PDF, la generazione di PDF genera errori nell&#39;ottenere dipendenze per la pubblicazione di `Node.js`. (14445)
- Il predefinito AEM non consente la selezione di un modello esterno alla gerarchia `/content` nell&#39;editor Web. (14260)
- Nell&#39;output di AEM Sites, lo stile o le interruzioni di riga sono stati persi per l&#39;elemento `<lines>` con elementi secondari. (12542)
- I metadati personalizzati non sono disponibili nell’output finale. (12116)
- Nella pubblicazione nativa di PDF non è possibile utilizzare le proprietà dei metadati delle mappe DITA per popolare i metadati per l&#39;output di file PDF. (15159)



## Gestione

- **I file del filtro della linea di base** non funzionano con il nome file nell&#39;editor Web. (13486)
- La disattivazione dell&#39;indicizzazione della mappa DITA padre per ottenere prestazioni migliori può influire sulle funzionalità di alcune funzionalità.(12213)


## Rivedi

- Il menu di scelta rapida visualizzato facendo clic con il pulsante destro del mouse non funziona per **Accept** o **Reject** track changes. (14607)
- L’opzione per chiudere gli argomenti DITA nella schermata di revisione non funziona nella versione di dicembre 2023 di Adobe Experience Manager Guides. (14537)
- La personalizzazione dei modelli e-mail per il flusso di lavoro di revisione non funziona con la sovrapposizione. (13954)

## Problema noto

L’Adobe ha identificato il seguente problema noto per la versione 2024.2.0:

- La versione 1.0 non viene visualizzata nell&#39;interfaccia utente del file DITA duplicato.
- La propagazione dei metadati delle risorse non funziona per la versione 2024.2.0 di con il microservizio abilitato per qualsiasi predefinito.
