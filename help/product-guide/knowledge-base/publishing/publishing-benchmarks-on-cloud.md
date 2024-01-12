---
title: Guide alla pubblicazione di benchmark su AEMaaCS
description: Comprendere i limiti di sistema per la pubblicazione su AEM Cloud.
exl-id: 2cb4dfa4-dafc-409a-8d29-dbb00fabeae5
feature: Publishing
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 8%

---

# Guide AEM per la pubblicazione di benchmark su AEMaaCS

Attualmente il servizio cloud Guide AEM ha alcuni limiti sulla pubblicazione delle dimensioni delle mappe che il team Guide sta attivamente lavorando per risolvere.

Il team Guide ha introdotto un microservizio di pubblicazione scalabile per supportare mappe di grandi dimensioni e più pubblicazioni simultanee. Per ulteriori informazioni sul nuovo microservizio di pubblicazione, consulta [pubblicazione dell&#39;architettura dei microservizi](publish-microservice-architecture-and-performance.md)

Per configurare il nuovo servizio di pubblicazione per qualsiasi ambiente cloud AEM consulta [configurare una nuova pubblicazione basata su microservizi](configure-microservices.md)


## Ambiente di esecuzione

    Versione AEM: 2023.5.11983.20230511T173830Z
    Versione Del Componente Aggiuntivo Della Guida: 2023.6.0
    Modello per sito AEM: modello OOTB delle guide AEM
    Versione DITA-OT: 3.5.4
    Tipo di flusso di lavoro di pubblicazione: Dividi flusso di lavoro di pubblicazione
    Output supportato dal microservizio: Native PDF, PDF (Dita-OT)

## Numeri di generazione output

| Tipo di output | Dimensione mappa (riferimenti argomento) | Tempo di esecuzione (in secondi) | Pubblicazione di Microsoft Service |
|---------------|------------------------------|----------------------------|-----------------------|
| Sito AEM | 3500 | 5220 | No |
| Native PDF | 3500 | 780 | Sì |
| PDF (DITA-OT) | 11000 | 960 | Sì |
| HTML5 | 3500 | 240 | No |
| Personale | 300 | 300 | No |

## Punti chiave da ricordare

- Il sito AEM crea molti nodi cq:Page e li appiattisce eseguendo il rendering singolarmente durante la generazione. Per questo motivo, è consigliabile evitare di eseguire più pubblicazioni simultanee di grandi dimensioni del sito AEM, in quanto ciò potrebbe sovraccaricare il sistema.
- Il tempo di generazione del sito AEM dipende dal modello utilizzato. Il tempo di esecuzione può aumentare se si utilizza un modello complesso.
- Il tempo di esecuzione della pubblicazione personalizzata si riferisce a un output personalizzato di esempio. Il tempo di pubblicazione personalizzato dipende esclusivamente dalla logica di trasformazione del cliente.
