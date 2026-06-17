---
title: Configurare i profili delle cartelle
description: Scopri come configurare i profili delle cartelle quando utilizzi i contenuti di apprendimento e formazione in Experience Manager Guides.
feature: Authoring
role: Admin
level: Experienced
exl-id: dc26ae48-c953-492c-823a-5f65157b6902
TQID: https://experienceleague.adobe.com/jp7oUSIZlnTfGnx58E9rPn6Tk4zE2lp-oZSTdjblbZ0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: b89a36a9-95de-429b-adde-f901256d8f24
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9132140a0305eb0507598a7caf5f704861879a93
workflow-type: tm+mt
source-wordcount: 1960
ht-degree: 0%

---

# Configurare i profili delle cartelle

È necessario un profilo di cartella per separare le configurazioni dei diversi reparti o prodotti dell&#39;azienda. Per i contenuti di apprendimento e formazione, puoi creare e configurare un profilo a livello di cartella per gestire modelli di authoring, modelli di output, predefiniti di output e altre impostazioni a livello di cartella.

Scopri le [best practice per la configurazione della struttura di cartelle](best-practices-folder-structure.md).

Per iniziare a configurare il profilo della cartella per i contenuti di apprendimento e formazione, è necessario:

1. **Creare cartelle diverse per gestire i modelli di creazione e di output**: è possibile creare cartelle per autori e autori che lavorano in reparti o prodotti diversi della propria azienda. Queste cartelle possono essere mappate su profili di cartelle specifici, ciascuno configurato con diversi modelli di authoring e output per supportare la creazione di corsi di apprendimento specifici per il reparto e l’amministrazione decentrata.

   Puoi creare una nuova cartella dal pannello Archivio.

   ![](assets/create-new-folder.png){width="350"}
2. **Crea cartelle per lingua per gestire la traduzione**: se traduci il contenuto in lingue diverse, devi creare cartelle corrispondenti a ciascuna lingua. Ognuna di queste cartelle della lingua conterrà il contenuto corrispondente a tale lingua.

3. **Crea una cartella per gestire Assets**: analogamente alle cartelle, puoi anche creare diverse cartelle di Assets per soddisfare le esigenze dei diversi reparti. In questo modo, assicurati anche che gli autori e gli editori abbiano accesso al CSS corretto configurato nei loro modelli, immagini e altre risorse.

   ![](assets/configure-assets-folder.png){width="350"}
