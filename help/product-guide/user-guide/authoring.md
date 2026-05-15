---
title: Gestire i contenuti
description: Gestisci i contenuti e identifica i ruoli e le autorizzazioni in AEM Guides. Scopri i concetti chiave della gestione dei contenuti e dell’utilizzo dei profili a livello globale o di cartella.
exl-id: 84926dc2-1180-48ef-85d0-50e3478bf26a
feature: Content Management
role: User
TQID: https://experienceleague.adobe.com/IoB9Dk9vwDaGSsqR-M7VobGnVcD5fMnACBhwkJrLN-I
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: da3860b0-d637-47df-bef0-273751180266
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 604
ht-degree: 12%

---

# Gestire i contenuti {#id164JBG0M0T1}

Prima di iniziare a creare effettivamente i contenuti, è necessario acquisire familiarità con alcuni concetti di base del content management in Adobe Experience Manager Guides. Quindi, inizia con la creazione di diversi gruppi di utenti e l’organizzazione delle risorse.

## Concetti fondamentali

Di seguito sono riportati alcuni concetti chiave della gestione dei contenuti in Adobe Experience Manager:

**Gestione risorse**

Experience Manager Guides utilizza la gestione delle risorse digitali (DAM\) di Adobe Experience Manager per gestire i file DITA. I file caricati o archiviati in DAM vengono memorizzati come risorse digitali. Puoi gestire e modificare le risorse in Adobe Experience Manager Assets. Per ulteriori informazioni sulla gestione delle risorse, visualizzare [Gestione risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=en).

**Gestione dei collegamenti**

Spostare o rinominare file o modificare la struttura delle cartelle nell&#39;archivio dei contenuti, senza preoccuparsi dei riferimenti interrotti. Tutti i riferimenti a e dal contenuto interessato vengono aggiornati automaticamente. Per evitare interruzioni involontarie, genera avvisi durante l’eliminazione di contenuto a cui si fa riferimento da altre aree.

**Gestione delle versioni**

Experience Manager Guides fornisce la gestione della versione per le risorse digitali. Questa funzionalità può essere facilmente attivata da un&#39;applicazione di authoring DITA. Consente agli autori di eseguire le funzioni standard di controllo della versione, ad esempio il check-in e il check-out.

Per ulteriori informazioni sulla creazione di versioni o sul ripristino di una versione specifica, visualizzare [Branch, Revert e versioni successive](web-editor-preview-topics.md#branch-revert-and-subsequent-versioning).

**Gestione DITA nativa**

Experience Manager Guides mantiene la struttura dei file DITA, ma consente anche a Adobe Experience Manager di gestire in modo nativo la DITA utilizzando la mappatura degli elementi per mappare gli elementi DITA ai componenti Adobe Experience Manager. La gestione DITA nativa viene utilizzata in funzioni quali l&#39;anteprima degli argomenti, la pubblicazione Adobe Experience Manager Sites e i flussi di lavoro di revisione.

## Identificare il ruolo e le autorizzazioni {#id181TF0K0MHT}

Experience Manager Guides fornisce tre gruppi preconfigurati. Questi gruppi sono: *Autori*, *Revisori* e *Editori*. A seconda del gruppo a cui sei associato, disponi delle autorizzazioni per eseguire attività specifiche come indicato nella tabella riportata di seguito. Ad esempio, un’attività di pubblicazione può essere eseguita solo da un editore, ma non da un autore o un revisore. Analogamente, un autore può creare un nuovo argomento e un revisore può solo esaminare un argomento.

>[!TIP]
>
> Visualizza la sezione *Autorizzazioni* nella guida alle best practice per le best practice sull&#39;impostazione delle autorizzazioni utente.

Nella tabella seguente sono elencate le varie attività e i gruppi che possono eseguirle:

| Attività | Autori | Revisori | Editori |
|----|-------|---------|----------|
| Crea argomento DITA | Sì |   | Sì |
| Crea mappa DITA | Sì |   | Sì |
| Mappare le raccolte | Sì |   | Sì |
| Crea attività di revisione | Sì |   | Sì |
| Rivedi argomento[1](#fntarg_1) | Sì | Sì | Sì |
| Risoluzione chiave | Sì |   | Sì |
| Check-out/check-in | Sì |   | Sì |
| Modifica argomento | Sì |   | Sì |
| Sposta argomento | Sì |   | Sì |
| Modifica proprietà argomento | Sì |   | Sì |
| Copia | Sì |   | Sì |
| Eliminare | Sì |   | Sì |
| Condividi | Sì |   | Sì |
| **Stato documento** |  |  |  |
| Crea/modifica profilo stato documento |   |   | Sì |
| Cambia stato documento[2](#fntarg_2) | Sì | Sì | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Predefiniti di output\)** |  |  |  |
| Genera |   |   | Sì |
| Modifica |   |   | Sì |
| Duplica |   |   | Sì |
| Creare |   |   | Sì |
| Elimina predefinito |   |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Output\)** |  |  |  |
| Visualizza output generato | Sì |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Argomenti\)** |  |  |  |
| Crea attività di revisione | Sì |   | Sì |
| Modifica | Sì |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Baseline\)** |  |  |  |
| Creare |   |   | Sì |
| Modifica |   |   | Sì |
| Duplica |   |   | Sì |
| Rimuovere |   |   | Sì |
| Console mappe DITA \(scheda Rapporti\) | Sì |   | Sì |
| **Funzionalità disponibili nella console delle mappe DITA \(Predefiniti condizione\)** |  |  |  |
| Crea/modifica predefinito condizione |   |   | Sì |

[1](#fnsrc_1) Se *Autori* e *Editori* sono invitati a una revisione.

[2](#fnsrc_2) a seconda dei diritti assegnati all&#39;utente nel profilo dello stato del documento.
