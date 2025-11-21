---
title: Gestire i contenuti
description: Gestisci i contenuti e identifica i ruoli e le autorizzazioni in AEM Guides. Scopri i concetti chiave della gestione dei contenuti e dell’utilizzo dei profili a livello globale o di cartella.
feature: Content Management
role: User
hide: true
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 10%

---

# Gestire i contenuti {#id164JBG0M0T1}

Prima di iniziare a creare effettivamente i contenuti, è necessario acquisire familiarità con alcuni concetti di base del content management in AEM Guides. Quindi, inizia con la creazione di diversi gruppi di utenti e l’organizzazione delle risorse.

## Concetti fondamentali

Di seguito sono riportati alcuni concetti chiave della gestione dei contenuti in AEM:

**Gestione risorse**

AEM Guides utilizza la funzione di gestione delle risorse digitali (DAM) di AEM per gestire i file DITA. I file caricati o archiviati in DAM vengono memorizzati come risorse digitali. Puoi gestire e modificare le risorse in AEM Assets. Per ulteriori informazioni sulla gestione delle risorse, consulta [Gestione risorse](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=it).

**Gestione dei collegamenti**

Spostare o rinominare file o modificare la struttura delle cartelle nell&#39;archivio dei contenuti, senza preoccuparsi dei riferimenti interrotti. Tutti i riferimenti a e dal contenuto interessato vengono aggiornati automaticamente. Per evitare interruzioni involontarie, genera avvisi durante l’eliminazione di contenuto a cui si fa riferimento da altre aree.

**Gestione delle versioni**

AEM Guides fornisce la gestione della versione per le risorse digitali. Questa funzionalità può essere facilmente attivata da un&#39;applicazione di authoring DITA. Consente agli autori di eseguire le funzioni standard di controllo della versione, ad esempio il check-in e il check-out.

Per ulteriori informazioni sulla creazione di versioni o sul ripristino di una versione specifica, vedere [Branch, Revert e versioni successive](web-editor-preview-topics.md#id193PG0Y051X).

**Gestione DITA nativa**

AEM Guides mantiene la struttura dei file DITA, ma consente anche ad AEM di gestire in modo nativo la DITA utilizzando la mappatura degli elementi per mappare gli elementi DITA ai componenti AEM. La gestione DITA nativa viene utilizzata in funzioni quali l&#39;anteprima degli argomenti, la pubblicazione AEM Sites e i flussi di lavoro di revisione.

## Identificare il ruolo e le autorizzazioni {#id181TF0K0MHT}

AEM Guides fornisce tre gruppi preconfigurati. Questi gruppi sono: *Autori*, *Revisori* e *Editori*. A seconda del gruppo a cui sei associato, disponi delle autorizzazioni per eseguire attività specifiche come indicato nella tabella riportata di seguito. Ad esempio, un’attività di pubblicazione può essere eseguita solo da un editore, ma non da un autore o un revisore. Analogamente, un autore può creare un nuovo argomento e un revisore può solo esaminare un argomento.

>[!TIP]
>
> Consulta la sezione *Autorizzazioni* nella guida alle best practice per le best practice sull&#39;impostazione delle autorizzazioni utente.

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

## Prerequisiti per l’authoring dei contenuti

**Utilizzare profili globali o a livello di cartella**

In un&#39;azienda, gruppi o prodotti diversi possono utilizzare diversi modelli di authoring, modelli di output, profili di attributi condizionali \(o schemi argomento\) e configurazioni dell&#39;editor Web. Configurarli solo a livello aziendale (o globale) può rendere difficile l’esperienza degli autori, in quanto vedranno modelli o profili che non sono rilevanti per loro.

AEM Guides consente di configurare modelli di authoring (argomento o mappa\), modelli di output, attributi condizionali e configurazioni dell’editor web a livello aziendale (globale\) e a livello di cartella. In questo modo è possibile segregare le configurazioni per diversi reparti o prodotti dell&#39;azienda.

Inoltre, puoi delegare le configurazioni specifiche della cartella a un reparto o agli amministratori di prodotto per decentralizzare l’amministrazione.

Per informazioni dettagliate sulla configurazione dei profili globali e a livello di cartella, consulta *Configurare i profili globali o a livello di cartella* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.
