---
title: Nuovo motore di pubblicazione per PDF nativo | Generazione output PDF
description: Scopri come utilizzare il nuovo motore di pubblicazione per la pubblicazione nativa di PDF
feature: Publishing, Native PDF Output
role: User
TQID: https://experienceleague.adobe.com/GV3iYtBdFVrQwFjdvfqnfDIWPMugO3hFjS4FZqspG2M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: afb45297-4313-4f67-818e-bc0b03abe086
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 2b6a0f1a6ac03984286e9d3df40c197f28d52f8d
workflow-type: tm+mt
source-wordcount: 844
ht-degree: 0%

---

# Utilizzare il motore PDF nativo v2

Il nuovo motore di pubblicazione *Motore PDF nativo v2*, è basato su un framework di generazione PDF aggiornato e include modifiche alla gestione dei caratteri, all&#39;elaborazione CSS e al comportamento di rendering.

Di conseguenza, l&#39;output di PDF generato con il nuovo motore di pubblicazione potrebbe essere diverso dall&#39;output generato con il motore di PDF esistente (*Motore PDF nativo v1*). Possono essere visibili differenze in aree quali il layout del testo, la spaziatura, lo stile, il rendering delle immagini e la formattazione delle note a piè di pagina.

Ad esempio, il motore nativo di PDF v2 supporta `OpenType` font, mentre il motore nativo di PDF v1 si basa principalmente su `TrueType` font. Miglioramenti di rendering simili possono influenzare l’aspetto complessivo dei PDF generati.

Per informazioni dettagliate su come abilitare il motore di PDF nativo v2 nell&#39;ambiente, visualizzare [Configurare il nuovo motore di pubblicazione per PDF nativo](./conf-new-pdf-engine.md).

## Aggiornamenti CSS consigliati per il nuovo motore di pubblicazione

Se desideri mantenere l’aspetto dell’output PDF generato dal motore PDF nativo v1 durante l’utilizzo del motore PDF nativo v2, potrebbe essere necessario aggiornare il CSS personalizzato. Le modifiche CSS consigliate descritte di seguito possono contribuire a mantenere la coerenza dell’output dopo l’abilitazione della nuova impostazione.

| Descrizione | Aggiornamento CSS consigliato |
|-------------|------------------------------------------------|
| Le immagini ridimensionate possono apparire diverse a causa di modifiche nel comportamento di rendering delle immagini. | Per ripristinare il comportamento di rendering dell&#39;immagine, aggiungere:<br><br> `image-rendering: pixelated` |
| L&#39;allineamento della linea guida del sommario può apparire leggermente diverso a causa di modifiche nel comportamento di rendering della linea guida. | Per ripristinare l&#39;allineamento della linea guida del sommario, regolare lo stile degli elementi della linea guida nel foglio di stile personalizzato. Le modifiche CSS richieste possono variare a seconda del layout e della formattazione del sommario. |
| La spaziatura del testo e la disposizione delle linee possono variare a causa delle modifiche apportate al rendering dei caratteri e all&#39;elaborazione del layout dei glifi. | Se il foglio di stile utilizza la famiglia di caratteri `sans-serif` o tipi di carattere che presentano differenze di spaziatura, aggiungere:<br><br> `-ro-glyph-layout-mode: quality;` |
| I riferimenti alle note a piè di pagina potrebbero non essere più visualizzati come marcatori apice a causa delle modifiche apportate allo stile predefinito delle note a piè di pagina. | Per ripristinare i marcatori note a piè di pagina in stile apice, aggiungere:<br><br>`.fn::footnote-marker` <br> `{ content: counter(footnote) " ";`<br> `vertical-align: super;`<br>`font-size: 65%;}` |
| Il testo sottolineato può essere visualizzato con più spazio tra il testo e la sottolineatura a causa di modifiche nella posizione della sottolineatura. | Per ripristinare il posizionamento della sottolineatura, utilizzare la proprietà `text-underline-offset` e regolare il valore di offset in base alle esigenze. Esempio:<br><br>`text-decoration: underline;`<br>`text-underline-offset: -0.1em;` |
| La spaziatura tra i marcatori elenco e il testo delle voci di elenco può variare a causa di modifiche nel comportamento di rendering degli elenchi. | Per ripristinare la spaziatura, aumentare la spaziatura a sinistra per le voci di elenco. Esempio:<br><br>`.step {`<br> ` margin-top: 0.3rem;`<br> `margin-bottom: 0.5rem;`<br> `padding-left: calc(1.5rem + 1ch);}` |
| La spaziatura prima delle intestazioni può variare a causa di modifiche nel comportamento di compressione dei margini. | Per ripristinare la spaziatura, esaminare i margini degli elementi adiacenti e ridurre o rimuovere i margini superiori e inferiori sovrapposti, se necessario. Esempio:<br><br>`h1.chapter { `<br> `margin-top: 0;` <br>`}`<br>`chaptoc-body { margin-bottom: 0;`<br>` }` |
| I marcatori di segno di spunta generati con CSS possono essere visualizzati con dimensioni o stili diversi perché vengono riprodotti utilizzando font di fallback diversi. | Per eseguire il rendering coerente dei marcatori, utilizzate una famiglia di font che contenga entrambi i glifi. Esempio:<br><br>`::marker {`<br> `font-family: -ro-symbols !important;}` |
| I marcatori di elenco circolari generati da CSS possono apparire parzialmente ritagliati o troncati a causa di modifiche nel comportamento di posizionamento dei marcatori. | Per ripristinare l&#39;aspetto dei marcatori elenco circolari, evitate di utilizzare il posizionamento assoluto per il marcatore. Se è necessario il posizionamento assoluto, specificare esplicitamente un valore `top` appropriato per posizionare correttamente l&#39;indicatore. |
| L&#39;ordine di lettura delle voci di elenco nell&#39;output di PDF/UA può essere diverso quando le voci di elenco utilizzano stili di posizionamento come `position: relative`. | Per fare in modo che l&#39;ordine di lettura segua più da vicino la struttura del documento di origine, applicare la seguente proprietà CSS alle voci di elenco:<br><br>`li {`<br>`-ro-paint-reordering: avoid;}` |


