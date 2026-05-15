---
title: Note sulla versione | Novità di Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Scopri le funzioni nuove e migliorate di Adobe Experience Manager Guides versione 5.1.0 Service Pack 3
role: Leader
exl-id: 1b2e45a8-bea6-4b78-bd2e-cc02df86f40a
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 0%

---

# Novità della versione 5.1.0 Service Pack 3 (dicembre 2025)

Questo articolo descrive le nuove funzioni introdotte con la versione 5.1.0 Service Pack 3 di Adobe Experience Manager Guides.

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 5.1.0 Service Pack 3](fixed-issues-5-1-0-sp3.md).

Informazioni sulle [istruzioni di aggiornamento per la versione 5.1.0 Service Pack 3](../release-info/upgrade-instructions-5-1-0-sp3.md).


## Configurare rappresentazioni di immagini personalizzate per predefiniti di output specifici

È ora possibile configurare diverse rappresentazioni di immagini per singoli predefiniti di output nello stesso tipo di output utilizzando l&#39;attributo `outputName` in `renditionmapping.xml`. Questo miglioramento offre maggiore flessibilità quando si pubblicano contenuti che richiedono risoluzioni di immagine diverse per scenari diversi. Ad esempio, potresti desiderare un’immagine ad alta risoluzione per l’output principale di HTML5 mentre utilizzi una miniatura più piccola per un predefinito leggero.

Per ulteriori dettagli, visualizzare [Gestire la rappresentazione dell&#39;immagine nella generazione dell&#39;output](../install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).
