---
title: Aumentare le prestazioni di traduzione per i file DITA nelle guide di AEM
description: Best practice, suggerimenti e trucchi per migliorare le prestazioni dei progetti di traduzione DITA in AEM Guides
feature: Translation
role: User, Admin
author: Pulkit Nagpal (punagpal)
exl-id: d7e4f3ae-2143-4767-b7ab-c89f5e5eef59
TQID: https://experienceleague.adobe.com/n6-b3-ZsOIueVYWgcm1NkDLKRAOwQhWxctbgj7Q6P1U
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 0%

---

# Best practice da seguire per la traduzione in AEM Guides

Le prestazioni del progetto di traduzione possono diminuire con l’aumento dell’attività di traduzione sul sistema nel tempo.

Ogni progetto di traduzione genera più gruppi di utenti per l’accesso, con conseguente aumento del numero di gruppi di utenti all’interno del sistema. Con l’aumento del numero di gruppi di utenti, può gradualmente rallentare le operazioni CRUD relative alle autorizzazioni utente, influendo potenzialmente sulle prestazioni complessive di AEM. Inoltre, se i progetti di traduzione rimangono attivi dopo il completamento, può influire negativamente sulle prestazioni della sincronizzazione della traduzione tra AEM e il fornitore di traduzione.

**Seguendo le best practice descritte di seguito sarà possibile mantenere un ambiente efficiente.**

## Se utilizzi una build precedente alla 4.6 (on-prem) o alla 2404 (cloud):

- Contrassegna tutti i progetti come &quot;Inattivi&quot; una volta completata e approvata la traduzione.Il progetto rimane disponibile per la revisione ed è semplicemente contrassegnato come inattivo.
   - Segui questi passaggi per mantenere le prestazioni complessive di traduzione in buona salute.
     ![Progetto di traduzione inattivo ](../assets/translation/translation-project-image1.png)

- Per i progetti meno recenti, elimina la cartella contrassegnata come inattiva, approvata e rivista
   - Segui questi passaggi per mantenere buone le prestazioni complessive di traduzione pulendo i file di traduzione temporanei e i gruppi di utenti associati a questa cartella di progetto.
     ![Elimina progetto di traduzione e cartella ](../assets/translation/translation-project-image2.png)


## Se utilizzi, build 4.6 o 2404 o successiva:

Puoi continuare a seguire gli stessi passaggi indicati sopra. A partire dalla versione 4.6/2404, AEM Guides introduce un’impostazione di editor che consente agli amministratori di disabilitare l’eliminazione automatica dei progetti di traduzione.

Riferito: [Elimina o disabilita automaticamente un progetto di traduzione completato](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Impostazioni automatizzate per eliminare e disabilitare il progetto di traduzione in AEM Guides ](../assets/translation/translation-project-image3.png)
