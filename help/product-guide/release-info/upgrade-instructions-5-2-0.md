---
title: Note sulla versione | Istruzioni per l’aggiornamento a Adobe Experience Manager Guides versione 5.2.0
description: Scopri la matrice di compatibilità e come effettuare l’aggiornamento alla versione 5.2.0 di Adobe Experience Manager Guides.
source-git-commit: a2d4731af4f4996c87dd177a6e45f1d8ebabd6cf
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 4%

---

# Istruzioni per l’aggiornamento alla versione 5.2.0 (maggio 2026)

Questo articolo descrive le istruzioni per l’aggiornamento e la matrice di compatibilità per la versione 5.2.0 di Adobe Experience Manager Guides.

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizzare [Novità della versione 5.2.0](../release-info/whats-new-5-2-0.md).

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 5.2.0](../release-info/fixed-issues-5-2-0.md).

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate da Experience Manager Guides versione 5.2.0.

| AEM Guides | Versione di AEM | Service Pack |
| --- | --- | --- |
| 5.2.0 (UUID) | 6.5 LTS | 2 |
| 5.2.0 (UUID) | 6.5 | 24, 23, 22 |

Per ulteriori dettagli, consulta la sezione [Requisiti tecnici](../install-guide/download-install-technical-requirements.md) nella Guida all&#39;installazione e alla configurazione on-premise.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione | FMPS | FM |
| --- | --- | --- |
| 5.2.0 (UUID) | Supportato | 2026 o versione successiva |

### Connettore ossigeno

| Versione | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.2.0 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti per componenti Experience Manager Guides per Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Nuova versione del modello del sito AEM


| AEM Guides | Versione AEM | Versione componenti | Versione sito |
|---|---|---| ---|
| 5.2.0 UUID | 6.5 LTS | guides-components.all-1.4.1 | ND |
| 5.2.0 UUID | 6,5 | guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Prerequisiti

Prima di avviare il processo di aggiornamento di Experience Manager Guides 5.2.0, verificare di disporre dei seguenti elementi:

1. Aggiornamento a Experience Manager Guides versione 5.0.0, 5.0.3, 5.1.0, 5.1.3 o 5.1.4.
1. (Facoltativo) Ha chiuso tutte le attività di traduzione.
1. Il livello di registro è stato modificato in **INFO** per la classe `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` e questi registri sono stati aggiunti in un nuovo file di registro, ad esempio `logs/translation_upgrade.log`.

## Percorso di aggiornamento per Experience Manager Guides 5.2.0

Puoi aggiornare facilmente la versione corrente di Experience Manager Guides alla versione 5.2.0 in **AEM 6.5** o **AEM 6.5 LTS**.

