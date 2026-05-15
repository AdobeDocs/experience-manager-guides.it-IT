---
title: Note sulla versione | Novità della versione 2025.10.0 di Adobe Experience Manager Guides
description: Scopri le funzioni nuove e migliorate della versione 2025.10.0 di Adobe Experience Manager Guides
role: Leader
exl-id: 5bc6f1f6-225b-46c0-a05a-099583e402d8
TQID: https://experienceleague.adobe.com/G-6R7iN6pqp0e2J68IyyXdN9Fz--FjmMKcEhwtdAP2Q
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 523
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

![](assets/duplicate-element-IDs.png){width="350"}

## Miglioramenti all’archivio e ai filtri per i rapporti

Il filtro **Bloccato da** nei filtri Avanzati dell&#39;archivio e il filtro **Autore** nella mappa DITA ora caricano gli elenchi utente gradualmente durante lo scorrimento, anziché tutti contemporaneamente. Questo caricamento impaginato migliora la velocità e rende più efficiente e semplice l’utilizzo di set di dati per utenti di grandi dimensioni.

## Accedere allo stato delle attività di revisione direttamente dal pannello Revisione

In qualità di iniziatore di un’attività di revisione, ora puoi controllare lo stato dell’attività di revisione direttamente dal pannello Revisione. Con gli ultimi miglioramenti, la finestra di dialogo **Aggiorna attività** nel pannello Revisione include una nuova opzione **Controlla stato revisione**. Selezionando questa opzione si passa direttamente al dashboard di revisione, in cui è possibile visualizzare lo stato dell&#39;attività per ogni revisore, consentendo un accesso più rapido all&#39;avanzamento dell&#39;attività senza dover cambiare contesto.

Per ulteriori dettagli, visualizzare [Richiedere un riesame o chiudere un&#39;attività di revisione come autore](../user-guide/review-close-review-task.md).

![](assets/check-review-status-icon.png){width="350"}



## API per monitorare lo stato di post-elaborazione di cartelle o risorse

È ora disponibile una nuova API per monitorare lo stato di post-elaborazione di singole risorse e cartelle. Questa funzione è particolarmente utile per i team che utilizzano flussi di lavoro automatizzati, in cui la pubblicazione deve avvenire solo dopo che il contenuto è stato completamente elaborato. L’API offre un modo affidabile per confermare la preparazione, riducendo il rischio di errori di pubblicazione causati da un’elaborazione incompleta.

Inoltre, con l’introduzione di questa API, gli eventi di post-elaborazione delle risorse non verranno attivati automaticamente. Gli amministratori possono ora abilitare questo evento tramite un&#39;impostazione in `fmdita config manager`.

Per ulteriori informazioni, vedere:

- [API per tenere traccia dello stato di post-elaborazione di singole risorse e cartelle](../api-reference/track-post-processing-status.md)
- [Impostazione del gestore eventi di post-elaborazione in Gestione configurazione fmdita](../api-reference/post-process-event.md)
