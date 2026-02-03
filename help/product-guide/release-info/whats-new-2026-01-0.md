---
title: Note sulla versione | Novità di Adobe Experience Manager Guides versione 2026.01.0
description: Scopri le funzioni nuove e migliorate della versione 2026.01.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: f0ba8dce38a6eef5dedc8a81107c8e31ea6b26b3
workflow-type: tm+mt
source-wordcount: '1542'
ht-degree: 1%

---

# Novità della versione 2026.01.0 (febbraio 2026)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2026.01.0 di Adobe Experience Manager Guides as a Cloud Service.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2026.01.0](fixed-issues-2026-01-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.01.0](../release-info/upgrade-instructions-2026-01-0.md).


## Introduzione alla ricerca in modalità Source in Trova e sostituisci

Experience Manager Guides ha introdotto diversi miglioramenti alla funzione Trova e sostituisci disponibile nel pannello a sinistra dell’interfaccia dell’editor. Oltre a un&#39;interfaccia utente migliorata per una migliore usabilità, questa versione introduce un nuovo interruttore **Usa modalità origine** nel pannello **Trova e sostituisci**.

L’attivazione di questa modalità consente di eseguire una ricerca globale non solo sul contenuto visibile, ma anche sul contenuto sorgente sottostante (struttura XML, inclusi elementi, tag e valori di attributi) della stringa cercata. Questa modalità garantisce una ricerca completa nell’intero contenuto.

![](assets/map-find-replace-with-source-mode.png){width="650" align="left"}

In questa modalità è possibile applicare i filtri per restringere la ricerca in base al tipo di file, allo stato del documento, alla data dell&#39;ultima modifica e altro ancora. Puoi anche scaricare un rapporto CSV dettagliato dopo aver eseguito l’operazione Sostituisci tutto, che fornisce un’istantanea di tutte le azioni di sostituzione eseguite insieme al loro stato di esito positivo e negativo.