>[!IMPORTANT]
>
> - **Per AEM 6.5 LTS**: Experience Manager Guides 5.2.0 è supportato solo con AEM 6.5 LTS Service Pack 2.
> - **Per AEM 6.5**: Experience Manager Guides 5.2.0 è supportato solo con AEM 6.5 Service Pack 24, 23 e 22.
> - Se al momento utilizzi AEM 6.5 e prevedi di passare ad AEM 6.5 LTS, assicurati di completare l’aggiornamento ad AEM prima di procedere con l’aggiornamento a Experience Manager Guides 5.2.0. Per informazioni dettagliate, visualizzare [Aggiornamento a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/it/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Prima di procedere con l’aggiornamento alla versione 5.2.0 di Experience Manager Guides, è necessario considerare i seguenti punti:

- Se utilizzi le versioni 5.0.0, 5.0.3, 5.1.0, 5.1.3 o 5.1.4, puoi eseguire direttamente l’aggiornamento alla versione 5.2.0.
- Se utilizzi le versioni 4.6.3, 4.6.4, 5.0.x, puoi eseguire direttamente l’aggiornamento alla versione 5.1.0.
- Se utilizzi le versioni 4.6.0, 4.6.1, devi effettuare l’aggiornamento alla versione 4.6.3, 4.6.4 o 5.0.0 prima di eseguire l’aggiornamento alla versione 5.1.0.
- Se utilizzi le versioni 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 o 4.1.x, devi effettuare l’aggiornamento alla versione 4.4 prima di eseguire l’aggiornamento alla versione 5.1.0.
- Se utilizzi la versione 4.0, devi effettuare l’aggiornamento alla versione 4.2 prima di passare alla versione 4.3.x.
- Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
- Se utilizzi una versione precedente alla 3.8.5, consulta la sezione Aggiornamento di Experience Manager Guides nella guida all&#39;installazione specifica per il prodotto, disponibile in [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/it/xml-documentation-for-experience-manager/archive.html).

## Processo di aggiornamento per Experience Manager Guides 5.2.0

>[!IMPORTANT]
>
> La post-elaborazione e l’indicizzazione potrebbero richiedere alcune ore. Si consiglia di avviare il processo di aggiornamento durante le ore non di punta.

1. Scarica il pacchetto della versione 5.2.0 da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).
1. Installa il pacchetto della versione su cui desideri eseguire l’aggiornamento e attendi che il bundle sia installato.
1. *(Facoltativo)* Aggiornamento del plug-in del connettore ossigeno rilasciato con la versione a cui si sta effettuando l&#39;aggiornamento.
1. Cancella la cache del browser dopo l’installazione del pacchetto.
1. Se è stata abilitata l&#39;impostazione `Enable markup find and replace` per accedere alla funzionalità Trova e sostituisci nella visualizzazione origine per il contenuto acquisito in precedenza, è necessario reindicizzare l&#39;indice `guidesAssetLucene`. Per ulteriori dettagli, visualizzare [Reindicizzazione per Trova e sostituisci](../install-conf-guide/custom-indexing-on-prem.md).
1. Aggiorna la configurazione di sistema per incorporare le nuove impostazioni introdotte nella versione 5.2.0, garantendo il supporto dei seguenti miglioramenti:


| Configurazioni aggiunte | File di configurazione | Visualizza etichetta dell’impostazione | Nome dell’impostazione |
|-----|-----|------|-----|
| Attivare o disattivare il nuovo editor | `com.adobe.fmdita.config.ConfigManager` | Abilita editor 2.0 | `enable.markup.editor` |
| Attivare o disattivare la nuova baseline | `com.adobe.fmdita.config.ConfigManager` | Abilita previsione più veloce (v2) | `enable.baseline.v2` |
| Ignora le proprietà dei metadati per contrassegnare una versione come dirty | `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | Ignora proprietà metadati per versione dirty | `xmleditor.dirtychecker.ignoremetadata` |
| Trova e sostituisci funzione nella vista Source | `com.adobe.fmdita.config.ConfigManager` | Abilita ricerca e sostituzione markup | `enable.markup.findreplace` |
| Abilita o disabilita il salto dei collegamenti dei peer per la baseline precedente | `com.adobe.fmdita.config.ConfigManager` | Ignora i collegamenti dei peer per la linea di base V1 | `guides.baseline.v1.skip.peer.links` |
| Abilita o disabilita l’inizializzazione delle copie di destinazione con il contenuto sorgente nel flusso di lavoro di traduzione. Questo è applicabile solo quando il flusso di lavoro di traduzione legacy è disabilitato.  | `com.adobe.fmdita.config.ConfigManager` | Inizializza la copia per lingua di destinazione con il contenuto sorgente | `translation.workflow.propagate.source.content` |
| Pulizia archivio di riferimento | `com.adobe.fmdita.config.ConfigManager` | Eliminazione btree delle guide abilitata | `btree.deletion.enabled` |
| Replica di risorse DITA | `com.adobe.fmdita.config.ConfigManager` | Replica risorse DITA | `publish.replicate` |
| Elaborazione risorse | `com.adobe.fmdita.config.ConfigManager` | Abilita processo pianificato elaborazione risorse guide | `enable.asset.processing.scheduler` |

Per informazioni dettagliate su queste impostazioni di configurazione, visualizzare [Aggiornamenti configurazione](../install-conf-guide/configuration-on-prem.md).







