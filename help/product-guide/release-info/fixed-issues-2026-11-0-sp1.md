---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2026.11.0 Service Pack 1
description: Scopri le correzioni di bug nella versione 2026.11.0 Service Pack 1 di Adobe Experience Manager Guides as a Cloud Service.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8821e671951d83439688aa33f88ac1f91f0919eb
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%
---
# Sono stati risolti i problemi nella versione 2026.11.0 Service Pack 1

Questo articolo descrive i bug corretti nella versione 2026.11.0 Service Pack 1 di Adobe Experience Manager Guides as a Cloud Service.

## Pubblicazione

Durante la pubblicazione in AEM Sites (con mappatura di componenti compositi) si verificano i seguenti problemi:

- La rigenerazione degli argomenti selezionati o di una mappa secondaria con la pubblicazione di `microservice-based` richiede circa il tempo necessario per generare la mappa completa. (GUIDES-59322)
- Se si rigenera una mappa secondaria contenente argomenti raggruppati, nel sommario verranno visualizzati titoli e collegamenti non corretti. Ogni voce di argomento a blocchi mostra il titolo dell&#39;ultimo argomento a blocchi. (GUIDES-58650)

I seguenti problemi si verificano quando si pubblica in AEM Sites utilizzando una linea di base dinamica, Baseline (legacy) o Nuova linea di base:

- La linea di base viene ricreata più volte durante la stessa operazione di pubblicazione, il che allunga i tempi di pubblicazione e, in alcuni casi, causa l’arresto della ricostruzione. Con Nuova linea di base, la pubblicazione incrementale utilizza anche una linea di base obsoleta invece di quella corrente, pertanto l’output potrebbe non riflettere il contenuto più recente. (GUIDES-60189)
- Durante l’utilizzo della dashboard Mappa vengono rilevati alcuni problemi di prestazioni. (GUIDE-60189, GUIDE-55646)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2026.11.0 Service Pack 1:

- Quando si utilizza Experience Manager Guides as a Cloud Service 2026.11.0 o versione successiva, la pubblicazione non riesce e viene restituito un errore di applicazione se AEM riavvia alcuni servizi interni durante il processo di pubblicazione, ad esempio all’avvio di un’istanza del server. (GUIDES-60804)<br>**Soluzione:** Per risolvere il problema, ritentare la pubblicazione.
- Quando si genera l&#39;output per più predefiniti di AEM Sites (mediante la mappatura di componenti compositi) o predefiniti di PDF nativi tramite **Raccolta mappe** o API, la generazione dell&#39;output non riesce e viene generata un&#39;eccezione `Rebuild the Baseline`. <br>**Soluzione alternativa:** pubblicare i predefiniti in sequenza anziché simultaneamente per evitare il problema.