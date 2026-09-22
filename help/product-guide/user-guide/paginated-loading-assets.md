---
title: Miglioramenti delle prestazioni in Experience Manager Guides
description: Scopri come il caricamento impaginato di file e cartelle migliora le prestazioni in Experience Manager Guides.
feature: Authoring, Publishing
role: User
source-git-commit: e4019ae1e605bd26f7df676a4fab8c632fd8fa8e
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%
---

## Caricamento impaginato di file e cartelle

>[!NOTE]
>
> Questa funzione è attivata per impostazione predefinita. Per disattivarlo, contatta il team di successo del cliente.

Experience Manager Guides utilizza un’API impaginata per caricare file e cartelle. Invece di caricare tutto il contenuto contemporaneamente, le cartelle vengono caricate progressivamente in batch, con risorse aggiuntive recuperate automaticamente durante lo scorrimento o selezionando l&#39;opzione **Carica altro**.

L’ordinamento viene eseguito lato server, pertanto l’applicazione di un ordinamento recupera i risultati appena ordinati anziché riordinare i dati già caricati nel browser. Le operazioni comuni, ad esempio rinominare, eliminare, aggiungere e spostare, non consentono più di ricaricare un&#39;intera cartella. ma aggiorna solo l’elemento interessato o la prima pagina dei risultati. La funzionalità *Individua sempre un file in Esplora risorse* non è più disponibile. Per qualsiasi risorsa, è comunque possibile utilizzare il menu di scelta rapida per individuare il file in Esplora risorse.

Le sezioni seguenti descrivono in che modo ciascuna di queste impostazioni si applica a interfacce, pannelli e finestre di dialogo diversi.

### Tabella dell’archivio principale

- **Esplorazione**: utilizza uno scorrimento infinito. Il primo batch di risorse viene caricato inizialmente; i batch successivi vengono aggiunti automaticamente durante lo scorrimento. Quando si passa da una cartella all’altra, l’elenco corrente viene cancellato e le risorse vengono caricate dalla cartella appena selezionata.
- **Rinomina**: sul posto; nessun aggiornamento cartella.
- **Elimina**: la cartella principale viene aggiornata per visualizzare il primo batch di risorse.
- **Aggiungi**: il nuovo file viene inserito nella parte superiore (della cartella corrente). Metadati aggiuntivi, come lo stato del documento, lo stato del blocco, il tipo di file, la data di creazione e altri dettagli, vengono recuperati in una singola richiesta in background in batch e compilati automaticamente dopo un certo periodo di tempo.
- **Sposta**: lo spostamento di un file nella cartella attiva lo aggiunge nella parte superiore. Se si sposta un file fuori dalla cartella attiva, la cartella viene aggiornata al primo batch di risorse.
- **Pulsante Aggiorna**: ricarica la cartella attiva, mostrando il primo batch di risorse.
- **Ordinamento**: visualizza la prima pagina ordinata con scorrimento infinito.
- **Pannello di navigazione cartelle**: l&#39;apertura di una cartella carica il primo batch di risorse, con l&#39;aggiunta dell&#39;opzione **Carica altri** per i batch successivi.

  ![paginazione per il pannello di navigazione delle cartelle](images/home-tree-pagination.png){width="650"}

### Raccolte

- Se si aggiunge un file, questo viene inserito nella parte superiore della cartella senza l&#39;aggiornamento della cartella.
- Quando si apre una cartella, viene caricato il primo batch di risorse e viene aggiunta l&#39;opzione **Carica altro** per i batch successivi.

  ![paginazione per la raccolta](images/collections-paginated.png){width="650"}


### Explorer

- **Cartella principale**: scorrimento infinito. Il primo batch di risorse viene caricato inizialmente; i batch successivi vengono aggiunti automaticamente durante lo scorrimento.
- **Cartelle secondarie**: l&#39;espansione di una cartella comporta il caricamento del primo batch di risorse, con l&#39;aggiunta dell&#39;opzione **Carica altro** per i batch successivi.

  ![paginazione per explorer](images/explorer-pagination.png){width="650"}

- **Rinomina**: avviene sul posto senza aggiornamento della cartella.
- **Elimina**: la cartella principale viene aggiornata per visualizzare il primo batch di risorse.
- **Aggiungi o duplica**: il nuovo file viene visualizzato nella parte superiore della cartella.
- **Sposta**: lo spostamento tra cartelle non correlate aggiorna la cartella di origine al primo batch di risorse e aggiunge l&#39;elemento nella parte superiore della destinazione (caricando il primo batch di risorse della destinazione se non era già aperto).
- **Aggiorna**: un nuovo pulsante di aggiornamento nell&#39;intestazione del pannello Esplora risorse ricarica il livello principale, mostrando il primo batch di risorse.

### Pannello di ricerca

- La visualizzazione dei risultati di ricerca utilizza lo scorrimento infinito. Il primo batch di risorse viene caricato inizialmente; i batch successivi vengono aggiunti automaticamente durante lo scorrimento.

### Pannello Modello

- Il livello radice mostra solo le categorie **map** e **topic**. L&#39;espansione di una sottocartella comporta il caricamento del primo batch di risorse, con l&#39;aggiunta dell&#39;opzione **Carica altro** per i batch successivi.

### Finestra di dialogo Seleziona percorso

- Ogni nodo di cartella carica il primo batch di risorse, con un&#39;opzione **Carica altri** aggiunta per i batch successivi.

  ![paginazione per la finestra di dialogo seleziona percorso](images/select-path-pagination.png){width="650"}

- Quando la finestra di dialogo si apre e passa a un percorso di destinazione specifico, la struttura si espande automaticamente dalla radice alla destinazione. Le cartelle lungo il percorso vengono caricate con una dimensione di pagina maggiore, mentre la cartella di destinazione viene caricata con la dimensione batch standard.