## Soluzioni per i problemi noti

Le seguenti soluzioni possono essere utili per risolvere i problemi noti nell’output PDF generato quando si utilizza il motore PDF nativo v2.

- Le proprietà css `text-decoration` applicate al contenuto della tabella non vengono sottoposte a rendering nell&#39;output di PDF.

  **Soluzione**: applicare le proprietà di decorazione del testo a `span` elementi all&#39;interno del contenuto della tabella anziché applicarli direttamente agli elementi della tabella.

- Le proprietà CSS `-ro-colorbar-top-left` e `-ro-colorbar-top-right` non influiscono sulla barra dei colori nell&#39;output di PDF.

  **Soluzione**: rimuovere i valori corrispondenti dal foglio di stile utente in `mergedHTML.json` oppure aggiungere `!important` ai valori delle proprietà nel CSS del documento in modo che non vengano sostituiti dal foglio di stile utente.

- Le barre dei colori possono apparire unite quando la larghezza della pagina è limitata, perché le barre dei colori non vengono ridimensionate in base alle dimensioni della pagina nell&#39;output di PDF.

  **Soluzione**: visualizzare le barre grigie e colorate su lati diversi della pagina oppure modificare le impostazioni della barra dei colori in modo che non si sovrappongano a pagine di larghezza inferiore.

## Sono stati risolti i problemi relativi al nuovo motore di pubblicazione

I seguenti problemi nell&#39;output di PDF generato con _Native PDF Engine v1_ sono stati risolti in _Native PDF Engine v2_:

- Quando si genera l’output del PDF nativo per determinati contenuti, in PDF viene riprodotto solo il rendering della prima pagina, nonostante il HTML intermedio contenente il contenuto completo per più pagine. (GUIDES-28270)
- L’ordine di lettura dei contenuti nell’output PDF nativo con le impostazioni di accessibilità abilitate non è corretto. I numeri di pagina dei piè di pagina vengono letti prima del contenuto principale anziché alla fine. (GUIDES-27790)
- La barra dei colori nell&#39;output del PDF nativo non si estende per l&#39;intera larghezza della pagina e si sovrappone quando la dimensione della pagina viene personalizzata, causando la visualizzazione di alcune caselle di colore nascoste. (GUIDES-15505)
- Il selettore `CSS:is()pseudo-class` non viene rispettato nell&#39;output PDF nativo, con conseguenti differenze di stile rispetto al rendering del browser. (GUIDES-11328)