---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides 5.0.0 Service Pack 1
description: Scopri le correzioni di bug nella versione 5.0.0 Service Pack 1 di Adobe Experience Manager Guides
role: Leader
source-git-commit: 083a8e16b9d3cd6c3894d7eaa2fee489b1dc0bb8
workflow-type: tm+mt
source-wordcount: '293'
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

## Rivedi

- I tentativi di creare attività di revisione tramite il flusso di lavoro di AEM hanno esito negativo in modo coerente perché il nodo di revisione non viene creato. (GUIDES-28214)
