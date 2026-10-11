---
title: Guide alla pubblicazione di benchmark su AEMaaCS
description: Comprendere i limiti di sistema per la pubblicazione su AEM Cloud.
feature: Publishing
role: User, Admin
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 20%
---
# Benchmark per la pubblicazione di AEM Guides su AEMaaCS

Questo benchmark valuta le prestazioni delle nuove API di pubblicazione nei diversi predefiniti di output e nelle dimensioni crescenti delle mappe in AEM Guides as a Cloud Service. L’obiettivo è comprendere il comportamento in termini di scalabilità e identificare i colli di bottiglia nelle prestazioni.

Il servizio di pubblicazione utilizza un&#39;architettura [basata su microservizi](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/publish-microservice-architecture-and-performance) con scalabilità automatica che consente la gestione di carichi di lavoro di grandi dimensioni tramite pod aggiuntivi.

## Ambiente di esecuzione

- **Versione di AEM**:2026.4.25322.20260407T085152Z
- **Versione componente aggiuntivo Guide**: 2026.5.0
- **Conteggio pod iniziale**: 2 pod
- **Comportamento scalabilità automatica**: ridimensionato fino a 4 pod in 4 nodi con l&#39;aumento del carico
- **vCPU**: 10
- **RAM per pod**: 8 GB
- **Utenti simultanei**: 1 utente

>[!NOTE]
>
> Questo esercizio si concentra sul comportamento della pubblicazione all’aumentare delle dimensioni delle mappe, evidenziando l’impatto di mappe più grandi sulla velocità effettiva, sulla latenza e sul completamento complessivo della pubblicazione sotto carico.


## Numeri di generazione dell’output

**Sito AEM nativo**

| MapSize | Tempo di esecuzione (s) | Microservizio |
| ------- | ------------------ | ------------ |
| 10 | 62.378 | Sì |
| 100 | 64.27 | Sì |
| 1000 | 93.091 | Sì |
| 5000 | 496.319 | Sì |
| 10000 | 922.602 | Sì |

**PDF nativo**

| MapSize | Tempo di esecuzione (s) | Microservizio |
| ------- | ------------------ | ------------ |
| 10 | 62.302 | Sì |
| 100 | 62.431 | Sì |
| 1000 | 108.666 | Sì |
| 5000 | 201.379 | Sì |
| 10000 | 1170.689 | Sì |

**PDF**

| MapSize | Tempo di esecuzione (s) | Microservizio |
| ------- | ------------------ | ------------ |
| 10 | 30.926 | Sì |
| 100 | 30.987 | Sì |
| 1000 | 77.007 | Sì |
| 5000 | 247.505 | Sì |
| 10000 | 686.61 | Sì |

**HTML5**

| MapSize | Tempo di esecuzione (s) | Microservizio |
| ------- | ------------------ | ------------ |
| 10 | 30.844 | Sì |
| 100 | 30.834 | Sì |
| 1000 | 77.384 | Sì |
| 5000 | 170.237 | Sì |
| 10000 | 419.166 | Sì |


## Osservazioni chiave

- Il tempo di generazione del sito AEM dipende dal modello utilizzato. Se si utilizza un modello complesso, il tempo di esecuzione potrebbe aumentare.
- Il tempo di esecuzione della pubblicazione personalizzata si basa su un output personalizzato di esempio. Il tempo di pubblicazione personalizzato dipende esclusivamente dalla logica di trasformazione del cliente.