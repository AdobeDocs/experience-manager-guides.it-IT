---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides 4.6.0 Service Pack 1
description: Scopri le correzioni di bug nella versione 4.6.0 Service Pack 1 di Adobe Experience Manager Guides
role: Leader
exl-id: ab45ac10-8a97-4ade-accc-2b884da0e973
TQID: https://experienceleague.adobe.com/-PGxudGeachzaYoru1fHTObZcwRuXzle5s7KRRJlfBA
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
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 4%

---

# Sono stati risolti i problemi nella versione 4.6.0 Service Pack 1 (ottobre 2024)


Questo articolo descrive i bug corretti in varie aree della versione 4.6.0 Service Pack 1 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 4.6.0 Service Pack 1](upgrade-instructions-4-6-0-sp1.md).

## Authoring

- La creazione di mappe DITA in un&#39;istanza UUID non riesce se `xmleditor.uniquefilenames` è abilitato in `XMLEditorConfig`. (21201)
- Quando si chiude un file, i commenti e le etichette aggiunti nella finestra di dialogo **Salva modifiche e sblocca file** non vengono salvati nella cronologia delle versioni con la nuova versione. Questo è specifico per un caso d&#39;uso in cui **Chiedi archiviazione alla chiusura** o **Chiedi nuova versione alla chiusura** è abilitato in `XMLEditorConfig`. (20065)
- Lo stato del documento contrassegnato come **Fine** viene ripristinato come **Bozza** prima di salvare una nuova versione. Lo stato **Fine** non persiste in nessuna versione del documento. (20006)
- Impossibile aggiungere un file PDF come riferimento a un&#39;immagine in un argomento dell&#39;editor Web. (21206)
- Se si seleziona un file DITA nell&#39;interfaccia utente di Assets, viene visualizzata l&#39;opzione **Apri in FrameMaker**, anche se disabilitata nella configurazione. (20082)


## Pubblicazione

- Il caricamento di allegati in Salesforce non riesce se il percorso dell&#39;allegato supera la lunghezza consentita. (19420)
- Quando si pubblica un argomento in Salesforce, i collegamenti ai file di PDF non vengono risolti. (19304)
- L&#39;errore `DUPLICATE_VALUE` si verifica in modo intermittente quando si tenta di ripubblicare un articolo esistente in Salesforce. (17932)
- Nell’output del PDF nativo, i titoli dei capitoli non sono presenti nel sommario, generando una gerarchia errata. (21840)
- Quando si pubblica AEM Sites, è disponibile solo un numero limitato di attributi da includere nel sommario. (7483)

## Gestione

- Le perdite di risorse si verificano a causa di errori **ResourceResolver** non chiusi nei registri. (18488)
- Quando si crea una baseline nuova o duplicata, le etichette vengono visualizzate in ordine casuale. (19307)
