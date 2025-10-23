---
title: Funzioni aggiuntive nell’editor
description: Esplora altre funzioni dell’editor in Adobe Experience Manager Guides. Scopri come utilizzare queste funzioni per migliorare l’authoring in Experience Manager Guides.
exl-id: 1833b1e3-c7f1-4f2c-be35-235b65ba2f36
feature: Authoring, Web Editor
role: User
source-git-commit: fd4612037581d1d554c9dc144b998ba8a2ab8ccf
workflow-type: tm+mt
source-wordcount: '2652'
ht-degree: 0%

---

# Funzioni aggiuntive nell’editor {#id2056B0B0YPF}

Nell’editor sono disponibili alcune altre funzioni utili che puoi utilizzare:

## Funzioni del menu di scelta rapida nella scheda di un file

Quando apri un file nell’editor, puoi eseguire varie azioni dal menu di scelta rapida. È possibile visualizzare opzioni diverse a seconda che si apra un file multimediale, un singolo file DITA o più file.

**File multimediale**

Nel menu di scelta rapida della scheda di un file multimediale aperto vengono visualizzate le seguenti funzioni:

![](images/media-file-context-menu.png){width="300" align="left"}


**File DITA singolo**

Nel menu di scelta rapida della scheda di un file aperto vengono visualizzate le seguenti funzioni:

![](images/single-file-context-menu.png){width="400" align="left"}

**Più file**

Quando sono aperti più file, nel menu di scelta rapida vengono visualizzate altre opzioni:

![](images/multiple-files-context-menu.png){width="550" align="left"}

Di seguito sono illustrate le varie opzioni del menu di scelta rapida:

***Salva***: puoi scegliere tra le seguenti opzioni:

- **Salva**: per salvare un file senza creare una nuova versione, selezionare **Salva**. Ogni volta che crei un nuovo argomento, in DAM viene creata una copia di lavoro senza versione dell’argomento. Il salvataggio del documento aggiorna la copia di lavoro del documento in DAM. Se si esegue un semplice salvataggio su questa versione, non viene creata una nuova versione di un argomento. Se l&#39;argomento è in revisione, il salvataggio di un argomento non consente ai revisori di accedere al contenuto dell&#39;argomento modificato.

- **Salva tutto**: se nell&#39;editor sono presenti più documenti aperti, è disponibile anche un&#39;opzione per **Salva tutti** i documenti aperti.


***Salva come nuova versione***

