---
title: Utilizzare Markdown in DITA AEM Guides
description: Migrare e utilizzare markdown in DITA AEM Guides
author: Pulkit Nagpal(punagpal)
exl-id: a94c0129-df40-4b61-ac60-679b2ffe7e86
TQID: https://experienceleague.adobe.com/z41KjrBkAeDaH-iKXOFLH44qOQElziip1FqcRhnKaUI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 0%

---

# Utilizzare Markdown in AEM Guides

## Opzioni disponibili

Sono disponibili 2 opzioni per l’utilizzo dei file Markdown in AEM Guides:

- Opzione 1: importa markdown esistente in AEM Guides e utilizzali direttamente in ditamap per la pubblicazione

- Opzione 2: conversione di file Markdown esistenti in DITA

Parliamo di ogni opzione:

### Opzione 1: importa markdown esistente in AEM Guides e utilizzali direttamente all’interno di ditamap per la pubblicazione

Offre una configurazione più semplice e un&#39;implementazione più rapida. Tuttavia, l’utilizzo delle funzionalità di AEM Guides è limitato, come la riutilizzabilità dei contenuti.

L&#39;utente deve aggiungere l&#39;attributo `format="markdown" ` o `format="mdita"` in modo che i motori di pubblicazione comprendano il tipo di file e pubblichino di conseguenza.

File di esempio: [Markdown Ditamap](https://acrobat.adobe.com/id/urn:aaid:sc:AP:da31137e-be84-44fb-8974-d038eeff0283)

![schermata per riferimento](../../assets/authoring/markdown_map.png)


#### Pubblica su PDF e output Web

AEM Guides offre sia l’opzione Web (Html5/Sito AEM) che l’opzione PDF (Native-PDF/DITA-OT) per pubblicare ditamap con contenuto Markdown

### Opzione 2: convertire Markdown in formato DITA

Pieno utilizzo delle funzionalità di AEM Guides, quali riutilizzabilità dei contenuti, traduzione dell’elaborazione condizionale, linea di base, ecc. Tuttavia, per convertire `.md` nel formato `.dita` sono necessari sforzi iniziali.

È possibile convertire Markdown in DITA utilizzando strumenti esterni come Adobe FrameMaker e DITA-OT.


Per Adobe FrameMaker, fare riferimento a: [Importa markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Per DITA-OT, fare riferimento a: [Markdown come input](https://www.dita-ot.org/dev/topics/markdown-input.html)

File di esempio convertito con Adobe FrameMaker: [Esempio Markdown in DITA](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Pubblica su PDF e output Web

Una volta convertiti i file Markdown in DITA, l’utente può pubblicare facilmente l’output in qualsiasi formato disponibile in AEM Guides.

Formati disponibili in AEM Guides: [Formati di output](../../../../user-guide/generate-output-understand-presets.md)
