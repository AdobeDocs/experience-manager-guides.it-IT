---
title: Domande frequenti sulla nuova migrazione della linea di base in Adobe Experience Manager Guides
description: Scopri le domande frequenti sulla nuova migrazione della linea di base in Adobe Experience Manager Guides.
TQID: https://experienceleague.adobe.com/hsiglBlwA8KOqUkkDck1RZb307TBuHfoVFb64DKTcXk
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388bid: f6b497f1-f8e0-42ce-8e95-56c28d94026eid: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: 919
ht-degree: 0%

---

# Domande frequenti sulla migrazione della nuova linea di base

Queste domande frequenti riguardano le domande comuni relative alla migrazione della nuova linea di base, alle modifiche del comportamento, alle considerazioni sulla migrazione e ai risultati previsti durante l’aggiornamento al modello della nuova linea di base.

## Quali sono i vantaggi principali della migrazione alla nuova linea di base?

Il modello Nuova linea di base offre diversi miglioramenti, tra cui:

- Prestazioni e scalabilità migliorate
- Migliore coerenza dell’interfaccia utente e del back-end
- Comportamento deterministico di modifica e salvataggio
- Funzionalità di filtraggio e navigazione migliorate
- Anteprime di impatto delle dipendenze
- Maggiore affidabilità durante la creazione e gli aggiornamenti della linea di base
- Migliore supporto per API e automazione

## La migrazione della linea di base crea nuove linee di base per tutte le versioni di una mappa?

No, il processo di migrazione crea nuove linee di base solo per la **copia di lavoro corrente** della mappa. Le linee di base associate ad altre copie in modifica non sono incluse nella migrazione.

## Cosa succede quando un utente ripristina una versione precedente di una mappa?

Quando si ripristina o si accede a una versione precedente di una mappa, le linee di base associate a tale versione vengono migrate automaticamente al nuovo modello di linea di base tramite un processo di migrazione asincrono.

## I riferimenti non validi vengono migrati alla nuova linea di base?

No, i riferimenti non validi vengono ignorati durante la migrazione per mantenere la coerenza della linea di base e garantire l’affidabilità della linea di base migrata.

## La migrazione della linea di base modifica la linea di base?

La migrazione della linea di base mantiene tutti i contenuti e i riferimenti della linea di base validi esattamente come sono. I riferimenti non validi, tuttavia, non vengono inclusi nella baseline migrata. A parte la rimozione dei riferimenti non validi, la migrazione non introduce alcuna modifica ai riferimenti o al comportamento di risoluzione delle dipendenze.

Eventuali ulteriori modifiche ai riferimenti o alla risoluzione delle dipendenze possono essere apportate solo dopo la modifica, la ricostruzione o la nuova creazione della baseline migrata mediante il nuovo modello di baseline.

Fino a quando non viene eseguita una di queste azioni, la linea di base migrata continua a riflettere la definizione della linea di base originale.

## `reltable` riferimenti sono inclusi nel nuovo modello di base?

No, i riferimenti provenienti da `reltable` elementi sono esclusi dalla risoluzione della linea di base, coerentemente con il comportamento del modello di base legacy.

## Come vengono gestiti i riferimenti DIRETTI nella nuova linea di base?

Nel modello della nuova linea di base, i riferimenti alle mappe dirette sono esplicitamente classificati come **riferimenti DIRETTI**. Durante la migrazione e la risoluzione della linea di base, questi riferimenti hanno la precedenza più alta e vengono risolti prima di tutti gli altri tipi di riferimento.

## Sono inclusi `scope="peer"` riferimenti nella linea di base?

No, i riferimenti con `scope="peer"` non sono inclusi nel modello di base. L’esclusione di questi riferimenti migliora le prestazioni di pubblicazione ed evita un’inutile risoluzione delle dipendenze.

## È ancora possibile gestire le linee di base dal dashboard mappa?

No, la gestione della baseline è supportata solo dalla **console mappa** nella nuova baseline.La creazione e la gestione delle baseline dalla **dashboard mappa** non sono supportate.

