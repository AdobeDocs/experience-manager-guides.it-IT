---
title: Utilizzare Markdown in DITA AEM Guides
description: Migrare e utilizzare markdown in DITA AEM Guides
author: Pulkit Nagpal(punagpal)
exl-id: a94c0129-df40-4b61-ac60-679b2ffe7e86
source-git-commit: f971be4be9e2d32618616727cd9c682941dd3fb2
workflow-type: tm+mt
source-wordcount: '256'
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


#### Output da Publish a PDF e Web

AEM Guides offre sia l’opzione Web (Html5/Sito AEM) che l’opzione PDF (Native-PDF/DITA-OT) per pubblicare ditamap con contenuto Markdown

### Opzione 2: convertire Markdown in formato DITA

Pieno utilizzo delle funzionalità di AEM Guides, quali riutilizzabilità dei contenuti, traduzione dell’elaborazione condizionale, linea di base, ecc. Tuttavia, per convertire `.md` nel formato `.dita` sono necessari sforzi iniziali.

È possibile convertire Markdown in DITA utilizzando strumenti esterni come Adobe FrameMaker e DITA-OT.


Per Adobe FrameMaker, fare riferimento a: [Importa markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Per DITA-OT, fare riferimento a: [Markdown come input](https://www.dita-ot.org/dev/topics/markdown-input.html)

File di esempio convertito con Adobe FrameMaker: [Esempio Markdown in DITA](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Output da Publish a PDF e Web

Una volta convertiti i file Markdown in DITA, l’utente può pubblicare facilmente l’output in qualsiasi formato disponibile in AEM Guides.

Formati disponibili in AEM Guides: [Formati di output](../../../../user-guide/generate-output-understand-presets.md)
