---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Scopri le correzioni di bug nella versione 5.1.0 Service Pack 3 di Adobe Experience Manager Guides
role: Leader
source-git-commit: 64d7e4f8028ade36c4fee9bb3407e70b10da6869
workflow-type: tm+mt
source-wordcount: '251'
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