4. [Crea un profilo di cartella](../cs-install-guide/conf-folder-level.md#create-and-configure-a-folder-level-profile) per mappare diverse cartelle.
5. **Selezionare il profilo di cartella da configurare**: una volta creato il profilo di cartella, è necessario selezionare il profilo di cartella nella pagina [Preferenze utente](../user-guide/intro-home-page.md#user-preferences) per assicurarsi che autori e autori abbiano accesso ai modelli corretti.

   ![](assets/folder-profile.png){width="650"}

6. **Configura impostazioni profilo cartella**: per i contenuti di apprendimento e formazione, è possibile configurare le seguenti impostazioni a livello di cartella:
   - [Generale](#general)
   - [Pannelli](#configure-panels)
   - [Modelli di contenuto](#configure-content-templates)
   - [Predefiniti di output](#configure-output-presets)
   - [Editor HTML](#html-editor-settings)
   - [Profili di pubblicazione](#manage-publish-profiles)

Per accedere a queste impostazioni, passare alla visualizzazione Editor e selezionare **Impostazioni Workspace** dal menu **Opzioni** come illustrato di seguito:

![](assets/access-editor-settings.png)

## Generale

Nella scheda Generale, puoi configurare le seguenti impostazioni specifiche per la funzione dei contenuti di formazione e apprendimento del prodotto:

![](assets/lc-config-settings-general.png){width="350"}

- **Contenuto di apprendimento**: utilizza l&#39;interruttore **Abilita contenuto di apprendimento** per abilitare o disabilitare la funzione a livello di profilo della cartella.
- **Editor HTML**: questa impostazione consente di configurare l&#39;editor per l&#39;authoring basato su HTML. Le opzioni di configurazione principali presenti in questa impostazione sono le seguenti:

   - **Nascondi stile in linea**: abilita questa opzione per impedire agli autori di applicare formattazione in linea al contenuto del corso. Quando questa opzione è attivata, tutte le opzioni di stile in linea come Font, Bordo, Layout, Sfondo e Colonne presenti nel pannello di destra dell’Editor rimangono nascoste per gli autori. Tuttavia, gli autori possono comunque utilizzare le opzioni di stile globali basate su classi disponibili nel pannello **Stili**. Questo consente di mantenere la coerenza con le linee guida di stile della tua organizzazione.
   - **Nascondi visualizzazione Source per autori**: abilitare questa opzione per limitare l&#39;accesso al codice sorgente HTML. Questa funzione ti consente di semplificare l’esperienza di modifica o di evitare modifiche accidentali al codice sottostante.

## Configurare i pannelli

Questa impostazione controlla i pannelli visualizzati nei pannelli sinistro e destro dell&#39;**Editor** e della **Console mappe** in Experience Manager Guides. Puoi attivare o disattivare il pulsante per mostrare o nascondere il pannello desiderato.

Per i contenuti di apprendimento e formazione, assicurati che solo le seguenti funzioni siano abilitate per la console Editor e Mappa.

![](assets/panels-settings.png){width="350"}


### Editor

**Pannello sinistro**

- **Raccolte**: consente di organizzare e salvare i file utilizzati di frequente o di accedere rapidamente ai file condivisi.
- **Esplora risorse**: consente di visualizzare e accedere a tutte le mappe, gli argomenti, le immagini e le altre risorse archiviate nel repository dei contenuti.
- **Gestione corsi**: fornisce un&#39;area di lavoro dedicata per la creazione e la gestione dei corsi.
- **Mappa**: fornisce una visualizzazione mappa del file di mappa aperto.
- **Struttura**: visualizza la gerarchia strutturale dell&#39;argomento o della mappa attualmente aperta, consentendo una navigazione rapida e l&#39;accesso a livello di elemento.
- **Workfront**: consente di accedere a solide funzionalità di gestione dei progetti oltre alle funzionalità principali di Experience Manager Guides CCMS.
- **Contenuto riutilizzabile**: consente di gestire e inserire elementi o argomenti riutilizzabili per garantire la coerenza e ridurre la duplicazione tra i contenuti.
- **Glossario**: consente di creare e gestire i termini del glossario e di includerli negli argomenti per mantenere una terminologia coerente.
- **Snippet**: consente di creare e riutilizzare frammenti di contenuto di piccole dimensioni in vari argomenti dei corsi di apprendimento.
- **Condizioni**: consente di configurare gli attributi condizionali a livello globale e di cartella.
- **Modelli**: ti consente di creare e gestire i modelli del corso.
- **Citazioni**: consente di aggiungere e gestire citazioni nel contenuto utilizzando gli stili di citazione supportati.
- **Variabili di lingua**: consente di definire le variabili di lingua per l&#39;output pubblicato.
- **Variabili**: ti consente di creare e gestire le variabili da utilizzare nel contenuto di apprendimento.
- **Modelli di output**: consente di creare e gestire modelli di output per generare output in vari formati.
- **Trova e sostituisci**: fornisce le opzioni per cercare e sostituire il testo nei file in una mappa o in una cartella all&#39;interno del repository. 
- **Origini dati**: consente di connettere origini dati esterne e riutilizzare i dati all&#39;interno del contenuto.
- **Revisione**: consente di creare e gestire flussi di lavoro di revisione in Experience Manager Guides.
- **Report di sistema**: consente di creare e gestire report.

**Pannello destro**

- **Proprietà contenuto**: contiene informazioni sul tipo e sugli attributi dell&#39;elemento attualmente selezionato nell&#39;editor.
- **Proprietà file**: consente di visualizzare e gestire le proprietà del file selezionato.
- **Stili**: visualizza le opzioni di stile globali basate su classi da utilizzare nel contenuto di apprendimento.
- **Filtri**: consente di filtrare il contenuto in base alle condizioni applicate nella modalità Anteprima di un argomento.

### Console mappe

**Pannello sinistro**

- **Predefiniti**: consente di configurare i predefiniti di output per la pubblicazione del corso di apprendimento.
- **Traduzione**: fornisce opzioni per tradurre il contenuto in più lingue.
- **Rapporti**: ti consente di generare e gestire i rapporti per ottenere un insight utile sullo stato complessivo del contenuto del corso.
- **Predefiniti condizione**: fornisce opzioni per configurare predefiniti di output basati su condizioni per diversi tipi di pubblico, reparti e altro ancora.

**Pannello destro**

- **Filtri**: ti consente di utilizzare i filtri quando lavori con rapporti e traduzione.

## Configurare i modelli di contenuto

>[!NOTE]
>
> Questa impostazione è disponibile solo quando la funzionalità dei contenuti di apprendimento è abilitata nelle **impostazioni Workspace** > **Generale**.

Questa impostazione consente di gestire i modelli di authoring e pubblicazione presenti nel [pannello sinistro dell&#39;editor](../user-guide/web-editor-left-panel.md). Puoi aggiungere, rimuovere o riordinare i modelli di authoring e output, che saranno quindi accessibili agli autori e agli editori.

![](assets/templates-settings.png){width="350"}

I modelli di authoring sono disponibili in quattro categorie: corso di apprendimento, contenuto di apprendimento, quiz e banca delle domande. Eventuali modelli predefiniti configurati nell’istanza verranno visualizzati per impostazione predefinita.

![](assets/templates-list.png){width="350"}

### Aggiungi modelli

Per aggiungere un nuovo modello, effettua le seguenti operazioni:

1. Passa alla categoria del modello in cui desideri aggiungere un modello e seleziona **Aggiungi**.
2. Nella finestra di dialogo Seleziona percorso, seleziona il modello desiderato.
3. Scegli **Seleziona**.

   ![](assets/add-templates.png){width="350"}

Il modello viene aggiunto nella rispettiva categoria nel pannello Impostazioni.

Allo stesso modo, potete aggiungere gli altri modelli di creazione e di output. Una volta aggiunti, questi modelli vengono resi disponibili agli autori e agli editori nelle rispettive finestre di dialogo del corso. Ad esempio, il modello di corso di apprendimento aggiunto dall’Amministratore sarà disponibile per gli autori quando creano un nuovo corso.

![](assets/templates-added-course.png){width="350"}

### Utilizzare nuovi modelli di authoring e output

Per utilizzare un modello diverso da quelli visualizzati nella finestra di dialogo **Seleziona percorso**, creare un modello di creazione o di output personalizzato.

**Crea nuovi modelli di authoring**

Per utilizzare una mappa o un modello di argomento diverso, create un nuovo modello di authoring dal pannello Modelli nell&#39;Editor. Utilizza i modelli di mappa per creare corsi di apprendimento e modelli di argomenti per contenuti di apprendimento, quiz o riepilogo di apprendimento.

Per ulteriori dettagli, visualizzare [Creare modelli personalizzati dall&#39;editor](../user-guide/create-maps-customized-templates.md).

![](assets/authoring-templates-editor.png){width="350"}

**Crea nuovi modelli di output**

Per creare un nuovo modello di output per il contenuto di apprendimento e formazione, effettua le seguenti operazioni:

1. Dal pannello a sinistra nell&#39;editor, seleziona **Altro** > **Modelli di output**.

   Viene visualizzato il pannello Modelli di output.

   ![](assets/output-templates-editor.png){width="350" height=""}
2. Nel pannello Modelli di output, selezionate (+) per creare un nuovo modello di output.

   ![](assets/create-new-output-template.png){width="350"}
3. Seleziona un modello di output dal menu a discesa.


   ![](assets/output-template-types.png){width="650"}
4. In base al tipo di modello di output selezionato, viene visualizzata una finestra di dialogo in cui è possibile creare un nuovo modello basato sui modelli disponibili.

   ![](assets/new-scorm-template-dialog.png){width="350"}

5. Seleziona **Crea**.

   Viene creato un nuovo modello di output.

6. Per accedere e aggiungere il modello di output per gli editori, passa a **Impostazioni** > **Modelli** > **Modelli di output** e seleziona **Aggiungi**.

   ![](assets/add-output-template-settings-panel.png){width="350"}

   Il modello di output viene visualizzato nella finestra di dialogo Seleziona percorso.
7. Selezionare il modello e scegliere **Conferma**.

   ![](assets/select-scorm-template-dialog.png){width="350"}

   Il modello di output selezionato viene ora aggiunto al pannello Impostazioni.

   ![](assets/scorm-template-added.png){width="350"}

### Configurare i layout di pagina per i modelli di output SCORM

I modelli di output SCORM consentono di assegnare layout di pagina diversi a tipi di argomenti diversi all&#39;interno di un corso. Questo consente di personalizzare la presentazione di lezioni, quiz, pagine di panoramica e altri tipi di contenuto nel pacchetto SCORM generato.

Ad esempio, una pagina della lezione può utilizzare un layout che include un&#39;intestazione, un&#39;area di contenuto e un piè di pagina, mentre una pagina del quiz può utilizzare un layout semplificato senza piè di pagina. Puoi anche creare layout dedicati per le pagine di panoramica o per qualsiasi altro tipo di argomento e mapparli di conseguenza.

Le assegnazioni di layout sono configurate al livello **Modello di output**. Qualsiasi predefinito SCORM che utilizza il modello di output configurato applicherà le mappature di layout selezionate durante la generazione dei corsi.
Per configurare il layout di pagina per i modelli, effettua le seguenti operazioni:

1. Passa a **Modelli di output** e apri il **modello di output SCORM** richiesto.

2. Selezionare la scheda **Impostazioni**.

3. Nella finestra **Layout di pagina**, individua i tipi di argomento disponibili.

   ![](assets/page-layout-scorm.png){width="650"}

4. Per ogni tipo di argomento, seleziona il layout di pagina da utilizzare durante la generazione del corso.

   **Esempio:**
   - **Layout di pagina predefinito**: lezione
   - **Quiz**: Quiz
   - **Panoramica**: lezione

5. Per utilizzare un nuovo layout, crea il layout di pagina richiesto all&#39;interno del modello di output utilizzando l&#39;opzione **Nuovo layout di pagina** dal menu di scelta rapida dal pannello **Modelli di output**.

   ![](assets/new-page-layout-scorm.png){width="650"}

6. Torna alla scheda **Impostazioni** e assegna il layout appena creato al tipo di argomento appropriato.

7. Salvare il layout di pagina per il modello di output utilizzando l&#39;icona Salva nell&#39;angolo destro della barra della scheda.


Quando viene generato un corso utilizzando un predefinito SCORM che utilizza il modello di output configurato, viene eseguito il rendering di ciascun argomento utilizzando il layout assegnato al relativo tipo di argomento. Questo consente a diversi tipi di contenuto all’interno dello stesso corso di avere strutture di pagina e presentazioni visive personalizzate.

### Rimuovere o riordinare i modelli

Una volta aggiunti, è possibile rimuovere o riordinare i modelli dal pannello Impostazioni.

Per rimuovere un modello, seleziona l&#39;icona **Rimuovi** accanto al modello.

![](assets/remove-teamplates.png){width="350"}

È inoltre possibile definire l&#39;ordine di visualizzazione dei modelli presenti in una categoria. Per modificare l&#39;ordine di visualizzazione dei modelli, selezionare le barre punteggiate e trascinare un modello nella posizione desiderata.

![](assets/reorder-templates.png){width="350"}


## Configurare i predefiniti di output

>[!NOTE]
>
> Questa impostazione è disponibile solo quando la funzionalità dei contenuti di apprendimento è abilitata nelle **impostazioni Workspace** > **Generale**.

La scheda Predefiniti di output consente di definire i formati di output disponibili per la pubblicazione di un corso. Contiene due sezioni: **Tipi di predefiniti di output consentiti** e **Predefiniti di output comuni**.

![](assets/configure-course-output-presets.png){width="350"}

- **Tipi di predefiniti di output consentiti**: in questa sezione sono elencati tutti i predefiniti di output supportati nell&#39;istanza di Experience Manager Guides. Per la pubblicazione del corso sono applicabili solo i formati **SCORM** e **PDF**. Puoi selezionare una o entrambe le opzioni. I predefiniti selezionati saranno disponibili per gli editori durante la generazione dell’output del corso.

  ![](assets/allowed-output-presets.png){width="350"}

- **Predefiniti di output comuni**: in questa sezione vengono visualizzati i predefiniti di output comunemente creati e aggiunti dagli editori a un profilo di cartella specifico. È inoltre possibile rimuovere qualsiasi predefinito non più necessario.

  ![](assets/common-output-presets.png){width="350"}

## Gestisci profili di pubblicazione

Questa sezione ti consente di visualizzare, creare e gestire i profili di pubblicazione utilizzati per pubblicare i corsi su SCORM Cloud o Adobe Learning Manager (ALM). Ogni profilo definisce le impostazioni di connessione e i dettagli di configurazione necessari per pubblicare un corso di apprendimento su un server di pubblicazione selezionato.

Puoi creare più profili per pubblicare contenuti su diversi account SCORM Cloud o istanze ALM, fornendo flessibilità e controllo sul flusso di lavoro di pubblicazione.

Per configurare un profilo di pubblicazione, seleziona il server di pubblicazione desiderato (SCORM Cloud o Adobe Learning Manager) e fornisci i dettagli di connessione richiesti. Per SCORM Cloud, immettere le informazioni sul server insieme all&#39;ID client e al segreto client dell&#39;applicazione SCORM Cloud associata. Per Adobe Learning Manager, fornire i dettagli del server e dell&#39;autenticazione corrispondenti necessari per l&#39;ambiente ALM.

![](assets/configure-publish-profiles.png){width="350"}
