---
title: Note sulla versione | Sono stati risolti dei problemi nella versione 2024.10.0 Service Pack 1 di Adobe Experience Manager Guides
description: Scopri le correzioni di bug nella versione 2024.10.0 Service Pack 1 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: d5fa200b-1f15-4ec2-adf9-a29382afc3de
TQID: https://experienceleague.adobe.com/ziRAAFKf5Dl-6Hd7ziXwSJepbiVzkXLGz5jDWIILPkU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 5%

---

# Sono stati risolti i problemi nella versione 2024.10.0 Service Pack 1

Questo articolo descrive i bug corretti in varie aree della versione 2024.10.0 Service Pack 1 di Adobe Experience Manager Guides as a Cloud Service.

## Authoring

- La creazione di mappe DITA in un&#39;istanza UUID non riesce se `xmleditor.uniquefilenames` è abilitato in `XMLEditorConfig`. (21201)
- Quando si chiude un file, i commenti e le etichette aggiunti nella finestra di dialogo **Salva modifiche e sblocca file** non vengono salvati nella cronologia delle versioni con la nuova versione. Questo è specifico per un caso d&#39;uso in cui **Chiedi archiviazione alla chiusura** o **Chiedi nuova versione alla chiusura** è abilitato in `XMLEditorConfig`. (20065)
- Lo stato del documento contrassegnato come **Fine** torna a **Bozza** prima di salvare una nuova versione, con conseguente stato **Fine** non persistente in nessuna versione del documento. (20006)
- Impossibile aggiungere un file PDF come riferimento a un&#39;immagine in un argomento dell&#39;editor Web. (21206)
- Se si seleziona un file DITA nell&#39;interfaccia utente di Assets, viene visualizzata l&#39;opzione **Apri in FrameMaker**, anche se disabilitata nella configurazione. (20082)

## Pubblicazione

- Nell’output del PDF nativo, i titoli dei capitoli non sono presenti nel sommario, generando una gerarchia errata. (21840)


## Gestione

- Le perdite di risorse si verificano a causa di **errori ResourceResolver** non chiusi nei registri. (18488)
- Quando si crea una baseline nuova o duplicata, le etichette vengono visualizzate in ordine casuale. (19307)


## Riferimento

- La modifica e il salvataggio di una baseline in una configurazione Cloud hanno timeout dopo 1 minuto se la baseline ha un numero elevato di argomenti o mappe. (19558)

## Traduzione

- La traduzione delle mappe tramite Baseline diventa lenta e alla fine non riesce a caricare l’elenco di tutti gli argomenti e i file di mappe associati. (19733)
