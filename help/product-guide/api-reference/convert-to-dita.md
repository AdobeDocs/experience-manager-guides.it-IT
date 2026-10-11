---
title: API REST per il flusso di lavoro di conversione
description: Scopri le API REST per il flusso di lavoro di conversione
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/EG-ugDPVpviaEI1SXHOaFLPfChkzqQ8tSkPV-LZ-X3o'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: d3b388b7-b49d-4f87-b444-9b6f7fc2ef0c
    internal-label: REST API Conversion Workflow
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 9%
---
# API REST per il flusso di lavoro di conversione {#id175UB30E05Z}

Le seguenti API REST consentono di convertire documenti Word, HTML e InDesign in formato DITA.

## Convertire documenti di Word

Un metodo GET che converte i documenti di Word in formato DITA.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/fmdita/conversion

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| ``operation`` | Stringa | Sì | Nome dell&#39;operazione chiamata. Il valore di questo parametro è ``word2dita``. <br> **Nota:** il valore non distingue tra maiuscole e minuscole. |
| `inputFile` | Stringa | Sì | Percorso assoluto dei file Word di origine nell’archivio AEM. |
| `destPath` | Stringa | Sì | Percorso assoluto della posizione di destinazione in cui verranno salvati i file DITA convertiti. |
| `createRev` | Booleano | Sì | Specificare se creare una revisione dei file \( `true`\) nella destinazione specificata o meno \( `false`\). Questo viene considerato solo quando il percorso di destinazione contiene una versione esistente dei file convertiti. |
| `style2tagMap` | Stringa | Sì | Percorso assoluto del file di mapping degli stili che verrà utilizzato per la conversione. |

**Valori risposta**:
Restituisce una risposta HTTP 200 \(Riuscito\).

## Conversione di documenti HTML

Un metodo GET che converte i documenti HTML in formato DITA.

**URL richiesta**:

http://*<server-guide-aem\>*: *<numero-porta\>*/bin/fmdita/conversion

**Parametri**:

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `operation` | Stringa | Sì | Nome dell&#39;operazione chiamata. Il valore di questo parametro è ``html2dita``. <br> **Nota:** il valore non distingue tra maiuscole e minuscole. |
| `inputFile` | Stringa | Sì | Percorso assoluto dei file HTML di origine nell’archivio AEM. |
| `destPath` | Stringa | Sì | Percorso assoluto della posizione di destinazione in cui verranno salvati i file DITA convertiti. |
| `createRev` | Booleano | Sì | Specificare se creare una revisione dei file \( `true`\) nella destinazione specificata o meno \( `false`\). Questo viene considerato solo quando il percorso di destinazione contiene una versione esistente dei file convertiti. |

**Valori risposta**:

Restituisce una risposta HTTP 200 \(Riuscito\).

## Conversione di documenti InDesign

Un metodo GET che converte i documenti InDesign in formato DITA.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/fmdita/conversion

**Parametri**:

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| ``operation`` | Stringa | Sì | Nome dell&#39;operazione chiamata. Il valore di questo parametro è ``idml2dita``. <br> **Nota:** il valore non distingue tra maiuscole e minuscole. |
| `inputFile` | Stringa | Sì | Percorso assoluto dei file InDesign di origine nell’archivio AEM. |
| `destPath` | Stringa | Sì | Percorso assoluto della posizione di destinazione in cui verranno salvati i file DITA convertiti. |
| `createRev` | Booleano | Sì | Specificare se creare una revisione dei file \( `true`\) nella destinazione specificata o meno \( `false`\). Questo viene considerato solo quando il percorso di destinazione contiene una versione esistente dei file convertiti. |

**Valori risposta**:
Restituisce una risposta HTTP 200 \(Riuscito\).
