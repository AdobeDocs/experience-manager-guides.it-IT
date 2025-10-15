---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Scopri le correzioni di bug nella versione 5.1.0 Service Pack 1 di Adobe Experience Manager Guides
role: Leader
source-git-commit: 575488e1b378c17419add75876a8e7f7423d5116
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 1%

---

# Sono stati risolti i problemi nella versione 5.1.0 Service Pack 1 (ottobre 2025)


Questo articolo descrive i bug corretti in varie aree della versione 5.1.0 Service Pack 1 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 5.1.0 Service Pack 1](upgrade-instructions-5-1-0-sp1.md).


## Platform

- Durante la migrazione da un UUID non UUID a UUID e l’aggiornamento alla versione più recente (5.0+), se sposti le immagini di riferimento da una cartella all’altra e quindi ripristini i file DITA (a cui si riferivano queste immagini) alle versioni precedenti, i riferimenti immagine risultano interrotti. (GUIDES-34315)

## Pubblicazione

- Quando si pubblica una mappa DITA utilizzando la linea di base su AEM Sites (con mappatura di componenti legacy), vengono pubblicati anche gli elementi mappa con l&#39;attributo `processing-role = resource-only`. (GUIDES-34298)
