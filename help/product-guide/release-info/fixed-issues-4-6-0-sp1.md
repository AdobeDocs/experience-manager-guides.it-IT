---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides 4.6.0 Service Pack 1
description: Scopri le correzioni di bug nella versione 4.6.0 Service Pack 1 di Adobe Experience Manager Guides
role: Leader
source-git-commit: 2362870e0e3e6c08df03e8c547bb77de7faa0a02
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---


# Sono stati risolti i problemi nella versione 4.6.0 Service Pack 1 (ottobre 2024)


Questo articolo descrive i bug corretti in varie aree della versione 4.6.0 Service Pack 1 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 4.6.0 Service Pack 1](upgrade-instructions-4-6-0-sp1.md).

## Authoring

- La creazione di mappe DITA in un&#39;istanza UUID non riesce se `xmleditor.uniquefilenames` è abilitato in `XMLEditorConfig`. (21201)
- Quando si chiude un file, i commenti e le etichette aggiunti nella finestra di dialogo **Salva modifiche e sblocca file** non vengono salvati nella cronologia delle versioni con la nuova versione. Questo è specifico per un caso d&#39;uso in cui **Chiedi archiviazione alla chiusura** o **Chiedi nuova versione alla chiusura** è abilitato in `XMLEditorConfig`. (20065)
- Lo stato del documento contrassegnato come **Fine** viene ripristinato come **Bozza** prima di salvare una nuova versione. Lo stato **Fine** non persiste in nessuna versione del documento. (20006)
- Impossibile aggiungere un file PDF come riferimento a un&#39;immagine in un argomento dell&#39;editor Web. (21206)
- Se si seleziona un file DITA nell&#39;interfaccia utente di Assets, viene visualizzata l&#39;opzione **Apri nel FrameMaker**, anche se disabilitata nella configurazione. (20082)


## Pubblicazione

- Il caricamento di allegati in Salesforce non riesce se il percorso dell&#39;allegato supera la lunghezza consentita. (19420)
- Quando si pubblica un argomento in Salesforce, i collegamenti al file PDF non vengono risolti. (19304)
- L&#39;errore `DUPLICATE_VALUE` si verifica in modo intermittente quando si tenta di ripubblicare un articolo esistente in Salesforce. (17932)
- Nell’output di Native PDF, i titoli dei capitoli non sono presenti nel sommario, generando una gerarchia errata. (21840)
- Quando si pubblica AEM Sites, è disponibile solo un numero limitato di attributi da includere nel sommario. (7483)

## Gestione

- Le perdite di risorse si verificano a causa di errori **ResourceResolver** non chiusi nei registri. (18488)
- Quando si crea una baseline nuova o duplicata, le etichette vengono visualizzate in ordine casuale. (19307)









