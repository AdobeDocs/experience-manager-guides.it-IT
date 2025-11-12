---
title: Note sulla versione | Novità di Adobe Experience Manager Guides versione 2025.10.0
description: Scopri le funzioni nuove e migliorate della versione 2025.10.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: 6f212862855e5ce1125137f462b88c933d23ed26
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 3%

---

# Novità della versione 2025.10.0 (ottobre 2025)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2025.10.0 di Adobe Experience Manager Guides as a Cloud Service.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2025.10.0](fixed-issues-2025-10-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.10.0](../release-info/upgrade-instructions-2025-10-0.md).


## Le impostazioni dell’editor vengono ora rinominate in impostazioni Workspace e sono accessibili dalla homepage

Per migliorare la navigazione e l’usabilità, sono stati introdotti i seguenti miglioramenti:

- **Impostazioni editor** in Experience Manager Guides è stato rinominato in **Impostazioni Workspace**.
- Il menu **Altre azioni** (il menu a tre punti), in precedenza disponibile solo nell&#39;interfaccia della console Editor e Mappa, è ora accessibile dalla [homepage](../user-guide/intro-home-page.md).

  ![](assets/workspace-settings.png)

## Identificare e correggere facilmente gli ID duplicati negli argomenti e nelle mappe nella visualizzazione Autore

Experience Manager Guides ora include un pulsante **ID duplicati** nell&#39;editor per identificare e correggere rapidamente gli ID duplicati presenti in un singolo argomento o mappa. Quando vengono rilevati ID duplicati, questo pulsante viene visualizzato nell&#39;angolo inferiore sinistro dell&#39;interfaccia dell&#39;editor nella visualizzazione **Autore**. Quando selezioni il pulsante, in un messaggio a comparsa viene visualizzato un elenco di tutte le istanze con ID duplicati. Selezionando un’istanza viene evidenziato il contenuto corrispondente nell’argomento o nella mappa, consentendo di individuare e correggere gli ID duplicati dal pannello di destra.

Per ulteriori dettagli, visualizzare [Altre funzionalità nell&#39;editor](../user-guide/web-editor-other-features.md).

![](assets/duplicate-element-IDs.png){width="350" align="left"}

## Miglioramenti all’archivio e ai filtri per i rapporti

Il filtro **Bloccato da** nei filtri Avanzati dell&#39;archivio e il filtro **Autore** nella mappa DITA ora caricano gli elenchi utente gradualmente durante lo scorrimento, anziché tutti contemporaneamente. Questo caricamento impaginato migliora la velocità e rende più efficiente e semplice l’utilizzo di set di dati per utenti di grandi dimensioni.

## Accedere allo stato delle attività di revisione direttamente dal pannello Revisione

In qualità di iniziatore di un’attività di revisione, ora puoi controllare lo stato dell’attività di revisione direttamente dal pannello Revisione. Con gli ultimi miglioramenti, la finestra di dialogo **Aggiorna attività** nel pannello Revisione include una nuova opzione **Controlla stato revisione**. Selezionando questa opzione si passa direttamente al dashboard di revisione, in cui è possibile visualizzare lo stato dell&#39;attività per ogni revisore, consentendo un accesso più rapido all&#39;avanzamento dell&#39;attività senza dover cambiare contesto.

Per ulteriori dettagli, visualizzare [Richiedere un riesame o chiudere un&#39;attività di revisione come autore](../user-guide/review-close-review-task.md).

![](assets/check-review-status-icon.png){width="350" align="left"}



## API per monitorare lo stato di post-elaborazione di cartelle o risorse

È ora disponibile una nuova API per monitorare lo stato di post-elaborazione di singole risorse e cartelle. Questa funzione è particolarmente utile per i team che utilizzano flussi di lavoro automatizzati, in cui la pubblicazione deve avvenire solo dopo che il contenuto è stato completamente elaborato. L’API offre un modo affidabile per confermare la preparazione, riducendo il rischio di errori di pubblicazione causati da un’elaborazione incompleta.

Inoltre, con l’introduzione di questa API, gli eventi di post-elaborazione delle risorse non verranno attivati automaticamente. Gli amministratori possono ora abilitare questo evento tramite un&#39;impostazione in `fmdita config manager`.

Per ulteriori informazioni, vedere:

- [API per tenere traccia dello stato di post-elaborazione di singole risorse e cartelle](../api-reference/track-post-processing-status.md)
- [Impostazione del gestore eventi di post-elaborazione in Gestione configurazione fmdita](../api-reference/post-process-event.md)

