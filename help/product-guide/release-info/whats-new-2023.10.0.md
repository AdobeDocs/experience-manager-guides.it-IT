---
title: Note sulla versione | Novità delle guide di Adobe Experience Manager, versione di ottobre 2023
description: Scopri le funzioni nuove e migliorate nella versione di ottobre 2023 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 41bfed0d-5901-4ada-b6d7-a5be93b25ba8
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Novità della versione di ottobre 2023 di Adobe Experience Manager Guides as a Cloud Service

Questo articolo descrive le funzioni nuove e migliorate della versione di ottobre 2023 delle Guide di Adobe Experience Manager (in seguito denominate *Guide AEM as a Cloud Service*).

Per ulteriori dettagli sulle istruzioni di aggiornamento, sulla matrice di compatibilità e sui problemi risolti in questa versione, consulta [Note sulla versione](release-notes-2023.10.0.md).


## Configurare un connettore origine dati dall’interfaccia utente

Experience Manager Guides ora fornisce un **Origini dati** strumento che consente di configurare connettori predefiniti per le origini dati. È possibile creare facilmente i connettori per i database JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce e Elasticsearch.

È inoltre possibile modificare, riconnettersi, duplicare o eliminare facilmente un connettore di origine dati. Scopri come [configurare facilmente un connettore origine dati dall’interfaccia utente](../cs-install-guide/conf-data-source-connector-tools.md).

![connettori di origini dati elencati nel pannello origini dati](assets/data-sources-create-window.png){width="550" align="left"}

*Crea e visualizza i connettori dell’origine dati dal pannello origini dati.*

## Visualizza registri per il generatore di argomenti

Ora puoi anche visualizzare il file di registro per la generazione dei contenuti. Questo file di registro consente di controllare avvisi, errori ed eccezioni.  Ulteriori informazioni su come [opzioni per un generatore di argomenti](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) consente di generare e gestire facilmente i generatori di argomenti.

## Supporto per gli strumenti Velocity nei modelli di origini dati

Ora puoi utilizzare gli strumenti Velocity nei modelli delle guide di Experience Manager. Questi strumenti consentono di applicare varie funzioni ai dati recuperati dalle origini dati. È possibile utilizzare i modelli durante la creazione di uno snippet di contenuto o di un argomento. Questa funzione ti consente di risparmiare tempo e fatica nell’applicare manualmente la stessa funzione a ciascun set di dati.  Garantisce inoltre risultati accurati.
È ad esempio possibile utilizzare $mathTool per eseguire funzioni matematiche.
Ulteriori informazioni su come [utilizzare gli strumenti Velocity nei modelli di origini dati](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Miglioramenti di Native PDF

Nella versione di ottobre 2023 sono stati apportati i seguenti miglioramenti a Native PDF:

### Reimposta il numero di pagina per la prima pagina di un layout

Nell&#39;output nativo di PDF è possibile riavviare i numeri di pagina e specificare il numero da cui inizia la numerazione. Ora è anche possibile iniziare la numerazione solo per la prima occorrenza di una sezione.
Ulteriori informazioni su come [utilizzare le proprietà di pagina di un layout di pagina](../native-pdf/design-page-layout.md#page-props-page-layout).


### Visualizza capitoli senza numeri automatici nel sommario

Experience Manager Le guide visualizzano i numeri dei capitoli insieme ai nomi dei capitoli nel sommario. Ora puoi scegliere di pubblicare solo i nomi dei capitoli senza i numeri dei capitoli. Visualizza ulteriori dettagli su come configurare [impostazioni PDF avanzate di un modello](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Scaricare una mappa dall’editor web

Ora è possibile non solo modificare una mappa nella vista mappa dell&#39;Editor Web, ma anche scaricarla. Puoi scegliere di scaricare la mappa utilizzando una linea di base specifica. È inoltre possibile appiattire la gerarchia e salvare tutti i file e le cartelle in un&#39;unica cartella.

Per ulteriori informazioni, consulta **Vista mappa** descrizione della funzione all’interno di [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS) sezione.

![menu opzioni di un file nella vista archivio](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Selezionare un file nella vista del repository e scegliere l&#39;opzione per eseguire un&#39;azione sul file.*

## Modificare un file nel plug-in del connettore ossigeno

Experience Manager Guides ora consente di selezionare un file nell&#39;editor Web e quindi scegliere di modificare il file nel plug-in del connettore di ossigeno. Questa opzione non è abilitata come parte del supporto predefinito.

Per ulteriori informazioni, consulta **Opzioni per un file** descrizione della funzione all’interno di [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS) sezione.
