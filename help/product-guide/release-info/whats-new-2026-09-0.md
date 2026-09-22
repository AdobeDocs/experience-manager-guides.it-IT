---
title: Note sulla versione | Novità della versione 2026.09.0 di Adobe Experience Manager Guides
description: Scopri le funzioni nuove e migliorate della versione 2026.09.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: 5d42c75d75b85b97fc3795c87004510eb43acd29
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 0%
---
# Novità della versione 2026.09.0 (settembre 2026)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2026.09.0 di Adobe Experience Manager Guides as a Cloud Service.

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 2026.09.0](fixed-issues-2026-09-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.09.0](../release-info/upgrade-instructions-2026-09-0.md).

## Introduzione di tag avanzati basati sull’intelligenza artificiale nell’Assistente all’intelligenza artificiale

Ora puoi utilizzare l’Assistente AI per suggerire e aggiungere tag al contenuto. Con la nuova funzionalità di assegnazione tag avanzati, gli autori possono chiedere all’Assistente all’intelligenza artificiale di suggerire i tag per uno o più argomenti, grazie all’abilità di assegnazione tag avanzati fornita da Adobe CX Enterprise Coworker. L’abilità rivede il contenuto, genera consigli sui tag e li presenta per la tua revisione. Una volta confermata, i tag suggeriti vengono applicati agli argomenti rilevanti all’interno di una mappa.

