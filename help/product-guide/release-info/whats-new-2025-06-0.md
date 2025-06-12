---
title: Note sulla versione | Novità di Adobe Experience Manager Guides versione 2025.06.0
description: Scopri le funzioni nuove e migliorate della versione 2025.06.0 di Adobe Experience Manager Guides
role: Leader
exl-id: 48f27aa6-d870-4228-8e62-db81699a25f7
source-git-commit: 158c2a99ac43fd70726bedf30f4de1a970a48864
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 3%

---

# Novità della versione 2025.06.0 (giugno 2025)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2025.06.0 di Adobe Experience Manager Guides as a Cloud Service.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2025.06.0](fixed-issues-2025-06-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.06.0](../release-info/upgrade-instructions-2025-06-0.md).

## I file temporanei per l’output pubblicato ora includono gli URL Author e Publish in un nuovo file di configurazione

I più recenti miglioramenti apportati alla pubblicazione di Experience Manager Guides ora aggiungono un nuovo file `system_config.json` ai file temporanei generati durante la pubblicazione degli output HTML, PDF e JSON tramite DITA-OT, nonché dell&#39;output PDF nativo. Questo file viene incluso automaticamente nel processo di pubblicazione e accessibile tramite file temporanei quando si abilita l&#39;opzione **Mantieni file temporanei** per i predefiniti e si genera l&#39;output.

Il file `system_config.json` contiene i dettagli chiave dell&#39;istanza, inclusi l&#39;URL di authoring, l&#39;URL locale e l&#39;URL di pubblicazione, che forniscono un contesto più chiaro e migliorano la tracciabilità degli URL scaricati.

Per ulteriori dettagli, visualizzare [Comprendere i predefiniti di output](../user-guide/generate-output-understand-presets.md).

## Richiesta di timeout della sessione per evitare la perdita accidentale di contenuto

Un messaggio a comparsa ora notifica la scadenza della sessione Adobe Experience Manager e l&#39;utente viene disconnesso a causa di inattività. Questo messaggio viene attivato quando si tenta di modificare il contenuto in Experience Manager Guides al termine della sessione. Questa funzione consente di ridurre il rischio di perdere il lavoro non salvato e di migliorare l’affidabilità e la fluidità complessive dell’esperienza, anche durante i periodi di inattività.

![](assets/sign-out-prompt.png)

Ulteriori informazioni sulla [richiesta di timeout sessione](../user-guide/session-timeout-prompt.md) in Experience Manager Guides.

## Opzioni avanzate per il download delle mappe nell’editor

Experience Manager Guides introduce una nuova opzione **Utilizza nomi di file effettivi** nella finestra di dialogo **Scarica mappa**. Ora, quando scarichi i file mappa, puoi scegliere di mantenere i nomi dei file originali invece degli UUID predefiniti, semplificando notevolmente il riconoscimento e la gestione dei file. Questa opzione è disponibile solo se si seleziona **Mantieni gerarchia file** ed è disabilitata quando si sceglie **Appiattisci gerarchia file**, per offrire maggiore flessibilità nell&#39;organizzazione delle mappe scaricate.

Per ulteriori dettagli, visualizzare [Scarica file](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}


## Gestione `navref` migliorata nell&#39;editor

Gli ultimi miglioramenti apportati all&#39;editor migliorano la gestione di `navref` elementi in una mappa DITA. Ora, quando si aggiunge un elemento `navref` a una mappa, viene visualizzata la finestra di dialogo **Seleziona percorso**, che consente di scegliere facilmente i riferimenti della mappa da includere come collegamenti di navigazione nella mappa. Una volta aggiunto, il titolo della mappa aggiunta viene visualizzato sia nella vista Author che nella vista Layout, fornendo una migliore visibilità della navigazione inclusa durante l’authoring.  Inoltre, l&#39;elemento `navref` aggiunto viene risolto automaticamente per visualizzare la mappa a cui si fa riferimento nell&#39;editor.

Per ulteriori dettagli, visualizzare [Aggiungi riferimenti di navigazione](../user-guide/map-editor-other-features.md#add-navigation-references).

## Miglioramenti delle prestazioni in AI Assistant

Questa versione introduce miglioramenti al motore di back-end di AI Assistant, offrendo prestazioni migliori e maggiore stabilità. Per attivare questo aggiornamento e continuare a utilizzare la Guida dell&#39;Assistente IA:

- Aggiorna la configurazione `chat.url` per riflettere il nuovo URL dell&#39;endpoint.
- Aggiungere una nuova variabile di ambiente `GUIDES_AI_SITE_ID` in Cloud Manager.

Per ulteriori dettagli, visualizzare [Configurare l&#39;Assistente AI](../cs-install-guide/conf-smart-suggestions.md).

