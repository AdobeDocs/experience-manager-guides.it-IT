---
title: Guide alla pubblicazione di benchmark su AEMaaCS
description: Comprendere i limiti di sistema per la pubblicazione su AEM Cloud.
feature: Publishing
role: User, Admin
source-git-commit: 6e2577f04f1092ec9d8445ddbb97aa34be1e53a4
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 20%

---

# Benchmark per la pubblicazione di AEM Guides su AEMaaCS

Questo benchmark valuta le prestazioni delle nuove API Publishing per diversi predefiniti di output e per dimensioni di mappa crescenti in AEM Guides as a Cloud Service. L’obiettivo è comprendere il comportamento in termini di scalabilità e identificare i colli di bottiglia nelle prestazioni.

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