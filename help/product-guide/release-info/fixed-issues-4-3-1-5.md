---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides versione 4.3.1.5
description: Scopri le correzioni di bug nella versione 4.3.1.5 di Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---

# Sono stati risolti i problemi nella versione 4.3.1.5 di


Questo articolo descrive i bug corretti in varie aree della versione 4.3.1.5 di Adobe Experience Manager Guides.



Scopri le [istruzioni di aggiornamento per la versione 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Authoring

- L&#39;aggiunta di spazi tra elementi in linea all&#39;interno di `<codeblock>` causa un&#39;interruzione di riga nell&#39;output generato. (15247)
- Si verificano problemi di esperienza durante l’aggiunta di elementi dalla finestra di dialogo &quot;Inserisci elemento&quot;. (15108)

## Pubblicazione

- I registri degli errori visualizzano informazioni non corrette sulla pubblicazione di contenuti con ambiti esterni. (15242)
- I collegamenti interni ai file DITA che iniziano con `HTTP` vengono trattati come collegamenti esterni e causano errori di ambito. (15155)
- La rigenerazione del sito AEM non riesce per le mappe DITA. (14369)

## Gestione

- La proprietà **fmditaTopicrefs** mostra percorsi relativi invece di percorsi assoluti. (15341)
