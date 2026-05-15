---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Scopri le correzioni di bug nella versione 5.1.0 Service Pack 1 di Adobe Experience Manager Guides
role: Leader
exl-id: 4b51085b-1f71-41e2-b0a9-88a12990fc97
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 144
ht-degree: 1%

---

# Sono stati risolti i problemi nella versione 5.1.0 Service Pack 1 (ottobre 2025)


Questo articolo descrive i bug corretti in varie aree della versione 5.1.0 Service Pack 1 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 5.1.0 Service Pack 1](upgrade-instructions-5-1-0-sp1.md).


## Platform

- Durante la migrazione da un UUID non UUID a UUID e l’aggiornamento alla versione più recente (5.0+), se sposti le immagini di riferimento da una cartella all’altra e quindi ripristini i file DITA (a cui si riferivano queste immagini) alle versioni precedenti, i riferimenti immagine risultano interrotti. (GUIDES-34315)

## Pubblicazione

- Quando si pubblica una mappa DITA utilizzando la linea di base su AEM Sites (con mappatura di componenti legacy), vengono pubblicati anche gli elementi mappa con l&#39;attributo `processing-role = resource-only`. (GUIDES-34298)
