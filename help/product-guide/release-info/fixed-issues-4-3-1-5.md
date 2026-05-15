---
title: Note sulla versione | Problemi risolti nella versione 4.3.1.5 di Adobe Experience Manager Guides
description: Scopri le correzioni di bug nella versione 4.3.1.5 di Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
TQID: https://experienceleague.adobe.com/ujQFyhAp5bIB1OJnmqvbHCaiDip7T2qsjlVAWevykK8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 6%

---

# Sono stati risolti dei problemi nella versione 4.3.1.5


Questo articolo descrive i bug risolti in varie aree della versione 4.3.1.5 di Adobe Experience Manager Guides.



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