Per ulteriori dettagli, visualizzare [Utilizzare l&#39;Assistente di intelligenza artificiale in modalità agente](../user-guide/ai-assistant-agentic.md).

![](./assets/guides-ai-tags-review.png)

Attualmente, la funzionalità di assegnazione tag avanzati è disponibile quando l&#39;Assistente IA è configurato in modalità **Agente**. Gli amministratori possono scegliere di abilitare la modalità **Agentic** o **Standard** dalle **impostazioni Workspace** per un&#39;istanza.

- La modalità **Agentic** fornisce agli autori l&#39;interfaccia di assegnazione tag avanzati per l&#39;applicazione e i consigli sui tag.
- **La modalità standard** fornisce l&#39;esperienza dell&#39;Assistente di intelligenza artificiale esistente, con le schede **Help** e **Authoring** nel pannello dell&#39;Assistente di intelligenza artificiale.

## Miglioramenti dell’editor

### Impedisci sovrascrittura del contenuto durante la modifica simultanea

Quando due autori lavorano contemporaneamente sullo stesso argomento, un autore può avere l’argomento aperto mentre un altro lo blocca, apporta modifiche e salva una versione più recente. L’argomento già aperto potrebbe quindi contenere contenuto non aggiornato e la modifica di questa versione potrebbe sovrascrivere le modifiche più recenti.

Per evitare tali conflitti, l&#39;ultima versione salvata viene ora caricata automaticamente nell&#39;editor quando si blocca un argomento. In questo modo potrai lavorare con il contenuto più recente e non sovrascrivere le modifiche effettuate da un altro autore.

Ciò si applica quando è abilitata l&#39;impostazione **Disabilita modifica senza bloccare il file**.

Per ulteriori dettagli, visualizzare [Impedisci sovrascrittura del contenuto durante la modifica simultanea](../user-guide/web-editor-edit-topics.md#prevent-content-overwrite-during-concurrent-editing).

### Anteprima del contenuto della mappa come di una baseline statica selezionata

Quando una mappa ha una o più linee di base statiche, ora puoi visualizzare in anteprima la mappa in base a una linea di base selezionata invece della copia di lavoro corrente nell’editor.

Tutte le versioni di argomenti, risorse, immagini e riferimenti associati alla baseline selezionata vengono visualizzate nell&#39;anteprima, fornendo una visualizzazione accurata del contenuto della mappa al momento della creazione della baseline. Per ulteriori dettagli, visualizzare [Visualizzazioni editor per argomenti](../user-guide/web-editor-views.md#preview-content-using-baseline).

## Miglioramenti della revisione

### Contrassegna singoli argomenti come completati in un&#39;attività di revisione

Experience Manager Guides introduce il tracciamento dell’avanzamento a livello di argomento per i revisori, fornendo una migliore visibilità dell’avanzamento della revisione per le attività con più argomenti. In qualità di revisore, ora puoi contrassegnare i singoli argomenti come completati e distinguere tra gli argomenti che hai completato e quelli che richiedono ancora attenzione.

![](./assets/mark-topics-done-review-ui.png)

Per supportare questa funzione, gli argomenti nella visualizzazione Documento dell&#39;interfaccia utente Revisione sono organizzati in base a una casella di controllo **Contrassegna argomento come completato**. Gli argomenti contrassegnati come revisionati utilizzando la casella di controllo sono indicati nel pannello **Argomenti**, mentre il contatore **Argomenti revisionati** nella parte superiore mostra lo stato di avanzamento rispetto agli argomenti assegnati. Insieme, questi dati forniscono una visione chiara di ciò che è stato trattato e di ciò che rimane, anche quando si ritorna a un&#39;attività di revisione più lunga dopo un&#39;interruzione.

Per ulteriori dettagli, visualizzare [Rivedi argomenti](../user-guide/review-topics.md#mark-individual-topics-as-done-in-a-review-task).


### Identificare gli utenti con i ruoli quando si assegnano tag ai commenti

I revisori e gli autori possono ora visualizzare il ruolo di un utente, ad esempio Revisore, Autore o Proprietario, insieme al nome utente e all’indirizzo e-mail (se disponibili), quando applicano un tag a un utente in un commento o in una risposta. Questo consente di identificare rapidamente l’utente giusto per assegnare tag, soprattutto nei progetti con un numero elevato di partecipanti.

Ulteriori informazioni su [assegnare tag agli utenti in un commento](../user-guide/review-topics.md#tag-task-users-in-a-comment).

### Visualizza la gerarchia delle mappe durante la selezione degli argomenti da esaminare

Quando si seleziona il contenuto per una revisione, come autore o iniziatore di un&#39;attività di revisione, è ora possibile visualizzare mappe, sottopagine e argomenti nella gerarchia esistente nella pagina **Contenuto**, anziché visualizzare tutti gli argomenti come un elenco semplice. La visualizzazione gerarchica semplifica la comprensione della struttura del contenuto e consente di selezionare singoli argomenti o intere sottopagine da rivedere.

Per ulteriori dettagli, visualizzare [Visualizzare la gerarchia delle mappe durante la selezione degli argomenti per la revisione](../user-guide/review-send-topics-for-review.md#view-the-map-hierarchy-while-selecting-topics-for-review).

![](assets/review-map-hierarchy.png)

## Miglioramenti alla pubblicazione

### Pubblicare l&#39;output PDF nativo utilizzando la lingua della mappa

La pagina del predefinito di output PDF nativo ora include una nuova opzione **Usa linguaggio mappa**. Se questa opzione è selezionata, le variabili del modello di output risolvono la propria lingua dall&#39;attributo `xml:lang` della mappa principale anziché da una lingua selezionata in modo esplicito nel predefinito. Ciò significa che non è più necessario mantenere un predefinito di output separato per ogni lingua quando si pubblicano le mappe tradotte. Se per la mappa non è definito alcun `xml:lang`, l&#39;output predefinito sarà Inglese (en_US).

Per ulteriori dettagli, visualizzare [Configurazione predefinita PDF nativa](../web-editor/native-pdf-web-editor.md) e [Utilizzare le variabili di lingua nei modelli di output](../native-pdf/native-pdf-language-variables.md#use-language-variables-in-the-output-templates).

## Miglioramenti dei contenuti di apprendimento

### Attivare la visualizzazione a schermo intero per i contenuti H5P in un corso di apprendimento

Gli autori possono ora abilitare o disabilitare la visualizzazione a schermo intero per ogni elemento H5P utilizzato in un corso di apprendimento. Utilizza l&#39;interruttore **Abilita schermo intero** nel pannello **Proprietà contenuto** per controllare questa impostazione. Se abilitati, gli Allievi possono espandere il contenuto H5P a schermo intero. Se è disattivata, il contenuto rimane in linea all’interno della visualizzazione standard. Questa impostazione viene applicata in modo coerente in modalità Anteprima e nell’output pubblicato.

Ulteriori informazioni su [Altre opzioni nel menu Inserisci](../learning-content/lc-other-insert-options.md) dei contenuti di formazione e apprendimento del prodotto.

![](./assets/h5p-fullscreen.png)

## Miglioramenti delle prestazioni

### Prestazioni migliorate con il caricamento impaginato di file e cartelle

Experience Manager Guides ora supporta il caricamento impaginato di file e cartelle per un’esperienza di navigazione avanzata, in particolare per le cartelle con un numero elevato di risorse. Invece di caricare tutto il contenuto contemporaneamente, le cartelle vengono caricate progressivamente in batch di 50 risorse, con risorse aggiuntive recuperate mentre scorri o selezioni **Carica altro**, a seconda del pannello o della finestra di dialogo.

L’ordinamento viene eseguito lato server, pertanto l’applicazione di un ordinamento recupera i risultati appena ordinati anziché riordinare i dati già caricati nel browser. Le operazioni comuni, ad esempio rinominare, eliminare, aggiungere e spostare, non consentono più di ricaricare un&#39;intera cartella. ma aggiorna solo l’elemento interessato o la prima pagina dei risultati.

Il caricamento impaginato è disponibile nei pannelli Tabella archivio principale, Raccolte, Esplora risorse, Ricerca e modello e nella finestra di dialogo Seleziona percorso.

Per ulteriori dettagli, visualizzare [Caricamento impaginato di file e cartelle](../user-guide/paginated-loading-assets.md).

![paginazione per il pannello di navigazione delle cartelle](../user-guide/images/home-tree-pagination.png){width="650"}









