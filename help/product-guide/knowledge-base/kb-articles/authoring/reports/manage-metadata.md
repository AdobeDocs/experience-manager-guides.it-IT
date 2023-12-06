---
title: Gestire i tag per i file DITA nelle guide AEM
description: Breve articolo da raccontare sulla gestione di cq:tags nelle guide AEM
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Come aggiungere, rimuovere e gestire i tag nel contenuto DITA

I tag risultano utili per categorizzare il contenuto. Se il contenuto è correttamente taggato, può essere utile individuare gli argomenti esatti nella mappa digitale e l’utente finale può trovare il contenuto appropriato più rapidamente nell’output pubblicato

> **_NOTA:_**  Il seguente articolo è relativo alla build 4.2 (on-prem)/Feb 2023 (versione cloud ) o alle versioni successive delle guide dell’AEM


## Creare i tag

L’assegnazione tag è una funzione AEM nativa e l’amministratore AEM può aiutarti nella creazione e nella configurazione iniziale di questi tag.


## Aggiungere, rimuovere e gestire i tag nel contenuto DITA

**Qualsiasi tag creato in AEM cq: tags può essere aggiunto, rimosso e gestito per i contenuti DITA**

Esistono diversi modi per aggiungere tag ai contenuti DITA, ma questo articolo si concentrerà sull’interfaccia utente dell’editor web delle guide dell’AEM.

### Passaggi:

1. Vai alla vista archivio nell’interfaccia utente Guide
2. Fai doppio clic su mappa e apri in vista mappa
3. Vai alla scheda Gestione
4. Nella scheda Gestisci , vai all’opzione Metadati
5. Tutti i file ditamap diretti e indiretti vengono caricati qui.
6. Seleziona uno o più file e fai clic sull’icona &quot;Gestisci&quot;. Qui puoi aggiungere tag ai file selezionati.
È inoltre possibile rimuovere i tag esistenti comuni nei file selezionati.

<img title="Gestire i tag nelle guide AEM " alt="Gestire i tag in DITA " src="ManageTags.jpg">

## Risoluzione dei problemi e domande frequenti

### L’elenco in Gestisci->metadati è vuoto o incompleto

Se l’elenco è vuoto o incompleto, potrebbe essere necessario eseguire l’indicizzazione sulla mappa digitale. Puoi fare riferimento a [Istruzioni per l’aggiornamento (indicizza il contenuto)](/help/product-guide/install-guide/upgrade-xml-documentation.md#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### I metadati personalizzati non vengono visualizzati nell’elenco

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Altre risorse utili

- [Assegnazione di tag in blocco tramite Map Dashboard (interfaccia utente Assets)](/help/product-guide/user-guide/map-editor-bulk-tagging.md)
- [Rapporti Ditamap nell’editor web](/help/product-guide/user-guide/reports-web-editor.md)
- [Assegnazione di tag in AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Contatta il tuo CSM per qualsiasi altra domanda**
