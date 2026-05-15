---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides 5.0.0 Service Pack 1
description: Scopri le correzioni di bug nella versione 5.0.0 Service Pack 1 di Adobe Experience Manager Guides
role: Leader
exl-id: 1d0bc3d0-aedf-4f67-b6f7-2208facdee96
TQID: https://experienceleague.adobe.com/0qxye7ZUWt1iixHthjjTNJgtlOQX-C30jGi5zQlRJfA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 1%

---

# Sono stati risolti i problemi nella versione 5.0.0 Service Pack 1 (giugno 2025)


Questo articolo descrive i bug risolti in varie aree della versione 5.0.0 Service Pack 1 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 5.0.0 Service Pack 1](upgrade-instructions-5-0-0-sp1.md).

## Authoring

- Quando il contenuto viene incollato in un `codeblock` o quando vengono aggiunti spazi in `codeblock` e la visualizzazione viene cambiata, la spaziatura viene persa. (GUIDES-29347)
- Quando si aggiunge un commento XML all&#39;interno di un elemento nella visualizzazione **Source**, gli spazi iniziali e finali del commento vengono persi quando si passa da una visualizzazione all&#39;altra. (GUIDE - 28188)

## Gestione risorse

- Quando si apre un argomento nella visualizzazione **Autore** dopo un aggiornamento del browser, i tag applicati in precedenza nel pannello **Proprietà file** non vengono mantenuti e l&#39;aggiunta di nuovi tag sovrascrive quelli esistenti, in particolare quando è disponibile un numero elevato di tag per la selezione. (GUIDES-29078)
- Quando si genera un report metadati per una mappa DITA contenente un numero elevato di risorse, il pulsante **Gestisci** non risponde o mostra una risposta ritardata. (GUIDES-29778)

## Traduzione

- Quando si inviano risorse per la traduzione da Experience Manager Guides, le risorse non vengono aggiunte nel processo di traduzione, impedendo la visualizzazione del pulsante **Avvia** e impedendo l&#39;avvio del processo di traduzione. (GUIDES-28237)

## Pubblicazione

- Quando si modificano le impostazioni di un predefinito di output nel profilo di cartella e si seleziona **Applica modifiche predefinito**, le modifiche non vengono propagate ai predefiniti di output presenti nella mappa DITA. (GUIDES-26694)

## Rivedere

- I tentativi di creare attività di revisione tramite il flusso di lavoro di AEM hanno esito negativo in modo coerente perché il nodo di revisione non viene creato. (GUIDES-28214)
