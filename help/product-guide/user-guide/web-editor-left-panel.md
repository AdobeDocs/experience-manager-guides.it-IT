---
title: Pannello sinistro nell’editor
description: Scopri il pannello a sinistra nell’editor. Scopri l’interfaccia e le funzioni dell’editor in Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
exl-id: 92496d39-b423-4635-8b05-c67fd6af47de
source-git-commit: f0ba8dce38a6eef5dedc8a81107c8e31ea6b26b3
workflow-type: tm+mt
source-wordcount: '10929'
ht-degree: 0%

---

# Pannello sinistro nell’editor

Il pannello a sinistra consente di accedere rapidamente alle raccolte, alla vista Archivio, alla vista Mappa e ad altre funzioni. Puoi espandere il pannello selezionando l&#39;icona **Espandi** posta nell&#39;angolo inferiore sinistro dell&#39;interfaccia. Una volta espanso, utilizza l&#39;icona **Comprimi** per comprimere il pannello. Nella visualizzazione espansa vengono visualizzati i nomi delle icone visualizzate come descrizioni comandi nella visualizzazione compressa.

>[!NOTE]
>
>Il pannello sinistro è ridimensionabile. Per ridimensionare il pannello, posiziona il cursore sul bordo del pannello. Il cursore si trasforma in una freccia a due punte, seleziona e trascina per ridimensionare la larghezza del pannello.

Il pannello sinistro consente di accedere alle seguenti funzioni:

