---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di aprile 2023
description: Versione di aprile 2023 di Adobe Experience Manager Guides as a Cloud Service
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/c1aOcwHgxAs11yAalOnlW-ghsTP1Or32TnBwLsc59-M
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 386
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

Nella versione di aprile è ora possibile eseguire più richieste di pubblicazione simultaneamente e generare output in blocco di PDF in modo molto efficiente utilizzando la pubblicazione nativa di PDF basata su microservizi.
Per ulteriori dettagli, vedere [Configurare la nuova pubblicazione basata su microservizi per AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
