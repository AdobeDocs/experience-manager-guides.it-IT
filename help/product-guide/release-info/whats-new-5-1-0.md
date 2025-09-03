---
title: Note sulla versione | Novità di Adobe Experience Manager Guides versione 5.1.0
description: Scopri le funzioni nuove e migliorate di Adobe Experience Manager Guides versione 5.1.0
role: Leader
source-git-commit: f6617b727d385d31ba66d575ee48f29e77ac716f
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# Novità della versione 5.1.0 (settembre 2025)

Questo articolo descrive le nuove funzioni introdotte con la versione 5.1.0 di Adobe Experience Manager Guides.

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 5.1.0](fixed-issues-5-1-0.md).

Scopri le [istruzioni di aggiornamento per la versione 5.1.0](../release-info/upgrade-instructions-5-1-0.md).


## Flusso di lavoro di revisione migliorato

Con questa versione, il flusso di lavoro di revisione è stato notevolmente migliorato per supportare in modo migliore la comunicazione diretta tra autori e revisori. Gli aggiornamenti principali includono:

- Flussi di lavoro di gestione delle attività con notifiche fruibili
- Possibilità di assegnare tag agli utenti per richiedere attenzione immediata
- Accesso semplificato ai dettagli del progetto e dell’attività dal pannello di revisione

Grazie a questi miglioramenti, gli utenti possono ora aspettarsi:

- Cicli di revisione efficienti e tempestivi
- Riduzione dello sforzo manuale durante gli scambi di feedback

Per ulteriori dettagli, visualizzare [Introduzione alla revisione](../user-guide/review.md)

## Esperienza migliorata per la creazione e l&#39;utilizzo di file DITAVAL

Questo aggiornamento introduce diversi miglioramenti che semplificano la creazione, la gestione e l’applicazione dei file DITAVAL, consentendo un migliore controllo del contenuto condizionale e dello stile tra gli output.

Gli elementi di rilievo sono i seguenti:

