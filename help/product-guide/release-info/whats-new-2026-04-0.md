---
title: Note sulla versione | Novità della versione 2026.04.0 di Adobe Experience Manager Guides
description: Scopri le funzioni nuove e migliorate della versione 2026.04.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: ce2c9da0d9beb05a15f7cefcf9483e0c93abbf37
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 2%

---

# Novità della versione 2026.04.0 (aprile 2026)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2026.04.0 di Adobe Experience Manager Guides as a Cloud Service.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2026.04.0](fixed-issues-2026-04-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.04.0](../release-info/upgrade-instructions-2026-04-0.md).

## Presentazione dei contenuti di formazione e apprendimento dei prodotti in Experience Manager Guides

La funzionalità di contenuto **Formazione e apprendimento del prodotto** in Experience Manager Guides consente ai team di formazione e ai designer di formazione di creare corsi di eLearning interattivi direttamente dall&#39;interfaccia di Experience Manager Guides.

![](assets/lc-overview.png)

Grazie all’authoring basato su modelli, ai componenti dei corsi interattivi e al supporto per le valutazioni, i team possono sviluppare contenuti di formazione di alta qualità in linea con i loro obiettivi organizzativi.

>[!NOTE]
> 
> La funzione del contenuto di apprendimento e formazione del prodotto rimane disabilitata per impostazione predefinita per tutte le istanze di Experience Manager Guides as a Cloud Service. Gli amministratori possono abilitare questa funzione a livello di profilo della cartella da **Impostazioni Workspace** > **Generale**.

Le funzionalità principali sono le seguenti:

- Gestione centralizzata dei contenuti di apprendimento
- Authoring basato su modelli
- Supporto per il riutilizzo dei contenuti
- Creazione e gestione della valutazione
- Flussi di lavoro di revisione basati sul web
- Gestione delle traduzioni leader del settore
- Pubblicazione multicanale tramite i formati di output standard SCORM e PDF

Per ulteriori dettagli, fare riferimento alle [guide introduttive](../learning-content/course-overview.md) e [guide alla configurazione](../lc-config-guide/introduction.md).


## Miglioramenti dell’editor

Con questa versione sono stati apportati i seguenti miglioramenti all’editor:

### Miglioramenti al pannello di convalida Schematron

Sono stati apportati i seguenti miglioramenti all’interfaccia utente di Schematron per migliorare la chiarezza, l’usabilità e i risultati di convalida:

- Nel pannello Convalida, quando non viene aggiunto alcun file Schematron, viene visualizzato un messaggio a stato vuoto che fornisce maggiore chiarezza e direzione per i passaggi successivi.

  ![](assets/schematron-panel.png){width="350" align="left"}
- Quando vengono aggiunti più file Schematron, questi vengono organizzati in un pannello a soffietto consolidato, fornendo una migliore visibilità nei file Schematron configurati.

  ![](assets/schematron-panel-error.png){width="350" align="left"}
- In base all&#39;attributo di ruolo definito nel file Schematron, i risultati della convalida sono ora classificati come: `Fatal`, `Error`, `Warn` o `Info`. Ogni categoria include un conteggio visibile insieme a una descrizione contestuale per un’interpretazione più chiara.

  ![](assets/schematron-validation-errors.png){width="350" align="left"}

Per ulteriori dettagli sull&#39;utilizzo dei file Schematron in Experience Manager Guides, visualizzare [Supporto per i file Schematron](../user-guide/support-schematron-file.md).

### Le copie per lingua di traduzione sono ora disponibili nel pannello a destra dell’interfaccia dell’editor

Una nuova sezione **Traduzioni** è ora disponibile nel pannello a destra in *Proprietà file* nell&#39;editor. Questa sezione fornisce accesso diretto a tutte le copie per lingua disponibili per la risorsa attualmente aperta (mappa, argomento, immagine, ecc.). Non è più necessario passare all’interfaccia utente di Assets per visualizzare o accedere a queste copie per lingua.

![](assets/translations-right-panel.png){width="350" align="left"}

Per ogni copia per lingua, puoi passare il cursore sul file per individuarne il percorso nell’archivio o selezionarlo semplicemente per aprirlo nell’editor. Oltre ad aprire i file, è possibile eseguire molte azioni utilizzando il menu **Opzioni**. Alcune delle azioni che puoi eseguire includono Modifica, Anteprima, Copia UUID, Copia percorso, Aggiungi a raccolte e Proprietà.

Per ulteriori dettagli, visualizza il [pannello destro nell&#39;editor](../user-guide/web-editor-right-panel.md#file-properties).


### Cerca citazioni in tutti i campi del diario

È ora possibile cercare le citazioni in tutti i campi di Journal, ad esempio *Titolo*, *Titolo diario*, *Autore*, *Anno*, *Volume*, *Numero* e *Pagine*, utilizzando l&#39;opzione **Qualsiasi campo** nella finestra di dialogo **Aggiungi citazione**. La ricerca restituisce la citazione corrispondente più vicina in base al testo immesso.

Per ulteriori dettagli sull&#39;aggiunta di citazioni in Experience Manager Guides, visualizzare [Aggiungere e gestire citazioni nel contenuto](../user-guide/web-editor-apply-citations.md).

![](assets/add-citations.png){width="350" align="left"}



## Miglioramenti della revisione

I seguenti miglioramenti sono disponibili per la funzione Revisione di questa versione:

- L’assegnazione di un revisore a un’attività di revisione dipende ora dalla selezione di un progetto attivo. Il campo **Assegna a** nella pagina *Crea attività di revisione* rimane disabilitato fino a quando non viene selezionato un progetto attivo. Dopo aver selezionato un progetto, il campo **Assegna a** è attivato e contiene un elenco solo degli utenti e dei gruppi di utenti associati al progetto. In questo modo le attività di revisione vengono assegnate solo a membri validi del progetto e si evita la selezione involontaria di revisori.

  ![](assets/create-review-task-023.png)

- Il campo **Assegna a** ora supporta la ricerca automatica e consente di individuare rapidamente utenti o gruppi di utenti digitando del testo.

Insieme, questi miglioramenti rendono la selezione dei revisori più precisa, efficiente e allineata ai flussi di lavoro di revisione specifici per il progetto.

Per ulteriori dettagli, visualizzare [Invia argomenti per la revisione](../user-guide/review-send-topics-for-review.md).

## Miglioramenti alla gestione delle risorse

Questa versione introduce i seguenti miglioramenti alla gestione delle risorse:

### Utilizzare la gerarchia dei file Flatten per scaricare mappe con nomi di file originali e metadati associati

Ora puoi utilizzare l’opzione Flatten file hierarchy per scaricare una mappa con il suo nome file originale. Inoltre, il pacchetto scaricato include un file `metadata.json`, rendendo i metadati associati facilmente accessibili e riutilizzabili al di fuori di Experience Manager Guides.

Per ulteriori dettagli sul download di file in Experience Manager Guides, visualizzare [Scarica file](../user-guide/authoring-download-assets.md).

### Usa regex per abilitare o disabilitare la post-elaborazione

Ora puoi utilizzare regex per abilitare o disabilitare la post-elaborazione per le cartelle. Questo miglioramento consente agli amministratori di definire regole di post-elaborazione da applicare a più cartelle o gerarchie di cartelle intere utilizzando una singola configurazione, invece di specificare percorsi di cartelle individuali.

Per ulteriori dettagli, visualizzare [Utilizzare regex per abilitare o disabilitare la post-elaborazione](../cs-install-guide/conf-folder-post-processing.md#use-regex-to-enable-or-disable-post-processing).
