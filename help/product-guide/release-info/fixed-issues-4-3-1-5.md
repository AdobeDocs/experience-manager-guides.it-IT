---
title: Note sulla versione | Sono stati risolti i problemi relativi alla versione 4.3.1.5 delle Guide di Adobe Experience Manager
description: Scopri le correzioni di bug nella versione 4.3.1.5 delle guide di Adobe Experience Manager
role: Leader
source-git-commit: 485f88e2e8724d1dc28deac13d677734fcc15c25
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---


# Sono stati risolti i problemi nella versione 4.3.1.5 di


Questo articolo descrive i bug corretti in varie aree della versione 4.3.1.5 delle Guide di Adobe Experience Manager.



Informazioni su [istruzioni di aggiornamento per la versione 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Authoring

- Aggiunta di spazi tra elementi in linea all’interno di `<codeblock>` causa un&#39;interruzione di riga nell&#39;output generato. (15247)
- Si verificano problemi di esperienza durante l’aggiunta di elementi dalla finestra di dialogo &quot;Inserisci elemento&quot;. (15108)

## Pubblicazione

- I registri degli errori visualizzano informazioni non corrette sulla pubblicazione di contenuti con ambiti esterni. (15242)
- Collegamenti interni a file DITA che iniziano con `HTTP` vengono trattati come collegamenti esterni e causano errori di ambito. (15155)
- La rigenerazione del sito AEM non riesce per le mappe DITA. (14369)

## Gestione

- **fmditaTopicrefs** mostra percorsi relativi invece di percorsi assoluti. (15341)

