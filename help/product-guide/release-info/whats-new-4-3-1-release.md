---
title: Note sulla versione | Novità della versione 4.3.1 delle Guide di Adobe Experience Manager
description: Scopri le funzioni nuove e migliorate delle versioni 4.3.1 delle Guide di Adobe Experience Manager
exl-id: 14db7453-ccc1-4709-903f-677f55c263b2
feature: What's New
role: Leader
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Novità della versione 4.3.1 delle guide di Adobe Experience Manager (ottobre 2023)

Questo articolo descrive le funzioni nuove e migliorate della versione 4.3.1 delle Guide di Adobe Experience Manager (in seguito denominate *Guide Experience Manager*).

Per ulteriori dettagli sulle istruzioni di aggiornamento, sulla matrice di compatibilità e sui problemi risolti in questa versione, consulta [Note sulla versione](./release-notes-4-3-1.md).

## Connessione a un&#39;origine dati e inserimento degli argomenti

Experience Manager Guides fornisce connettori predefiniti per la connessione con le origini dati, rendendo Experience Manager Guides un vero e proprio hub di contenuti. In questo modo è possibile risparmiare tempo e fatica, che altrimenti verrebbero utilizzati per l&#39;aggiunta o la replica manuale dei dati.

Oltre ai connettori predefiniti come JIRA e SQL (MySQL, PostgreSQL, SQL Server, SQLite), l’amministratore può anche configurare connettori per database MariaDB, H2DB, AdobeCommerce e Elasticsearch. Possono inoltre aggiungere altri connettori estendendo le interfacce predefinite.

Puoi visualizzare i connettori configurati nella sezione **Origini dati** nell&#39;editor Web.

<img src="assets/data-sources.png" alt="Elenco origini dati nel pannello" width="300">

*Visualizzare le origini dati collegate.*

È ora possibile anche creare un argomento da un&#39;origine dati connessa. Un argomento può contenere dati in vari formati, ad esempio tabelle, elenchi e paragrafi. Consente inoltre di creare una mappa DITA per tutti gli argomenti. È possibile associare i metadati all&#39;argomento quando si estrae da un&#39;origine dati.

Per ulteriori dettagli, vedi [Utilizzare dati dall’origine dati](../user-guide/web-editor-content-snippet.md).

## Configurare un connettore origine dati dall’interfaccia utente

Experience Manager Guides ora fornisce anche un **Origini dati** strumento che consente di configurare connettori predefiniti per le origini dati. È possibile creare facilmente i connettori per i database JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce e Elasticsearch.

È inoltre possibile modificare, riconnettersi, duplicare o eliminare facilmente un connettore di origine dati. Ulteriori informazioni su come [configurare facilmente un connettore origine dati dall’interfaccia utente](../install-guide/conf-data-source-connector-tools.md).

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


## Supporto per più definizioni di soggetti in una singola definizione di enumerazione

Ora puoi definire una o più definizioni dei soggetti in una mappa e le definizioni di enumerazione in un&#39;altra mappa, quindi aggiungere il riferimento alla mappa. I riferimenti di enumerazione dei soggetti vengono risolti nella stessa mappa o nella mappa di riferimento.

Ora puoi anche definire le condizioni e applicarle ad alcuni elementi specifici di un argomento.  Le condizioni sono visibili solo per questi elementi specifici e non per tutti gli altri elementi.

Per ulteriori dettagli sulla gestione delle definizioni gerarchiche delle definizioni e delle enumerazioni dei soggetti, vedere la descrizione della caratteristica Schema dei soggetti in [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS) sezione.




## Esperienza di anteprima migliorata dal menu di scelta rapida

Utilizza il menu di scelta rapida per visualizzare rapidamente in anteprima il file (.dita, .xml, audio, video o immagine) senza aprirlo. Ora è possibile ridimensionare il riquadro di anteprima e, se il contenuto contiene un collegamento di riferimento, è possibile selezionarlo per aprirlo in una nuova scheda.

![Riquadro di anteprima ](assets/quick-preview_cs.png){width="800" align="left"}

*Visualizzare l&#39;anteprima del file nel riquadro.*

Per ulteriori dettagli sul menu di scelta rapida, vedere **Opzioni per un file** descrizione della funzione in [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS) sezione.

## Modificare un file nel plug-in del connettore ossigeno

Experience Manager Guides ora consente di selezionare un file nell&#39;editor Web e quindi scegliere di modificare il file nel plug-in del connettore di ossigeno. Questa opzione non è abilitata come parte del supporto predefinito.

Per ulteriori informazioni, consulta **Opzioni per un file** descrizione della funzione all’interno di [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS) sezione.

## Utilizzare le variabili per la data e l&#39;ora correnti nelle opzioni Percorso di destinazione, Nome sito o Nome file

Durante la generazione di output nel sito AEM o nei PDF, è possibile utilizzare le variabili per impostare **Percorso di destinazione**, **Nome sito**, o **Nome file** opzioni. Ora puoi anche utilizzare il `${system_date}`e `${system_time}` variabili. Queste variabili consentono di aggiungere la data e l’ora correnti a queste opzioni.

Scopri come [utilizzare le variabili per impostare le opzioni Percorso di destinazione, Nome sito o Nome file](../user-guide/generate-output-use-variables.md).


## Scelte rapide da tastiera per spostare il cursore nell’editor web

Experience Manager Guide consente ora di utilizzare le scelte rapide da tastiera per spostare il cursore nell&#39;editor Web. È possibile utilizzare le scelte rapide da tastiera per spostare rapidamente una parola verso sinistra o verso destra. È inoltre possibile spostarsi all&#39;inizio o alla fine della riga con l&#39;aiuto delle scelte rapide da tastiera.

Ulteriori informazioni su [scelte rapide da tastiera nell’Editor web](../user-guide/web-editor-keyboard-shortcuts.md).
