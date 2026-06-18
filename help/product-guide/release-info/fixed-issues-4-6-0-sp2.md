---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides 4.6.0 Service Pack 3
description: Scopri le correzioni di bug nella versione 4.6.0 Service Pack 3 di Adobe Experience Manager Guides
role: Leader
exl-id: 8ff26c28-4a88-4eb2-b359-5b1b0138dd4b
TQID: https://experienceleague.adobe.com/bsiTHK--FPkvfF4bdYUnL-HbAMuhtBKj7wT2eCmd7hM
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 4%

---

# Sono stati risolti i problemi nella versione 4.6.0 Service Pack 3 (gennaio 2025)


Questo articolo descrive i bug corretti in varie aree della versione 4.6.0 Service Pack 3 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 4.6.0 Service Pack 3](upgrade-instructions-4-6-0-sp2.md).

## Authoring

- Tutti i gruppi di condizioni vengono persi e le condizioni vengono appiattite all’aggiornamento delle condizioni dal profilo della cartella. (23526)
- La modifica del valore delle righe di intestazione per una tabella nel pannello **Proprietà contenuto** non applica il valore aggiornato. (23213)
- Quando si aggiungono nuovi riferimenti ad argomenti nella mappa DITA utilizzando la finestra di dialogo **Riferimento argomento** nella visualizzazione Layout, i riferimenti aggiunti vengono visualizzati come collegamenti interrotti. (22859)
- Quando si aggiungono argomenti in una mappa DITA utilizzando la finestra di dialogo **Riferimento argomento** nella visualizzazione Autore, gli argomenti selezionati vengono inseriti in ordine inverso rispetto alla selezione. (22858)
- Quando si copia un’immagine da un prodotto esterno (ad esempio, MS PowerPoint) e la si incolla nelle Guide, la funzionalità di caricamento rapido della risorsa per l’utilizzo nel file si interrompe. (24983)
- Non è possibile selezionare più file durante la ricerca di file nel repository utilizzando la funzionalità **Ricerca e filtro**. (25104)

## Pubblicazione

- La pubblicazione in Salesforce ha esito negativo se il contenuto contiene spazi unificatori. (23664)
- Per gli argomenti che presentano errori come i collegamenti interrotti, la pubblicazione di Salesforce non riesce e la barra di avanzamento viene visualizzata a tempo indeterminato. (22985)
- Per le mappe con collegamenti interrotti, la pubblicazione di Salesforce non riesce e la barra di avanzamento viene visualizzata a tempo indeterminato. (24963)
- Se un collegamento esterno contiene un UUID, viene sottoposto a post-elaborazione e converte il collegamento esterno in UUID, interrompendo in tal modo il collegamento nell’editor e anche nei siti di pubblicazione. (22574)
- `xref` viene convertito in collegamento relativo anche quando l&#39;**ambito** del collegamento è impostato su **esterno**. (23059)
- Generazione nativa di PDF non riuscita per il contenuto con attributo **chunk** impostato su **to-content**. (21772)
- La finestra di dialogo **Modifica proprietà** per una baseline non mostra i criteri salvati in precedenza per la baseline dinamica. (23964)


## Traduzione

- Per la traduzione non legacy (per UUID non), lo spostamento di un argomento nel percorso di origine in una cartella diversa genera riferimenti interrotti nelle impostazioni internazionali di destinazione. (24152)
