---
title: Note sulla versione | Sono stati risolti i problemi nella versione 2024.12.0 di Adobe Experience Manager Guides
description: Scopri le correzioni di bug nella versione 2024.12.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f643a4a22151af2ff14288ab3885c1a6657a80ca
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# Sono stati risolti i problemi nella versione 2024.12.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2024.12.0 di Adobe Experience Manager Guides as a Cloud Service.

Scopri le [istruzioni di aggiornamento per la versione 2024.12.0](./upgrade-instructions-2024-12-0.md).

## Authoring

- La creazione di mappe DITA in un&#39;istanza UUID non riesce se `xmleditor.uniquefilenames` è abilitato in `XMLEditorConfig`. (21201)
- Quando si chiude un file, i commenti e le etichette aggiunti nella finestra di dialogo **Salva modifiche e sblocca file** non vengono salvati nella cronologia delle versioni con la nuova versione. Questo è specifico per un caso d&#39;uso in cui **Chiedi archiviazione alla chiusura** o **Chiedi nuova versione alla chiusura** è abilitato in `XMLEditorConfig`. (20065)
- Lo stato del documento contrassegnato come **Fine** torna a **Bozza** prima di salvare una nuova versione, con conseguente stato **Fine** non persistente in nessuna versione del documento. (20006)
- Impossibile aggiungere un file PDF come riferimento a un&#39;immagine in un argomento dell&#39;editor Web. (21206)
- Se si seleziona un file DITA nell&#39;interfaccia utente di Assets, viene visualizzata l&#39;opzione **Apri nel FrameMaker**, anche se disabilitata nella configurazione. (20082)

## Pubblicazione

- Nell’output di Native PDF, i titoli dei capitoli non sono presenti nel sommario, generando una gerarchia errata. (21840)


## Gestione

- Le perdite di risorse si verificano a causa di **errori ResourceResolver** non chiusi nei registri. (18488)
- Quando si crea una baseline nuova o duplicata, le etichette vengono visualizzate in ordine casuale. (19307)


## Riferimento

- Se la baseline presenta un numero elevato di argomenti o mappe, la modifica e il salvataggio di una baseline in una configurazione cloud hanno un timeout dopo 1 minuto. (19558)

## Traduzione

- La traduzione delle mappe utilizzando la linea di base diventa lenta e alla fine non riesce a caricare l’elenco di tutti gli argomenti e i file di mappe associati. (19733)