Per creare una nuova versione del file, selezionare **Salva come nuova versione**. Per ulteriori dettagli su **Salva** e **Salva come nuova versione**, visualizza [Barra degli strumenti nell&#39;editor](web-editor-toolbar.md).

***Copia***: puoi scegliere tra le seguenti opzioni:

- **Copia UUID**: per copiare negli Appunti l&#39;UUID del file attualmente attivo, selezionare **Copia \> Copia UUID**.
- **Copia percorso**: per copiare negli Appunti il percorso completo del file attualmente attivo, selezionare **Copia \> Copia percorso**.


***Individua in***: è possibile scegliere tra le opzioni seguenti:

- **Mappa**: se hai aperto una mappa DITA di grandi dimensioni e desideri trovare la posizione esatta di un file nella mappa, seleziona **Individua in \> Mappa**. Quando si seleziona l&#39;opzione Individua nella mappa, il file \(da cui viene richiamata l&#39;opzione\) viene posizionato ed evidenziato nella gerarchia della mappa. Per poter utilizzare questa funzione, è necessario aprire il file di mappa nell&#39;editor. Se la vista mappa è nascosta, quando si richiama questa funzione viene visualizzata la vista mappa e il file viene evidenziato nella gerarchia delle mappe.

- **Archivio**: simile a Individua in mappa, **Individua in \> Archivio** mostra la posizione del file nel repository \(o DAM\). Viene aperta la vista Archivio e il file selezionato viene evidenziato nel repository. Se il file si trova all&#39;interno di una cartella, quest&#39;ultima viene espansa per mostrare la posizione del file selezionato nel repository.


***Aggiungi a***: puoi scegliere tra le seguenti opzioni:

- **Raccolte**: per aggiungere il file selezionato alle raccolte, selezionare **Aggiungi a \> Raccolte**. Per ulteriori dettagli, visualizza la descrizione della funzione **Raccolte** nella sezione [Pannello sinistro](web-editor-left-panel.md).

- **Contenuto riutilizzabile**: per copiare il file selezionato nell&#39;elenco dei contenuti riutilizzabili, selezionare **Aggiungi a \> Contenuto riutilizzabile**. Per ulteriori dettagli, visualizzare la descrizione della funzionalità **Contenuto riutilizzabile** nella sezione [Pannello sinistro](web-editor-left-panel.md).

***Proprietà***

Per visualizzare la pagina delle proprietà di AEM del file selezionato, selezionare **Proprietà**.

***Dividi***: puoi scegliere tra le seguenti opzioni:

**Su, Giù, Sinistra o Destra**

Per impostazione predefinita, l&#39;editor consente di visualizzare un argomento alla volta. In alcuni casi potrebbe essere utile visualizzare due o più argomenti contemporaneamente. La suddivisione della schermata dell&#39;editor consente di visualizzare più argomenti contemporaneamente. Ad esempio, se hai due argomenti: A e B aperti nell’editor. Facendo clic con il pulsante destro del mouse sull&#39;argomento B e scegliendo **Dividi \> Su**, la finestra dell&#39;editor viene divisa in due parti. L&#39;argomento B viene visualizzato nella metà superiore e l&#39;argomento A nella metà inferiore. Allo stesso modo, è possibile dividere lo schermo orizzontalmente selezionando **Dividi \> Sinistra** o **Dividi \> Destra**. È possibile spostare i documenti da una schermata all&#39;altra trascinando la scheda del file e rilasciandola sulla schermata in cui si desidera posizionarla. Analogamente, è possibile riordinare le schede dei file trascinandole e spostandole in base alle proprie preferenze.



<!--------------------------------------------

***Quick Generate***

Generate the output for the selected file. Output can be generated only for files that are a part of an output preset. For more details, view [Article-based publishing from the Web Editor](web-editor-article-publishing.md#id218CK0U019I).

--->

***Chiudi***: è possibile scegliere tra le opzioni seguenti:

**Chiudi**, **Chiudi altri** o **Chiudi tutti**

Se si desidera chiudere il file da cui è stato richiamato il menu di scelta rapida, selezionare **Chiudi \> Chiudi**. Utilizzare **Chiudi \> Chiudi gli altri** per chiudere tutti gli altri file aperti ad eccezione del file attivo. Per chiudere tutti i file aperti, selezionare l&#39;opzione **Chiudi \> Chiudi tutti** dal menu di scelta rapida oppure è possibile scegliere di chiudere l&#39;editor. Se nella sessione sono presenti file non salvati, viene richiesto di salvarli.

**Scenari di chiusura e salvataggio dei file**

Quando si tenta di chiudere un file aperto nell&#39;editor utilizzando il pulsante **Chiudi** nella scheda del file o l&#39;opzione **Chiudi** nel menu Opzioni, Experience Manager Guides richiede di salvare le modifiche e sbloccare un file bloccato.

Le richieste di conferma si basano sulle seguenti configurazioni selezionate dall’amministratore:

- **Richiedi sblocco alla chiusura:** È possibile sbloccare il file \(che è stato bloccato\) alla chiusura dell&#39;editor.
- **Richiedi nuova versione alla chiusura**: è possibile salvare il file \(che è stato modificato\) come nuova versione alla chiusura dell&#39;editor.

L’esperienza di salvataggio dei file dipenderà dai tre scenari seguenti, in cui disponi di:

- Nessuna modifica apportata al contenuto.
- Ha modificato il contenuto e ha salvato le modifiche.
- Ha modificato il contenuto ma non ha salvato le modifiche.

A seconda che il file sia bloccato o sbloccato e che siano presenti modifiche salvate o non salvate, è possibile visualizzare le seguenti opzioni:

- **Sblocca e chiudi**: il blocco sul file viene rilasciato e il file viene chiuso.
- **Salva come nuova versione**: verranno salvate le modifiche apportate al contenuto e verrà creata una nuova versione del file. Puoi anche aggiungere etichette e commenti per la nuova versione salvata. Per ulteriori informazioni sul salvataggio di una nuova versione, visualizzare [Salva come nuova versione](web-editor-toolbar.md#version-information-and-save-as-new-version).

- **Sblocca il file**: se si sceglie di sbloccare un file, il blocco verrà rilasciato sul file e le modifiche verranno salvate nella versione corrente del file.

  >[!NOTE]
  >
  > Se si deseleziona l&#39;opzione per sbloccare il file, si ottiene anche un&#39;opzione per chiudere il file senza salvare le modifiche.

  Ad esempio, nella schermata seguente viene visualizzato uno dei prompt:

  ![](images/file-close-save-changes-unlock.png){width="400" align="left"}

**Indicazioni visive per riferimenti interrotti**

Se l&#39;argomento contiene riferimenti incrociati o riferimenti a contenuti interrotti, questi vengono visualizzati in rosso.

**Copia e incolla avanzati**

Puoi copiare e incollare facilmente contenuti all’interno e tra gli argomenti. La struttura dell’elemento sorgente viene mantenuta nella destinazione. Inoltre, se il contenuto copiato contiene riferimenti al contenuto, anche questi vengono copiati.

**Ricorda ultima posizione esplorata**

L’editor fornisce una finestra di dialogo per la ricerca intelligente dei file. L’editor ricorda l’ultima posizione utilizzata durante l’inserimento di un riferimento o di un contenuto. La prima volta che si richiama la finestra di dialogo Sfoglia file \(mediante Inserisci riferimento o Inserisci contenuto riutilizzo\), si viene portati nel percorso in cui viene salvato il documento corrente. Nella stessa sessione, se si tenta di inserire un altro riferimento, la finestra di dialogo Sfoglia file passa automaticamente alla posizione da cui è stato inserito l&#39;ultimo riferimento.

>[!NOTE]
>
> In caso di file immagine, audio o video, la finestra di dialogo per la ricerca dei file viene impostata automaticamente sul percorso del file e non sull’ultimo percorso utilizzato.

## Supporto per la pubblicazione basata su articoli

Dall&#39;editor è possibile generare l&#39;output per uno o più argomenti o per l&#39;intera mappa DITA. È necessario creare predefiniti di output per la mappa DITA e quindi generare facilmente l&#39;output per uno o più argomenti. Se hai aggiornato alcuni argomenti nella mappa, puoi anche generare l’output solo per tali argomenti dall’Editor. Per ulteriori dettagli, visualizzare [Pubblicazione basata su articolo](web-editor-article-publishing.md#id218CK0U019I).

## Supporto per i documenti Markdown

L&#39;editor consente di utilizzare i documenti Markdown \(.md\) insieme ai documenti DITA. È possibile creare e visualizzare in anteprima un documento Markdown nell&#39;Editor e aggiungerlo nel file di mappa tramite l&#39;editor di mappe DITA. Per ulteriori dettagli, visualizzare [Documenti Markdown dell&#39;autore dall&#39;editor](web-editor-markdown-topic.md#).

## Supporto per l&#39;argomento termine del glossario DITA

L&#39;editor supporta i termini del glossario DITA che è possibile inserire aggiungendo `term` o `abbreviated-form` elementi.

## Utilizzare le equazioni di MathML

### Inserisci equazioni MathML

Experience Manager Guides offre un supporto predefinito per l&#39;inserimento di equazioni di MathML tramite l&#39;integrazione con l&#39;applicazione [MathType Web](https://docs.wiris.com/en/mathtype/mathtype_web/intro). Per inserire un&#39;equazione di MathML, selezionare l&#39;icona **Elemento** e digitare mathml. Quando si seleziona l&#39;elemento matml dall&#39;elenco, viene visualizzata la finestra di dialogo **Inserisci MathML**:

![inserire l&#39;equazione mathml nell&#39;editor mathml](images/insert-mathml-equation.png){width="550" align="left"}

Utilizzando gli strumenti di equazione di MathML, crea l&#39;equazione e seleziona **Inserisci** per aggiungerla al documento. L&#39;equazione viene inserita con uno sfondo grigio chiaro.

In qualsiasi momento è possibile aggiornare un&#39;equazione facendo clic con il pulsante destro del mouse su un&#39;equazione esistente e selezionando **Modifica MathML** dal menu di scelta rapida.

### Convalida delle equazioni nell’editor di MathML

Experience Manager Guides convalida le equazioni di MathML quando si salva un argomento che le contiene.
Quando si inserisce un&#39;equazione utilizzando l&#39;editor di MathML, in caso di problemi di sintassi Experience Manager Guides evidenzia l&#39;equazione in rosso. È possibile correggerla prima di inserirla. Se non si apportano modifiche ma si seleziona **Inserisci**, verrà visualizzato un avviso.

![convalida equazione matematica](images/validate-mathml-equation.png){width="400" align="left"}

Se si inserisce l&#39;equazione di MathML che contiene un errore di sintassi, quando si tenta di salvare l&#39;argomento si verifica un errore di convalida.


## Inserisci note a piè di pagina

Inserire una nota a piè di pagina nel contenuto utilizzando l&#39;elemento `fn`. Nella modalità di creazione, il valore della nota a piè di pagina viene visualizzato in linea con il contenuto. Tuttavia, quando si passa alla modalità Anteprima o si pubblica il documento, la nota a piè di pagina viene visualizzata alla fine dell&#39;argomento.


## Rinominare o sostituire un elemento

L’editor visualizza la breadcrumb dell’elemento in basso a sinistra nell’argomento. Se desideri scambiare o sostituire un elemento con un altro elemento, puoi farlo dal menu di scelta rapida della breadcrumb. Ad esempio, è possibile scambiare l&#39;elemento `p` con `note` o qualsiasi altro elemento valido nel contesto.

![](images/rename-element.png){width="400" align="left"}

Nella breadcrumb, fai clic con il pulsante destro del mouse sul nome di un elemento che desideri sostituire, quindi seleziona Rinomina elemento dal menu di scelta rapida. Nella finestra di dialogo Rinomina elemento vengono visualizzati tutti gli elementi validi consentiti nella posizione corrente. Dalla finestra di dialogo Rinomina elemento, seleziona l’elemento che desideri utilizzare. L’elemento originale viene sostituito con il nuovo elemento.

Oltre al menu di scelta rapida della breadcrumb, è possibile accedere alla finestra di dialogo Rinomina elemento da altre posizioni:

- Seleziona il nome dell’elemento nella breadcrumb per selezionare il contenuto dell’elemento, quindi fai clic con il pulsante destro del mouse sul contenuto selezionato per visualizzare il menu di scelta rapida.

- Abilita la visualizzazione Tag, seleziona il tag di apertura di qualsiasi elemento, quindi fai clic con il pulsante destro del mouse sul contenuto selezionato per visualizzare il menu di scelta rapida.

- Potete accedere alla finestra di dialogo Rinomina elemento (Rename Element) richiamando il menu Opzioni (Options) di un elemento nel pannello Struttura.

## Ritorno a capo e apertura di un elemento

### Racchiudi un elemento

- La disposizione di un elemento consente di aggiungere un tag elemento al testo selezionato. È possibile racchiudere il testo in qualsiasi elemento figlio seguendo gli standard DITA. Ad esempio, se il testo si trova sotto un elemento `note`, è possibile racchiuderlo in un elemento `p`.

- L&#39;opzione **Wrap Element** è disponibile nel menu di scelta rapida della breadcrumb dell&#39;argomento. Per racchiudere un elemento, fai clic con il pulsante destro del mouse sull’elemento e apri il menu di scelta rapida. Selezionare l&#39;elemento dalla finestra di dialogo **Elemento a capo**. Il testo viene visualizzato nel nuovo elemento.

- È inoltre possibile selezionare il testo o l&#39;elemento nel contenuto e quindi selezionare l&#39;opzione **Elemento a capo** dal menu di scelta rapida.

### Annullare il wrapping di un elemento

L’apertura di un elemento consente di rimuovere il tag elemento dal testo selezionato e di unirlo al relativo elemento padre. Se ad esempio si dispone di un elemento `p` all&#39;interno di un elemento `note`, è possibile annullare il wrapping dell&#39;elemento `p` per unire il testo direttamente all&#39;interno dell&#39;elemento `note`. L&#39;opzione **Annulla wrapping elemento** è disponibile nel menu di scelta rapida della breadcrumb dell&#39;argomento. Per annullare il wrapping di un elemento, fare clic con il pulsante destro del mouse sull&#39;elemento per aprire il menu di scelta rapida, quindi selezionare **Annulla wrapping elemento** per rimuovere l&#39;elemento e unire il testo dell&#39;elemento con l&#39;elemento padre.

## Gestione degli spazi vuoti per gli elementi DITA

In XML, gli spazi vuoti includono spazi, tabulazioni, ritorni a capo e righe vuote. Experience Manager Guides converte più spazi vuoti conseguenti in un unico spazio. In questo modo è possibile mantenere la visualizzazione WYSIWYG dell’editor.

>[!NOTE]
>
> In alcuni elementi in cui gli spazi bianchi devono essere conservati secondo le regole DITA, vengono mantenuti i molteplici spazi bianchi conseguenti. Ad esempio, `<pre>` e `<codeblock>` elementi.


## Mantenimento delle interruzioni di riga e del rientro

Gli elementi DITA che contengono interruzioni di riga e spazi sono supportati e renderizzati in base alla loro definizione nelle modalità Autore, Source o Anteprima e anche nell’output finale pubblicato. La schermata seguente mostra il contenuto all&#39;interno dell&#39;elemento `msgblock` in cui sono stati mantenuti le interruzioni di riga e gli spazi \(rientro\):

![](images/new-line-support_cs.png){align="left"}



## Gestione degli spazi unificatori nell’editor

- È possibile inserire spazi unificatori nel documento utilizzando l&#39;icona **Simbolo** ![](images/symbol-icon.svg) o i tasti di scelta rapida **Alt** + **Spazio**.  Questi spazi unificatori vengono visualizzati come indicatori quando si modifica un argomento nell&#39;Editor. È possibile disattivare la visualizzazione degli spazi unificatori con l&#39;opzione **Mostra indicatore di spazio unificatore in modalità di creazione** dalla scheda **Aspetto** di [Preferenze utente](./intro-home-page.md#user-preferences).

- Se si copia e si incolla contenuto con uno spazio unificatore da qualsiasi origine esterna nella visualizzazione **Autore**, lo spazio unificatore viene convertito in uno spazio.
Tuttavia, se copi e incolla contenuto con uno spazio unificatore dalla visualizzazione **Autore**, questo verrà mantenuto.


## Genera automaticamente ID elemento

È possibile generare automaticamente gli ID per gli elementi nell&#39;argomento DITA. Questi ID sono univoci in un argomento DITA. Ad esempio, se generi ID per un elemento paragrafo, gli ID saranno p\_1, p2, p\_3 e così via. Puoi selezionare più elementi e generare ID per ciascun elemento selezionato.

Per generare automaticamente l’ID per uno o più elementi, effettua le seguenti operazioni:

1. Apri l’argomento nell’editor.
1. Seleziona il contenuto a cui assegnare gli ID.
1. Fare clic con il pulsante destro del mouse e selezionare **Genera ID** dal menu di scelta rapida.

In alternativa, puoi fare clic con il pulsante destro del mouse nella breadcrumb e selezionare **Genera ID**.

## Identificazione di ID duplicati per gli elementi di una mappa o di un argomento nella vista Creazione

Se un argomento o una mappa specifica contiene elementi con ID duplicati, nell&#39;angolo inferiore destro dell&#39;area di modifica del contenuto adiacente alle visualizzazioni dell&#39;editor viene visualizzato un pulsante **ID duplicati**.

![](images/duplicate-element-IDs.png){width="350" align="left"}

Selezionando **ID duplicati** si apre un popover in cui sono elencati tutti gli ID duplicati. Puoi selezionare l’ID visualizzato dal popover per passare all’elemento corrispondente e aggiornarlo con un ID univoco.

>[!NOTE]
>
> Il pulsante **ID duplicati** è disponibile solo nella visualizzazione **Autore** e ID di elementi simili sono consentiti in diversi argomenti nidificati.


## Gestione di file di grandi dimensioni nell’editor

Di seguito sono indicate le principali caratteristiche volte a migliorare la gestione dei file di grandi dimensioni:

- Per migliorare le prestazioni, alcune funzionalità come Annulla, Ripristina, il pannello della struttura e il marcatore sporco sono disabilitate. Per un’esperienza ottimale, si consiglia di suddividere gli argomenti in argomenti più piccoli.

- Nella parte superiore viene visualizzato un messaggio di avviso per i file di grandi dimensioni, come illustrato nel frammento seguente. Questo avviso evidenzia il numero di elementi in base al valore specificato nel parametro **largeFileTagCount** del file uiconfig.json. Per impostazione predefinita, **largeFileTagCount** è impostato su 2500.

![](images/add-toast-notification.png){width="600" align="left"}


- Inoltre, il conteggio dei tag viene visualizzato sulla barra inferiore dell’interfaccia. Quando passi il cursore del mouse sul valore del conteggio dei tag, viene visualizzata una descrizione comando. La selezione della scheda **Ulteriori informazioni** fornisce dettagli sulla gestione dei file di grandi dimensioni.

![](images/add-toast-tag-count.png){width="600" align="left"}


- Il messaggio di avviso è disponibile solo per i file DITA ed è visibile in tutte le visualizzazioni: Autore, Source e Layout.

**Argomento padre:**&#x200B;[&#x200B; Introduzione all&#39;editor](web-editor.md)