## Sono necessarie precauzioni durante la migrazione?

Sì, le modifiche della linea di base devono essere evitate mentre è in corso una migrazione, in particolare nelle copie di lavoro. Le modifiche apportate alle linee di base durante la migrazione possono causare errori di migrazione e lasciare le linee di base in uno stato incoerente.

## Cosa succede se mancano delle versioni dopo la migrazione?

Se le versioni a cui fanno riferimento queste baseline non sono più disponibili o accessibili, potrebbe essere necessario ricreare alcune baseline dopo la migrazione.


## Qual è il tempo approssimativo necessario per migrare le linee di base per una configurazione locale?

Il tempo di migrazione dipende da diversi fattori, tra cui:

- Numero di linee di base di cui eseguire la migrazione
- Numero totale di riferimenti tra le linee di base
- Dimensioni e complessità dell’archivio
- Configurazione hardware
- Risorse di sistema disponibili

In base ai test interni e alle osservazioni da archivi contenenti circa 18.000 riferimenti, la durata della migrazione può variare in modo significativo a seconda della struttura dell’archivio e dell’ambiente operativo.

| Ambito di migrazione | Durata tipica |
|-----------------|------------------|
| Linea di base singola | Qualche secondo |
| 10-15 linee di base | Qualche decina di secondi |
| 25-50 linee di base | Circa 1-2 minuti |

>[!NOTE]
>
> Queste cifre sono fornite solo a scopo di riferimento e si basano su un ambiente locale. I valori effettivi possono variare a seconda della complessità del repository, della capacità dell&#39;infrastruttura, della configurazione hardware e delle condizioni operative generali.

## È possibile ripristinare le vecchie linee di base?

Sì. Tuttavia, quando viene eseguito un rollback, le vecchie linee di base vengono ripristinate allo stato in cui si trovavano al momento della migrazione. Eventuali modifiche apportate mentre la vecchia configurazione di base è disabilitata e la nuova configurazione di base è attiva non vengono riportate nelle baseline ripristinate.

I vecchi oggetti della baseline originale rimangono disponibili nella posizione originale. Quando la nuova configurazione della linea di base viene disattivata, il sistema torna automaticamente a utilizzare gli oggetti originali.

## Come possiamo effettuare la migrazione a nuove linee di base?

Per eseguire la migrazione alla nuova linea di base, seguire i passaggi descritti in [Esegui migrazione a nuova linea di base](./web-editor-baseline-v2.md#migrate-to-new-baseline).

## È possibile migrare alla nuova linea di base in qualsiasi momento? Esistono prerequisiti?

Sì. Puoi abilitare la nuova linea di base in qualsiasi momento, purché l’ambiente soddisfi i requisiti minimi di versione.

**Prerequisiti:**

- AEM Guides (On-Premise): versione 5.2 o successiva
- AEM Guides (Cloud Service): versione 2026.05.0 o successiva

Una volta soddisfatti questi requisiti, è possibile migrare le baseline precedenti esistenti al nuovo modello di baseline e iniziare a utilizzarne le funzionalità.

## È necessario eseguire il backup dello stato corrente del server prima di eseguire la migrazione alla nuova linea di base?

Non è richiesto alcun backup aggiuntivo specifico per la migrazione alla nuova linea di base.

Tuttavia, le baseline associate alla copia in modifica possono andare perse se un utente esegue successivamente un&#39;operazione di ripristino della versione. Questo comportamento non è univoco per il nuovo modello di linea di base; il ripristino di una versione precedente può anche rimuovere i nodi delle vecchie copie di lavoro della linea di base corrispondenti.

Se è importante mantenere le linee di base della copia di lavoro, si consiglia di eseguirne il backup prima della migrazione. Dopo la migrazione, gli utenti lavoreranno principalmente con le nuove linee di base, ma un successivo ripristino della versione può ancora causare la perdita delle linee di base della copia in modifica.


