---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di aprile 2023
description: Versione di aprile 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Novità della versione di aprile 2023 di Adobe Experience Manager Guides as a Cloud Service

Questo articolo descrive le funzioni nuove e migliorate della versione di aprile 2023 di Adobe Experience Manager Guides (in seguito denominato *AEM Guides as a Cloud Service*).

Per ulteriori dettagli sulle istruzioni di aggiornamento, sulla matrice di compatibilità e sui problemi risolti in questa versione, consulta l&#39;articolo [Note sulla versione](release-notes-2023-4-0.md).

## Supporto avanzato dei metadati nella pubblicazione PDF

AEM Guides ora fornisce supporto avanzato per i metadati mappati sui metadati nell’output PDF. Le opzioni relative ai metadati includono informazioni sul documento e sul relativo contenuto, ad esempio il nome dell&#39;autore, il titolo del documento, le parole chiave, le informazioni sul copyright e altri campi dati.

<img src="assets/pdf-metadata.png" alt=" metadati pdf nativi">

Puoi importare un file XMP e AEM Guides può scegliere le informazioni dal file. Puoi anche fornire i nomi e i valori dei metadati utilizzando il menu a discesa. Puoi anche aggiungere metadati personalizzati digitando direttamente nel campo del nome.


## Pannello Visualizzazione Struttura migliorata

AEM Guides fornisce un pannello Visualizzazione struttura migliorato in cui è possibile ottenere la visualizzazione gerarchica degli elementi utilizzati nel documento.

<img src="assets/select-element-content-outline-view_cs.png" alt=" metadati pdf nativi">

La vista Struttura offre i seguenti miglioramenti:

* Il menu a discesa Opzioni vista (View Options) viene visualizzato sopra il pannello Visualizzazione struttura (Outline View). Se un elemento ha un ID, un attributo e un testo, puoi selezionarli dal menu a discesa per visualizzarli insieme all’elemento. Gli attributi che possono essere visualizzati nel pannello Visualizzazione struttura sono determinati dalle impostazioni Attributi di visualizzazione configurate dall&#39;amministratore nelle **Impostazioni editor**.

* Utilizzando la funzione di ricerca, puoi cercare un elemento in base al suo nome, ID, testo o valore dell’attributo.


## Pubblicazione basata su microservizi per AEM Guides as a Cloud Service

AEM Guides as a Cloud Service fornisce la funzione di eseguire carichi di lavoro di pubblicazione di grandi dimensioni in concomitanza con la pubblicazione basata su microservizi e di sfruttare la piattaforma senza server Adobe I/O Runtime leader del settore.

Nella versione di aprile è ora possibile eseguire più richieste di pubblicazione simultaneamente e generare output di PDF in blocco in modo molto efficiente utilizzando la pubblicazione di PDF nativi basata su microservizi.
Per ulteriori dettagli, consulta [Configurare la nuova pubblicazione basata su microservizi per AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
