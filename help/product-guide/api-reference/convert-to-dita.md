---
title: API REST per il flusso di lavoro di conversione
description: Scopri le API REST per il flusso di lavoro di conversione
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 45ae1471fe0f0586764ede9dd96530b7f75f69ee
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 9%

---

# API REST per il flusso di lavoro di conversione {#id175UB30E05Z}

Le seguenti API REST consentono di convertire documenti Word, HTML e InDesign in formato DITA.

## Convertire documenti di Word

Metodo di GET che converte i documenti di Word in formato DITA.

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

Metodo GET che converte i documenti HTML in formato DITA.

**URL richiesta**:

http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/fmdita/conversion

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

Metodo GET che converte i documenti InDesign in formato DITA.

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