- [Raccolte](#collections)
- [Archivio](#repository)
- [Explorer](#explorer)
- [Mappa](#map)
- [Contenuto riutilizzabile](#reusable-content)
- [Struttura](#outline)

Alcune delle funzionalità nel pannello a sinistra sono disponibili nella sezione **Altro**. Selezionare l&#39;icona Altro ![](images/Smock_MoreSmallList_18_N.svg) per accedere alle funzionalità seguenti:

- [Glossario](#glossary)
- [Condizioni](#conditions)
- [Schema soggetto](#subject-scheme)
- [Snippet](#snippets)
- [Modelli](#templates)
- [Citazioni](#citations)
- [Variabili di lingua](#language-variables)
- [Variabili](#variables)
- [Trova e sostituisci](#find-and-replace)
- [Modelli PDF](#pdf-templates)
- [Rivedere](#review)


Nel pannello a sinistra viene visualizzata anche un&#39;opzione aggiuntiva etichettata come **Workfront**, se Adobe Workfront è configurato.

Per ulteriori dettagli, visualizzare [Integrazione Workfront](./workfront-integration.md).

>[!NOTE]
>
> Le funzioni disponibili nel pannello a sinistra vengono gestite dall’amministratore, consentendo loro di abilitare o disabilitare le singole funzioni presenti nel pannello a sinistra. Nel pannello a sinistra vengono visualizzate solo le feature abilitate. Per ulteriori dettagli, visualizzare la sezione **Panels** di [Tab bar](./web-editor-tab-bar.md).

La spiegazione dettagliata delle funzioni del pannello sinistro è la seguente:

## Raccolte

Se si lavora su un insieme di file o cartelle, è possibile aggiungerli all&#39;elenco dei preferiti per accedervi rapidamente. **Le raccolte** mostrano l&#39;elenco dei documenti aggiunti e altri elenchi di documenti accessibili al pubblico degli altri utenti.

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

<details>
    <summary> Crea una nuova raccolta </summary>


Per creare una nuova raccolta, seleziona l&#39;icona + accanto al pannello Raccolte per visualizzare la finestra di dialogo **Nuova raccolta**:

![](images/favorite-new-collection.PNG){width="300" align="left"}

Immetti un titolo e una descrizione per la raccolta da creare. Se selezioni **Pubblico**, questo preferito verrà mostrato anche ad altri utenti.

>[!NOTE]
>
> Puoi anche creare una raccolta dalla home page di Experience Manager Guides. Apri la home page, passa al widget **Raccolte** nella [sezione Panoramica](./intro-home-page.md#overview) e seleziona **Nuova raccolta**.

</details>

<details>
    <summary> Aggiungere un file alle raccolte </summary>


Per aggiungere un file alle raccolte, utilizzare uno dei metodi seguenti:

- Passa al file o alla cartella richiesti nella vista Archivio, seleziona l&#39;icona *Opzioni* per aprire il menu di scelta rapida e scegli **Aggiungi a** > **Raccolte**. Nella finestra di dialogo **Aggiungi a raccolte** puoi scegliere di aggiungere il file o la cartella a un preferito esistente o crearne uno nuovo.

  ![](images/favorite-add-file-folder.png){width="300" align="left"}

- Fai clic con il pulsante destro del mouse sulla scheda di un file nell’editor per aprire il menu di scelta rapida. Scegli **Aggiungi a** > **Raccolte** per aggiungere il file all&#39;elenco dei preferiti.

  ![](images/favorite-add-from-file-context-menu_cs.png){align="left"}


>[!NOTE]
>
> - Per rimuovere un elemento dall&#39;elenco dei preferiti, selezionare l&#39;icona Opzioni accanto all&#39;elemento in una raccolta Preferiti e scegliere **Rimuovi da raccolte**.
> - Per visualizzare l&#39;anteprima del file senza aprirlo, selezionare un file e quindi **Anteprima** dal menu Opzioni.

</details>

**Menu Opzioni per una raccolta**

Puoi anche eseguire molte azioni utilizzando il menu Opzioni disponibile per una raccolta:

![](images/favorites-options.png){width="650" align="left"}

- **Rinomina**: rinomina la raccolta selezionata.
- **Elimina**: elimina la raccolta selezionata.
- **Aggiorna**: ottieni un nuovo elenco di file e cartelle dall&#39;archivio.
- **Visualizza nell&#39;interfaccia utente di Assets**: visualizza il contenuto del file o della cartella nell&#39;interfaccia utente di Assets.

>[!NOTE]
>
> Puoi aggiornare l&#39;elenco utilizzando l&#39;icona **Aggiorna** nella parte superiore. Inoltre, l’aggiornamento dell’elenco ricarica le raccolte e, di conseguenza, tutte le raccolte espanse nel pannello vengono compresse.


## Archivio

>[!NOTE]
>
> A partire dalla versione 2025.11.0, **L&#39;archivio** nell&#39;editor diventerà obsoleto e verrà sostituito da **Explorer** per l&#39;installazione di **Cloud Service**. Per la configurazione di **On-Premise**, continuerai a visualizzare e utilizzare l&#39;archivio tramite l&#39;interfaccia dell&#39;editor fino alla versione 5.1 di Experience Manager Guides.

Quando selezioni l’icona Archivio, ottieni un elenco di file e cartelle disponibili in DAM. Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il cursore del mouse su un file, potete visualizzare il titolo e il nome del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

Vengono caricati 75 file alla volta. Ogni volta che si seleziona **Carica altri**... vengono caricati 75 file e il pulsante non viene più visualizzato quando tutti i file sono elencati. Questo caricamento batch è efficiente e consente di accedere ai file più rapidamente rispetto al caricamento di tutti i file esistenti in una cartella.

Puoi passare facilmente al file richiesto all’interno di DAM e aprirlo nell’editor. Se si dispone dell&#39;accesso necessario per modificare il file, è possibile eseguire questa operazione.

È inoltre possibile selezionare e riprodurre un file audio o video nell&#39;editor. È possibile modificare il volume o
la visualizzazione del video. Nel menu di scelta rapida sono inoltre disponibili le opzioni per il download, la modifica della riproduzione
o di visualizzare immagini nell&#39;immagine.

Selezionare una mappa e premere Invio o fare doppio clic per aprirla nella **vista mappa**. Per ulteriori dettagli, visualizza la descrizione della funzione **Vista mappa** nel pannello a sinistra. Selezionare un argomento e premere Invio o fare doppio clic per aprirlo nell&#39;[area di modifica dei contenuti](./web-editor-content-editing-area.md). La possibilità di navigare e aprire un file direttamente dall’editor consente di risparmiare tempo e di aumentare la produttività.

## Filtra ricerca nel repository

L’editor fornisce filtri migliorati per la ricerca di testo. È possibile cercare e filtrare un testo nei file presenti nel percorso selezionato dell&#39;archivio Adobe Experience Manager. La ricerca viene eseguita nel titolo, nel nome del file e nel contenuto dei file.


![cerca i file nella vista archivio](images/repository-filter-search.png){width="300" align="left"}

*Applicare i filtri per cercare i file contenenti il testo`personal spaceship.`*

Seleziona l&#39;icona **Ricerca filtro** \(![Icona filtro di ricerca](images/filter-search-icon.svg)\) per aprire il popup Filtro.

>[!NOTE]
>
> Quando si esegue una ricerca in un testo o si filtra un file, sull&#39;icona \(**Icona filtro di ricerca**\) di ![Ricerca filtro](images/filter-search-icon.svg) viene visualizzato un punto blu per indicare che si trova nel pannello di ricerca e che sono stati applicati alcuni filtri.


Per filtrare i file e limitare la ricerca nell’archivio Adobe Experience Manager, sono disponibili le seguenti opzioni:

- **File DITA**: è possibile cercare tutti i **argomenti DITA** e le **mappe DITA** presenti nel percorso selezionato. Questi sono selezionati per impostazione predefinita.
- **File non DITA**: è possibile cercare **File Ditaval**, **File immagine**, **File multimediali**, **Documenti** e **JSON** nel percorso selezionato.

  ![filtro di ricerca rapida ](images/repository-filter-search-quick.png) {width="300" align="left"}

  *Utilizza i filtri rapidi per cercare file DITA e non DITA.*

>[!NOTE]
>
> È inoltre possibile utilizzare il filtro **Argomento DITA** per cercare contenuto specifico per i file Markdown nel repository, inclusi titoli, contenuto argomento e proprietà. Questa funzione si applica attualmente solo ai file Markdown appena creati.

**Filtro avanzato**

Seleziona l&#39;icona **Filtro avanzato** ![icona filtro avanzato](images/advanced-filter-gear-icon.svg)per visualizzare la finestra di dialogo **Filtro avanzato**.

Puoi visualizzare le seguenti opzioni nelle schede **Generale** e **Avanzate**.

![finestra di dialogo filtro avanzato](images/repository-filter-search-advanced.png) {width="650" align="left"}


**Generale**

- **Risultati della ricerca con**: cercare del testo nei file presenti nel percorso selezionato dell&#39;archivio Adobe Experience Manager. La ricerca viene eseguita nel titolo, nel nome del file e nel contenuto dei file.

È sincronizzato con la casella di ricerca nella finestra del repository. Se ad esempio si digita `general purpose` nella casella di ricerca nel pannello del repository, verrà visualizzato anche nella finestra di dialogo **Filtro avanzato** e viceversa.

- **Cerca in**: selezionare il percorso in cui si desidera eseguire la ricerca nei file presenti nell&#39;archivio di Adobe Experience Manager.
- **File DITA**: è possibile cercare tutti i **argomenti DITA** e le **mappe DITA** presenti nel percorso selezionato. Questi sono selezionati per impostazione predefinita.
- **File non DITA**: è possibile cercare **File Ditaval**, **File immagine**, **File multimediali**, **Documenti** e **JSON** nel percorso selezionato.
- **Bloccato da**: visualizza un elenco di utenti. L’elenco viene impaginato e caricato in modo asincrono, mostrando un set limitato di utenti alla volta e recuperandone altri durante lo scorrimento o la navigazione. Ciò migliora la velocità di caricamento e le prestazioni complessive, soprattutto quando si lavora con un numero elevato di utenti.
- **Modificato dopo** / **Modificato prima di**: filtra il contenuto in base alla data di modifica. Seleziona un intervallo di date dal calendario o scegli una delle seguenti opzioni per l’intervallo di tempo:
   - Nelle ultime due ore
   - Nell&#39;ultima settimana
   - Nell&#39;ultimo mese
   - Nell&#39;ultimo anno
- **Tag**: filtra il contenuto in base ai tag.

**Avanzate**

- **Elementi DITA**: è inoltre possibile cercare valori specifici negli attributi degli elementi DITA specificati.
   - Selezionare **Aggiungi elemento** per aggiungere elementi, attributi e valori.
   - Applica i filtri selezionati.

- Selezionare **Cancella tutto** per cancellare tutti i filtri applicati.


- Seleziona l&#39;icona **Chiudi filtro** ![Chiudi icona](images/close-icon.svg) per chiudere il filtro e tornare alla visualizzazione struttura dell&#39;archivio.

  >[!NOTE]
  >
  >L’amministratore di sistema può anche configurare i filtri di testo e mostrare o nascondere altri filtri. Per ulteriori dettagli, visualizzare la sezione *Configurare i filtri di testo* nella sezione Installare e configurare Adobe Experience Manager Guides as a Cloud Service.
  >
  >Viene visualizzato l’elenco dei file filtrati che contengono il testo cercato. I file contenenti il testo `personal spaceship` sono elencati nella schermata precedente. È possibile selezionare più file dall&#39;elenco filtrato per trascinarli in una mappa aperta per la modifica.

### Menu Opzioni

Oltre ad aprire i file dal pannello di sinistra, è possibile eseguire molte azioni utilizzando il menu Opzioni disponibile nella vista Archivio. Verranno visualizzate opzioni diverse, a seconda che si scelga una cartella, un file argomento o un file multimediale.

**Opzioni per una cartella**

Puoi eseguire le seguenti azioni utilizzando il menu Opzioni disponibile per una *cartella* nella vista Archivio:

![](images/options-menu-folder_cs.PNG){width="550" align="left"}


- **Nuovo**: creare un nuovo argomento DITA, una mappa DITA o una cartella.

<details>
    <summary> Passaggi per creare un nuovo argomento </summary>

Passaggi per creare un nuovo argomento:

1. Seleziona **Nuovo** > **Argomento**.
1. Viene visualizzata la finestra di dialogo **Nuovo argomento**.

   ![](images/create-topic-dialog.png){width="300" align="left"}

1. Nella finestra di dialogo **Nuovo argomento**, fornisci i seguenti dettagli:
   - Titolo per l&#39;argomento.
   - \(Facoltativo\)* Nome file dell&#39;argomento. Il nome del file viene suggerito automaticamente in base al Titolo dell’argomento. Se l’amministratore ha abilitato i nomi di file automatici in base all’impostazione UUID, il campo Nome non verrà visualizzato.
   - Modello su cui verrà basato l&#39;argomento. Ad esempio, per una configurazione predefinita, puoi scegliere tra i modelli Vuoto, Concetto, DITAVAL, Riferimento, Attività, Argomento, Markdown, Glossario e Risoluzione dei problemi. Se nella cartella è configurato un profilo di cartella, verranno visualizzati solo i modelli di argomento configurati nel profilo di cartella.

   - Percorso in cui salvare il file dell&#39;argomento. Per impostazione predefinita, il percorso della cartella attualmente selezionata nell’archivio viene visualizzato nel campo Percorso.
1. Seleziona **Crea**. L&#39;argomento viene creato nel percorso specificato. Inoltre, l’argomento viene aperto nell’Editor per la modifica.

</details>

<details>
<summary> Passaggi per creare una nuova mappa DITA </summary>


Passaggi per creare una nuova mappa DITA:

1. Selezionare **Nuovo** > **Mappa DITA**.
2. Viene visualizzata la finestra di dialogo **Nuova mappa**.

   ![](images/create-map-dialog.png){width="300" align="left"}

3. Nella finestra di dialogo **Nuova mappa**, fornisci i seguenti dettagli:
   - Un Titolo per la mappa.
   - *\(Facoltativo\)* Il nome file per la mappa. Il nome del file viene suggerito automaticamente in base al titolo della mappa. Se l’amministratore ha abilitato i nomi di file automatici in base all’impostazione UUID, il campo Nome non verrà visualizzato.
   - Modello su cui verrà basata la mappa. Ad esempio, per un&#39;impostazione predefinita, è possibile scegliere tra i modelli di mappe di Bookmap o di mappe DITA.
   - Percorso in cui si desidera salvare il file mappa. Per impostazione predefinita, il percorso della cartella attualmente selezionata nell’archivio viene visualizzato nel campo Percorso.
4. Seleziona **Crea**. La mappa viene creata e aggiunta all’interno della cartella specificata nel campo Percorso. Inoltre, la mappa viene aperta nella vista Mappa. Potete aprire il file mappa nell&#39;Editor mappa e aggiungervi un argomento. Per ulteriori informazioni sull&#39;aggiunta di argomenti a un file di mapping, vedere [Creare un mapping](map-editor-create-map.md#). In alternativa, selezionare **Apri nella console delle mappe** per aprire la mappa nella console delle mappe.
</details>

<details>
<summary> Passaggi per creare una nuova cartella </summary>

Passaggi per creare una nuova cartella:

1. Selezionare **Nuovo** > **Cartella**.
2. Viene visualizzata la finestra di dialogo **Nuova cartella**.

   ![](images/new-folder-dialog_cs.png){width="300" align="left"}

3. Nella finestra di dialogo **Nuova cartella**, fornisci i dettagli seguenti:
   - Titolo della cartella, che viene automaticamente convertito nel nome della cartella.
   - Percorso in cui desideri salvare la cartella. Per impostazione predefinita, il percorso della cartella attualmente selezionata nell’archivio viene visualizzato nel campo Percorso.
4. Seleziona **Crea**. La cartella viene creata e aggiunta all’interno della cartella da cui è stata eseguita l’opzione Crea cartella.

</details>

- **Carica risorse**: carica un file dal sistema locale alla cartella selezionata nell&#39;archivio di Adobe Experience Manager. È inoltre possibile trascinare i file dal sistema locale all&#39;argomento di lavoro corrente. Questa funzione è molto utile se si desidera inserire nell&#39;argomento immagini provenienti dal sistema locale.

  ![](images/upload-assets.png){width="300" align="left"}

  Puoi selezionare una cartella in cui desideri caricare il file e visualizzare anche un’anteprima dell’immagine. Se si desidera rinominare il file, è possibile farlo nella casella di testo Nome file. Seleziona **Carica** per completare il processo di caricamento dei file. Se hai trascinato e rilasciato un file di immagine su un argomento, il file di immagine viene aggiunto all’articolo e caricato.

  Se l&#39;amministratore ha abilitato l&#39;opzione UUID in *XMLEditorConfig*, l&#39;UUID dell&#39;immagine caricata verrà visualizzato nella proprietà **Source**.

  ![](images/uuid-in-source-upload-image_cs.png){align="left"}

  Dopo un caricamento riuscito, viene visualizzata la seguente finestra di dialogo di conferma:

  ![](images/upload-successful.png)

  <details>

  <summary>Gestione di caratteri non validi nei nomi dei file</summary>

  Se il nome file della risorsa da caricare contiene caratteri non validi (ad esempio * / : [\] | # % { } ?), possono verificarsi i seguenti scenari:

   - **Caricamento parziale**: indica che una o più risorse caricate contengono caratteri non validi nei nomi dei file.

     ![](images/partial-asset-upload.png)

   - **Caricamento non riuscito**: indica che tutte le risorse caricate contengono caratteri non validi nei nomi dei file.

     ![](images/upload-asset-failed.png)

  Per risolvere questi conflitti, rimuovi eventuali caratteri non validi dai nomi dei file delle risorse, quindi ricaricali nell’archivio.

  </details>

- **Aggiorna**: ottieni un nuovo elenco di file e cartelle dal repository.
- **Comprimi**: comprimi la cartella selezionata nell&#39;archivio.

  >[!NOTE]
  >
  > Utilizza l&#39;icona **\>** accanto a una cartella per espanderla.

- **Trova file nella cartella**: sposta lo stato attivo sulla ricerca del repository in cui è possibile immettere il termine di ricerca. La ricerca viene eseguita nella cartella selezionata nell’archivio. È inoltre possibile applicare un filtro per restituire file DITA, file di immagine o entrambi.

  ![](images/find-files-in-folders-repo-view_cs.png){width="300" align="left"}

  Puoi anche eseguire ricerche utilizzando l’UUID di un file. In tal caso, i risultati della ricerca visualizzano il titolo del file DITA/XML e, nel caso in cui il file sia un file di immagine, viene visualizzato l&#39;UUID del file. Nell’esempio di ricerca seguente viene eseguita la ricerca dell’UUID di un file di immagine e nei risultati vengono visualizzati l’UUID del file di immagine originale e il titolo dell’argomento del file in cui si fa riferimento a tale immagine.

  ![](images/uuid-repo-search-image-topic-file_cs.png){width="300" align="left"}

- **Aggiungi a raccolte**: aggiunge la cartella selezionata ai preferiti. Puoi scegliere di aggiungerlo a una raccolta esistente o nuova.

- **Rielabora risorse**: attiva l&#39;elaborazione di tutte le risorse per la cartella.
- **Visualizza nell&#39;interfaccia utente di Assets**: visualizza il contenuto della cartella nell&#39;interfaccia utente di Assets.

**Opzioni per un file**

Accedere a diverse opzioni del menu Opzioni a seconda che sia stato selezionato un file multimediale o un file DITA. Alcune opzioni comuni disponibili sia per i file multimediali che per i file DITA sono:

- Modifica
- Apri in FrameMaker
- Duplica
- Blocca/sblocca
- Anteprima
- Sposta in
- Rinomina
- Eliminare
- Genera
- Scarica come PDF
- Aggiungi a
- Copia
- Rielabora risorsa
- Visualizza nell’interfaccia di Assets
- Proprietà


![menu opzioni di un file nella vista archivio](images/options-menu-repo-view-file-level.png){width="550" align="left"}

Di seguito sono illustrate le varie opzioni del menu Opzioni:

- **Modifica**: apri il file per la modifica. Nel caso di un file .ditamap/.bookmap, viene aperto nell&#39;[Editor mappe](map-editor-advanced-map-editor.md#) per la modifica.

- **Modifica in ossigeno**: selezionare questa opzione per modificare il file selezionato nel plug-in del connettore di ossigeno. Il file viene aperto per la modifica.

  >[!NOTE]
  >
  >Contatta il team di successo del cliente per abilitare questa funzione nell’ambiente. Questa funzione non è abilitata come parte del supporto predefinito. Per ulteriori dettagli, vedere la sezione [Configurare l&#39;opzione da modificare in Ossigeno](../cs-install-guide/conf-edit-in-oxygen.md) nella Guida all&#39;installazione e alla configurazione.

- **Apri nel dashboard delle mappe**: se il file selezionato è una mappa DITA, questa opzione apre il dashboard delle mappe.

- **Apri nella console delle mappe**: se il file selezionato è una mappa DITA, questa opzione apre la console delle mappe.

- **Blocco**: ottieni un blocco sul file selezionato per la modifica. Se il file è bloccato, posizionando il puntatore del mouse sull&#39;icona del lucchetto viene visualizzato **Bloccato da te** se è stato bloccato oppure **Bloccato da [username]** se è stato bloccato da un altro utente.

- **Anteprima**: consente di ottenere un&#39;anteprima rapida del file (.dita, .xml, audio, video o immagine) senza aprirlo. È possibile ridimensionare il riquadro di anteprima. Se il contenuto contiene `<xref>` o `<conref>`, è possibile selezionarlo per aprirlo in una nuova scheda. Il titolo del file viene visualizzato nella finestra. Se non è presente alcun titolo, viene visualizzato il nome del file. Per chiudere il pannello **Anteprima**, è possibile selezionare l&#39;icona di chiusura o selezionare un punto qualsiasi all&#39;esterno del riquadro.

  ![](images/quick-preview_cs.png){align="left"}


- **Duplicato**: utilizzare questa opzione per creare un duplicato o una copia del file selezionato. Puoi anche rinominare il file duplicato nel prompt Duplica risorsa. Per impostazione predefinita, il file viene creato con il suffisso \(come nomefile\_1.extension\). Il titolo del file rimane invariato rispetto al file di origine e il nuovo file inizia con la versione 1.0. Tutti i riferimenti, i tag e i metadati vengono copiati mentre le baseline non vengono copiate nel file duplicato.

- **Sposta in**: utilizzare questa opzione per spostare il file selezionato in un&#39;altra cartella.
   - È possibile digitare il nome della cartella di destinazione oppure scegliere **Seleziona percorso** per selezionare la cartella di destinazione.
   - È possibile spostare un file di qualsiasi tipo in qualsiasi destinazione all&#39;interno della cartella Contenuto.
   - Due file non possono avere lo stesso nome. Pertanto, non è possibile spostare un file in una cartella in cui esiste già un file con lo stesso nome.

  Se si tenta di spostare un file in una cartella in cui esiste un file con lo stesso nome ma con un titolo diverso, viene visualizzata la finestra di dialogo Rinomina e sposta file e sarà necessario rinominare il file prima di spostarlo. Il file spostato nella cartella di destinazione ha il nuovo nome file.

  ![](images/rename-move-asset.png){width="550" align="left"}

  >[!NOTE]
  >
  > Puoi anche trascinare un file in un’altra cartella di destinazione.

  **Scenari di esclusione**

  Experience Manager Guides non consente di rinominare o spostare un file nei seguenti scenari:

   - Non è possibile spostare o rinominare un file se fa parte di un flusso di lavoro di revisione o di traduzione.

   - Se un altro utente blocca il file, non è possibile rinominarlo o spostarlo, non verrà visualizzata l&#39;opzione Rinomina o Sposta in per il file.

  >[!NOTE]
  >
  > Se l&#39;amministratore ti ha concesso le autorizzazioni per una cartella, verranno visualizzate solo le opzioni **Rinomina** o **Sposta in**.

  <details>
    <summary> Servizi cloud </summary>

  La ridenominazione o lo spostamento di un file non interrompe i riferimenti esistenti da o verso il file, in quanto ogni file ha un UUID univoco.
  </details>

- **Rinomina**: utilizzare questa opzione per rinominare il file selezionato. Immettere il nome del nuovo file nella finestra di dialogo **Rinomina risorsa**.
   - È possibile rinominare un file di qualsiasi tipo.
   - Impossibile modificare l&#39;estensione di un file.
   - Due file non possono avere lo stesso nome. Pertanto, non è possibile rinominare un file con un nome già esistente. Viene visualizzato un errore.

- **Elimina**: utilizzare questa opzione per eliminare il file selezionato. Viene visualizzata una richiesta di conferma prima di eliminare il file.

   - Viene visualizzata una richiesta di conferma prima di eliminare il file.
   - Se non viene fatto riferimento al file da alcun altro file, questo viene eliminato e viene visualizzato un messaggio di operazione riuscita.
   - Se il file è bloccato, non è possibile eliminarlo e viene visualizzato un messaggio di errore.

     >[!NOTE]
     >
     > Se l&#39;amministratore ha impedito l&#39;eliminazione dei file bloccati, viene visualizzato solo il messaggio di errore. Per ulteriori dettagli, visualizzare la sezione *Impedisci l&#39;eliminazione dei file estratti* nella sezione Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

   - Se il file viene aggiunto a una raccolta, viene visualizzata la finestra di dialogo **Forza eliminazione**, che è possibile eliminare forzatamente.
   - Se il file è referenziato da un altro file, viene visualizzata la finestra di dialogo **Forza eliminazione** con il messaggio di conferma ed è possibile eliminare forzatamente il file:

     ![](images/options-menu-force-delete.png){width="300" align="left"}

     >[!NOTE]
     >
     > Se l&#39;amministratore ha concesso l&#39;autorizzazione per l&#39;eliminazione del file, **Forza eliminazione** è abilitato. In caso contrario, **Forza eliminazione** è disabilitato e viene visualizzato un messaggio che informa che non si dispone dell&#39;autorizzazione per eliminare i file di riferimento. Per ulteriori dettagli, visualizzare la sezione *Impedisci l&#39;eliminazione dei file a cui si fa riferimento* nella sezione Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

   - Se si elimina un argomento di riferimento e si è aperto il file contenente riferimenti per la modifica, verrà visualizzato il collegamento interrotto per il file di riferimento.

  >[!NOTE]
  >
  > È inoltre possibile eliminare il file selezionato in modo simile utilizzando il tasto Elimina della tastiera.

- **Genera**: utilizza l&#39;opzione per pubblicare una mappa o argomenti all&#39;interno di una mappa in una pagina Sites, in un frammento di contenuto o in un frammento di esperienza.

- **Aggiungi a**: puoi scegliere tra le seguenti opzioni:
   - **Raccolte**: aggiunge il file selezionato alle raccolte. Puoi scegliere di aggiungerlo a una raccolta esistente o nuova.

   - **Contenuto riutilizzabile**: aggiunge il file selezionato all&#39;elenco Contenuto riutilizzabile nel pannello sinistro.

- **Copia**: puoi scegliere tra le seguenti opzioni:

   - **Copia UUID**: copia l&#39;UUID del file selezionato negli Appunti.

   - **Copia percorso**: copia il percorso completo del file selezionato negli Appunti.

- **Rielabora risorsa**: attiva l&#39;elaborazione per la risorsa selezionata.

- **Visualizza nell&#39;interfaccia utente di Assets**: consente di visualizzare un&#39;anteprima di un file .dita/.xml nell&#39;interfaccia utente di Assets. Nel caso di un file .ditamap/.bookmap, tutti i file di argomenti all&#39;interno della mappa vengono visualizzati in un&#39;unica visualizzazione unificata pagina per pagina.

- **Proprietà**: utilizzare questa proprietà per aprire la pagina delle proprietà del file selezionato.

  Qualsiasi aggiunta, eliminazione o modifica delle proprietà dei metadati in questa pagina (predefinita o personalizzata) attiverà l&#39;[indicatore della copia di lavoro](./web-editor-edit-topics.md#working-copy-indicator) nella versione del documento.

  Puoi accedere alla pagina Proprietà anche dall’interfaccia utente di Assets selezionando un file e quindi l’icona Proprietà nella barra degli strumenti.

- **Scarica come PDF**: utilizza l&#39;opzione per generare l&#39;output di PDF e scaricarlo.

## Explorer

>[!NOTE]
>
> A partire dalla versione 2025.11.0, il termine Archivio nell&#39;Editor verrà sostituito da **Explorer** per l&#39;installazione del servizio Cloud. Durante la configurazione on-premise, continuerà a visualizzare e ad accedere all’archivio nell’editor.

Explorer fornisce la maggior parte delle funzionalità precedentemente disponibili in Repository, tra cui:

- Navigazione tra file e cartelle
- Menu Opzioni per file e cartelle

Tuttavia, introduce un’esperienza di ricerca e filtro migliorata, progettata per migliorare l’usabilità e l’efficienza.

Per informazioni dettagliate sul menu di scelta rapida per file e cartelle, visualizzare [Menu Opzioni](#options-menu).

Per informazioni dettagliate sull&#39;esperienza di ricerca, visualizzare [Pannello di ricerca](./search-panel-explorer.md).

## Mappa

Quando si seleziona l&#39;icona della vista Mappa, viene visualizzata la vista Mappa in cui viene visualizzato un elenco di argomenti all&#39;interno del file di mappa. Se non è stato aperto alcun file di mappa, la vista Mappa appare vuota. Facendo doppio clic su un file di mappa, il file di mappa viene aperto in questa vista. Puoi fare doppio clic su qualsiasi file all’interno della mappa per aprirlo nell’editor.

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
>In qualità di amministratore, puoi anche scegliere di visualizzare il nome del file della mappa principale che è attualmente aperto nella vista mappa. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.


Quando apri una mappa nella vista mappa, il titolo della mappa corrente viene visualizzato al centro della barra della scheda. Se il titolo è troppo lungo, vengono visualizzati dei puntini di sospensione e puoi anche passare il puntatore del mouse sul titolo per visualizzare il titolo completo nella descrizione comando.

Quando definite gli attributi chiave per i riferimenti argomento o mappa, potete visualizzare il titolo, l&#39;icona corrispondente e il tasto nel pannello sinistro. La chiave viene visualizzata come `keys=<key-name>`.

![chiavi nella vista mappa](images/view-key-title-map-view.png){width="300" align="left"}

Se si dispone dei diritti di modifica sui file di mappa, sarà possibile modificare anche i file. Per ulteriori informazioni sull&#39;apertura e la modifica di un argomento tramite mappa DITA, visualizzare [Modifica argomenti tramite mappa DITA](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

Per un file di mappa nella vista Mappa sono disponibili le seguenti opzioni:

- **Apri nella console mappe**: apre il file mappa nella console Mappa.
- **Modifica**: apre il file mappa per la modifica.
- **Opzioni**: apre il menu di scelta rapida per il file di mapping selezionato.

Potete eseguire le seguenti operazioni utilizzando il menu Opzioni (Options) del file di mappa:

![](images/options-menu-map-view_cs.png){align="left"}

- **Modifica**: apri il file mappa per la modifica nell&#39;editor mappa.

- **Seleziona tutti**: seleziona tutti i file nella mappa.

- **Cancella selezione**: deseleziona i file selezionati nella mappa.

- **Blocco**: ottieni un blocco per i file selezionati nella mappa.

- **Sblocca**: sblocca il file mappa e lo rende disponibile per la modifica. Le modifiche non vengono ripristinate alla versione precedente.

- **Salva come nuova versione e sblocca**: crea una versione più recente e rilascia il blocco sui file selezionati nella mappa.

- **Anteprima**: consente di aprire un&#39;anteprima del file di mapping. In questa visualizzazione, tutti i file degli argomenti della mappa vengono visualizzati in un&#39;unica visualizzazione unificata pagina per pagina.

- **Copia**: puoi scegliere tra le seguenti opzioni:
   - **Copia UUID**: copia l&#39;UUID del file di mappa negli Appunti.
   - **Copia percorso**: copia il percorso completo del file di mappa negli Appunti.

- **Individua in Esplora**: mostra la posizione del file di mappa in Esplora\(o DAM\).

- **Aggiungi a**: puoi scegliere tra le seguenti opzioni:
   - **Raccolte**: aggiunge il file di mapping alle raccolte. Puoi scegliere di aggiungerlo a una raccolta esistente o nuova.

   - **Contenuto riutilizzabile**: aggiunge il file mappa all&#39;elenco Contenuto riutilizzabile nel pannello sinistro.

- **Proprietà**: utilizzare questa proprietà per aprire la pagina delle proprietà del file di mappa. Puoi accedere a questa pagina delle proprietà anche dall’interfaccia utente di Assets selezionando un file e facendo clic sull’icona Proprietà nella barra degli strumenti.

- **Apri dashboard mappe**: apre il dashboard delle mappe.

- **Visualizza nell&#39;interfaccia utente di Assets**: consente di visualizzare un&#39;anteprima del file mappa nell&#39;interfaccia utente di Assets. In questa visualizzazione, tutti i file degli argomenti della mappa vengono visualizzati in un&#39;unica visualizzazione unificata pagina per pagina.
- **Scarica mappa**: selezionare questa opzione per aprire la finestra di dialogo **Scarica mappa**.

  Nella finestra di dialogo **Scarica mappa** puoi scegliere le seguenti opzioni:

  **Usa baseline**: selezionare questa opzione per ottenere un elenco delle baseline create per la mappa DITA. Per scaricare il file mappa e il relativo contenuto in base a una baseline specifica, selezionare la baseline dall&#39;elenco a discesa. Per ulteriori dettagli sull&#39;utilizzo delle baseline, visualizzare [Utilizzo delle baseline](./generate-output-use-baseline-for-publishing.md).

  **Flatten File Hierarchy**: selezionare questa opzione per salvare tutti gli argomenti e i file multimediali di riferimento in un&#39;unica cartella.

  È inoltre possibile scaricare il file mappa senza selezionare alcuna opzione. In tal caso, vengono scaricate le ultime versioni persistenti degli argomenti e dei file multimediali a cui si fa riferimento.

  Dopo aver selezionato il pulsante **Scarica**, la richiesta del pacchetto di esportazione della mappa è in coda. Se il pacchetto viene creato correttamente, viene visualizzata la finestra di dialogo **Operazione riuscita**.  Puoi selezionare il pulsante **Scarica** nella finestra di dialogo **Operazione riuscita**.

  Se la mappa è pronta per il download, riceverai una notifica di pronto per il download. Se il download non riesce, viene inviata la notifica che indica che il download della mappa non è riuscito.

  Puoi accedere al collegamento per il download dalla casella in entrata delle notifiche Adobe Experience Manager. Seleziona la notifica della mappa generata nella casella in entrata per scaricare la mappa in formato .zip.

  >[!NOTE]
  >
  >  Per impostazione predefinita, le mappe scaricate rimangono per cinque giorni nella casella in entrata delle notifiche Adobe Experience Manager.

- **Chiudi contesto mappa**: chiude il file mappa.

La schermata seguente mostra il menu Opzioni per un file nella vista mappa:

![](images/options-menu-file_cs.PNG){align="left"}

È possibile eseguire le azioni seguenti utilizzando il menu Opzioni:

- **Modifica**: apri il file per la modifica. Nel caso di un file .ditamap/.bookmap, viene aperto nell&#39;[Editor mappe](map-editor-advanced-map-editor.md#) per la modifica.

- **Blocca**: blocca il file selezionato. Per un file bloccato, questa opzione diventa **Sblocca**.



  >[!NOTE]
  >
  > - Se un file è bloccato da un utente, posizionando il puntatore del mouse sull&#39;icona del blocco viene visualizzato l&#39;utente \(name\) che ha bloccato il file.
  > - Quando si archivia un file, viene richiesto di salvare le modifiche. Se le modifiche non vengono salvate, verrà archiviato solo il file.

- **Anteprima**: consente di ottenere un&#39;anteprima rapida del file (.dita, .xml, audio, video o immagine) senza aprirlo. È possibile ridimensionare il riquadro di anteprima. Se il contenuto contiene `<xref>` o `<conref>`, è possibile selezionarlo per aprirlo in una nuova scheda.  Il titolo del file viene visualizzato nella finestra. Se non è presente alcun titolo, viene visualizzato il nome del file. Per chiudere il riquadro **Anteprima**, è possibile selezionare l&#39;icona di chiusura o selezionare un punto qualsiasi all&#39;esterno del riquadro.
- **Copia**: puoi scegliere tra le seguenti opzioni:
   - **Copia UUID**: copia l&#39;UUID del file selezionato negli Appunti.
   - **Copia percorso**: copia il percorso completo del file selezionato negli Appunti.


- **Individua in Esplora**: mostra la posizione del file selezionato in Esplora \(o DAM\).
- **Espandi tutto**: consente di espandere tutti gli argomenti nei file di mappa.

- **Comprimi tutto**: comprimi tutti gli argomenti che fanno parte del file di mapping corrente.

- **Aggiungi a**: puoi scegliere tra le seguenti opzioni:
   - **Raccolte**: aggiunge il file selezionato alle raccolte. Puoi scegliere di aggiungerlo a una raccolta esistente o nuova.

   - **Contenuto riutilizzabile**: aggiunge il file selezionato all&#39;elenco Contenuto riutilizzabile nel pannello sinistro.

- **Proprietà**: utilizzare questa proprietà per aprire la pagina delle proprietà del file selezionato. Puoi accedere a questa pagina delle proprietà anche dall’interfaccia utente di Assets selezionando un file e facendo clic sull’icona Proprietà nella barra degli strumenti.

- **Visualizza nell&#39;interfaccia utente di Assets**: consente di visualizzare un&#39;anteprima di un file .dita/.xml nell&#39;interfaccia utente di Assets. Nel caso di un file .ditamap/.bookmap, tutti i file di argomenti all&#39;interno della mappa vengono visualizzati in un&#39;unica visualizzazione unificata pagina per pagina.

- **Genera**: genera l&#39;output per il file selezionato nella pagina Sites, nel frammento di contenuto o nel frammento di esperienza.

>[!NOTE]
>
> È inoltre possibile aprire e modificare le proprietà degli argomenti selezionati in una mappa DITA dal menu **Altre opzioni** in Riferimenti.

## Contenuto riutilizzabile

Una delle caratteristiche principali di DITA è la possibilità di riutilizzare i contenuti. Il pannello **Contenuto riutilizzabile** può memorizzare i file DITA da cui vengono generalmente inseriti i contenuti riutilizzabili. Una volta aggiunti, i file DITA rimangono nel pannello Contenuto riutilizzabile per più sessioni. Ciò significa che non è necessario aggiungere di nuovo i file DITA per accedervi in un secondo momento.

Puoi semplicemente trascinare e rilasciare i contenuti riutilizzabili dal pannello sull’argomento corrente, per inserirli in modo semplice e rapido. È inoltre possibile ottenere un&#39;anteprima del contenuto prima di inserirlo nel documento.

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

Per aggiungere un file DITA al pannello Contenuto riutilizzabile, utilizzare uno dei metodi seguenti:

- Selezionare l&#39;icona **+** accanto a Contenuto riutilizzabile per aprire la finestra di dialogo **Seleziona file**.
- Selezionare il file da aggiungere, quindi scegliere **Seleziona**. Puoi anche cercare file specifici utilizzando l’opzione di ricerca del filtro. Per ulteriori dettagli, visualizzare [Altre funzionalità nell&#39;editor](./web-editor-other-features.md).



  ![](images/reusable-content-selection-left-panel.png){width="650" align="left"}

  È inoltre possibile utilizzare l&#39;icona **Rimuovi** per deselezionare alcuni file dall&#39;anteprima.

  ![](images/resusable-content-remove-preview.png){width="650" align="left"}
- Nella vista Archivio, selezionare l&#39;icona **Opzioni** del file desiderato e scegliere **Aggiungi a** > **Contenuto riutilizzabile** dal menu di scelta rapida.

- Fare clic con il pulsante destro del mouse sulla scheda di un file nell&#39;editor per aprire il menu di scelta rapida e scegliere **Aggiungi a** > **Contenuto riutilizzabile**.

Una volta aggiunto il file, nel pannello Contenuto riutilizzabile è possibile visualizzare tutti gli elementi di contenuto riutilizzabili dal file. Il contenuto riutilizzabile viene visualizzato con i relativi ID e nomi di elementi.

Quando aggiungi un file all’elenco Contenuto riutilizzabile, viene visualizzato il titolo del file invece dell’UUID del file. Per verificare l’UUID del file, passa il cursore del mouse sul titolo del file e nella descrizione comando viene visualizzato l’UUID del file.

![](images/uuid-reusable-content-file-title_cs.png){width="400" align="left"}

>[!NOTE]
>
> È possibile aggiungere più file all&#39;elenco dei contenuti riutilizzabili. È quindi possibile inserire nel documento il contenuto desiderato dal pannello Contenuto riutilizzabile.

**Aggiorna**: verifica nuovamente tutti i contenuti riutilizzabili e visualizza un nuovo elenco di contenuti riutilizzabili.

Per inserire contenuto dal pannello Contenuto riutilizzabile, utilizzate uno dei seguenti metodi:

- Passa il puntatore del mouse su un elemento da inserire, seleziona l&#39;icona **Opzioni** e scegli **Inserisci contenuto riutilizzabile** dal menu a discesa.

  ![](images/insert-reusable-content_cs.png){width="400" align="left"}

  >[!NOTE]
  >
  > Selezionare un file, quindi selezionare **Anteprima** dal menu **Opzioni** per visualizzare l&#39;anteprima del file senza aprirlo. È inoltre possibile visualizzare in anteprima i riferimenti presenti in un argomento. L&#39;ID di riferimento viene visualizzato nella finestra.
  >
  > L&#39;opzione **Anteprima** è disponibile anche nel menu **Opzioni** di un elemento, che offre un&#39;anteprima rapida dell&#39;elemento prima di inserirlo.

- Trascinare l&#39;elemento di contenuto riutilizzabile dal pannello nella posizione desiderata nel documento.

## Struttura

Quando si seleziona l&#39;icona **Struttura**, viene visualizzata la visualizzazione gerarchica degli elementi utilizzati nel documento.

![](images/outline-view_cs.png){width="300" align="left"}

La vista Struttura offre le seguenti caratteristiche:

- Visualizzazione struttura di tutti gli elementi utilizzati nel documento.

- Se un elemento ha un ID, un attributo e un testo, puoi visualizzarli insieme all’elemento.

- Accedi alla vista Struttura sia nella vista Autore che in quella Source.

- Utilizza l’elenco a discesa dei filtri per mostrare tutti gli elementi o solo i riferimenti interrotti:

- Quando si sceglie un elemento nella visualizzazione Struttura, viene selezionato il contenuto dell&#39;elemento nella visualizzazione Autore o Source. La visualizzazione Struttura rimane sincronizzata con le visualizzazioni Autore e Source. Se si apportano modifiche in qualsiasi visualizzazione, è possibile visualizzarle nella visualizzazione Struttura. Ad esempio, se aggiungete un paragrafo o aggiornate un elemento nella vista Creazione, questo verrà visualizzato nella vista Struttura.

  ![](images/select-element-content-outline-view_cs.png){width="650" align="left"}

- Trascina gli elementi. Puoi sostituire facilmente un elemento rilasciandone un altro. Se trascini un elemento su un altro elemento e visualizzi una casella rettangolare tratteggiata intorno all’elemento, questo indica che l’elemento verrà sostituito. Sostituisce l’elemento su cui viene rilasciato l’elemento.

  ![](images/replace-element-outline-view_cs.png){align="left"}

  Se si trascina un elemento, un rettangolo tratteggiato indica che l&#39;elemento può essere posizionato nella posizione corrente. Se il trascinamento della selezione non è valido, viene visualizzato un messaggio di errore per indicare che l’operazione non è consentita.

  ![](images/drop-element-outline-view_cs.png){align="left"}

- Il menu **Opzioni** nella visualizzazione *Struttura* consente di eseguire operazioni generiche quali Taglia, Copia, Elimina, Genera ID, Inserisci elemento prima o dopo l&#39;elemento corrente, Rinomina o sostituisci un elemento, Racchiudi un elemento, Annulla il wrapping di un elemento e crea uno snippet dall&#39;elemento selezionato.

>[!NOTE]
>
>Per ulteriori dettagli su Genera ID, Inserisci elemento prima o dopo l&#39;elemento corrente e Annulla wrapping di un elemento, visualizza [Altre funzionalità nell&#39;editor](web-editor-other-features.md#).

**Visualizza configurazione**

Utilizzando l&#39;opzione **Visualizza configurazione**, è possibile scegliere di visualizzare:

- **Mostra ID**: mostra l&#39;ID dell&#39;elemento.
- **Mostra attributo**: visualizza l&#39;attributo insieme al relativo valore.
- **Mostra testo**: visualizza il testo. Se il testo supera i 20 caratteri, viene visualizzato un puntino di sospensione.

Se un elemento blocco dispone di un proprio testo, viene visualizzato insieme a tale elemento blocco. Se non dispone di testo proprio, il testo del primo elemento figlio viene visualizzato insieme a tale elemento blocco.

![](images/outline-view-block-element.png){width="550" align="left"}

Se l&#39;amministratore ha creato un profilo per gli attributi, questi verranno ottenuti insieme ai relativi valori configurati. Puoi anche assegnare gli attributi di visualizzazione configurati dall&#39;amministratore nella scheda **Attributi di visualizzazione** delle **impostazioni di Workspace** (come **Impostazioni** per **Prem**). Gli attributi definiti per un elemento vengono visualizzati nella vista Layout e Struttura.


**Funzione di ricerca**

Utilizzando la funzione di ricerca, puoi cercare un elemento in base al suo nome, ID, testo o valore dell’attributo.

La ricerca non distingue tra maiuscole e minuscole e corrisponde esattamente alla stringa. I risultati della ricerca vengono ordinati in base alla posizione dell&#39;elemento nel documento.

È possibile cercare una stringa nell&#39;elemento se è visualizzata nella visualizzazione **Struttura**. Se, ad esempio, la stringa &quot;Adobe&quot; è presente nel testo dell&#39;elemento ed è visualizzata nel pannello Visualizzazione Struttura (come hai selezionato **Mostra testo** dal menu a discesa Opzioni visualizzazione), l&#39;elemento che la contiene viene filtrato. Tuttavia, se il testo non viene visualizzato nel pannello Visualizzazione Struttura (poiché non è stato selezionato **Mostra testo** dal menu a discesa Opzioni di visualizzazione), l&#39;elemento che lo contiene non viene filtrato. Allo stesso modo, se li hai selezionati, troverai la stringa nell’ID o negli attributi.

## Glossario

Experience Manager Guides consente di creare e utilizzare facilmente i documenti di tipo glossario. È possibile creare file di argomenti del glossario e quindi includerli in una mappa del glossario comune. Una volta aggiunta questa mappa come mappa principale, le voci del glossario vengono quindi visualizzate nel pannello Glossario.

![](images/glossary-panel.png){width="650" align="left"}

Per inserire un termine dal glossario, è sufficiente trascinare la voce dal pannello nella posizione desiderata nell’argomento. Il menu Opzioni di un termine del glossario ti consente di ottenere una **Anteprima** rapida del termine di ingresso, **Copia percorso** del file del termine di ingresso, oppure di individuare il file del termine di ingresso nell&#39;archivio.

<details>
    <summary> Passaggi per cercare e sostituire il testo nelle abbreviazioni del glossario </summary>

Per cercare termini di testo e sostituirli con abbreviazioni del glossario, effettuare le seguenti operazioni:

1. Aprire l&#39;argomento o la mappa DITA in cui si desidera cercare e convertire il testo o i termini.
1. Selezionare il pannello glossario per visualizzare i termini del glossario presenti nella mappa principale. È possibile trascinare questi termini per aggiungerli all&#39;argomento aperto.
1. Selezionare lo strumento **Punto attivo** \( ![](images/hotspot-icon.svg)\) nel pannello Glossario per cercare e convertire termini di testo specifici in abbreviazioni di glossario collegate. Inoltre, viceversa, è possibile utilizzarlo per cercare abbreviazioni del glossario e convertirle in termini di testo.

</details>


È possibile configurare le seguenti impostazioni dello strumento Punto attivo:

![](images/glossary-hotspot-tool.png){width="300" align="left"}


- **Tasti glossario**: Selezionare i tasti del glossario dalla mappa DITA che si desidera utilizzare per la ricerca nell&#39;argomento selezionato. I tasti selezionati verranno visualizzati di seguito. È possibile rimuovere una chiave selezionata selezionando l&#39;icona **Rimuovi**.

- **Argomenti**: scegliere l&#39;**Argomento corrente** aperto nell&#39;editor, tutti i **Argomenti aperti** nella mappa corrente oppure la **Mappa corrente** modificata nell&#39;editor mappe per cercare i termini.
- **Filtra argomenti per stato**: è possibile limitare la ricerca agli argomenti con lo stato del documento selezionato. Gli argomenti possono essere in stato Bozza, Modifica, In revisione, Approvato, Rivisto, Fine o in uno qualsiasi degli stati configurati dall’organizzazione.
- **Azione**: è possibile scegliere di cercare manualmente le chiavi del glossario **per ogni argomento** o **Automaticamente per tutti gli argomenti**. Se si sceglie **Manualmente per ogni argomento**, verrà richiesto di confermare prima di convertire ogni termine in ogni argomento. Se si sceglie **Automaticamente per tutti gli argomenti**, tutti i termini in tutti gli argomenti verranno convertiti automaticamente.
- **Converti**: è possibile convertire un **testo cercato in termine glossario** o un **termine glossario in testo.**
- **Opzioni**: è possibile selezionare una delle opzioni seguenti:
   - **Corrispondenza con distinzione tra maiuscole e minuscole**: cerca un termine per trovare la corrispondenza con lo stesso carattere. Ad esempio, &#39;USB&#39; non corrisponderà a &#39;usb&#39;.
   - **Converti solo la prima istanza**: se in un argomento sono presenti più istanze del termine cercato, viene convertita solo la prima istanza.
   - **Blocca il file prima della conversione**: il file cercato viene bloccato prima della conversione dei termini.
   - **Crea una nuova versione dopo la conversione**: viene creata una nuova versione dell&#39;argomento al termine della conversione dei termini.
- Il pulsante **Avanti** viene visualizzato se si seleziona **Manualmente per ogni argomento**. Seleziona **Successivo** per convertire i termini di ogni argomento in base alle impostazioni selezionate. Richiede la conversione dei termini in ciascun argomento e passa al file successivo. Puoi scegliere di convertire un termine o saltarlo e passare al termine successivo.

  ![](images/manual-convert-skip.png){width="300" align="left"}

- Il pulsante **Converti** viene visualizzato se si seleziona **Automaticamente per tutti gli argomenti**. Selezionare **Converti** per convertire tutti i termini presenti nel documento in abbreviazioni di glossario collegate.

Viene visualizzato un elenco di **argomenti aggiornati** con i termini convertiti e **argomenti con errore**. Passa il cursore del mouse sull’icona delle informazioni accanto ad Argomenti con errore per visualizzare i dettagli dell’errore.

>[!NOTE]
>
> Aggiornare l&#39;argomento per visualizzare i termini convertiti.

## Condizioni

Il pannello Condizioni visualizza gli attributi condizionali definiti dall&#39;amministratore nel profilo globale o a livello di cartella. Puoi aggiungere condizioni al contenuto semplicemente trascinando e rilasciando la condizione desiderata sul contenuto. Il contenuto condizionale viene evidenziato utilizzando il colore definito per la condizione per una facile identificazione.

Puoi anche applicare più condizioni a un elemento trascinando più condizioni su di esso. Quando applicate più condizioni a un elemento, il pannello Proprietà mostra le condizioni applicate separate da una virgola.

![](images/multiple-conditions-applied_cs.png){align="left"}

Tuttavia, nella vista Codice le condizioni vengono separate utilizzando un delimitatore di spazio. Quando aggiungi o modifichi una condizione nella vista Codice, accertati che più condizioni siano separate utilizzando uno spazio.

>[!IMPORTANT]
>
> La schermata seguente è di un utente con privilegi di amministratore. In qualità di utente con privilegi di amministratore, puoi aggiungere, modificare ed eliminare condizioni. Altrimenti, in qualità di autore normale, avrai la possibilità di applicare solo le condizioni.

![](images/conditional-content-through-panel_cs.png){align="left"}

Per aggiungere o definire una condizione, seleziona l’icona + accanto al pannello Condizioni per visualizzare la finestra di dialogo Definisci condizione:

![](images/conditional-panel-create-cond.png){width="400" align="left"}

Dall&#39;elenco Attributo (Attribute), selezionate l&#39;attributo condizionale da definire, immettete un valore per la condizione, quindi specificate l&#39;etichetta visualizzata nel pannello Condizioni (Conditions). Definisci un gruppo per la condizione. È possibile aggiungere più condizioni a un gruppo. Puoi anche definire un colore per la condizione. Questo colore viene impostato come colore di sfondo del contenuto a cui viene applicata la condizione.

Puoi raggruppare le condizioni e strutturarle in cartelle nidificate. I gruppi consentono di creare condizioni a più livelli e di organizzarle meglio per l’utilizzo nel contenuto.

Ad esempio, puoi creare gruppi di condizioni di prodotti come *Acrobat* e *AEM Guides*. È possibile selezionare gli attributi condizionali per entrambi i gruppi. In ogni gruppo, puoi avere valori specifici come *Utente*, *Amministratore*, *Revisore* e *Autore*.

>[!NOTE]
>
> Digitare per creare un nuovo gruppo o selezionare un gruppo esistente per un determinato attributo.

È possibile utilizzare `/` e definire sottogruppi come `AEM Guides/Cloud Service`.



![condizioni organizzate in una gerarchia nidificata](images/conditions-nested-hierarchy.png){width="300" align="left"}


Per modificare una condizione, scegliere **Modifica** dal menu Opzioni. Viene visualizzata la finestra di dialogo Modifica condizione:

![](images/conditional-panel-edit-cond.png){width="400" align="left"}

Specifica i dettagli nello stesso modo in cui sono configurati durante la definizione di una nuova condizione.

## Schema soggetto

Le mappe di schema argomento sono una forma specializzata di mappe DITA utilizzate per definire soggetti tassonomici e valori controllati. A seconda delle esigenze, puoi creare una mappa dello schema di soggetti e farvi riferimento all’interno del file della mappa principale. Experience Manager Guides consente di definire la gerarchia a livello nidificato delle definizioni dei soggetti nello schema dei soggetti.

È possibile creare e quindi utilizzare facilmente lo schema dell&#39;oggetto in una mappa dello schema dell&#39;oggetto. Una volta aggiunta questa mappa come mappa principale, lo schema soggetto viene visualizzato nel pannello Schema soggetto. Il pannello Schema soggetto visualizza lo schema soggetto disponibile in modo nidificato o gerarchico.

Experience Manager Guides supporta inoltre le mappe di schema soggetto di livello nidificato ed è possibile definire più schemi soggetto nella mappa di schema soggetto principale.

<details>
    <summary> Come utilizzare lo schema soggetto in Experience Manager Guides </summary>
Nell'esempio seguente viene illustrato come utilizzare lo schema soggetto in Experience Manager Guides.

1. Creare un file dello schema soggetto in uno strumento desiderato. Il codice XML seguente crea uno schema soggetto che associa i valori per l&#39;attributo `platform`.

   ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "subjectScheme.dtd">
   <subjectScheme id="GUID-4f942f63-9a20-4355-999f-eab7c6273270">
       <title>rw</title>
       <!-- Define new OS values that are merged with those in the unixOS scheme -->
       <subjectdef keys="os">
           <subjectdef keys="linux">    </subjectdef>
           <subjectdef keys="mswin">    </subjectdef>
           <subjectdef keys="zos">    </subjectdef>
       </subjectdef>
       <!-- Define application values -->
       <subjectdef keys="app" navtitle="Applications">
           <subjectdef keys="apacheserv">    </subjectdef>
           <subjectdef keys="mysql">    </subjectdef>
       </subjectdef>
       <!-- Define an enumeration of the platform attribute, equal to       each value in the OS subject. This makes the following values       valid for the platform attribute: linux, mswin, zos -->
       <enumerationdef>
           <attributedef name="platform">    </attributedef>
           <subjectdef keyref="os">    </subjectdef>
       </enumerationdef>
       <!-- Define an enumeration of the otherprops attribute, equal to       each value in the application subjects.       This makes the following values valid for the otherprops attribute:       apacheserv, mysql -->
       <enumerationdef>
           <attributedef name="otherprops">    </attributedef>
           <subjectdef keyref="app">    </subjectdef>
       </enumerationdef>
   </subjectScheme>
   ```

   ![](images/subject-scheme-panel-new.png){width="300" align="left"}

1. Salva il file con estensione a.ditamap e caricalo in qualsiasi cartella in DAM.

   >[!NOTE]
   >
   > È possibile aggiungere un riferimento al file dello schema soggetto nella mappa DITA padre.

   ![](images/subject-scheme-root-map-new.png){width="550" align="left"}

1. Imposta la mappa padre come mappa radice nelle **Preferenze utente**. Una volta aggiunta questa mappa come mappa principale, lo schema soggetto viene visualizzato nel pannello Schema soggetto.

   ![](images/subject-scheme-user-preferences-new.png){width="650" align="left"}


1. Nell&#39;editor aprire il file in cui si desidera utilizzare le definizioni dello schema di oggetti.
1. Applica lo schema soggetto al contenuto semplicemente trascinando lo schema soggetto desiderato sul contenuto. Il contenuto viene quindi evidenziato nel colore definito.
</details>

<details>
    <summary> Gestione delle definizioni gerarchiche delle definizioni e delle enumerazioni dei soggetti </summary>

Oltre a gestire le enumerazioni e le definizioni dei soggetti presenti nella stessa mappa, Experience Manager Guides fornisce anche la funzione di definire enumerazioni e definizioni dei soggetti in due mappe separate. È possibile definire una o più definizioni di oggetto in una mappa e le definizioni di enumerazione in un&#39;altra mappa, quindi aggiungere il riferimento alla mappa. Ad esempio, il codice XML seguente crea definizioni di oggetti e definizioni di enumerazione in due mappe separate.

Le definizioni dell&#39;oggetto sono definite in `subject_scheme_map_1.ditamap`


```XML
  <?xml version="1.0" encoding="UTF-8"?> 
    <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
    <subjectScheme id="subject-scheme.ditamap_f0bfda58-377b-446f-bf49-e31bc87792b3"> 

    <title>subject_scheme_map_1</title> 
    
    <subjectdef keys="os" navtitle="Operating system">
        <subjectdef keys="linux" navtitle="Linux">
        <subjectdef keys="redhat" navtitle="RedHat Linux">
        </subjectdef>
        <subjectdef keys="suse" navtitle="SuSE Linux">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="windows" navtitle="Windows">
        </subjectdef>
        <subjectdef keys="zos" navtitle="z/OS">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="deliveryTargetValues">
        <subjectdef keys="print">
        </subjectdef>
        <subjectdef keys="online">
        </subjectdef>
    </subjectdef>
    <subjectdef keys="mobile" navtitle="Mobile">
        <subjectdef keys="android" navtitle="Android">
        </subjectdef>
        <subjectdef keys="ios" navtitle="iOS">
    </subjectdef>
    </subjectdef>
    <subjectdef keys="cloud" navtitle="Cloud">
        <subjectdef keys="aws" navtitle="Amazon Web Services">
        </subjectdef>
        <subjectdef keys="azure" navtitle="Microsoft Azure">
        </subjectdef>
        <subjectdef keys="gcp" navtitle="Google Cloud Platform">
        </subjectdef>
    </subjectdef>
    </subjectScheme>
```

La definizione di enumerazione è presente in    subject_scheme_map_2.ditamap.

```XML
    ?xml version="1.0" encoding="UTF-8"?> 
        <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
        <subjectScheme id="subject-scheme.ditamap_17c433d9-0558-44d4-826e-3a3373a4c5ae"> 
        <title>subject_scheme_map_2</title> 
        <mapref format="ditamap" href="subject_scheme_map_1.ditamap" type="subjectScheme"> 
        </mapref> 
        <enumerationdef>
        <attributedef name="platform">
        </attributedef>
        <subjectdef keyref="mobile">
        </subjectdef>
        <subjectdef keyref="cloud">
        </subjectdef>
        </enumerationdef>
        </subjectScheme>
```

Qui le definizioni dei soggetti sono definite in `subject_scheme_map_1.ditamap` mentre la definizione dell&#39;enumerazione è presente in `subject_scheme_map_2.ditamap`. Il riferimento a `subject_scheme_map_1.ditamap` è stato aggiunto anche in `subject_scheme_map_2.ditamap`.

>[!NOTE]
>
> Poiché `subject_scheme_map_1.ditamap` e `subject_scheme_map_2.ditamap` sono referenziati tra loro, gli schemi soggetto vengono risolti.

I riferimenti di enumerazione dei soggetti vengono risolti nel seguente ordine di priorità:

1. Stessa mappa
1. Mappa di riferimento


I riferimenti non vengono risolti se l’enumerazione non viene trovata nella stessa mappa e nella mappa di riferimento.

</details>

<details>
    <summary> Limita i valori a un elemento specifico </summary>


È inoltre possibile limitare le condizioni ad alcuni elementi all&#39;interno di un argomento. Utilizzare il tag `<elementdef>` per definire l&#39;elemento e il tag `<attributedef>` per definire la condizione che può essere applicata all&#39;elemento.  Se non aggiungi il tag `<elementdef>`, puoi applicare le condizioni a tutti gli elementi.
Utilizzare ad esempio l&#39;enumerazione seguente per limitare l&#39;attributo `@platform` all&#39;elemento `<shortdesc>`.  Le altre condizioni sono visibili per tutti gli elementi.

```XML
<enumerationdef>
    <elementdef name="shortdesc">
    </elementdef>
    <attributedef name="platform">
    </attributedef>
    <subjectdef keyref="deliveryTargetValues">
    </subjectdef>
    <subjectdef keyref="os">
    </subjectdef>
  </enumerationdef>
```

</details>


Elenco a discesa **Attributi**

Puoi anche modificare il valore dello schema dell&#39;oggetto utilizzando il menu a discesa **Attributi** dal pannello **Proprietà contenuto** nella visualizzazione **Autore**.

Per modificare il valore, effettua le seguenti operazioni:

1. Selezionare un attributo dal menu a discesa **Attributo**.
1. Seleziona **Modifica**.
1. Seleziona il valore richiesto dal menu a discesa **Valore**.
1. Seleziona **Aggiorna**.

Puoi anche applicare valori a un attributo selezionando più valori dal menu a discesa.

**Visualizzazione Source**

Puoi anche modificare i valori dal menu a discesa dell’attributo nella vista Source. La vista Source impedisce inoltre di aggiungere valori errati.

![](images/subject-scheme-code-error.png){width="550" align="left"}

**Visualizza e applica lo schema soggetto dal pannello Condizioni**

Potete anche visualizzare e applicare lo schema soggetto dal pannello Condizioni.

Per visualizzare lo schema di oggetti dal pannello Condizioni, l&#39;amministratore di sistema deve selezionare l&#39;opzione **Mostra schema di oggetti nel pannello Condizioni** nella scheda Generale in **Impostazioni Workspace** (come **Impostazioni** per **Prem**). Per ulteriori dettagli, visualizzare la [barra delle schede](./web-editor-tab-bar.md).

Il pannello Condizioni visualizza la struttura verticale piatta delle definizioni dei soggetti all&#39;interno dello schema.

Puoi aggiungere condizioni al contenuto trascinando e rilasciando la condizione desiderata sul contenuto. Il contenuto condizionale viene evidenziato utilizzando il colore definito per la condizione.

## Snippet

I frammenti sono piccoli frammenti di contenuto che possono essere riutilizzati in vari argomenti nel progetto di documentazione. Il pannello Snippet mostra una raccolta di snippet di contenuto creati dall&#39;utente. Per inserire uno snippet, trascinarlo dal pannello nella posizione desiderata nell&#39;argomento. Il pannello Snippet consente di aggiungere, modificare, eliminare, visualizzare in anteprima e inserire uno snippet.

>[!IMPORTANT]
>
> La schermata seguente è di un utente con privilegi di amministratore. In qualità di utente con privilegi di amministratore, puoi aggiungere, modificare ed eliminare snippet. Altrimenti, in qualità di autore normale, avrai accesso solo alle opzioni per visualizzare in anteprima e inserire uno snippet.

![](images/snippets-panel_cs.png){align="left"}

**Crea un frammento**

Per aggiungere uno snippet, utilizzare uno dei metodi seguenti:

1. Seleziona l&#39;icona **+** accanto a Snippet per aprire la finestra di dialogo **Nuovo snippet**.

   ![](images/snippet-new-dialog.png){width="300" align="left"}

   Nella finestra di dialogo Nuovo snippet, specificate un titolo da visualizzare nel pannello Snippet, una descrizione, selezionate un formato (DITA o HTML) per il contenuto e fornite un codice del contenuto del frammento che desiderate creare. Seleziona **Crea** per salvare e creare lo snippet.

2. Nell&#39;area di modifica del contenuto fare clic con il pulsante destro del mouse sulla breadcrumb dell&#39;elemento che si desidera utilizzare come frammento e scegliere **Crea frammento** dal menu di scelta rapida. Viene visualizzata la finestra di dialogo Nuovo frammento con il codice XML dell&#39;elemento selezionato popolato nel campo **Contenuto**. Immetti il **Titolo** e la **Descrizione** per lo snippet e seleziona **Crea** per salvare lo snippet.

3. Nell&#39;area di modifica del contenuto fare clic con il pulsante destro del mouse in un punto qualsiasi del contenuto che si desidera utilizzare come frammento e scegliere **Crea frammento** dal menu di scelta rapida. Viene visualizzata la finestra di dialogo Nuovo frammento con il codice XML dell&#39;elemento selezionato popolato nel campo **Contenuto**. Immetti il **Titolo** e la **Descrizione** per lo snippet e seleziona **Crea** per salvare lo snippet.

   La schermata seguente evidenzia la breadcrumb e l’area del contenuto da cui è possibile richiamare il menu di scelta rapida.

   ![](images/snippet-create-from-breadcrumb-content.png){width="350" align="left"}

**Inserire uno snippet**

Per inserire uno snippet, utilizzare uno dei metodi seguenti:

- Selezionate uno snippet dal pannello Snippet e trascinatelo nella posizione desiderata nell&#39;argomento. Per perfezionare la vista, potete anche usare le opzioni filtro nella parte superiore del pannello Snippet:

   - **Mostra tutti i frammenti**: elenca tutti i frammenti disponibili, inclusi i formati DITA e HTML.
   - **Mostra solo snippet applicabili**: filtra l&#39;elenco in modo da visualizzare solo i frammenti rilevanti per l&#39;argomento o il contesto corrente. Ad esempio, se si sta lavorando su un argomento DITA, i frammenti di codice HTML verranno esclusi dall&#39;elenco per garantire l&#39;accuratezza contestuale.

- Posizionare il punto di inserimento nel punto in cui si desidera inserire lo snippet. Scegliere Inserisci snippet dal menu Opzioni dello snippet desiderato.


>[!NOTE]
>
> Dal menu di scelta rapida di una voce di frammento, è inoltre possibile scegliere di modificare, eliminare, ottenere un&#39;anteprima o inserire uno snippet.

## Modelli

Il pannello Modelli è disponibile solo per gli amministratori. Utilizzando questo pannello, l’amministratore può creare e gestire facilmente modelli che possono quindi essere utilizzati dagli autori. Per impostazione predefinita, i modelli sono classificati nei modelli di tipo *map* e *topic*.

![](images/templates-panel_cs.png){width="300" align="left"}

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un modello, è possibile visualizzare il titolo e il nome del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file nell’editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

Per informazioni su come creare modelli personalizzati, visualizzare [Creare mappe in base a modelli personalizzati](./create-maps-customized-templates.md).

## Citazioni

In Experience Manager Guides, puoi aggiungere e importare citazioni e applicarle al contenuto. È possibile aggiungere queste citazioni da qualsiasi origine di libri, siti Web e giornali.

Per informazioni dettagliate, visualizza [Aggiungi e gestisci le citazioni nel contenuto](./web-editor-apply-citations.md).

## Variabili di lingua

Experience Manager Guides fornisce la funzione di utilizzare le variabili di lingua nell’output del PDF nativo. È possibile utilizzare le variabili di lingua per definire stringhe localizzate nell’output di PDF o per localizzare qualsiasi testo statico nei modelli di output. È possibile utilizzare gli stili CSS per localizzare le stringhe provenienti da un CSS.

Per ulteriori dettagli, visualizzare [Supporto per le variabili di lingua](../native-pdf/native-pdf-language-variables.md).

## Variabili

Experience Manager Guides consente di creare e gestire le variabili per la pubblicazione PDF nativa. Per ulteriori dettagli, visualizzare [Variabili nell&#39;output di PDF](../native-pdf/native-pdf-variables.md).


## Trova e sostituisci

L’icona Trova e sostituisci si trova nella parte inferiore del pannello a sinistra. Il pannello Trova e sostituisci consente di cercare e sostituire il testo tra i file di una mappa o di una cartella all’interno dell’archivio. È possibile eseguire operazioni di ricerca e sostituzione in tutti gli argomenti di una mappa, inclusi gli argomenti contenuti nelle mappe secondarie e nei file Markdown.

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

La funzione Trova e sostituisci può essere utilizzata in due modalità distinte, a seconda dei requisiti:

- **In modalità Source:** la ricerca esegue la scansione non solo del contenuto visibile, ma anche del contenuto di origine sottostante (struttura XML, inclusi elementi, tag e valori di attributi) per la stringa cercata. Questa modalità garantisce una ricerca completa nell’intero contenuto. Per utilizzare questa funzionalità, è necessario abilitare l&#39;opzione **Usa modalità origine** disponibile nel pannello Trova e sostituisci.

  >[!NOTE]
  >
  > La funzione **Usa modalità origine** è disponibile in Experience Manager Guides as a Cloud Service con versione 2026.01.0 e per la configurazione locale con versione 5.2. Per utilizzare questa funzione, devi innanzitutto indicizzare il contenuto a seconda della configurazione in uso.
  > - **Per Cloud Services**: è necessario eseguire una distribuzione dell&#39;indice personalizzata. Per ulteriori dettagli, visualizzare [Distribuzione dell&#39;indice personalizzato](/help/product-guide/cs-install-guide/custom-indexing.md). Al termine, contatta il team di successo del cliente per abilitare questa funzione.
  > - **On-Premise**: è necessaria la reindicizzazione del contenuto esistente prima che la funzionalità possa essere utilizzata. Per ulteriori dettagli, visualizzare [Contenuto reindicizzazione](/help/product-guide/install-guide/custom-indexing-prem.md). Al termine, contatta il team di successo del cliente per abilitare questa funzione.

  ![](images/map-find-replace-with-source-mode.png){align="left"}

<br>

<details>
    <summary> Esegui ricerca globale e sostituisci con modalità Source</summary>

Per eseguire la ricerca globale e sostituirla con la modalità Source, effettuare le seguenti operazioni:

1. Apri il pannello **Trova e sostituisci** globale.
1. Abilitare l&#39;opzione **Usa modalità origine**.
1. Selezionare il menu a discesa **Percorso** e selezionare una delle opzioni seguenti per eseguire la ricerca.

   - **Percorso**: per eseguire una ricerca nel percorso selezionato
   - **Mappa**: per eseguire ricerche in una mappa specifica dall&#39;archivio o dalle raccolte
   - **Mappa corrente**: per eseguire ricerche nella mappa attualmente aperta

   ![](images/path-dropdown-source-mode.png){width="350" align="left"}


1. Immettere la stringa di ricerca nel campo **Trova**. Per limitare i risultati, selezionare l&#39;icona **Filtro** accanto al campo Trova e selezionare i seguenti filtri desiderati:

   ![](images/find-filters-source-mode.png){width="350" align="left"}

   - **Tipo di file**: scegliere il tipo di file; **Argomenti** e **Mappe** in cui si desidera cercare il testo
   - **Stato documento**: è possibile selezionare uno stato del documento tra le opzioni disponibili. Le opzioni dello stato del documento visualizzate derivano dai profili delle cartelle. Essi rappresentano il set combinato di tutti i possibili stati del documento in tali profili. Gli stati predefiniti includono In-review, Fatto (Done), Bozza (Draft), Approvato (Approved), Modifica (Edit) e Rivisto (Reviewed).
   - **Ultima modifica**: filtra il contenuto in base alla data di modifica. Seleziona un intervallo di date dal calendario o scegli una delle seguenti opzioni per l’intervallo di tempo:

      - Nelle ultime 2 ore
      - Nell&#39;ultima settimana
      - Nell&#39;ultimo mese
      - Nell&#39;ultimo anno
   - **Altri**: puoi configurare i seguenti elementi:
      - **Tag**: filtra il contenuto in base ai tag.
      - **Ricerca con distinzione tra maiuscole e minuscole**: abilita la ricerca per garantire che i risultati corrispondano esattamente alla combinazione di maiuscole e minuscole specificata.
      - **Elenca i file bloccati da altri utenti**: visualizza i file attualmente bloccati da altri utenti, impedendo eventuali modifiche fino al rilascio del blocco.

1. Premi Invio o seleziona l&#39;icona **Cerca** per eseguire la ricerca.

   ![](images/search-icon.png){width="350" align="left"}

1. Selezionare un file dall&#39;elenco dei risultati della ricerca. Il file viene aperto nella visualizzazione Source con il termine cercato evidenziato nel contenuto.

1. Immettere il termine da utilizzare come sostituto nel campo **Sostituisci con**. Per personalizzare la modalità di applicazione delle sostituzioni, fare clic sull&#39;icona **Impostazioni** accanto al campo e scegliere tra le opzioni disponibili.

   - **Sostituisci file sbloccati**: selezionare questa opzione per consentire la sostituzione nei file sbloccati.

   - **Crea nuova versione dopo la sostituzione**: selezionare questa opzione se si desidera creare una nuova versione dell&#39;argomento in cui si sceglie di sostituire il testo. Puoi anche fornire commenti sulla versione che verranno aggiunti a ogni file aggiornato. Se non si seleziona questa opzione, le modifiche verranno salvate nella versione corrente dell&#39;argomento e non verrà creata alcuna nuova versione.

   ![](images/replace-settings-source-mode.png){width="350" align="left"}


1. Seleziona **Sostituisci occorrenza** per sostituire la stringa di ricerca attualmente evidenziata nell&#39;argomento o seleziona le frecce in alto e in basso per passare all&#39;occorrenza successiva o precedente del testo.

   ![](images/replace-occurrence.png){width="350" align="left"}

1. Selezionare **Sostituisci tutto** per sostituire tutte le occorrenze della stringa cercata in tutti i file cercati con la stringa sostitutiva specificata in un&#39;unica operazione. Verrà visualizzata una notifica dopo la sostituzione di tutte le occorrenze.

   ![](images/replace-all.png){width="350" align="left"}

   >[!NOTE]
   >
   >Per abilitare il pulsante **Sostituisci tutto**, l&#39;amministratore del profilo di cartella o l&#39;amministratore di sistema deve selezionare l&#39;opzione **Abilita Sostituisci tutto** nella scheda **Generale** in **Impostazioni Workspace** (come **Impostazioni** per **Prem**).

1. È inoltre possibile passare il cursore del mouse su un file dall&#39;elenco dei risultati della ricerca per visualizzare l&#39;icona **Sostituisci tutto nel file** sulla destra, che consente di sostituire tutte le occorrenze del termine in un unico file.

   >[!NOTE]
   >
   > Per rimuovere il file dal risultato della ricerca, viene inoltre visualizzata l&#39;icona **Rimuovi**. I file rimossi vengono rimossi dall&#39;elenco e il termine cercato non viene sostituito al loro interno.

   ![](images/replace-all-in-file.png){width="350" align="left"}

1. Al termine dell’operazione Sostituisci tutto, viene generato un rapporto CSV scaricabile che fornisce un’istantanea di tutte le azioni di sostituzione eseguite. È possibile scaricare il report per visualizzare informazioni dettagliate sulle operazioni di sostituzione, incluso il numero di occorrenze sostituite correttamente, insieme ai dettagli di ciascuna, nonché eventuali errori e le relative motivazioni. L&#39;operazione potrebbe non riuscire per alcuni motivi specifici, ad esempio il blocco del file da parte di un altro utente, errori di convalida causati dalle modifiche apportate al file durante l&#39;operazione o altri problemi simili.

   ![](images/snapshot-replace-all.png){width="350" align="left"}

È possibile eseguire una sola operazione di sostituzione alla volta nell&#39;intero sistema e, fino a quando non viene eseguita, verrà visualizzato lo stato &quot;Sostituisci tutto in corso&quot;. È inoltre possibile interrompere l&#39;operazione Sostituisci tutto nel mezzo. Se si interrompe l&#39;operazione, si riceverà una notifica nella Posta in arrivo.

![](images/replace-all-in-progress-source-mode.png){width="350" align="left"}

</details>

<br>

- **Senza modalità Source:** la ricerca è limitata al testo visualizzato nella visualizzazione Autore, concentrandosi solo sul contenuto visibile ignorando il contenuto sorgente come elementi o attributi XML. Questa modalità è ideale per ricerche rapide di solo contenuto.

  ![](images/map-find-replace-without-source-mode.png){align="left"}

<br>
<details>
    <summary> Esecuzione di ricerche globali e sostituzione senza modalità Source</summary>


Per eseguire la ricerca globale e sostituirla senza la modalità Source, effettuare le seguenti operazioni:

1. Apri il pannello **Trova e sostituisci** globale.
1. Selezionare il menu a discesa **Percorso** e scegliere una delle opzioni seguenti per eseguire la ricerca.

   - **Percorso**: per eseguire una ricerca nel percorso selezionato
   - **Mappa**: per eseguire ricerche in una mappa specifica dall&#39;archivio o dalle raccolte
   - **Mappa corrente**: per eseguire ricerche nella mappa attualmente aperta

   ![](images/path-dropdown.png){width="350" align="left"}

1. Immettere la stringa di ricerca nel campo **Trova**. Per limitare i risultati, selezionare l&#39;icona **Filtro** accanto al campo Trova e selezionare i seguenti filtri desiderati:


   - **Solo parole intere**: selezionare questa opzione per cercare l&#39;intera stringa di ricerca. Ad esempio, se si immette nella stringa di ricerca, il risultato della ricerca restituirà tutti i file contenenti parole come over e overview. Se si desidera limitare la ricerca per restituire il termine specificato, selezionare questa opzione.

   - **Includi riferimenti indiretti**: selezionare questa opzione se si desidera cercare la stringa nei riferimenti indiretti anche all&#39;interno della mappa DITA. Per impostazione predefinita, questa opzione è disabilitata, pertanto la ricerca viene eseguita solo sui riferimenti diretti.

   ![](images/find-filters.png){width="350" align="left"}

1. Premi Invio o seleziona l&#39;icona **Cerca** per eseguire la ricerca.

   ![](images/search-icon.png){width="350" align="left"}

1. Selezionare un file dall&#39;elenco dei risultati della ricerca. Il file viene aperto nella visualizzazione Autore nell’area di modifica del contenuto con il termine cercato evidenziato nel contenuto.

1. Immettere il termine da utilizzare come sostituto nel campo **Sostituisci con**. Per personalizzare la modalità di applicazione delle sostituzioni, fare clic sull&#39;icona **Impostazioni** accanto al campo e scegliere tra le opzioni disponibili.

   - **Blocca il file prima di sostituirlo**: selezionare questa opzione se si desidera bloccare automaticamente un file prima di sostituire la stringa di ricerca. Questa impostazione è più rilevante nel caso in cui l’amministratore abbia abilitato la configurazione per bloccare un file prima della modifica. Con l’impostazione di back-end attivata, seleziona questa opzione. In questo modo, la finestra di dialogo relativa al blocco dei file non richiederà di bloccare ogni file prima di apportare qualsiasi modifica. Se non si seleziona questa opzione, prima di aprire un file per la modifica verrà visualizzato un messaggio.

   - **Crea nuova versione dopo la sostituzione**: selezionare questa opzione se si desidera creare una nuova versione dell&#39;argomento in cui si sceglie di sostituire il testo. Puoi anche fornire commenti sulla versione che verranno aggiunti a ogni file aggiornato. Se non si seleziona questa opzione, le modifiche verranno salvate nella versione corrente dell&#39;argomento e non verrà creata alcuna nuova versione.

   ![](images/replace-settings.png){width="350" align="left"}


1. Seleziona **Sostituisci occorrenza** per sostituire la stringa di ricerca attualmente evidenziata nell&#39;argomento o seleziona le frecce in alto e in basso per passare all&#39;occorrenza successiva o precedente del testo

   ![](images/replace-occurrence.png){width="350" align="left"}

1. Selezionare **Sostituisci tutto** per sostituire tutte le occorrenze del termine ricercato in un unico file con il termine sostitutivo in un&#39;unica operazione. Dopo la sostituzione di tutte le occorrenze nel file selezionato, verrà visualizzata una notifica.

   >[!NOTE]
   >
   > Per abilitare l&#39;icona **Sostituisci tutto**, l&#39;amministratore del profilo della cartella o l&#39;amministratore di sistema deve selezionare l&#39;opzione **Abilita Sostituisci tutto** nella scheda **Generale** in **Impostazioni Workspace** (come **Impostazioni** per **Prem**). Se si verificano errori durante l&#39;operazione di sostituzione, tali file verranno ignorati a causa di problemi di analisi XML o di errori DITA.

   ![](images/replace-all.png){width="350" align="left"}

1. È inoltre possibile passare il cursore del mouse su un file dall&#39;elenco dei risultati della ricerca per visualizzare l&#39;icona **Sostituisci tutto nel file** sulla destra, che consente di sostituire tutte le occorrenze del termine in un unico file.

   >[!NOTE]
   >
   > Per rimuovere il file dal risultato della ricerca, viene inoltre visualizzata l&#39;icona **Rimuovi**. I file rimossi vengono rimossi dall&#39;elenco e il termine cercato non viene sostituito al loro interno.

   ![](images/replace-all-in-file-no-source.png){width="350" align="left"}

È possibile eseguire una sola operazione di sostituzione alla volta nell&#39;intero sistema e, fino a quando non viene eseguita, verrà visualizzato lo stato &quot;Sostituisci tutto in corso&quot;. Puoi anche interrompere l’operazione Sostituisci tutto tra o visualizzare il rapporto del registro. Se si interrompe l&#39;operazione, si riceverà una notifica nella Posta in arrivo. Dopo la sostituzione di tutte le occorrenze nel file selezionato, verrà visualizzata una notifica di esito positivo.

![](images/replace-all-in-progress.png){width="350" align="left"}

È inoltre possibile utilizzare l&#39;opzione **Trova in mappa** dal menu **Opzioni** di una mappa per trovare e sostituire il testo in una mappa. Questa opzione viene visualizzata per una mappa aperta nel pannello del repository o nella vista mappa.

![](images/map-options-menu.png){width="650" align="left"}

</details>

## Modelli PDF

Consente di utilizzare diversi modelli di PDF. Per ulteriori dettagli, visualizzare [modelli di PDF](../native-pdf/pdf-template.md).

## Rivedere

In Experience Manager Guides è disponibile la funzione che consente di visualizzare tutte le attività di revisione nei progetti. Puoi visualizzare tutti i progetti di revisione e le attività di revisione attive nei progetti di revisione di cui fai parte dal pannello **Revisione**.  È quindi possibile aprire le attività di revisione per visualizzare i commenti dei vari revisori.

Nel pannello Revisione vengono visualizzate le attività di revisione. Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

In qualità di autore, puoi indirizzare i commenti in un argomento utilizzando l’Editor.

<details>
    <summary> Passaggi per rivedere i commenti </summary>


Per visualizzare i commenti di revisione nelle attività di revisione attive presenti nei progetti, effettuare le seguenti operazioni:

1. Seleziona Revisione nel pannello a sinistra. Viene aperto il pannello **Rivedi**.  Vengono visualizzati tutti i progetti di revisione e le attività di revisione attive all&#39;interno dei progetti di revisione di cui fai parte.

   ![](images/web-editor-review-panel.png){width="300" align="left"}
1. Selezionare un progetto di revisione e quindi selezionare un&#39;attività di revisione dall&#39;elenco per aprirla.
1. È possibile selezionare l&#39;icona **Apri dashboard progetti** per aprire il progetto nella console **Progetti**.

   ![](images/web-editor-project-dashboard.png){width="300" align="left"}

1. Puoi anche filtrare i progetti nei seguenti modi:

   - Immetti il termine o il testo da cercare nel titolo del progetto. Quindi premere Invio per eseguire la ricerca. Ad esempio, puoi cercare tutti i progetti il cui titolo contiene il termine &quot;spazio&quot;.

   - Selezionare ![](images/filter-search-icon.svg) per aprire la finestra di dialogo **Filtro**. Puoi selezionare tutti o solo progetti specifici. I progetti selezionati sono elencati nel pannello **Rivedi**.

     ![](images/active-review-select-project.png){width="300" align="left"}

     La finestra di dialogo **Filtro** include anche le seguenti opzioni che possono essere attivate o disattivate utilizzando l&#39;interruttore:

      - **Attività avviate da me**: se abilitata, mostra solo le attività avviate.
      - **Mostra solo le attività attive**: se questa opzione è attivata, filtra l&#39;elenco dei progetti in modo da visualizzare solo le attività attive.

     Per impostazione predefinita, entrambe le opzioni sono disabilitate. Inoltre, lo stato di attivazione selezionato viene mantenuto anche dopo l’aggiornamento della pagina.

1. Per impostazione predefinita, nel progetto di revisione viene visualizzato un elenco semplice di argomenti a cui sono associati commenti. Applica i filtri richiesti dalla barra a sinistra per filtrare gli argomenti in base ai commenti di revisione presenti in essi:

   - **Visualizza tutti gli argomenti**: elenca tutti gli argomenti presenti nei progetti.
   - **Visualizza argomenti con commenti**: elenca solo gli argomenti contenenti commenti di revisione.
1. È inoltre possibile immettere il termine di ricerca o il testo che si desidera trovare nel titolo o nel percorso del file dell&#39;argomento. Vengono elencati gli argomenti che contengono il termine nel titolo o nel percorso del file.
1. Fare doppio clic su un argomento per aprirlo nella visualizzazione Autore. Puoi visualizzare i commenti nel pannello **Commenti**.

   ![](images/active-review-task-comments.png){align="left"}

   >[!NOTE]
   > 
   > Il pannello **Rivedi** e il pannello **Commenti** sono sempre sincronizzati. Nel pannello Commenti, i commenti vengono caricati in base all&#39;attività di revisione caricata nel pannello Revisione.
   >È possibile visualizzare le attività di revisione chiuse nella barra a sinistra del Pannello revisione insieme alle attività di revisione attive.
   >Inoltre, per un&#39;attività di revisione chiusa è possibile visualizzare i commenti di revisione nel pannello Commenti a destra, ma i pulsanti **Importa commenti** e **Ripristina versione** sono disabilitati.
   >Per ulteriori informazioni su come gestire i commenti, visualizzare [Commenti sulla revisione degli indirizzi](review-address-review-comments.md#).

</details>

**Argomento padre:**[ Introduzione all&#39;editor](web-editor.md)
