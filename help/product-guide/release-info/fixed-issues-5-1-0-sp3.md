---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Scopri le correzioni di bug nella versione 5.1.0 Service Pack 3 di Adobe Experience Manager Guides
role: Leader
exl-id: faa9a5d7-616f-4692-98d1-23abc78556b6
TQID: https://experienceleague.adobe.com/qiVY-B-D3FcHq2PH7Go2AAFpnstCrPJ2MVLEalQCVn0
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
source-wordcount: 297
ht-degree: 1%

---

# Sono stati risolti i problemi nella versione 5.1.0 Service Pack 3 (dicembre 2025)


Questo articolo descrive i bug corretti in varie aree della versione 5.1.0 Service Pack 3 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 5.1.0 Service Pack 3](upgrade-instructions-5-1-0-sp3.md).


## Authoring

- I CSS personalizzati applicati a un profilo a livello di cartella per argomenti o mappe vengono ripristinati allo stile predefinito nella modalità Anteprima dopo l’aggiornamento del browser. (GUIDES-31098)
- Impossibile aggiungere più **etichette versione** a un argomento dalla finestra di dialogo **Salva come nuova versione**. (GUIDES-32716)


## Gestione risorse

- Impossibile rimuovere le etichette di versione dal pannello **Cronologia versioni** nell&#39;interfaccia utente di Assets. (GUIDES-38276)


## Rivedere

- Quando un revisore completa un’attività di revisione o l’iniziatore aggiorna un’attività di revisione senza inserire commenti, nell’e-mail di notifica inviata viene visualizzato il commento precedente più recente. (GUIDES-33590)

## Pubblicazione

- Quando si genera l&#39;output di AEM Sites utilizzando la mappatura dei componenti legacy, gli argomenti che utilizzano l&#39;attributo `copy-to` vengono pubblicati con il nome dell&#39;argomento `copy-from` invece del nome impostato nell&#39;attributo `copy-to`. (GUIDES-22155)
- Quando l&#39;output del PDF nativo viene generato utilizzando una linea di base dinamica, il termine **PDFProject** viene visualizzato come titolo del PDF invece del titolo effettivo della mappa. (GUIDES-31102)

## Platform

- Se si utilizza `scope="external"` come riferimento al contenuto DAM in un argomento o in una mappa, il percorso relativo della risorsa viene sostituito da un GUID. (GUIDES-35605)

## Problema noto

Adobe ha identificato il seguente problema noto per la versione 5.1.0 Service Pack 3:

- Quando si contrassegna un&#39;attività di revisione come completata dalla pagina dei dettagli dell&#39;attività, l&#39;attività viene completata e chiusa; tuttavia, il suo stato continua a essere visualizzato come **In corso** nel dashboard di revisione. (GUIDES-39375)
