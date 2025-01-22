---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides 4.6.0 Service Pack 3
description: Scopri le correzioni di bug nella versione 4.6.0 Service Pack 3 di Adobe Experience Manager Guides
role: Leader
source-git-commit: d60fea16831af458c479df24c877ef7095b2fd15
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

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
- Se un collegamento esterno contiene un UUID, viene inserito nella fase di post-elaborazione e converte il collegamento esterno in un collegamento UUID, interrompendo in tal modo il collegamento nell’editor web e anche nei siti di pubblicazione. (22574)
- `xref` viene convertito in collegamento relativo anche quando l&#39;**ambito** del collegamento è impostato su **esterno**. (23059)
- Generazione nativa di PDF non riuscita per il contenuto con attributo **chunk** impostato su **to-content**. (21772)
- La finestra di dialogo **Modifica proprietà** per una baseline non mostra i criteri salvati in precedenza per la baseline dinamica. (23964)


## Traduzione

- Per la traduzione non legacy (per UUID non), lo spostamento di un argomento nel percorso di origine in una cartella diversa genera riferimenti interrotti nelle impostazioni internazionali di destinazione. (24152)
