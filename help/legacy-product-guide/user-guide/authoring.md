---
title: Manage content
description: Manage content and identify your roles and permissions in AEM Guides. Learn the key concepts of content management and working with the global or folder-level profiles.
feature: Content Management
role: User
hide: true
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 10%

---

# Manage content {#id164JBG0M0T1}

Before you start with the actual content creation, you must familiarize yourself with some basic concepts of content management in AEM Guides. Then, start with creating different user groups and organizing your assets.

## Concetti fondamentali

Some key concepts of content management in AEM are as follows:

**Asset management**

AEM Guides uses AEM&#39;s digital asset management \(DAM\) to manage your DITA files. The files that you upload or check into the DAM are stored as digital assets. You can manage and edit your assets in AEM Assets. For more information about asset management, see [Manage assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=it).

**Link management**

Move or rename files or change folder structure in the content repository, without worrying about broken references. All references to and from the impacted content are automatically updated. Get warnings when deleting content which is referenced from elsewhere, to prevent unintentional breakages.

**Managing versions**

AEM Guides provides version management for your digital assets. You can easily enable this functionality from a DITA authoring application of choice. Allowing your writers to perform the standard version control functions such as check-in and check-out.

For more information about creating versions or reverting to a specific version, see [Branch, revert, and subsequent versioning](web-editor-preview-topics.md#id193PG0Y051X).

**Native DITA handling**

While AEM Guides maintains the structure of your DITA files, it also enables AEM to natively handle DITA using element mapping to map the DITA elements to AEM components. The native DITA handling is used in features such as topic preview, AEM Sites publishing, and the review workflows.

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