- **Supporto migliorato dei contrassegni nell&#39;authoring dei file DITAVAL:** Experience Manager Guides offre nuove funzionalità per personalizzare la pubblicazione dei contenuti tramite il supporto migliorato dei contrassegni nei file DITAVAL. È ora possibile applicare i flag di inizio e fine a contenuto specifico, incluse le immagini, e arricchire le sezioni contrassegnate con opzioni di formattazione come grassetto, corsivo e altro ancora. Per gestire le sovrapposizioni di condizioni, è possibile configurare il **conflitto di stili**, che include l&#39;impostazione di un colore di sfondo e di testo predefinito, garantendo chiarezza e coerenza nell&#39;output. Questi flag sono completamente supportati nella generazione di PDF nativi e l&#39;output risultante riflette in modo accurato e completo tutti gli elementi di stile applicati.
Per ulteriori dettagli, visualizzare [Utilizzare l&#39;editor DITAVAL](../user-guide/ditaval-editor.md).

  ![](assets/ditaval-flag-style-new.png){width="350" align="left"}

- **Supporto di più file DITAVAL per PDF nativo:** Per PDF nativo è ora possibile aggiungere più file DITAVAL, ciascuno visualizzato come voce con tag per facilitarne l&#39;identificazione e la rimozione, offrendo maggiore flessibilità e controllo sui contenuti condizionali negli output di PDF

  Inoltre, questo aggiornamento migliora la creazione dei predefiniti di output consentendo la modifica dei campi DITAVAL tra i formati, consentendo agli utenti di specificare manualmente i percorsi DITAVAL.

  Per ulteriori dettagli, visualizzare [Comprendere i predefiniti di output](../user-guide/generate-output-understand-presets.md) in Experience Manager Guides.

## Miglioramenti alla pubblicazione

Con la nuova versione sono stati apportati i seguenti miglioramenti in termini di pubblicazione:

### È stato migliorato il filtro del registro di generazione dell’output

Questa versione apporta miglioramenti all’interfaccia utente e alla funzionalità di filtro dei registri di generazione dell’output. Ora puoi filtrare meglio i registri di generazione dell&#39;output per tutti e quattro i livelli distinti: **Info**, **Warn**, **Error** (inclusi errori ed eccezioni) e **Fatal**; con indicatori di colore migliorati e intuitivi che semplificano l&#39;analisi e migliorano la visibilità nel flusso del registro. Questo miglioramento consente di navigare nei registri in modo più efficiente e individuare con precisione i problemi critici.

Per ulteriori dettagli, visualizzare [Risoluzione dei problemi di base](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png){align="left"}


### I file temporanei per l’output pubblicato ora includono gli URL Author e Publish in un nuovo file di configurazione

I più recenti miglioramenti apportati alla pubblicazione di Experience Manager Guides ora aggiungono un nuovo file `system_config.xml` ai file temporanei generati durante la pubblicazione degli output HTML, PDF e JSON tramite DITA-OT, nonché dell&#39;output PDF nativo. Questo file viene incluso automaticamente nel processo di pubblicazione e accessibile tramite file temporanei quando si abilita l&#39;opzione **Mantieni file temporanei** per i predefiniti e si genera l&#39;output.

Il file `system_config.xml` contiene i dettagli dell&#39;istanza di AEM, inclusi l&#39;URL di authoring, l&#39;URL locale e l&#39;URL di pubblicazione, che forniscono un contesto più chiaro e migliorano la tracciabilità degli URL scaricati.

Per ulteriori dettagli, visualizzare [Comprendere i predefiniti di output](../user-guide/generate-output-understand-presets.md).

### Supporto della nuova variabile del percorso di output per la generazione dell&#39;output

Questo aggiornamento introduce la configurazione dinamica `output path` per i predefiniti di output come PDF nativo, PDF DITA-OT, JSON, HTML5 e Personalizzato. Anziché utilizzare un percorso fisso, gli utenti possono ora definire il percorso di output utilizzando la variabile `${base_output_path}` durante l&#39;installazione, offrendo maggiore flessibilità. Il percorso predefinito precedente `/content/dam/fmdita-outputs` non è più obbligatorio.

Tutti i percorsi di output associati ai predefiniti del profilo di cartella globale verranno migrati automaticamente per utilizzare la nuova variabile del percorso di output di base. Per i profili di cartelle personalizzati, tuttavia, la migrazione non è automatica; ti consigliamo di contattare il team Customer Success per assistenza.

Per ulteriori dettagli, visualizzare [Comprendere i predefiniti di output](../user-guide/generate-output-understand-presets.md).

### La baseline esportata ora include lo stato del documento

La funzionalità Esporta baseline ora include lo **stato del documento** insieme a dettagli chiave quali titolo, nome file, tipo di file e numero di versione nello snapshot della baseline. Questo miglioramento migliora la gestione della linea di base fornendo una panoramica più completa.

Per ulteriori dettagli, visualizzare [Crea e gestisci baseline dalla console Mappa](../user-guide/web-editor-baseline.md#manage-baselines).

### Supporto per la pubblicazione incrementale basata su linee di base tramite dashboard delle mappe per l’output di AEM Sites utilizzando la mappatura dei componenti legacy

Il processo di generazione dell’output incrementale è stato migliorato per supportare la pubblicazione di versioni specifiche degli argomenti definiti nella linea di base selezionata per i siti AEM utilizzando la mappatura dei componenti legacy, garantendo una propagazione accurata del contenuto nell’output.

Per ulteriori dettagli, visualizzare [Generazione output incrementale](../user-guide/generate-output-aem-site.md).

## Miglioramenti dell’editor

Con la nuova versione sono stati apportati i seguenti miglioramenti all’editor:

### Esperienza di ricerca avanzata per il pannello Contenuti riutilizzabili

Experience Manager Guides introduce un’esperienza di ricerca avanzata nel pannello Contenuto riutilizzabile. Con questo aggiornamento, la ricerca di qualsiasi parola chiave ora analizza tutti i file aggiunti come contenuto riutilizzabile e non solo quelli aperti, garantendo di trovare la posizione esatta della parola chiave in tutte le occorrenze, indipendentemente dal fatto che i contenitori siano aperti o compressi. Inoltre, quando si cancella la barra di ricerca, viene mantenuto lo stato originale di tutti i contenitori, fornendo una funzionalità di ricerca più efficiente e intuitiva.

Per ulteriori dettagli, visualizzare [Contenuto riutilizzabile](../user-guide/web-editor-features.md#reusable-content).

### Attributo &#39;Format&#39; aggiunto per i collegamenti di riferimento

Adobe Experience Manager Guides ora aggiunge un attributo **format** per i collegamenti di riferimento all&#39;interno dell&#39;editor. Questo attributo viene visualizzato nella **visualizzazione Source** e indica chiaramente il tipo di file, ad esempio:

- Per i file con estensione **.pdf**, il formato verrà impostato su **pdf**
- Per i file con estensione **.html**, il formato sarà impostato su **html**
- Per i file con un file **.dita** o **.ditamap**, il formato verrà impostato su **dita**

Inoltre, anche i file con estensione **.xml** avranno il formato impostato su **dita**. Per i file senza estensione, il formato viene lasciato vuoto. Inoltre, per qualsiasi collegamento di riferimento con ambito impostato su **external**, il formato verrà impostato su **html** indipendentemente dall&#39;estensione del file nei collegamenti di riferimento.

### Opzioni avanzate per il download delle mappe nell’editor

Experience Manager Guides introduce una nuova opzione **Utilizza nomi di file effettivi** nella finestra di dialogo **Scarica mappa**. Ora, quando scarichi i file mappa, puoi scegliere di mantenere i nomi dei file originali invece degli UUID predefiniti, semplificando notevolmente il riconoscimento e la gestione dei file. Questa opzione è disponibile solo se si seleziona **Mantieni gerarchia file** ed è disabilitata quando si sceglie **Appiattisci gerarchia file**, per offrire maggiore flessibilità nell&#39;organizzazione delle mappe scaricate.

Per ulteriori dettagli, visualizzare [Scarica file](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}

### Richiesta di timeout della sessione per evitare la perdita accidentale di contenuto

Un messaggio a comparsa ora notifica la scadenza della sessione Adobe Experience Manager e l&#39;utente viene disconnesso a causa di inattività. Questo messaggio viene attivato quando si tenta di modificare il contenuto in Experience Manager Guides al termine della sessione. Questa funzione consente di ridurre il rischio di perdere il lavoro non salvato e di migliorare l’affidabilità e la fluidità complessive dell’esperienza, anche durante i periodi di inattività.

![](assets/sign-out-prompt.png)

Ulteriori informazioni sulla [richiesta di timeout sessione](../user-guide/session-timeout-prompt.md) in Experience Manager Guides.

### Gestione `navref` migliorata nell&#39;editor

Gli ultimi miglioramenti apportati all&#39;editor migliorano la gestione di `navref` elementi in una mappa DITA. Ora, quando si aggiunge un elemento `navref` a una mappa, viene visualizzata la finestra di dialogo **Seleziona percorso**, che consente di scegliere facilmente i riferimenti della mappa da includere come collegamenti di navigazione nella mappa. Una volta aggiunto, il titolo della mappa aggiunta viene visualizzato sia nella vista Author che nella vista Layout, fornendo una migliore visibilità della navigazione inclusa durante l’authoring.  Inoltre, l&#39;elemento `navref` aggiunto viene risolto automaticamente per visualizzare la mappa a cui si fa riferimento nell&#39;editor.

Per ulteriori dettagli, visualizzare [Aggiungi riferimenti di navigazione](../user-guide/map-editor-other-features.md#add-navigation-references).


### Miglioramenti dell’interfaccia utente nella barra degli strumenti dell’editor e nelle Preferenze utente

Con questa versione le impostazioni all&#39;interno delle **Preferenze utente** nella home page per le schede Generale e Aspetto sono state ristrutturate. È incluso rinominare l&#39;etichetta **Aprire le preferenze per le mappe** e spostare l&#39;opzione Spazi unificatori nella barra degli strumenti dell&#39;editor.

Inoltre, nella barra degli strumenti dell&#39;editor alcuni interruttori di accesso rapido per abilitare o disabilitare Revisioni, Tag e Spazi non interrotti sono ora raggruppati nell&#39;opzione **Mostra** nel menu a discesa per una migliore fruibilità.

Per ulteriori dettagli, visualizzare [Barra degli strumenti nell&#39;editor](../user-guide/web-editor-toolbar.md#menu-dropdown).