Per ulteriori dettagli, visualizzare la sezione [Trova e sostituisci](../user-guide/web-editor-left-panel.md#find-and-replace) in _Pannello sinistro nell&#39;editor_.

>[!NOTE]
>
> Per **Utilizzare la funzionalità della modalità di origine** nel pannello Trova e sostituisci, è necessario prima completare una distribuzione dell&#39;indice personalizzata. Una volta implementata l’indicizzazione, contatta il team Customer Success per abilitare questa funzione.

## Esperienza di esplorazione file e cartelle migliorata

Questa versione introduce un’interfaccia più pulita e intuitiva per la navigazione dei file e dei percorsi delle cartelle in Experience Manager Guides.

Durante l&#39;esplorazione dei file, la finestra di dialogo **Seleziona file** rinnovata presenta ora un layout a schede con due visualizzazioni: **Archivio** per l&#39;esplorazione dell&#39;intero archivio dei contenuti in formato tabulare e **Raccolte** per l&#39;accesso rapido ad argomenti, mappe e immagini utilizzati di frequente.

![](assets/select-file.png){width="650" align="left"}

I miglioramenti principali includono:

- Visualizzazione tabulare di file e cartelle per la navigazione organizzata.
- Breadcrumb e pannello di navigazione delle cartelle per spostarsi facilmente all’interno delle cartelle.
- Supporto per la selezione di più file per contenuti riutilizzabili, riferimenti ad argomenti, schemi, predefiniti di output (utilizzando DITAVAL) e Workfront.
- Visualizzate in anteprima i file selezionati per una facile revisione; per selezioni multiple, visualizzate in anteprima tutti i file e rimuovetene alcuni dal pannello Anteprima, se necessario.
- Opzioni di ricerca e filtro per limitare i risultati per nome, titolo, tipo di file, stato del documento e tag.

La finestra di dialogo **Seleziona percorso** offre anche una visualizzazione struttura migliorata per la navigazione delle cartelle, garantendo un modo più organizzato ed efficiente di selezionare i percorsi nell&#39;archivio dei contenuti.

![](assets/select-path-dialog-new.png){width="350" align="left"}

Per ulteriori dettagli, visualizzare [Esplorazione di file e cartelle nella sezione di Experience Manager Guides](../user-guide/web-editor-other-features.md#browse-files-and-folders-in-experience-manager-guides) in _Altre funzionalità nell&#39;editor_.

## Miglioramenti alla ricerca e al filtro dell’archivio

### Supporto per il filtro dello stato del documento

Ora, filtra i risultati della ricerca nel repository in base allo stato corrente del documento dei file. Con il nuovo filtro **Stato documento**, è possibile restringere la ricerca utilizzando i valori di filtro disponibili definiti nel file `ui_config.json` all&#39;interno del profilo cartella.

![](assets/document-state-filter-repository.png){align="left"}

I valori di filtro predefiniti disponibili per lo stato del documento sono: Bozza, Modifica, In revisione, Approvato, Rivisto e Fine. Per informazioni dettagliate sulla personalizzazione dei valori predefiniti dei filtri dello stato del documento, visualizzare [Configurare i filtri dello stato del documento](../cs-install-guide/config-doc-state-filters.md).

>[!NOTE]
>
> Se utilizzi impostazioni personalizzate per `ui_config.json`, assicurati di riprenderle prima dell&#39;aggiornamento. Dopo l’aggiornamento, rivedi e regola le impostazioni per allinearle alle modifiche introdotte nell’ultima versione.

### Icona miniatura per contenuti multimediali

Tutti i file multimediali vengono ora visualizzati con icone di miniatura, per facilitare l&#39;identificazione visiva e l&#39;individuazione delle immagini all&#39;interno del **repository**. Questo miglioramento si applica anche alla ricerca di file nel **pannello di ricerca**, per consentire di distinguere rapidamente le risorse multimediali da altri tipi di file.

![](assets/thumbnail-repository.png){align="left"}

## Miglioramenti dell’editor

Con questa versione sono stati apportati i seguenti miglioramenti all’editor:

### Aggiorna argomenti o mappa in modalità Anteprima

Presentazione della nuova funzionalità **Aggiorna** per le mappe già aperte in modalità Anteprima. Con questa nuova funzione, è possibile aggiornare facilmente il contenuto dell&#39;intera mappa o dei singoli argomenti presenti al suo interno.

- Per aggiornare l&#39;intera mappa (inclusi tutti gli argomenti), nell&#39;angolo in alto a sinistra dell&#39;editor verrà introdotto un nuovo pulsante **Aggiorna**.

  ![](assets/refresh-map.png){width="600" align="left"}

- Per aggiornare il contenuto di singoli argomenti, nel menu di scelta rapida viene introdotta una nuova opzione **Aggiorna argomento**.

  ![](assets/refresh-topic.png){width="600" align="left"}

Per ulteriori dettagli, visualizzare [le funzionalità dell&#39;editor di mappe](../user-guide/map-editor-advanced-map-editor.md).

### Indicatore della copia di lavoro per le modifiche ai metadati

Eventuali modifiche ai campi metadati disponibili in **Proprietà file** attiveranno ora l&#39;indicatore della copia di lavoro. Una versione del documento è contrassegnata come _dirty (*)_ ogni volta che si aggiungono, eliminano o modificano campi di metadati predefiniti o personalizzati. Questo miglioramento garantisce un monitoraggio accurato di tutte le modifiche apportate ai metadati, fornendo maggiore visibilità e controllo sulle versioni dei documenti.

### Conteggio delle parole per argomenti e mappe

È ora possibile tenere traccia del numero di parole presenti in un file mappa o argomento. Nel nuovo campo **Conteggio parole** nel pannello di destra verrà visualizzato il numero totale di parole presenti in un argomento (o mappa), dove le parole separate da spazi vengono conteggiate come singole parole. Si aggiorna automaticamente ogni volta che si salvano le modifiche. Per i riferimenti incrociati, è incluso solo il testo visualizzato, mentre le chiavi sono escluse.

![](assets/file-properties-new.png){width="350" align="left"}

Per ulteriori dettagli, visualizzare il [pannello destro nell&#39;editor](../user-guide/web-editor-right-panel.md#file-properties).

### Gestione migliorata per i file di sola lettura

La modifica delle proprietà dei file è ora limitata per i file in modalità **Sola lettura**. Se un file è bloccato da un altro utente (disponibile in modalità di sola lettura), non è possibile modificare alcuna proprietà dei metadati, né dal [pannello destro](../user-guide/web-editor-right-panel.md#file-properties), né dall&#39;opzione **Proprietà** nel [menu di scelta rapida di un file](../user-guide/web-editor-other-features.md#context-menu-functions-on-a-files-tab), né dal [report metadati](../user-guide/reports-web-editor.md#metadata-report). In questo modo è possibile evitare modifiche accidentali ai file di sola lettura.

## Miglioramenti della revisione

### Aggiungere o rimuovere argomenti da un&#39;attività di revisione in corso

Ora è possibile aggiungere nuovi argomenti a un&#39;attività di revisione in corso (se non sono stati precedentemente inviati per la revisione) o rimuovere argomenti da un&#39;attività di revisione in corso senza influire sul flusso di lavoro di revisione.

Nella pagina **Dettagli attività**, è sufficiente selezionare o deselezionare gli argomenti per modificare l&#39;elenco degli argomenti. I revisori ricevono notifiche (tramite AEM e e-mail) su eventuali modifiche apportate agli argomenti assegnati tramite AEM e notifiche e-mail. Per ulteriori dettagli, visualizzare [Invia argomenti per la revisione](../user-guide/review-send-topics-for-review.md).

![](assets/modify-review-topics.png){width="650" align="left"}

## Miglioramenti alla traduzione

### Indicatore per risorse senza versione inviate per la traduzione

Durante la gestione delle traduzioni, è importante assicurarsi che tutte le versioni siano state salvate prima di inviarle per l’elaborazione. Per facilitare questa fase, Experience Manager Guides fornisce ora un chiaro indicatore per gli argomenti in cui sono state salvate modifiche ma non sono ancora presenti versioni.

Se un file contiene modifiche senza versione (non salvate come nuova versione nella mappa), accanto al file viene visualizzata un&#39;icona _info_ che indica che sono presenti aggiornamenti. Per concentrarti rapidamente su questi file, abilita l&#39;opzione **Mostra solo le risorse con modifiche senza versione** nel pannello Filtri.

Per ulteriori dettagli, visualizzare [Traduci documenti dalla console Mappa](../user-guide/translate-documents-web-editor.md).

![](assets/unversioned-changes-translation.png){width="650" align="left"}

## Miglioramenti alla pubblicazione

### Rappresentazioni di immagini personalizzate per predefiniti di output specifici

È ora possibile configurare diverse rappresentazioni di immagini per singoli predefiniti di output nello stesso tipo di output utilizzando l&#39;attributo `outputName` in `renditionmapping.xml`. Questo miglioramento offre maggiore flessibilità quando si pubblicano contenuti che richiedono risoluzioni di immagine diverse per scenari diversi. Ad esempio, potresti desiderare un’immagine ad alta risoluzione per l’output principale di HTML5 mentre utilizzi una miniatura più piccola per un predefinito leggero.

Per ulteriori dettagli, visualizzare [Gestire la rappresentazione dell&#39;immagine nella generazione dell&#39;output](../cs-install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).


### Scaricare i registri per l’output generato

Durante la generazione dell&#39;output tramite l&#39;interfaccia utente di Assets, è ora disponibile un nuovo pulsante **Scarica registri** che consente di scaricare i registri nel dispositivo locale per accedervi e rivederli più facilmente.


### Variabili di lingua per riferimenti incrociati nell’output PDF nativo

Quando si pubblica l&#39;output di PDF nativo, è possibile utilizzare [variabili di linguaggio](../native-pdf/native-pdf-language-variables.md) per tradurre testo di rimando statico come _Vedere nel capitolo_ o _Vedere a pagina_. La variabile utilizza il linguaggio definito nell&#39;argomento tramite l&#39;attributo `xml:lang`.

Per informazioni dettagliate sulla configurazione del predefinito di output del PDF nativo e delle impostazioni dei riferimenti incrociati, visualizzare [Predefinito di output del PDF nativo](../web-editor/native-pdf-web-editor.md).


### Supporto per la mappatura dei componenti a livello di elemento nella pubblicazione del nuovo AEM Sites (utilizzando la mappatura dei componenti compositi)

Experience Manager Guides ora supporta la mappatura dei componenti a livello di elemento nell’output di AEM Sites (utilizzando la mappatura dei componenti compositi), fornendo ai team un controllo preciso sul rendering degli elementi DITA utilizzando `componentmapping.json`. Mappando `topicref`, titoli, immagini, tabelle e altro ancora ai componenti core di AEM appropriati, si ottiene una struttura più pulita invece di tutte le impostazioni predefinite del componente Testo. Ciò si traduce in prestazioni migliori e sfrutta esperienze Sites più ricche e moderne.

## Miglioramenti all’elaborazione delle risorse

Questa versione introduce i seguenti miglioramenti all’elaborazione delle risorse:

- Eseguire l’elaborazione delle risorse a livello di cartella e di singolo file
- Per filtrare le risorse, scegli tipi di risorse specifici, ad esempio argomenti, mappe, Markdown, HTML/CSS, DITAVAL o altri file supportati, in modo da elaborare solo i file necessari.
- Applica filtri basati sulla data per limitare l’ambito di elaborazione per un intervallo temporale specificato.
- Rielabora le risorse direttamente utilizzando la nuova opzione (**Rielabora risorse**) disponibile nel menu di scelta rapida dei file e delle cartelle nella vista Archivio e nel pannello Esplora risorse.

Per ulteriori dettagli sull&#39;elaborazione delle risorse, visualizzare [Elabora risorse](../user-guide/asset-processor.md).

## Miglioramenti API

Con questa versione sono stati apportati i seguenti miglioramenti API:

- Vengono introdotte nuove API per creare un nuovo progetto di traduzione e tracciarne lo stato. Queste API consentono di automatizzare il processo di traduzione, riducendo lo sforzo manuale e migliorando l’efficienza. Per informazioni dettagliate, visualizza [Crea progetto di traduzione](../api-reference/translation-project.md)
- API di elaborazione delle risorse migliorate con una migliore funzionalità di filtro per file e cartelle. Per ulteriori dettagli, visualizzare [Elabora risorse](../api-reference/bulk-assets-processing.md).
















