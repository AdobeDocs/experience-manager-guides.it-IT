---
title: Gestire i tag per i file DITA in AEM Guides
description: Breve articolo da raccontare sulla gestione di cq:tags in AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
TQID: 'https://experienceleague.adobe.com/u3MZ3fUZIp-FYQE895I7kDRkF3l96KhwYMRMJ-rG2RE'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: da9cce28-0561-45e7-851e-4500741b9744
    internal-label: Metadata management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%
---
# Come aggiungere, rimuovere e gestire i tag nel contenuto DITA

I tag risultano utili per categorizzare il contenuto. Se il contenuto è correttamente taggato, può essere utile individuare gli argomenti esatti nella mappa digitale e l’utente finale può trovare il contenuto appropriato più rapidamente nell’output pubblicato

> **_NOTA:_** Il seguente articolo è per AEM Guides Build 4.2 (on-prem) /Feb 2023 (versione cloud ) o versioni successive


## Creare i tag

L’assegnazione tag è una funzione nativa di AEM e l’amministratore AEM può aiutarti nella creazione e nella configurazione iniziale di questi tag.


## Aggiungere, rimuovere e gestire i tag nel contenuto DITA

**Qualsiasi tag creato in AEM cq: tags può essere aggiunto, rimosso e gestito per i contenuti DITA**

Esistono diversi modi per aggiungere tag ai contenuti DITA, ma questo articolo si concentrerà sull’interfaccia utente dell’editor web di AEM Guides.

### Passaggi:

1. Vai alla vista archivio nell’interfaccia utente Guide
2. Fai doppio clic su mappa e apri in vista mappa
3. Vai alla scheda Gestione
4. Nella scheda Gestisci , vai all’opzione Metadati
5. Tutti i file ditamap diretti e indiretti vengono caricati qui.
6. Seleziona uno o più file e fai clic sull’icona &quot;Gestisci&quot;. Qui puoi aggiungere tag ai file selezionati.
È inoltre possibile rimuovere i tag esistenti comuni nei file selezionati.

<img title="Gestire i tag in AEM Guides " alt="Gestire i tag in DITA " src="ManageTags.jpg">

## Risoluzione dei problemi e domande frequenti

### L’elenco in Gestisci->metadati è vuoto o incompleto

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Istruzioni per l&#39;aggiornamento (indicizza il contenuto)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=en#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### I metadati personalizzati non vengono visualizzati nell’elenco

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Altre risorse utili

- [Assegnazione di tag in blocco tramite Map Dashboard (interfaccia utente di Assets)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=en)
- [Rapporti Ditamap nell’editor web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=en)
- [Assegnazione di tag in AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Contatta il tuo CSM per qualsiasi altra domanda**
