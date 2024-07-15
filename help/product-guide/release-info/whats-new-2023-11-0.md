---
title: Note sulla versione | Novità di Adobe Experience Manager Guides, versione di novembre 2023
description: Scopri le funzioni nuove e migliorate nella versione di novembre 2023 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 83c04e01-92f1-41b0-8866-a202f4106b51
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Novità della versione di novembre 2023 di Adobe Experience Manager Guides as a Cloud Service

Questo articolo tratta le funzioni nuove e migliorate nella versione di novembre 2023 di Adobe Experience Manager Guides (in seguito denominato *Experience Manager Guides as a Cloud Service*).

Per ulteriori dettagli sulle istruzioni di aggiornamento, sulla matrice di compatibilità e sui problemi risolti in questa versione, visualizzare le [note sulla versione](release-notes-2023-11-0.md).

## Miglioramenti di Native PDF

Nella versione di novembre 2023 sono stati apportati i seguenti miglioramenti a Native PDF:

### Utilizzare e duplicare modelli di PDF predefiniti

Experience Manager Guides fornisce modelli di PDF preconfigurati o predefiniti. Duplicare i modelli di factory PDF per creare i modelli di PDF personalizzati.

Ora è possibile anche visualizzare in anteprima l&#39;immagine miniatura di un modello durante la creazione e la duplicazione di un modello. Puoi anche modificare o eliminare questa immagine. Questa funzione è utile per marcare o distinguere i modelli con nomi simili.
Ulteriori informazioni sul modello [PDF](../native-pdf/pdf-template.md).

![Finestra di dialogo Modello PDF duplicato](assets/duplicate-template.png){width="550" align="left"}

*Duplica un modello PDF esistente.*


### Modificare l&#39;ordine delle pagine e pubblicare più pagine per foglio

Oltre a pubblicare le pagine in base al documento di origine, è possibile modificare l’ordine delle pagine in PDF durante la pubblicazione di un documento con più pagine.  Questo offre la flessibilità di pubblicare le pagine in vari ordini, come prima tutte le pagine dispari o tutte le pagine pari. Puoi anche pubblicare come opuscolo e leggere le pagine come un libro. Puoi anche decidere il numero di pagine da pubblicare su un singolo foglio. Per ulteriori dettagli, visualizzare la sezione [Organizzazione pagina](../native-pdf/components-pdf-template.md#page-organization).

### Ordinare i termini del glossario in base ai tasti di ordinamento

Ora è anche possibile ordinare i termini del glossario in base ai tasti di ordinamento. È possibile utilizzare il tag ‘sort-as’ per definire una chiave di ordinamento per i termini del glossario. Quindi, puoi ordinarli in base ai tasti di ordinamento al posto dei termini. Questo consente di ordinare i termini del glossario in base ai termini utilizzati in lingue diverse. È inoltre possibile definire una singola chiave di ordinamento per un termine del glossario con una frase o un gruppo di parole.
Per ulteriori dettagli, visualizzare le [Impostazioni avanzate di PDF](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Gestione delle risorse migliorata per i modelli di PDF nativi

Experience Manager Guides ora ha migliorato la gestione delle risorse per i modelli Native PDF. È ora possibile condividere e riutilizzare le risorse, come immagini, file CSS e file font, tra più modelli di Native PDF. Grazie a questo miglioramento, la gestione delle risorse per un set elevato di modelli è molto più semplice. Non è necessario creare risorse duplicate per ciascun modello, ma è possibile mantenerle in una cartella condivisa e utilizzarle in tutti i modelli di PDF nativi.
Per ulteriori dettagli, visualizzare [Modello PDF](../native-pdf/pdf-template.md).

## Miglioramenti dell’editor web

Nella versione di novembre 2023 sono stati apportati i seguenti miglioramenti all’editor web:


### Visualizza i file per titolo o nomi file

È ora possibile scegliere la modalità predefinita di visualizzazione dei file nell&#39;editor Web. È possibile visualizzare l’elenco dei file in base ai titoli o ai nomi dei file dai vari pannelli nella vista Autore.

![Finestra di dialogo Preferenze utente](assets/user-preferences-2311.png){width="550" align="left"}

*Modifica la modalità predefinita di visualizzazione dei file dalla finestra di dialogo **Preferenze utente**.*


### Gestire i predefiniti per le condizioni

È possibile definire gli attributi della condizione negli argomenti DITA. Quindi, utilizzate gli attributi condizione nel predefinito condizione per pubblicare il contenuto in una mappa DITA. Experience Manager Guides ora consente anche di creare e gestire i predefiniti per le condizioni dall’editor web. È inoltre possibile modificarli, duplicarli o eliminarli facilmente.

![Predefiniti di condizione dalla scheda Gestisci dell&#39;editor Web ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Per ulteriori dettagli, visualizzare [Usa predefiniti di condizione](../user-guide/generate-output-use-condition-presets.md).

### Ripristina schede file all&#39;aggiornamento del browser

Experience Manager Guides ripristina lo stato delle schede dei file aperte nell&#39;editor Web quando si aggiorna il browser. Per ulteriori dettagli, visualizzare la sezione **Aggiorna browser durante la modifica dei file** in [Modifica argomenti nell&#39;editor Web](../user-guide/web-editor-edit-topics.md).

### Disavvolgere facilmente un elemento

Ora è possibile decomprimere facilmente un elemento utilizzando l’opzione dal menu di scelta rapida di un elemento nell’Editor web. Questo consente di unire facilmente il testo dell’elemento con il relativo elemento padre.
Per ulteriori dettagli, visualizzare la sezione **Estrarre un elemento** dalle [altre funzionalità dell&#39;editor Web](../user-guide/web-editor-other-features.md).

### Scelte rapide da tastiera per spostare il cursore

Experience Manager Guides ora consente anche di utilizzare i tasti di scelta rapida per spostare il cursore nell’editor Web. È possibile utilizzare le scelte rapide da tastiera per spostare rapidamente una parola verso sinistra o verso destra. È inoltre possibile spostarsi all&#39;inizio o alla fine della riga con l&#39;aiuto delle scelte rapide da tastiera.
Ora è anche possibile utilizzare i tasti di scelta rapida per spostare il cursore all&#39;inizio dell&#39;elemento successivo o alla fine dell&#39;elemento precedente.
Ulteriori informazioni sulle [scelte rapide da tastiera nell&#39;editor Web](../user-guide/web-editor-keyboard-shortcuts.md).
