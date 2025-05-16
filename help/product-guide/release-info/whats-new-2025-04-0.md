---
title: Note sulla versione | Novità di Adobe Experience Manager Guides versione 2025.04.0
description: Scopri le funzioni nuove e migliorate della versione 2025.04.0 di Adobe Experience Manager Guides
role: Leader
exl-id: 5d28119b-641f-402b-833c-6f7554e7c273
source-git-commit: fe7d81f1826fe4ee0c716df36daabe3c5efd8994
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 3%

---

# Novità della versione 2025.04.0 (aprile 2025)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2025.04.0 di Adobe Experience Manager Guides as a Cloud Service.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2025.04.0](fixed-issues-2025-04-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.04.0](../release-info/upgrade-instructions-2025-04-0.md).

## Attributo &#39;Format&#39; aggiunto per i collegamenti di riferimento

Adobe Experience Manager Guides ora aggiunge un attributo **format** per i collegamenti di riferimento all&#39;interno dell&#39;editor. Questo attributo viene visualizzato nella **visualizzazione Source** e indica chiaramente il tipo di file, ad esempio:

- Per i file con estensione **.pdf**, il formato verrà impostato su **pdf**
- Per i file con estensione **.html**, il formato sarà impostato su **html**
- Per i file con un file **.dita** o **.ditamap**, il formato verrà impostato su **dita**

Inoltre, anche i file con estensione **.xml** avranno il formato impostato su **dita**. Per i file senza estensione, il formato viene lasciato vuoto. Inoltre, per qualsiasi collegamento di riferimento con ambito impostato su **external**, il formato verrà impostato su **html** indipendentemente dall&#39;estensione del file nei collegamenti di riferimento.

## La baseline esportata ora include lo stato del documento

La funzionalità Esporta baseline ora include lo **stato del documento** insieme a dettagli chiave quali titolo, nome file, tipo di file e numero di versione nello snapshot della baseline. Questo miglioramento migliora la gestione della linea di base fornendo una panoramica più completa.

Per ulteriori dettagli, visualizzare [Crea e gestisci baseline dalla console Mappa](../user-guide/web-editor-baseline.md#manage-baselines).

## Esperienza di ricerca avanzata per il pannello Contenuti riutilizzabili

Experience Manager Guides introduce un’esperienza di ricerca avanzata nel pannello Contenuto riutilizzabile. Con questo aggiornamento, la ricerca di qualsiasi parola chiave ora analizza tutti i file aggiunti come contenuto riutilizzabile e non solo quelli aperti, garantendo di trovare la posizione esatta della parola chiave in tutte le occorrenze, indipendentemente dal fatto che i contenitori siano aperti o compressi. Inoltre, quando si cancella la barra di ricerca, viene mantenuto lo stato originale di tutti i contenitori, fornendo una funzionalità di ricerca più efficiente e intuitiva.

Per ulteriori dettagli, visualizzare [Contenuto riutilizzabile](../user-guide/web-editor-features.md#reusable-content).


## Aggiornamento della versione Java per i contenitori microservizi

Per gli ambienti cloud abilitati per i microservizi, passeremo all’utilizzo di Java 21, garantendo che i processi di generazione DITA-OT e PDF nativi esistenti non subiscano modifiche. Il flusso di lavoro esistente di DITA-OT 3 continuerà a funzionare senza problemi con Java 21.  Inoltre, DITA-OT 4 sarà completamente operativo, consentendo agli utenti di generare PDF utilizzando DITA-OT e PDF nativo, nonché di produrre output per siti AEM nativi e altri formati.
