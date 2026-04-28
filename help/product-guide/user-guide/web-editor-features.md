---
title: Conoscere le funzioni dell’editor
description: Scopri le funzioni dell’editor in Adobe Experience Manager Guides. Conoscere l’interfaccia dell’editor, inclusi la barra dell’intestazione, la barra delle schede, la barra degli strumenti, il pannello sinistro, l’area di modifica del contenuto e il pannello destro.
exl-id: 340cf72e-e44d-4df2-8312-50d00ac651b7
feature: Authoring, Features of Web Editor
role: User
hidefromtoc: true
hide: true
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '18790'
ht-degree: 0%

---

# Conoscere le funzioni dell’editor {#id176NC500V5Z}

Questa sezione descrive le varie funzioni disponibili nell’Editor. L’editor può essere suddiviso nelle sezioni o aree seguenti:

- [Barra intestazione](#header-bar)
- [Barra delle schede](#tab-bar)
- [Barra degli strumenti](#toolbar)
- [Pannello sinistro](#left-panel)
- [Area di modifica dei contenuti](#content-editing-area)
- [Pannello a destra](#right-panel)

La seguente sottosezione descrive in dettaglio le varie sezioni dell’Editor.

## Barra intestazione

La barra dell’intestazione è la barra superiore dell’editor che visualizza il logo Adobe Experience Manager (o Unified Shell se utilizzi Unified Shell come interfaccia utente di Experience Manager Guides). Quando selezioni il logo, viene visualizzata la pagina di navigazione di Experience Manager.

![](./images/aem-home-header.png)

Utilizza l&#39;icona **Espandi** nella barra degli strumenti per nascondere la barra dell&#39;intestazione e ingrandire l&#39;area del contenuto. Per ripristinare la visualizzazione standard, selezionare **Esci dalla visualizzazione espansa**.


## Barra delle schede

La barra delle schede si trova nella parte superiore dell’interfaccia dell’editor e consente di accedere alle seguenti funzioni:

![](./images/tab-bar.png)

**Schede**

Visualizza gli argomenti correntemente aperti nell&#39;Editor sotto forma di schede di file. È possibile aprire più argomenti contemporaneamente, che vengono visualizzati nelle rispettive schede nella barra delle schede. Per impostazione predefinita, è possibile visualizzare i titoli dei file nelle schede. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file per nome nelle schede. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione file editor** in [Preferenze utente](./intro-home-page.md#user-preferences).

Selezionando la scheda file si apre un menu di scelta rapida con le opzioni Salva come nuova versione, Copia, Individua in, Aggiungi a, Proprietà, Dividi, Scarica come PDF e Chiudi.

**Salva tutto**

Salva le modifiche apportate in tutti gli argomenti aperti. Se nell&#39;editor sono aperti più argomenti, se si seleziona **Salva tutto** o si utilizzano i tasti di scelta rapida **Ctrl**+**S** tutti i documenti vengono salvati con un solo clic. Non è necessario salvare ogni documento singolarmente.

>[!NOTE]
>
> L&#39;operazione **Salva tutto** non crea una nuova versione degli argomenti. Per creare una nuova versione, utilizzare l&#39;opzione **Salva come nuova versione**.

**Assistente IA**

Uno strumento potente e basato sull’intelligenza artificiale progettato per migliorare la produttività tramite funzioni di assistenza e authoring intelligenti. Riunisce due solide funzionalità di intelligenza artificiale, **Authoring** e **Guida**, nell&#39;interfaccia di Experience Manager Guides, consentendo di creare contenuti e accedere alle informazioni dalla documentazione di Experience Manager Guides in modo più rapido ed efficiente.

>[!NOTE]
>
>La funzione Assistente IA è attualmente disponibile per Adobe Experience Manager Guides as a Cloud Service.

**Espandi visualizzazione**: consente di espandere la visualizzazione della pagina utilizzando l&#39;icona **Espandi**. In questa visualizzazione, la barra dell&#39;intestazione contenente il logo Adobe Experience Manager è nascosta. In questo modo si ottimizza lo spazio del contenuto per la modifica. Per tornare alla visualizzazione standard, utilizzare l&#39;icona **Esci dalla visualizzazione espansa**.

**Altre azioni**: ti consente di passare alle **Assets** e **Impostazioni**.

L&#39;opzione **Assets** ti porta a una destinazione basata sulla configurazione:

- **Servizi cloud**: se utilizzi Servizi cloud, quando selezioni l&#39;opzione **Assets** vieni reindirizzato alla pagina di navigazione di AEM.

- **Software on-premise**: se si utilizza Adobe Experience Manager Guides (4.2.1 e versioni successive), se si seleziona l&#39;opzione **Assets**, verrà visualizzato il percorso del file corrente nell&#39;interfaccia utente di Assets.


L&#39;opzione **Impostazioni** è disponibile solo per gli amministratori e gli amministratori dei profili di cartella e consente di configurare le impostazioni seguenti:

>[!NOTE]
>
> Se si stanno aggiornando le impostazioni predefinite, è necessario riaprire i documenti per rendere effettive le modifiche.

- **Generale**: le impostazioni generali consentono di configurare il dizionario da utilizzare con l&#39;editor. Questa scheda contiene quattro sezioni: **Controllo ortografico**, **Condizione**, **Authoring** e **Citazioni**.

  ![](images/editor-setting-general.png){width="650" align="left"}

   - **Controllo ortografico**: sono disponibili due opzioni: **Controllo ortografico AEM** e **Controllo ortografico browser**. By default, the editor uses the Browser spell check feature, wherein the spell-check is performed using the browser&#39;s in-built dictionary. You can switch to AEM spell check to use Adobe Experience Manager&#39;s dictionary, which can also be customized to add your custom word list. For more information about customizing AEM dictionary, view [Customize AEM&#39;s default dictionary](../cs-install-guide/customize-aem-custom-dictionary.md) section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

   - **Condizione**

      - **Highlight conditional text in the Author view**: Select this to highlight the conditional text in the author view. Il contenuto condizionale viene evidenziato utilizzando il colore definito per la condizione.

      - **Validate with condition attributes**: Select this to allow the validation of the values defined for the attributes. Questo impedisce l’aggiunta di valori errati.

      - **Show key with the title in the Subject Scheme panel**: Select this to show the keys along with titles in the subject scheme. Se non si seleziona questa opzione, vengono visualizzati solo i titoli. Ad esempio, in questo caso, insieme ai titoli vengono visualizzati anche i tasti &quot;os&quot;, &quot;audience&quot; e &quot;other&quot;.

        ![](images/subject-scheme-title.png){width="550" align="left"}

      - **Show subject scheme in the Conditions panel**: Select this to view a subject scheme in the conditions panel. Se deselezionate questa opzione, le condizioni definite vengono visualizzate nel pannello condizioni.

   - **Authoring**

      - **Enable Replace All**: Select this to view the **Replace All** icon in the **Find and replace** panel.

   - **Citazioni**
Modificare lo stile delle citazioni. Scegli lo stile di citazione dal menu a discesa che desideri utilizzare nel progetto. For more details, view [Change citation styles](./web-editor-apply-citations.md#change-citation-style).

   - **AI Assistant**
Select this to enable the [AI Assistant](./ai-assistant.md) feature in the Experience Manager Guides. Unselect to disable the feature.

**Panels**: This setting controls the panels that are shown in the left and right panels of the Editor and Map console. You can toggle the button to show or hide the desired panel.

![](images/editor-setting-panel.png){width="650" align="left"}

You can also define the order in which the features present in panels are displayed. To change the default order of the available features in the panels, select the dotted bars to drag and drop the feature tabs at the desired location. A feature can also be moved from the **More** section to the main section of a panel, and vice versa as per the requirement. Once re-ordered, the features appear in the same sequence in the respective right and left panel.

![](images/panels-screen.png){width="650" align="left"}


A maximum of eight panels can be displayed at a time. Any changes made to the panel settings are applied immediately.


>[!NOTE]
>
> Se è stato configurato un pannello personalizzato, viene visualizzato anche nell’elenco dei pannelli. È possibile attivare o disattivare l&#39;opzione per mostrare o nascondere il pannello personalizzato.

- **Elements list**: As an administrator, you can control the list of elements that an author can insert into a file and also define the display name for the element. The Elements list setting allows you to specify the element&#39;s name as per DITA specifications and a label that you want to use instead of the DITA defined element name:

  ![](images/editor-setting-element-list.png){width="650" align="left"}

In the above screenshot, the `p` element has been given a label of Paragraph, and `codeblock` is given a label of Code Block along with some other elements.. If you select the **Use only above elements** option, then only the valid elements \(at current insertion point\) from this list will be shown in the **Insert element** dialog box.

In the following screenshot, only 3 out of 4 configured elements from the previous screenshot are shown in the current context:

![](images/editor-setting-insert-element-list.PNG){width="300" align="left"}

- **Attributes list**: Similar to the elements list, you can control the list of attributes and their display names to be displayed in the attributes list of an element. Nella schermata seguente, solo 3 attributi sono stati configurati per essere visualizzati nell’elenco degli attributi di un elemento:

  ![](images/editor-setting-attributes-list.png){width="650" align="left"}

  With this setting, when you try to add an attribute to an element, you only view the list of attributes configured in the list.

  ![](images/editor-setting-add-attributes-list.png){width="300" align="left"}

- **Colors**: Displays a list of pre-configured background colors for **Conditions**. Users can select a background color when applying a condition to a topic. As an administrator, you can also create and add custom background colors to the list. To add a new color, enter the desired name in the **Color Name** field, choose a custom color, and select the **+** icon. The custom color will appear at the end of the color list.

- **Publish profiles**: This contains the Profiles that can be used to publish the **Knowledge Base** output. È possibile creare un nuovo profilo per una knowledge base di destinazione. Ad esempio, Salesforce o ServiceNow.

   - **Create a Salesforce profile**

     **Prerequisiti**

      - Crea un&#39;app connessa per Salesforce. Per ulteriori dettagli, consulta [Abilitare le impostazioni OAuth per l&#39;integrazione API](https://help.salesforce.com/s/articleView?id=sf.connected_app_create_api_integration.htm&type=5).

      - Durante la configurazione dell’app connessa, verifica quanto segue:

         - Specifica il callback.

           `URL: http://<server name>:<port>/bin/dxml/thirdparty/callback/salesforce`

         - Selezionate i seguenti ambiti OAuth:
            - Accesso completo (completo)
            - Seleziona Gestisci dati utente tramite API (api)

     Una volta configurata l&#39;app, Salesforce fornisce **Chiave consumer** e **Segreto consumer**. Possono essere utilizzati per creare il profilo Salesforce.


   - Per creare un profilo Salesforce, selezionare la Knowledge Base **Salesforce** dal menu a discesa **Tipo di server**. Immettere un nome di profilo. Nell&#39;**URL sito**, immettere il sito consumer da utilizzare per pubblicare l&#39;output, quindi aggiungere la **Chiave consumer** e il **Segreto consumer** forniti dal sito consumer di Salesforce. Quindi **Convalida** e **Salva** il nuovo profilo creato.

     ![profilo di pubblicazione salesforce nelle impostazioni dell&#39;editor](./images/salesforce-publish-profile.png){width="550" align="left"}

     >[!NOTE]
     >
     >Per configurare un proxy per Salesforce in Experience Manager Guides, utilizza la configurazione proxy dei componenti HTTP Apache in AEM. Scopri come [configurare il proxy per AEM Link Checker](https://helpx.adobe.com/experience-manager/kb/How-to-configure-proxy-for-the-AEM-Link-Checker-AEM.html).


   - **Creare un profilo ServiceNow**

     **Prerequisiti**

     Configura il server ServiceNow per caricare le risorse.
      - Connetti al server **ServiceNow**.
      - Passa a **Proprietà di sistema** > **Sicurezza**.
      - Deseleziona la seguente opzione:

        **Questa proprietà deve essere impostata per attivare la verifica del tipo MIME per i caricamenti (tutte le versioni Eureka e successive). Abilita (true) o disabilita (false) la convalida del tipo MIME per i file allegati. Le estensioni file configurate tramite glide.attachment.extensions verranno controllate per verificare la presenza di tipi MIME durante il caricamento.**

      - Seleziona **Salva**.

     Dopo aver configurato l&#39;app, crea il profilo **ServiceNow**.

   - Per creare un profilo, selezionare la Knowledge Base ServiceNow dal menu a discesa **Tipo di server**. Immetti un profilo **Nome**. Nell&#39;**URL ServiceNow**, immettere il sito consumer da utilizzare per la pubblicazione dell&#39;output, quindi aggiungere **Nome utente** e **Password** forniti dal sito consumer ServiceNow. Quindi **Convalida** e **Salva** il nuovo profilo creato.

     ![Profilo di pubblicazione ServiceNow](./images/service-now-publish-profile.png){width="550" align="left"}

  Dopo la convalida, è possibile selezionare il profilo di pubblicazione nei predefiniti di output di una mappa DITA e utilizzarlo per generare l&#39;output nel server **Salesforce** o **ServiceNow** scelto.

  Ulteriori informazioni sul predefinito di output [Knowledge Base](../user-guide/generate-output-knowledge-base.md).


- **Convalida**: questa scheda contiene le opzioni per configurare le convalide Schematron nell&#39;Editor. È possibile attivare le seguenti funzionalità:

   - **Eseguire il controllo di convalida prima di salvare il file**: selezionare questa opzione per eseguire le convalide Schematron utilizzando i file Schematron selezionati prima di eseguire qualsiasi operazione di salvataggio. Potete aggiungere un file Schematron selezionando l&#39;icona +. Vengono elencati i file Schematron selezionati.

     >[!NOTE]
     >
     >I file Schematron selezionati persisteranno per il profilo di cartella selezionato.

     ![Convalida nelle impostazioni dell&#39;editor](./images/editor-setting-validation.png){width="550" align="left"}

     In questo modo si impedisce agli utenti di salvare qualsiasi file che non rispetti una regola definita nei file Schematron selezionati. Se questa opzione non è selezionata, il file non verrà convalidato prima di salvare le modifiche.

   - **Consenti a tutti gli utenti di aggiungere file schematron nel pannello di convalida**: selezionare questa opzione per consentire agli utenti di aggiungere qualsiasi file Schematron nel pannello di convalida dell&#39;editor. Questo consente agli utenti di aggiungere file Schematron e quindi convalidare gli argomenti rispetto al file Schematron. Se questa opzione non è selezionata, l&#39;opzione per aggiungere il file schematron **Aggiungi file schematron** non è disponibile per gli utenti nel **pannello di convalida** dell&#39;editor.


- **Visualizza attributi**: come l&#39;elenco Attributi, è possibile controllare l&#39;elenco degli attributi da visualizzare nell&#39;elenco degli attributi di un elemento. Per impostazione predefinita, quattro **Attributi di visualizzazione**: pubblico, piattaforma, prodotto e proprietà sono stati configurati per essere visualizzati nell&#39;elenco degli attributi di un elemento. Puoi anche aggiungere un attributo di visualizzazione utilizzando l&#39;icona **Aggiungi** nella parte superiore. Puoi anche eliminare gli attributi di visualizzazione utilizzando l&#39;icona **Elimina**.

  Gli attributi definiti per un elemento vengono visualizzati nella vista Layout e Struttura.

  ![](images/editor-settings-display-attributes.png){width="550" align="left"}

- **Traduzione**: questa scheda contiene le opzioni per creare gruppi di lingue, propagare le etichette di origine alla versione di destinazione e ripulire il progetto di traduzione.

  ![](images/editor-setting-translation.png){width="550" align="left"}

   - **Gruppi di lingue**: in qualità di amministratore, puoi creare un gruppo di lingue e utilizzarle come set per tradurre il contenuto.

     Per creare un nuovo gruppo di lingue, effettuare le operazioni riportate di seguito.

      1. Seleziona **Aggiungi**.
      1. Immettere il nome del gruppo di lingue. Each language should have a unique name. You can view an error if the name field is empty or if the name isn&#39;t unique.
      1. Select the languages from the dropdown. You can select multiple languages.

         Type the first few characters of the language, or the language code to filter the desired languages. For example, type &#39;en&#39; to filter all the languages that contain &#39;en&#39; at the beginning of their name or code.

      1. Select the Done icon to add the selected languages to the group. The languages are displayed. When you add three or more languages, the **Show more** option is displayed. You can select **Show more** to view all the languages present in the group.

         >[!TIP]
         >
         >Toggle **Show more** to **Show less** and view only a few languages.

      1. Hover over the languages in a group to edit ![edit icon](images/edit_pencil_icon.svg) or delete ![delete](images/Delete_icon.svg) the language groups.
      1. Save the **Settings**.

         >[!NOTE]
         >
         >In qualità di utente, puoi visualizzare i gruppi di lingue configurati nel tuo profilo di cartella.

   - **Propagate source version labels to the target version**: Select this option to pass the label of the source file version to the translated file. By default, this is disabled.
   - **Translation project cleanup after completion**: Select this option to configure the translation projects to be disabled or deleted automatically after the translation. By default, **None** is selected, so that the project exists after translation.

     You can disable the translation projects if you want to use them later. Deleting a project permanently deletes all files and folders present in the project.


- **Metadata**: You can control the version metadata of the topic and their values to be displayed in the **Version history** dialog box.  Nel percorso metadati, specifica la posizione dei nodi da cui desideri scegliere i metadati. Puoi anche definire un nome personalizzato per i metadati come etichetta. Le proprietà predefinite sono Titolo, Stato documento e Tag.

  I metadati possono essere scelti da qualsiasi proprietà sotto il nodo `/jcr:content` della risorsa, in modo da poter aggiungere il percorso della proprietà come percorso dei metadati.


  Se il percorso dei metadati è vuoto, viene visualizzato un errore. Se si lascia vuota l&#39;etichetta, l&#39;ultimo elemento viene scelto come etichetta.


  ![scheda metadati nelle impostazioni dell&#39;editor](images/editor-setting-metadata.png){width="550" align="left"}

  *Configurare i metadati per la finestra di dialogo **Cronologia versioni**.*



  Puoi anche definire l’ordine in cui vengono visualizzati questi tag di metadati. Per modificare l’ordine predefinito di questi tag, seleziona le barre punteggiate per trascinare i tag nella posizione desiderata.
Le etichette metadati vengono visualizzate nella stessa sequenza nella finestra di dialogo **Cronologia versioni** dell&#39;editor.

## Barra degli strumenti

La barra degli strumenti viene visualizzata quando si apre un argomento o una mappa per la modifica nell&#39;editor. Le funzioni disponibili nella barra degli strumenti sono le seguenti:

- [Menu a discesa](#menu-dropdown)
- [Opzioni di inserimento contenuti](#content-insertion-options)
- [Informazioni sulla versione e pulsante Salva come nuova versione](#save-as-new-version)
- [Blocca/sblocca](#lockunlock)

>[!NOTE]
>
> Le funzioni elencate sopra sono applicabili solo ai file di argomento. Quando si lavora con un file mappa, nella barra degli strumenti vengono visualizzate opzioni diverse in base alla vista dell’editor mappa corrente. Scopri le opzioni della barra degli strumenti dell&#39;editor mappe nel documento [Funzioni dell&#39;editor mappe](./map-editor-advanced-map-editor.md).

### Menu a discesa

Il menu a discesa consente di accedere alle azioni di modifica, Trova e sostituisci, Cronologia versioni, Etichetta versione, Unione, Crea attività di revisione, Traccia modifiche e Funzione tag.

La spiegazione dettagliata di queste caratteristiche è la seguente:

**Modifica delle azioni**

Durante la modifica di un argomento nell&#39;editor, accedere alle varie azioni di modifica, ad esempio **Taglia** o ***Ctrl***+***X*** , **Copia** o ***Ctrl***+***C*** , **Annulla** o ***Ctrl***+***Z*** , **Ripristina** o ***Ctrl***+***Y*** e **Elimina** presente nel menu a discesa.


**Trova e sostituisci**

La funzionalità **Trova e sostituisci** è disponibile nelle modalità di visualizzazione Creazione e Source. Quando questa opzione è attivata, la barra di testo Trova e sostituisci viene visualizzata nella parte inferiore dell&#39;area di modifica dell&#39;argomento. È possibile utilizzare i tasti di scelta rapida **CTRL**+**F** per richiamare la barra Trova e sostituisci.

![](images/find-replace-bar.png){align="left"}

Using the settings icon \(![](images/settings-find-replace-icon.svg)\), you can toggle the **Ignore case** and **Whole word only** search options. To perform the case-insensitive search, turn on (or select) the **Ignore case** option. Else, if you want to perform the case-sensitive search, turn off (or deselect) the **Ignore case** option. È inoltre possibile scegliere di cercare una parola intera.

La ricerca è istantanea, il che significa che quando si digita la frase o la parola di ricerca nel campo **Trova**, il termine viene immediatamente cercato e selezionato nell&#39;argomento. Similarly, for replacing a text in your topic, enter the search term and its replacement in the respective fields and select the **Replace** or **Replace All** button.

In the Source view, the **Find and replace** feature is extremely useful for searching for a specific element or attribute. Ad esempio, se desideri sostituire il valore dell&#39;attributo `@product`, puoi eseguirlo facilmente dalla vista Source. La visualizzazione Autore non consente di eseguire ricerche sulla base di un attributo o di un elemento. Tuttavia, è necessario prestare attenzione quando si utilizza la funzionalità **Sostituisci tutto**, in quanto potrebbe sovrascrivere il codice XML.

**Version history**

The **Version history** feature in the Editor allows you to check the available versions of your DITA files, compare them, and revert to any version from the Editor itself. You can compare the content and metadata of the current version (which can also be a working copy) with any previous version of the same file. Puoi anche visualizzare le etichette e i commenti per le versioni confrontate.

>[!NOTE]
>
> The Version history options only appear if there are changes made to the first version of the topic or map.

Per accedere alla cronologia delle versioni e ripristinare una versione specifica dell&#39;argomento, effettuare le seguenti operazioni:

1. Open a topic in the Editor.
1. Select **Version history** from the **Menu** dropdown.

   Viene visualizzata la finestra di dialogo **Cronologia versioni**.

   ![Version history dialog box](images/version-history-dialog-web-editor.png){width="550" align="left"}

   *Visualizzare in anteprima le modifiche nelle diverse versioni di un argomento.*

1. Scegliere una versione dell&#39;argomento da confrontare o ripristinare nell&#39;elenco a discesa **Confronta con**.

   >[!NOTE]
   >
   > Se a una versione sono applicate etichette, queste vengono visualizzate anche \(tra parentesi\) insieme al numero di versione.

1. Enable the **View labels and comments** option to view the labels and comments applied to the current and the compared versions.
1. You can also view the following information in the **Version history** dialog box:

   Scheda **Anteprima**: il contenuto appena aggiunto è in verde e il contenuto eliminato in rosso.

   Scheda **Metadati**: i metadati appena aggiunti sono in verde e quelli eliminati in rosso.

   ![Metadata difference for versions &#x200B;](images/metadata-version-diff.png){width="550" align="left"}

   *Confrontare i metadati di diverse versioni nella cronologia delle versioni.*

   >[!NOTE]
   >
   > Your system administrator can change the metadata to be shown from the Metadata tab in the **Settings**. For details, refer to the **More actions** section of the [Tab bar](#tab-bar).

   Puoi anche visualizzare i dettagli dell’utente e dell’ora della versione corrente e della versione confrontata.

   Once you choose a version from the drop-down list, the **Revert to selected version** option is made available. Nella finestra di anteprima vengono visualizzate le differenze tra la versione corrente e la versione selezionata dell&#39;argomento.

1. Select **Revert to selected version** to revert your working copy with the selected version of the topic.

   The Revert Version dialog box appears.

   ![](images/version-history-revert-dialog-save-working-copy.png){width="550" align="left"}

1. \(*Facoltativo*\) Fornire un motivo per ripristinare una versione precedente. È inoltre possibile creare una nuova versione della copia di lavoro attiva dell&#39;argomento.

1. Select **Confirm.**

   La copia di lavoro del file viene ripristinata alla versione selezionata. Se si sceglie di creare una nuova versione della copia di lavoro attiva, viene creata anche una nuova versione del file con tutte le modifiche di lavoro.

   Quando si ripristina una versione precedente, viene visualizzato un segnale visivo che indica che la versione su cui si sta lavorando non è quella più recente.

   ![](images/older-version-visual-cue.png){align="left"}

**Version labels**

Labels help you identify the stage in which a particular topic is in the DDLC (Document Development Life Cycle). Ad esempio, quando si lavora su un argomento, è possibile impostare l&#39;etichetta come &quot;Approvato&quot;. Quando un argomento viene pubblicato e reso disponibile ai clienti, puoi assegnare l’etichetta &quot;Rilasciato&quot; a tale argomento.

Experience Manager Guides allows you to specify labels in a free-form text format or use a set of predefined labels. L’etichetta personalizzata consente a qualsiasi autore nel sistema di specificare un’etichetta in base alla propria scelta. Questo offre flessibilità, ma introduce etichette non coerenti nel sistema. Per risolvere questo problema, gli amministratori possono configurare un set di etichette predefinite. Per ulteriori informazioni sulla configurazione delle etichette predefinite, visualizzare *Configurare e personalizzare l&#39;editor Web XML* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

Queste etichette vengono visualizzate sotto forma di elenco a discesa agli autori ogni volta che devono specificare un’etichetta. In questo modo nel sistema verranno utilizzate solo etichette coerenti e predefinite.

Esistono diversi metodi tramite i quali è possibile applicare etichette agli argomenti: [Pannello Cronologia versioni](web-editor-use-label.md) nell&#39;interfaccia utente di Assets, [Interfaccia baseline](/help/product-guide/user-guide/generate-output-use-baseline-for-publishing.md) e nell&#39;editor. La funzione Etichetta versione nell’editor consente agli autori di assegnare etichette ai loro argomenti in modo rapido e semplice.

Per aggiungere etichette all&#39;argomento dall&#39;editor, effettuare le seguenti operazioni:

1. Aprire un argomento nell&#39;editor.

1. Seleziona **Etichette versione** dal menu a discesa.

   Viene visualizzata la finestra di dialogo Gestione etichette versione.

   ![](images/version-label-management-dialog.png){width="650" align="left"}

   La finestra di dialogo Gestione etichette versione è suddivisa in due parti: nel pannello a sinistra è disponibile un elenco di versioni per l&#39;argomento con l&#39;elenco a discesa delle etichette \(o una casella di testo per immettere un&#39;etichetta\) e nel pannello a destra con un&#39;anteprima dell&#39;argomento.

1. Selezionare la versione alla quale si desidera applicare le etichette.

   Quando si sceglie una versione diversa dell&#39;argomento dall&#39;elenco delle versioni, nel pannello di anteprima vengono visualizzate le modifiche tra la versione corrente e la versione selezionata dell&#39;argomento

   >[!NOTE]
   >
   > Se un&#39;etichetta è già applicata a una versione, viene visualizzata accanto al numero di versione nell&#39;elenco a discesa e sotto l&#39;elenco Seleziona versione. È possibile rimuovere un&#39;etichetta esistente selezionando l&#39;icona \(**x**\) accanto all&#39;etichetta.

1. Se l&#39;amministratore ha definito un elenco di etichette, viene visualizzato un elenco a discesa delle etichette da cui è possibile scegliere le etichette da applicare. Puoi selezionare più etichette dall’elenco a discesa.

   Viene inoltre visualizzata una casella di testo in cui è possibile immettere le etichette che si desidera aggiungere all&#39;argomento.

   >[!NOTE]
   >
   > Non è possibile applicare la stessa etichetta a più versioni di un argomento. Se si tenta di associare un&#39;etichetta esistente, è possibile rimuoverla dalla versione esistente e applicarla alla versione selezionata dell&#39;argomento.

1. Selezionare **Aggiungi etichetta**.

1. Nel messaggio di conferma Applica etichetta, selezionare l&#39;opzione **Sposta etichetta (se utilizzata in un&#39;altra versione)** per spostare le etichette da una versione esistente alla versione selezionata. Se non si seleziona questa opzione e sono presenti etichette assegnate a una versione diversa dell&#39;argomento, tali etichette non verranno spostate nella versione dell&#39;argomento selezionato. Tali etichette vengono ignorate nel processo di applicazione delle etichette.

**Unisci**

Quando si lavora in un ambiente con più autori, diventa difficile tenere traccia delle modifiche apportate da altri autori in un argomento o in una mappa. La funzione di unione consente di controllare non solo le modifiche, ma anche le modifiche mantenute nell&#39;ultima versione del documento.

- **Unisci file argomenti**

  Per unire le modifiche in un argomento, effettuare le seguenti operazioni:

   1. Aprire un argomento nell&#39;editor.

   1. Seleziona **Unisci**.

      Viene visualizzata la finestra di dialogo Unisci.

      ![](images/merge-changes-in-topic.png){width="550" align="left"}

   1. *\(Facoltativo\)* È inoltre possibile sfogliare e selezionare un nuovo file da un&#39;altra posizione nell&#39;archivio.

   1. Selezionare una versione del file con cui si desidera confrontare la versione corrente del file.

   1. In Opzioni, scegliere:

      - **Rileva modifiche dalla versione selezionata**: questa opzione mostra tutti gli aggiornamenti di contenuto sotto forma di revisioni. È quindi possibile scegliere di accettare o rifiutare le modifiche nel documento una alla volta o tutte contemporaneamente.

      - **Ripristina la versione selezionata**: questa opzione ripristina la versione corrente del documento alla versione selezionata. Questa opzione non consente di controllare quale contenuto viene accettato o rifiutato.

   1. Seleziona **Fine**.

   1. Se hai selezionato l&#39;opzione **Rileva modifiche dalla versione selezionata**, tutte le modifiche dalla versione selezionata vengono visualizzate nella funzione Tracciamento modifiche nel pannello di destra.

      Potete scegliere di accettare o rifiutare tutti i commenti dal pannello Modifiche tracciate oppure accettare o rifiutare un singolo commento.


- **Unisci file mappa**

  Per unire le modifiche in un file di mappa, effettuare le seguenti operazioni:

   1. Apri una mappa nell’editor.

   1. Seleziona **Unisci**.

      Viene visualizzata la finestra di dialogo Unisci (Merge).

      ![](images/merge-changes-in-map.png){width="550" align="left"}

   1. *\(Facoltativo\)* È inoltre possibile sfogliare e selezionare un nuovo file da un&#39;altra posizione nell&#39;archivio.

   1. Selezionare una versione del file con cui si desidera confrontare la versione corrente del file.

   1. In Opzioni, scegliere:

      - **Rileva modifiche dalla versione selezionata**: questa opzione mostra tutti gli aggiornamenti del contenuto sotto forma di revisioni. È quindi possibile scegliere di accettare o rifiutare le modifiche nel documento una alla volta o tutte contemporaneamente.

      - **Ripristina la versione selezionata**: questa opzione ripristina la versione corrente del documento alla versione selezionata. Questa opzione non consente di controllare quale contenuto viene accettato o rifiutato.

   1. Seleziona **Fine**.

   1. Se hai selezionato l&#39;opzione **Rileva modifiche dalla versione selezionata**, tutte le modifiche dalla versione selezionata vengono visualizzate nel pannello Revisioni \(a destra\).

      Potete scegliere di accettare o rifiutare tutte le modifiche dal pannello Revisioni tracciate oppure accettare o rifiutare singole modifiche nel file di mappa.


**Crea attività di revisione**

Puoi [creare un&#39;attività di revisione](./review-send-topics-for-review.md) dell&#39;argomento corrente o mappare il file direttamente dall&#39;editor. Aprire il file per il quale si desidera creare l&#39;attività di revisione e selezionare **Crea attività di revisione** dal menu a discesa per avviare il processo di creazione della revisione.

**Rileva modifiche**

È possibile tenere traccia di tutti gli aggiornamenti apportati a un documento abilitando la modalità Revisioni. Dopo aver abilitato le modifiche di traccia, tutti gli inserimenti e le eliminazioni vengono acquisiti nel documento. Tutto il contenuto eliminato viene evidenziato con il metodo Barrato e tutti gli inserimenti vengono evidenziati in verde. Vengono inoltre visualizzate le barre di modifica sul bordo della pagina dell&#39;argomento. Di nuovo, viene visualizzata una barra rossa per il contenuto eliminato e una barra verde per il contenuto aggiunto. Nel caso in cui vi sia un&#39;aggiunta e un&#39;eliminazione sulla stessa riga, vengono visualizzate entrambe le barre verdi e rosse.

La schermata seguente evidenzia il contenuto eliminato e inserito insieme alle barre di modifica:

![](images/track-changes-content.png){width="650" align="left"}

Un caso d’uso tipico per il tracciamento delle modifiche in un documento può essere la revisione tra pari. È possibile abilitare la registrazione delle modifiche e condividere il documento per la revisione, quindi il revisore apporta le modifiche con la registrazione delle modifiche attivata. Quando ricevi il documento, dovresti disporre di un meccanismo per visualizzare gli aggiornamenti suggeriti e di un modo pratico per accettare o rifiutare le modifiche.

In Experience Manager Guides è disponibile la funzione Tracked changes che contiene informazioni sugli aggiornamenti apportati nel documento. La funzione Tracked changes (Modifiche tracciate) fornisce informazioni sugli aggiornamenti effettuati, su chi li ha effettuati e in quale momento. Tramite la funzione Modifiche rilevate, è inoltre possibile accettare o rifiutare facilmente gli aggiornamenti suggeriti nel documento.

Per accedere alla funzione, seleziona l&#39;icona **Rileva modifiche** nel pannello di destra.

![](images/changes-panel_cs.png){width="300" align="left"}

Se si seleziona una revisione, viene selezionato il contenuto modificato nel documento. Potete accettare una modifica selezionando l&#39;icona Accetta modifica (Accept Change) oppure rifiutarla selezionando Rifiuta modifica (Rifiuta change).

Per accettare o rifiutare tutte le modifiche con un solo clic, selezionare **Accetta tutte le modifiche** o **Rifiuta tutte le modifiche**.

>[!NOTE]
>
> La modalità Anteprima consente di visualizzare il documento con o senza i markup del contenuto modificato. For more details, view the [Preview](web-editor-views.md#preview-mode-id19AAGL00163) mode.

**Tag**

The **Tags** feature in the Editor is a toggle button that controls the visibility of DITA elements. When enabled, it displays structural tags within the content, allowing you to view and manage the underlying DITA elements more effectively. When disabled, the editor hides these tags, providing a cleaner and more focused authoring environment.

The following screenshot shows a document with the Tags view enabled:

![](images/tags-view.png){width="650" align="left"}

The following operations can be performed in a document with Tags:

- **Select an element**: Select the opening or closing tag of an element to select its content.

- **Expand or collapse tags**: Select the + or - sign in a tag to expand or collapse it.

- **Use the context menu**: The context menu provides options to cut, copy, or paste the selected element. You can also insert an element before or after the selected element. The other options allow you to Generate ID or open the Properties panel for the selected element.

- **Drag-and-drop elements**: Select an element&#39;s tag and easily drag-and-drop it on your document. If the drop location is a valid location where the element is allowed, the element is placed at the dropped location.


>[!NOTE]
>
> If a user enables the Tags view from the Editor, it remains enabled even across the sessions. This means that you don&#39;t have to enable the Tags view again to access it later. The default value for Tags view for a new user&#39;s session is determined by the `tagsView` property in the `ui\_config.json` file. For more details, view the [Configure default value for Tags View](../cs-install-guide/configure-default-value-tags-view.md) section in Install and configure Adobe Experience Manager Guides as a Cloud Service.

### Opzioni di inserimento contenuti

**Element** - ![](images/Add_icon.svg)

Inserisce un elemento valido nella posizione valida corrente o successiva. You can also use the keyboard shortcut ***Alt***+***Enter*** to open the Element dialog box. For example, you are editing a paragraph, then in the **Element** dialog box, a list of elements appears that can be inserted in the paragraph. Seleziona l’elemento da inserire. Puoi usare la tastiera per scorrere l&#39;elenco degli elementi e premere ***Invio*** per inserire l&#39;elemento richiesto.

Puoi visualizzare due tipi di elementi validi:

- **Elementi validi nella posizione corrente**: nell&#39;elenco vengono visualizzati gli elementi che è possibile inserire nella posizione corrente del cursore.

- **Elementi validi al di fuori del percorso corrente**: nell&#39;elenco vengono visualizzati gli elementi che è possibile inserire dopo qualsiasi elemento padre per l&#39;elemento corrente all&#39;interno della gerarchia degli elementi.

Ad esempio, se ti trovi all&#39;interno dell&#39;elemento in linea `<b>`, puoi inserire elementi come `<u>`, `<xref>`, `<i>` nella posizione corrente. È invece possibile inserire elementi come `<table>` e `<topic>` al di fuori del percorso corrente.

È inoltre possibile digitare un carattere o una stringa nella casella di ricerca e cercare gli elementi che iniziano con essa.

![inserisci elemento](images/insert-element.png){width="300" align="left"}

*Immettere &#39;t&#39; per cercare tutti gli elementi validi che iniziano con &#39;t&#39;.*

Se si lavora all&#39;interno di un elemento blocco come `note`, utilizzare l&#39;icona Inserisci elemento per inserire un nuovo elemento dopo l&#39;elemento `note`. Nella schermata seguente è stato inserito un elemento nota all’interno dell’elemento p \(paragrafo\):

![Inserisci elemento in un elemento di blocco](images/note-in-para-insert-element_cs.png){align="left"}

Se si preme Invio nell&#39;elemento nota, viene creato un nuovo paragrafo all&#39;interno dell&#39;elemento nota stesso. Per inserire un nuovo elemento all&#39;esterno di una nota, seleziona l&#39;elemento p \(evidenziato nella schermata\) nella breadcrumb degli elementi, quindi seleziona l&#39;icona Elemento o premi ***Alt***+***Invio*** per aprire la finestra di dialogo Inserisci elemento. Quindi, selezionate l&#39;elemento desiderato e premete Invio per inserire l&#39;elemento selezionato dopo l&#39;elemento nota.

È inoltre possibile aggiungere un elemento tra due elementi quando viene visualizzato un cursore a blocchi lampeggiante.


![](images/Block-cursor.png){width="300" align="left"}

Ad esempio, se si sta lavorando su un argomento DITA e il cursore di blocco lampeggia tra la breve descrizione e il corpo, è possibile aggiungere l&#39;elemento `prolog` e quindi aggiungere il copyright, l&#39;autore e altri dettagli.

Un altro modo per immettere un nuovo elemento consiste nell’utilizzare il menu di scelta rapida. Fare clic con il pulsante destro del mouse in qualsiasi punto del documento per richiamare il menu di scelta rapida. Da questo menu scegliere **Inserisci elemento** per visualizzare la finestra di dialogo **Inserisci elemento** e scegliere l&#39;elemento che si desidera inserire.

![](images/insert-element-before-after.png){width="300" align="left"}

**Paragrafo** - ![](images/Paragraph_icon.svg)

Inserisce l&#39;elemento paragrafo nella posizione corrente o successiva valida.

**Elenco puntato** - ![](images/BulletList_icon.svg)

Crea un elenco puntato nel percorso valido corrente o successivo. Se ti trovi in un elenco puntato e fai clic su questa icona, l’elemento viene convertito in un paragrafo normale.

**Elenco numerato** - ![](images/TextNumbered_icon.svg)

Crea un elenco numerato nel percorso valido corrente o successivo. If you are on a numbered list and select this icon, the item is converted into a normal paragraph.

>[!NOTE]
>
>You can also select the **Split list** option from the context menu of a list item to split the current list and begin a new list at the same level.

**Table** - ![](images/Table_icon.svg)

Inserisce una tabella nella posizione valida corrente o successiva. Select the Table icon to open the Insert Simple Table dialog box.

![](images/table-properties.png){width="550" align="left"}

>[!NOTE]
>
> You can also copy a table from MS Word or Excel and paste it into the Experience Manager Guides topic file. The copied table will be pasted as either `<simpletable>` or `<tgroup>` depending on the settings configured in the XML Editor Configuration. For more details, view [Configure the display of pasted tables](../cs-install-guide/conf-pasted-tables.md).

È possibile specificare il numero di righe e colonne richieste nella tabella. If you want to keep the first row as the table header, select the **Set first row as header** option. Per aggiungere un titolo alla tabella, immetterlo nel campo Titolo.

Once a table is inserted, you can modify the table using the context menu.

![](images/table-context-menu_cs.png){width="550" align="left"}



Utilizzando il menu di scelta rapida della tabella, è possibile:

- Inserisci celle, righe o colonne

- Unire le celle nelle direzioni destra e giù

- Dividi celle in orizzontale o in verticale

- Eliminare celle, righe o colonne

- Genera ID


È inoltre possibile definire attributi su più celle, righe intere o colonne di una tabella. Ad esempio, per allineare la cella della tabella, trascinare e selezionare la cella desiderata. In the Content Properties panel (on the right), the property **Type** changes to **entry**.

1. In the **Attributes** section, select **+Add**.
1. Selezionare l&#39;attributo `@valign` dall&#39;elenco a discesa **Attributo**.
1. Dall&#39;elenco a discesa valore, selezionare l&#39;allineamento del testo che si desidera applicare alle celle di tabella selezionate.
1. Seleziona **Aggiungi.**

![](images/align-table-cell_cs.png){align="left"}

**Immagine** - ![](images/Image_icon.svg)

Inserisce un&#39;immagine nel percorso valido corrente o successivo. Selezionare l&#39;icona Immagine per aprire la finestra di dialogo Inserisci immagine, quindi cercare e selezionare l&#39;immagine da inserire.

>[!NOTE]
>
> Puoi anche aggiungere un’immagine trascinandola dal sistema locale sull’articolo. In questo caso, il file di immagine viene aggiunto utilizzando il flusso di lavoro **Carica Assets**.  Per ulteriori dettagli, visualizza il flusso di lavoro **Carica Assets** nella sezione [Pannello sinistro](#left-panel).


![](images/insert-image.png){width="650" align="left"}

Potete aggiungere un titolo immagine/figura e un testo alternativo per l&#39;immagine nella finestra di dialogo Inserisci immagine.

>[!NOTE]
>
> Quando si inserisce un&#39;immagine e si specifica un testo alternativo per lo stesso elemento, questo viene aggiunto all&#39;interno dell&#39;elemento `<alt>` in conformità agli standard DITA più recenti. L&#39;utilizzo dell&#39;attributo `@alt` per il testo alternativo è obsoleto, ma rimane supportato nelle versioni DITA precedenti.

Utilizzando l&#39;opzione **Seleziona file**, è possibile cercare il file di immagine richiesto in base al nome del file. Puoi anche filtrare i risultati della ricerca per Percorso \(per cercare in\), Raccolte, Tipo file e Tag. Dopo aver trovato il file di immagine richiesto, selezionare il file e scegliere **Seleziona** per inserire l&#39;immagine nel documento. È possibile inserire vari formati di file immagine, ad esempio `.png`, `.svg`, `.gif`, `.jpg`, `.eps`, `.ai`, `.psd` e altri.

Dopo aver inserito un&#39;immagine, potete modificarne l&#39;altezza, la larghezza, il posizionamento e gli attributi dal pannello Proprietà contenuto. Seleziona il file di immagine e apporta le modifiche desiderate nel pannello Proprietà contenuto nel pannello di destra.

![](images/image-properties.png){align="left"}

Nel campo Source viene visualizzato l’UUID del file immagine inserito. Per trovare il percorso completo del file immagine inserito, posizionare il puntatore del mouse sul campo Source. Il percorso viene visualizzato nella descrizione comando.

Per ridimensionare un&#39;immagine, specificate Altezza (Height) o Larghezza (Width) per il file di immagine. Le proporzioni dell&#39;immagine vengono mantenute automaticamente. Se lo desideri, puoi anche scegliere di non mantenere le proporzioni del file di immagine selezionando l’icona del lucchetto \(di Mantieni proporzioni\) e fornendo i valori di Altezza e Larghezza.

Potete inoltre specificare l&#39;impostazione Posizionamento (Placement) per l&#39;immagine come In linea (Inline) o Interruzione (Break). Se si sceglie di utilizzare l&#39;opzione di posizionamento Interrompi, è possibile scegliere dove allineare l&#39;immagine (a sinistra, al centro o a destra).

Puoi anche aggiungere altre proprietà per un file di immagine selezionando le proprietà richieste nel campo **Attributi**.

>[!NOTE]
>
>Puoi anche definire le aree cliccabili \(mappa immagine\) nell’immagine. For more details, view the **Insert/Edit Image Map** feature description in the [Left panel](web-editor-features.md#left-panel) section.

**Menu di scelta rapida per file immagine o multimediali**

È inoltre possibile eseguire alcune operazioni comuni per immagini e file multimediali utilizzando il menu di scelta rapida. Fare clic con il pulsante destro del mouse in qualsiasi punto dell&#39;immagine per richiamare il menu di scelta rapida.

Il menu di scelta rapida fornisce le opzioni per tagliare, copiare o incollare l&#39;immagine o il supporto. Puoi inserire un elemento prima o dopo l’elemento selezionato. È inoltre possibile rinominare o decomprimere un elemento. Puoi individuare l’immagine o il supporto selezionato nell’archivio oppure visualizzare l’anteprima del file nell’interfaccia utente di Assets.

The other options in the context menu allow you to copy a path, edit an image map, rename element, create a snippet, or generate IDs for the selected element.

**Insert/Edit Image Map**

Inserts an image map on the selected image. An image with clickable areas that link to topics or web pages is called an image map.

Select an image in the current topic and select the Insert/Edit Image Map icon to open the insert Image Map dialog box.

![](images/insert-image-map.png){width="650" align="left"}

Choose the preferred shape Rectangle ![](images/imagemap-rectangle-toolbar.png), Circle ![](images/imagemap-circle-toolbar.png), or Polygon ![](images/imagemap-polygon-toolbr.png) to define an area over an image that you want to use as a link. After defining an area, the Reference dialog appears wherein you need to specify the link to internal or external content:

![](images/reference-dialog.png){width="650" align="left"}

If areas overlap, you can bring the shape forward or send it backward by clicking on the respective icon in the toolbar. You can also remove an area by selecting it and clicking the Delete icon. Double-clicking on an area opens the Reference dialog wherein you can change the destination link. Once you have marked the required areas on your image, save the changes by selecting **Done**.


**Multimedia**

Inserisce diversi tipi di file multimediali. Select the Multimedia dropdown icon and choose the type of file you want to insert. I formati multimediali supportati sono:

- File audio
- File video
- YouTube
- Vimeo

Quando si seleziona l&#39;opzione File audio o video, viene visualizzata la vista del repository per sfogliare e selezionare il file desiderato. Se scegli YouTube o Vimeo, viene visualizzata la finestra di dialogo Inserisci file multimediali. Paste the link of the video file in the Web Link field and select Insert to add the video at the current or next valid location in your document.

>[!NOTE]
>
> Durante l&#39;aggiunta di un collegamento video YouTube, è necessario sostituire la stringa `watch?v=` con `embed` nell&#39;URL. Per aggiungere ad esempio un collegamento video YouTube: `https://www.youtube.com/**watch?v**=WlIKQOrmZcs`, è necessario aggiungerlo come: `https://www.youtube.com/**embed/**WlIKQOrmZcs`. Questa modifica garantisce che il video venga incorporato nell’output del sito AEM e di PDF.

È inoltre possibile aggiungere il file audio o video dalla finestra di dialogo Inserisci file multimediale. Select the Audio/Video File option and then, select the browse icon to launch the repository view. Select the audio or video file from the repository and select **Select** to add the link of the file in the Audio/Video File field. Se scegliete un file video, nell&#39;area di anteprima viene visualizzata anche un&#39;anteprima del file. You can play the video file to view its preview.

![](images/insert-multimedia.png){width="650" align="left"}

**Cross Reference**

Inserisci riferimenti di tipo: riferimento contenuto, riferimento chiave contenuto, riferimento chiave, riferimento file, collegamento web o collegamento e-mail.

Select the **Select File** icon \(for Content Reference and File Reference\) or **Select Root Map** icon \(for Content Key Reference and Key Reference\) and select the desired file or content to link to.

![](images/insert-references.png){width="650" align="left"}

Nel documento viene aggiunto un collegamento del riferimento selezionato. Il menu di scelta rapida sul collegamento consente di:

- **Inserisci elemento**: mostra un elenco di elementi validi che è possibile inserire nel contesto specificato.
- **Copia UUID**: copia l&#39;UUID del riferimento inserito.
- **Copia percorso**: copia il percorso completo del riferimento inserito.
- **Genera ID**: genera un ID univoco per il riferimento inserito.

Puoi anche eseguire ricerche utilizzando l’UUID del file a cui desideri fare riferimento. Per i collegamenti a Contenuto e Riferimento chiave, immetti l’UUID del file a cui vuoi collegare e il file viene automaticamente cercato e visualizzato nella sezione Anteprima. Quando si specifica l&#39;UUID del file, non è necessario indicare esplicitamente l&#39;estensione per i file con estensione xml. L&#39;estensione .xml viene aggiunta automaticamente all&#39;UUID.

![](images/insert-content-using-uuid-search.png){width="650" align="left"}

Se l&#39;amministratore ha abilitato l&#39;opzione UUIDs in *XMLEditorConfig*, l&#39;UUID del contenuto a cui si fa riferimento verrà visualizzato nella proprietà **Link**.

![](images/ref-link-uuid_cs.png){align="left"}

>[!NOTE]
>
> Se l&#39;opzione **Abilita UUID** non è abilitata, viene visualizzato il percorso relativo del contenuto a cui si fa riferimento.

>[!IMPORTANT]
>
> Anche se il percorso relativo del contenuto a cui si fa riferimento è visualizzato nella proprietà **Link**, internamente il collegamento viene creato utilizzando l&#39;UUID del contenuto a cui si fa riferimento.

>[!TIP]
>
> Consulta la sezione Riferimenti nella guida alle best practice per le best practice sui riferimenti ai contenuti.

**Ricerca filtro**

Puoi cercare del testo nei file presenti nel percorso selezionato dell’archivio AEM. Ad esempio, la ricerca di &quot;generale&quot; viene eseguita nella schermata seguente. Puoi anche restringere la ricerca utilizzando filtri avanzati. È possibile cercare tutti i file DITA come Argomenti DITA e Mappe DITA presenti nel percorso selezionato.

È possibile cercare file non DITA come i file immagine, i file multimediali e i documenti nel percorso selezionato. È inoltre possibile cercare valori specifici negli attributi degli elementi DITA. È inoltre possibile cercare i file estratti dall&#39;utente specificato.

![](images/reference-search-filters.png){width="650" align="left"}

>[!NOTE]
>
> L’amministratore di sistema può anche configurare i filtri di testo e mostrare o nascondere altri filtri. Per ulteriori dettagli, visualizzare la sezione *Configurare i filtri di testo* nella sezione Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

Viene visualizzato l’elenco dei file filtrati che contengono il testo cercato. Ad esempio, nella schermata precedente sono elencati i file contenenti il testo &quot;generale&quot;. Puoi anche visualizzare in anteprima il contenuto del file.


**Contenuto riutilizzabile** - ![](images/reusable-content.svg)

Riutilizzare il contenuto esistente in qualsiasi altro documento del progetto. È possibile inserire contenuto collegando direttamente al contenuto di un file oppure utilizzando un riferimento chiave, visualizzare [Risolvi riferimenti chiave](map-editor-other-features.md#id176GD01H05Z). Quando si seleziona l&#39;icona Contenuto riutilizzabile, viene visualizzata la finestra di dialogo Riutilizza contenuto:

![](images/reuse-content-dialog.png){width="650" align="left"}

Nella finestra di dialogo Riutilizza contenuto selezionare il file DITA per i riferimenti di file o il file mappa DITA contenente i riferimenti chiave. Una volta selezionati, l’argomento o i riferimenti chiave vengono visualizzati nella finestra di dialogo. È possibile selezionare l&#39;ID o la chiave dell&#39;argomento che si desidera inserire e selezionare **Fine** per inserire il contenuto nell&#39;argomento.

Per inserire un riferimento contenuto, puoi anche immettere l’UUID del file e il contenuto riutilizzabile da quel file è elencato nella sezione Anteprima.

In base all’impostazione per l’inserimento dei collegamenti, puoi visualizzare l’UUID del contenuto inserito o il percorso relativo nel pannello Proprietà o nella vista Codice di Source. Il collegamento viene sempre creato utilizzando l’UUID del contenuto di riferimento. Visualizza *Configurare i collegamenti basati su UUID* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

>[!NOTE]
>
> Per aggiungere contenuto prima o dopo il contenuto a cui si fa riferimento, utilizzare i tasti freccia *Alt*+*Left* o Alt+*Right* per spostare il cursore nella posizione desiderata.

È inoltre possibile incorporare il contenuto di riferimento all&#39;interno dell&#39;argomento facendo clic con il pulsante destro del mouse sul contenuto di riferimento e scegliendo **Sostituisci riferimento con contenuto** dal menu di scelta rapida.

**Simbolo** - ![](images/symbol-icon.svg)

Inserisce caratteri speciali nell&#39;argomento. Selezionate l&#39;icona Simbolo per aprire la finestra di dialogo Inserisci carattere speciale.

>[!NOTE]
>
> Experience Manager Guides fornisce finestre di dialogo mobili e ridimensionabili. Le finestre di dialogo con due linee trasversali nell&#39;angolo inferiore destro possono essere ridimensionate. Le linee trasversali nella finestra di dialogo Carattere speciale sono mostrate di seguito.

![](images/insert-special-char.png){width="550" align="left"}

Nella finestra di dialogo Inserisci carattere speciale è possibile cercare un carattere speciale utilizzando il relativo nome. Tutti i caratteri speciali vengono memorizzati in varie categorie. Utilizzare l&#39;elenco a discesa Seleziona categoria e selezionare una categoria. Vengono visualizzati i caratteri speciali disponibili nella categoria selezionata. È possibile spostarsi nell&#39;elenco dei caratteri speciali utilizzando i tasti di direzione o selezionare il carattere desiderato che si desidera inserire. Il nome e il codice esadecimale del carattere speciale selezionato vengono visualizzati sotto l&#39;elenco. Selezionare **Inserisci** per inserire il carattere selezionato nel documento.

**Parola chiave** - ![](images/Keyword_icon.svg)

Inserisci parola chiave definita nella mappa DITA. Selezionate l&#39;opzione Parola chiave per aprire la finestra di dialogo Riferimento chiave (Key Reference).

![](images/insert-keyword.png){width="550" align="left"}

Le parole chiave sono elencate in ordine alfabetico ed è inoltre possibile cercare le parole chiave\(s\) digitando una stringa di ricerca nella casella Cerca. Il risultato della ricerca restituirà le parole chiave contenenti la stringa in ID o Value. Le parole chiave definite nella mappa DITA sono elencate in questa finestra di dialogo. Scegliere la parola chiave da inserire e selezionare **Inserisci**.

È inoltre possibile modificare gli attributi della parola chiave inserita facendo clic con il pulsante destro del mouse sulla parola chiave e selezionando l&#39;opzione Attributi. Viene visualizzata la finestra di dialogo **Attributi per parola chiave:

![](images/attributes-for-keyword.png){width="550" align="left"}

È possibile modificare gli attributi della parola chiave o aggiungere un nuovo attributo alla parola chiave.

**Snippet** - ![](images/insert-snippet-icon.svg)

Inserire uno snippet nella posizione valida corrente o successiva. Affinché questa funzione funzioni, è necessario che nel sistema siano definiti snippet. Per ulteriori informazioni sull&#39;aggiunta di uno snippet, vedere la descrizione della funzionalità **Snippet** nella sezione [Pannello sinistro](web-editor-features.md#left-panel).

Quando selezionate l&#39;opzione Snippet, viene visualizzato il catalogo Inserisci snippet. Il catalogo è sensibile al contesto, il che indica che i frammenti verranno visualizzati solo se sono consentiti nella posizione corrente.

Nell&#39;esempio seguente vengono illustrati due snippet preconfigurati: Warning ed Error che è possibile inserire nella posizione corrente del documento.

![](images/insert-snippet.png){width="300" align="left"}

Quando si sceglie un frammento dall&#39;elenco, questo viene inserito nella posizione valida corrente o successiva del documento. La schermata seguente mostra lo snippet di errore inserito nel documento:

![](images/error-snippet.png){width="400" align="left"}

**Citazioni** - ![](images/Citations_icon.svg)

Crea citazioni e aggiungile al contenuto. Scopri come [aggiungere e gestire le citazioni nel contenuto](./web-editor-apply-citations.md).

**Query dati** - ![](images/data-sources-new-icon.svg)

Connettiti con la tua origine dati e utilizza i dati per creare contenuti. Scopri come [utilizzare dati dall’origine dati](./web-editor-content-snippet.md).

### Informazioni sulla versione e Salva come nuova versione

La funzionalità **Informazioni sulla versione e salvataggio come nuova versione** combina il monitoraggio della versione e il salvataggio dei contenuti in un&#39;unica funzionalità.

- Nelle informazioni sulla versione viene visualizzata la versione corrente dell&#39;argomento o della mappa. Accanto al numero di versione viene visualizzato un asterisco (*) per indicare le modifiche non salvate.

  Il numero di versione cambia con ogni nuova versione creata per il file di argomento o di mappa. Se si sta lavorando su un documento appena creato, le informazioni sulla versione vengono visualizzate come **none**.

  ![](images/version-information.png){align="left"}


- **Salva come nuova versione** è un pulsante che consente di salvare le modifiche apportate nell&#39;argomento e di creare una nuova versione dell&#39;argomento.

  ![](images/save-as-new-version.png){align="left"}


When you choose to save a topic or map using **Save as new version**, the following dialog box appears:

![](images/save-as-new-version-dialog.PNG){width="300" align="left"}

Enter comments and version labels to identify the changes and select **Save** to create a new version of your file.

When you choose the **Save as new version** option, the first version of the topic is created in DAM, which also becomes the currently active version of your topic. In seguito, se si ripristina una versione precedente dell&#39;argomento, quella diventerà la versione attiva corrente dell&#39;argomento.

If your administrator has pre-configured version labels, then you will view those labels in a drop-down list. È possibile scegliere un&#39;etichetta dall&#39;elenco delle etichette disponibili e salvare il documento.

![](images/web-editor-pre-defined-labels.PNG){width="300" align="left"}

Al momento del salvataggio di un argomento, è possibile aggiungere un commento specificando le modifiche apportate nell&#39;argomento. Questo commento viene visualizzato nella Cronologia versioni dell&#39;argomento.

Se l&#39;argomento è in revisione, i revisori riceveranno una notifica che indica che è disponibile una versione più recente dell&#39;argomento. Possono accedere facilmente alla revisione più recente del documento e continuare a rivedere la versione più recente dell&#39;argomento.

When you hover your pointer over a topic&#39;s title, you are shown the file title, file path, and the version number.

![](images/mouse-hover-on-title_cs.png){align="left"}

>[!NOTE]
>
> Quando è disponibile una versione dell&#39;argomento, è anche possibile aggiungere etichette all&#39;argomento. Queste etichette possono quindi essere utilizzate per creare una baseline per la pubblicazione di una versione specifica del documento. For more information about using labels in your topics, view [Use labels](web-editor-use-label.md#).

### Blocca/sblocca

Locks or unlocks the current file. Locking a file gives you an exclusive write access to the file. This restricts other users from editing the file. Unlock the file if you want others to have editing access. When the file is unlocked, the changes are saved in the current version of the file.

![](images/web-editor-lock-button.png){align="left"}

If you are in the Map View and you expand the parent map, you can lock all files in the map with a single click. Simply expand the parent map file and select the parent file, which results in selecting all files within the map. Then you can select **Lock**  ![](images/LockClosed_icon.svg) to get the lock on all files within the map.

In the Repository panel, the locked files are displayed with a lock icon. When you hover over this lock icon, the Locked by you/username is displayed as a tooltip.

![](images/web-editor-locked-by-icon-new.png){width="350" align="left"}

Se un file è bloccato da un altro utente, passa il cursore sull’icona del lucchetto nel repository e viene visualizzato il nome dell’utente che lo ha bloccato. In questo caso, il file viene aperto in modalità di sola lettura, con **Accesso di sola lettura** visualizzato accanto alle informazioni sulla versione.

In qualità di amministratore, puoi anche accedere alla funzionalità **Forza sblocco** che ti consente di sbloccare il file bloccato da altri utenti. Utilizzare questa funzione per accedere ai diritti di modifica su un file bloccato da altri utenti.

![](images/web-editor-force-unlock-new.png){width="350" align="left"}

## Pannello sinistro

Il pannello a sinistra consente di accedere rapidamente alle raccolte, alla vista Archivio, alla vista Mappa e ad altre funzioni. Puoi espandere il pannello selezionando l&#39;icona **Espandi** posta nell&#39;angolo inferiore sinistro dell&#39;interfaccia. Una volta espanso, utilizza l&#39;icona **Comprimi** per comprimere il pannello. Nella visualizzazione espansa vengono visualizzati i nomi delle icone visualizzate come descrizioni comandi nella visualizzazione compressa.

>[!NOTE]
>
> Il pannello sinistro è ridimensionabile. Per ridimensionare il pannello, posiziona il cursore sul bordo del pannello. Il cursore si trasforma in una freccia a due punte, seleziona e trascina per ridimensionare la larghezza del pannello.

Il pannello sinistro consente di accedere alle seguenti funzioni:

- [Raccolte](#collections)
- [Archivio](#repository)
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
> Le funzioni disponibili nel pannello a sinistra vengono gestite dall’amministratore, consentendo loro di abilitare o disabilitare le singole funzioni presenti nel pannello a sinistra. Nel pannello a sinistra vengono visualizzate solo le feature abilitate. Per ulteriori dettagli, visualizzare la sezione **Panels** di [Tab bar](#tab-bar).

La spiegazione dettagliata delle funzioni del pannello sinistro è la seguente:

### Raccolte

Se si lavora su un insieme di file o cartelle, è possibile aggiungerli all&#39;elenco dei preferiti per accedervi rapidamente. **Le raccolte** mostrano l&#39;elenco dei documenti aggiunti e altri elenchi di documenti accessibili al pubblico degli altri utenti.

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

Per creare una nuova raccolta, seleziona l&#39;icona + accanto al pannello Raccolte per visualizzare la finestra di dialogo **Nuova raccolta**:

![](images/favorite-new-collection.PNG){width="300" align="left"}

Immetti un titolo e una descrizione per la raccolta da creare. Se selezioni **Pubblico**, questo preferito verrà mostrato anche ad altri utenti.

>[!NOTE]
>
> Puoi anche creare una raccolta dalla home page di Experience Manager Guides. Apri la home page, passa al widget **Raccolte** nella [sezione Panoramica](./intro-home-page.md#overview) e seleziona **Nuova raccolta**.

Per aggiungere un file alle raccolte, utilizzare uno dei metodi seguenti:

- Passa al file o alla cartella richiesti nella vista Archivio, seleziona l&#39;icona *Opzioni* per aprire il menu di scelta rapida e scegli **Aggiungi a** > **Raccolte**. Nella finestra di dialogo **Aggiungi a raccolte** puoi scegliere di aggiungere il file o la cartella a un preferito esistente o crearne uno nuovo.

  ![](images/favorite-add-file-folder.png){width="300" align="left"}

- Fai clic con il pulsante destro del mouse sulla scheda di un file nell’editor per aprire il menu di scelta rapida. Scegli **Aggiungi a** > **Raccolte** per aggiungere il file all&#39;elenco dei preferiti.

  ![](images/favorite-add-from-file-context-menu_cs.png){align="left"}


>[!NOTE]
>
> - Per rimuovere un elemento dall&#39;elenco dei preferiti, selezionare l&#39;icona Opzioni accanto all&#39;elemento in una raccolta Preferiti e scegliere **Rimuovi da raccolte**.
> - Per visualizzare l&#39;anteprima del file senza aprirlo, selezionare un file e quindi **Anteprima** dal menu Opzioni.

**Menu Opzioni per una raccolta**

Puoi anche eseguire molte azioni utilizzando il menu Opzioni disponibile per una raccolta:

![](images/favorites-options.png){width="650" align="left"}

- **Rinomina**: rinomina la raccolta selezionata.
- **Elimina**: elimina la raccolta selezionata.
- **Aggiorna**: ottieni un nuovo elenco di file e cartelle dall&#39;archivio.
- **Visualizza nell&#39;interfaccia utente di Assets**: visualizza il contenuto del file o della cartella nell&#39;interfaccia utente di Assets.

>[!NOTE]
>
> Puoi anche aggiornare l’elenco utilizzando l’icona Aggiorna nella parte superiore.


### Archivio

Quando selezioni l’icona Archivio, ottieni un elenco di file e cartelle disponibili in DAM. Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il cursore del mouse su un file, potete visualizzare il titolo e il nome del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

Vengono caricati 75 file alla volta. Ogni volta che si seleziona **Carica altri**... vengono caricati 75 file e il pulsante non viene più visualizzato quando tutti i file sono elencati. Questo caricamento batch è efficiente e consente di accedere ai file più rapidamente rispetto al caricamento di tutti i file esistenti in una cartella.

Puoi passare facilmente al file richiesto all’interno di DAM e aprirlo nell’editor. Se si dispone dell&#39;accesso necessario per modificare il file, è possibile eseguire questa operazione.

È inoltre possibile selezionare e riprodurre un file audio o video nell&#39;editor. È possibile modificare il volume o
la visualizzazione del video. Nel menu di scelta rapida sono inoltre disponibili le opzioni per il download, la modifica della riproduzione
o di visualizzare immagini nell&#39;immagine.

Selezionare una mappa e premere Invio o fare doppio clic per aprirla nella **vista mappa**. Per ulteriori dettagli, visualizzare la descrizione della funzione **Visualizzazione mappa** nella sezione [Pannello sinistro](#left-panel). Selezionare un argomento e premere Invio o fare doppio clic per aprirlo nell&#39;[area di modifica dei contenuti](#content-editing-area). La possibilità di navigare e aprire un file direttamente dall’editor consente di risparmiare tempo e di aumentare la produttività.

**Ricerca filtro nel repository**

L’editor fornisce filtri migliorati per la ricerca di testo. È possibile cercare e filtrare un testo nei file presenti nel percorso selezionato dell&#39;archivio Adobe Experience Manager. La ricerca viene eseguita nel titolo, nel nome del file e nel contenuto dei file.


![cerca i file nella vista archivio](images/repository-filter-search.png){width="300" align="left"}

*Applicare i filtri per cercare i file contenenti il testo`personal spaceship.`*

Seleziona l&#39;icona **Ricerca filtro** \(![Icona filtro di ricerca](images/filter-search-icon.svg)\) per aprire il popup Filtro.

>[!NOTE]
>
> Quando si esegue una ricerca in un testo o si filtra un file, sull&#39;icona \(![Icona filtro di ricerca](images/filter-search-icon.svg)\) di **Ricerca filtro** viene visualizzato un punto blu per indicare che si trova nel pannello di ricerca e che sono stati applicati alcuni filtri.


Per filtrare i file e limitare la ricerca nell’archivio Adobe Experience Manager, sono disponibili le seguenti opzioni:

- **File DITA**: è possibile cercare tutti i **argomenti DITA** e le **mappe DITA** presenti nel percorso selezionato. Questi sono selezionati per impostazione predefinita.
- **File non DITA**: è possibile cercare **File Ditaval**, **File immagine**, **File multimediali**, **Documenti** e **JSON** nel percorso selezionato.

  ![filtro di ricerca rapida &#x200B;](images/repository-filter-search-quick.png) {width="300" align="left"}

  *Utilizza i filtri rapidi per cercare file DITA e non DITA.*

**Filtro avanzato**

Seleziona l&#39;icona **Filtro avanzato** ![icona filtro avanzato](images/advanced-filter-gear-icon.svg)per visualizzare la finestra di dialogo **Filtro avanzato**.

Puoi visualizzare le seguenti opzioni nelle schede **Generale** e **Avanzate**.

![finestra di dialogo filtro avanzato](images/repository-filter-search-advanced.png) {width="650" align="left"}


**Generale**

- **Risultati della ricerca con**: cercare del testo nei file presenti nel percorso selezionato dell&#39;archivio Adobe Experience Manager. La ricerca viene eseguita nel titolo, nel nome del file e nel contenuto dei file.

È sincronizzato con la casella di ricerca nella finestra del repository. Se ad esempio si digita `general purpose` nella casella di ricerca nel pannello del repository, verrà visualizzato anche nella finestra di dialogo **Filtro avanzato** e viceversa.

- **Cerca in**: selezionare il percorso in cui si desidera eseguire la ricerca nei file presenti nell&#39;archivio di Adobe Experience Manager.

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

**Menu Opzioni**

In addition to opening files from the left panel, you can also perform many actions using the Options menu available in the Repository view. You will view different options, depending on whether you choose a folder, topic file, or a media file.

**Opzioni per una cartella**

You can perform the following actions using the Options menu available for a *folder* in the Repository view:

![](images/options-menu-folder_cs.PNG){width="550" align="left"}


- **New**: Create a new DITA topic, DITA map, or a folder.

  Steps to create a new topic:
   1. Select **New** > **Topic**.
   2. The **New topic** dialog box is displayed.

      ![](images/create-topic-dialog.png){width="300" align="left"}

   3. In the **New topic** dialog box, provide the following details:
      - Titolo per l&#39;argomento.
      - \(Optional\)* The file name for the topic. Il nome del file viene suggerito automaticamente in base al Titolo dell’argomento. In case your administrator has enabled automatic file names based on UUID setting, then you will not view the Name field.
      - Modello su cui verrà basato l&#39;argomento. For example, for an out-of-the-box setup, you can choose from the Blank, Concept, DITAVAL, Reference, Task, Topic, Markdown, Glossary, and Troubleshooting templates. If your folder has a Folder Profile configured on it, then you will view only those topic templates that are configured on the Folder profile.

      - Percorso in cui salvare il file dell&#39;argomento. Per impostazione predefinita, il percorso della cartella attualmente selezionata nell’archivio viene visualizzato nel campo Percorso.

   4. Seleziona **Crea**. The topic is created at the specified path. Also, the topic is opened in the Editor for editing.

  Steps to create a new DITA map:

   1. Select **New** > **DITA map**.
   2. The **New map** dialog box is displayed.

      ![](images/create-map-dialog.png){width="300" align="left"}

   3. In the **New map** dialog box, provide the following details:
      - Un Titolo per la mappa.
      - *\(Facoltativo\)* Il nome file per la mappa. Il nome del file viene suggerito automaticamente in base al titolo della mappa. Se l’amministratore ha abilitato i nomi di file automatici in base all’impostazione UUID, il campo Nome non verrà visualizzato.
      - Modello su cui verrà basata la mappa. Ad esempio, per un&#39;impostazione predefinita, è possibile scegliere tra i modelli di mappe di Bookmap o di mappe DITA.
      - Percorso in cui si desidera salvare il file mappa. Per impostazione predefinita, il percorso della cartella attualmente selezionata nell’archivio viene visualizzato nel campo Percorso.
   4. Seleziona **Crea**. La mappa viene creata e aggiunta all’interno della cartella specificata nel campo Percorso. Inoltre, la mappa viene aperta nella vista Mappa. Potete aprire il file mappa nell&#39;Editor mappa e aggiungervi un argomento. Per ulteriori informazioni sull&#39;aggiunta di argomenti a un file di mapping, vedere [Creare un mapping](map-editor-create-map.md#). In alternativa, selezionare **Apri nella console delle mappe** per aprire la mappa nella console delle mappe.

  Passaggi per creare una nuova cartella:

   1. Selezionare **Nuovo** > **Cartella**.
   2. Viene visualizzata la finestra di dialogo **Nuova cartella**.

      ![](images/new-folder-dialog_cs.png){width="300" align="left"}

   3. Nella finestra di dialogo **Nuova cartella**, fornisci i dettagli seguenti:
      - Titolo della cartella, che viene automaticamente convertito nel nome della cartella.
      - Percorso in cui desideri salvare la cartella. Per impostazione predefinita, il percorso della cartella attualmente selezionata nell’archivio viene visualizzato nel campo Percorso.
   4. Seleziona **Crea**. La cartella viene creata e aggiunta all’interno della cartella da cui è stata eseguita l’opzione Crea cartella.

- **Carica Assets**: carica un file dal sistema locale alla cartella selezionata nell&#39;archivio Adobe Experience Manager. È inoltre possibile trascinare i file dal sistema locale all&#39;argomento di lavoro corrente. Questa funzione è molto utile se si desidera inserire nell&#39;argomento immagini provenienti dal sistema locale.

  ![](images/upload-assets.png){width="300" align="left"}

  Puoi selezionare una cartella in cui desideri caricare il file e visualizzare anche un’anteprima dell’immagine. Se si desidera rinominare il file, è possibile farlo nella casella di testo Nome file. Seleziona **Carica** per completare il processo di caricamento dei file. Se hai trascinato e rilasciato un file di immagine su un argomento, il file di immagine viene aggiunto all’articolo e caricato.

  Se l&#39;amministratore ha abilitato l&#39;opzione UUID in *XMLEditorConfig*, l&#39;UUID dell&#39;immagine caricata verrà visualizzato nella proprietà **Source**.

  ![](images/uuid-in-source-upload-image_cs.png){align="left"}

- **Trova file nella cartella**: sposta lo stato attivo sulla ricerca del repository in cui è possibile immettere il termine di ricerca. La ricerca viene eseguita nella cartella selezionata nell’archivio. È inoltre possibile applicare un filtro per restituire file DITA, file di immagine o entrambi.

  ![](images/find-files-in-folders-repo-view_cs.png){width="300" align="left"}

  Puoi anche eseguire ricerche utilizzando l’UUID di un file. In tal caso, i risultati della ricerca visualizzano il titolo del file DITA/XML e, nel caso in cui il file sia un file di immagine, viene visualizzato l&#39;UUID del file. Nell’esempio di ricerca seguente viene eseguita la ricerca dell’UUID di un file di immagine e nei risultati vengono visualizzati l’UUID del file di immagine originale e il titolo dell’argomento del file in cui si fa riferimento a tale immagine.

  ![](images/uuid-repo-search-image-topic-file_cs.png){width="300" align="left"}

- **Comprimi**: comprimi la cartella selezionata nell&#39;archivio.

  >[!NOTE]
  >
  > Utilizza l&#39;icona **\>** accanto a una cartella per espanderla.

- **Aggiungi a raccolte**: aggiunge la cartella selezionata ai preferiti. Puoi scegliere di aggiungerlo a una raccolta esistente o nuova.

- **Aggiorna**: ottieni un nuovo elenco di file e cartelle dal repository.
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
- Visualizza nell’interfaccia di Assets
- Proprietà


![menu opzioni di un file nella vista archivio](images/options-menu-repo-view-file-level.png){width="550" align="left"}

Di seguito sono illustrate le varie opzioni del menu Opzioni:

- **Modifica**: apri il file per la modifica. In case of a .ditamap/.bookmap file, it is opened in the [Map Editor](map-editor-advanced-map-editor.md#) for editing.

- **Duplicato**: utilizzare questa opzione per creare un duplicato o una copia del file selezionato. Puoi anche rinominare il file duplicato nel prompt Duplica risorsa. Per impostazione predefinita, il file viene creato con il suffisso \(come nomefile\_1.extension\). Il titolo del file rimane invariato rispetto al file di origine e il nuovo file inizia con la versione 1.0. Tutti i riferimenti, i tag e i metadati vengono copiati mentre le baseline non vengono copiate nel file duplicato.
- **Lock**: Get a lock on the selected file for editing. If the file is locked, hovering the mouse pointer over the lock icon shows **Locked by you** if you locked it, or **Locked by [username]** if another user has locked it.

- **Anteprima**: consente di ottenere un&#39;anteprima rapida del file (.dita, .xml, audio, video o immagine) senza aprirlo. È possibile ridimensionare il riquadro di anteprima. Se il contenuto contiene `<xref>` o `<conref>`, è possibile selezionarlo per aprirlo in una nuova scheda. Il titolo del file viene visualizzato nella finestra. Se non è presente alcun titolo, viene visualizzato il nome del file. To close the **Preview** panel, you can either select the close icon or select anywhere outside the pane.

  ![](images/quick-preview_cs.png){align="left"}

- **Rinomina**: utilizzare questa opzione per rinominare il file selezionato. Immettere il nome del nuovo file nella finestra di dialogo **Rinomina risorsa**.
   - È possibile rinominare un file di qualsiasi tipo.
   - Impossibile modificare l&#39;estensione di un file.
   - Due file non possono avere lo stesso nome. Pertanto, non è possibile rinominare un file con un nome già esistente. Viene visualizzato un errore.

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

- **Copia**: puoi scegliere tra le seguenti opzioni:

   - **Copia UUID**: copia l&#39;UUID del file selezionato negli Appunti.

   - **Copia percorso**: copia il percorso completo del file selezionato negli Appunti.

- **Aggiungi a**: puoi scegliere tra le seguenti opzioni:
   - **Raccolte**: aggiunge il file selezionato alle raccolte. Puoi scegliere di aggiungerlo a una raccolta esistente o nuova.

   - **Contenuto riutilizzabile**: aggiunge il file selezionato all&#39;elenco Contenuto riutilizzabile nel pannello sinistro.

- **Proprietà**: utilizzare questa proprietà per aprire la pagina delle proprietà del file selezionato. È inoltre possibile accedere a questa pagina delle proprietà dall’interfaccia utente di Assets selezionando un file e quindi l’icona Proprietà nella barra degli strumenti.

- **Apri nel dashboard delle mappe**: se il file selezionato è una mappa DITA, questa opzione apre il dashboard delle mappe.

- **Apri nella console delle mappe**: se il file selezionato è una mappa DITA, questa opzione apre la console delle mappe.

- **Modifica in ossigeno**: selezionare questa opzione per modificare il file selezionato nel plug-in del connettore di ossigeno. Il file viene aperto per la modifica.

  >[!NOTE]
  >
  >Contatta il team di successo del cliente per abilitare questa funzione nell’ambiente. Questa funzione non è abilitata come parte del supporto predefinito. Per ulteriori dettagli, vedere la sezione [Configurare l&#39;opzione da modificare in Ossigeno](../cs-install-guide/conf-edit-in-oxygen.md) nella Guida all&#39;installazione e alla configurazione.


- **Visualizza nell&#39;interfaccia utente di Assets**: consente di visualizzare un&#39;anteprima di un file .dita/.xml nell&#39;interfaccia utente di Assets. Nel caso di un file .ditamap/.bookmap, tutti i file di argomenti all&#39;interno della mappa vengono visualizzati in un&#39;unica visualizzazione unificata pagina per pagina.

- **Scarica come PDF**: utilizza l&#39;opzione per generare l&#39;output di PDF e scaricarlo.

- **Genera**: utilizza l&#39;opzione per pubblicare una mappa o argomenti all&#39;interno di una mappa in una pagina Sites, in un frammento di contenuto o in un frammento di esperienza.

### Mappa

Quando si seleziona l&#39;icona della vista Mappa, viene visualizzata la vista Mappa in cui viene visualizzato un elenco di argomenti all&#39;interno del file mappa. Se non è stato aperto alcun file di mappa, la vista Mappa appare vuota. Facendo doppio clic su un file di mappa, il file di mappa viene aperto in questa vista. Puoi fare doppio clic su qualsiasi file all’interno della mappa per aprirlo nell’editor.

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
>In qualità di amministratore, puoi anche scegliere di visualizzare il nome del file della mappa principale che è attualmente aperto nella vista mappa. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.


Quando apri una mappa nella vista mappa, il titolo della mappa corrente viene visualizzato al centro della barra della scheda. Se il titolo è troppo lungo, vengono visualizzati dei puntini di sospensione e puoi anche passare il puntatore del mouse sul titolo per visualizzare il titolo completo nella descrizione comando.

Quando definite gli attributi chiave per i riferimenti argomento o mappa, potete visualizzare il titolo, l&#39;icona corrispondente e il tasto nel pannello sinistro. La chiave viene visualizzata come `keys=<key-name>`.

![Chiavi nella vista mappa](images/view-key-title-map-view.png){width="300" align="left"}

Se si dispone dei diritti di modifica sui file di mappa, sarà possibile modificare anche i file. Per ulteriori informazioni sull&#39;apertura e la modifica di un argomento tramite mappa DITA, visualizzare [Modifica argomenti tramite mappa DITA](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

Per un file di mappa nella vista Mappa sono disponibili le seguenti opzioni:

- **Apri nella console mappe**: apre il file mappa nella console Mappa.
- **Modifica**: apre il file mappa per la modifica.
- **Opzioni**: apre il menu di scelta rapida per il file di mapping selezionato.

Potete eseguire le seguenti operazioni utilizzando il menu Opzioni (Options) del file di mappa:

![Menu Opzioni nella vista Mappa](images/options-menu-map-view_cs.png){align="left"}

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

- **Locate in repository**: Shows the location of the map file in the repository \(or DAM\).

- **Aggiungi a**: puoi scegliere tra le seguenti opzioni:
   - **Collections**: Adds the map file to collections. Puoi scegliere di aggiungerlo a una raccolta esistente o nuova.

   - **Reusable content**: Adds the map file to the Reusable content list in the left panel.

- **Proprietà**: utilizzare questa proprietà per aprire la pagina delle proprietà del file di mappa. This properties page can also be accessed from the Assets UI by selecting a file and selecting the Properties icon in the toolbar.

- **Open map dashboard**: Opens the map dashboard.

- **Visualizza nell&#39;interfaccia utente di Assets**: consente di visualizzare un&#39;anteprima del file mappa nell&#39;interfaccia utente di Assets. In questa visualizzazione, tutti i file degli argomenti della mappa vengono visualizzati in un&#39;unica visualizzazione unificata pagina per pagina.
- **Download map**: Select this option to open the **Download map** dialog box.

  Nella finestra di dialogo **Scarica mappa** puoi scegliere le seguenti opzioni:

  **Usa baseline**: selezionare questa opzione per ottenere un elenco delle baseline create per la mappa DITA. Per scaricare il file mappa e il relativo contenuto in base a una baseline specifica, selezionare la baseline dall&#39;elenco a discesa. For more details about working with Baselines, view [Work with Baseline](./generate-output-use-baseline-for-publishing.md).

  **Flatten File Hierarchy**: selezionare questa opzione per salvare tutti gli argomenti e i file multimediali di riferimento in un&#39;unica cartella.

  È inoltre possibile scaricare il file mappa senza selezionare alcuna opzione. In tal caso, vengono scaricate le ultime versioni persistenti degli argomenti e dei file multimediali a cui si fa riferimento.

  After you select the **Download** button, the map export package request is queued. Se il pacchetto viene creato correttamente, viene visualizzata la finestra di dialogo **Operazione riuscita**.  You can select the **Download** button from the **Success** dialog box.

  You receive the map download-ready notification if the map is ready to download. Se il download non riesce, viene inviata la notifica che indica che il download della mappa non è riuscito.

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


- **Individua nel repository**: mostra la posizione del file selezionato nel repository \(o DAM\).
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

### Contenuto riutilizzabile

Una delle caratteristiche principali di DITA è la possibilità di riutilizzare i contenuti. Il pannello **Contenuto riutilizzabile** può memorizzare i file DITA da cui vengono generalmente inseriti i contenuti riutilizzabili. Una volta aggiunti, i file DITA rimangono nel pannello Contenuto riutilizzabile per più sessioni. Ciò significa che non è necessario aggiungere di nuovo i file DITA per accedervi in un secondo momento.

Puoi semplicemente trascinare e rilasciare i contenuti riutilizzabili dal pannello sull’argomento corrente, per inserirli in modo semplice e rapido. È inoltre possibile ottenere un&#39;anteprima del contenuto prima di inserirlo nel documento.

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

Per aggiungere un file DITA al pannello Contenuto riutilizzabile, utilizzare uno dei metodi seguenti:

- Selezionare l&#39;icona **+** accanto a Contenuto riutilizzabile per aprire la finestra di dialogo Sfoglia file. Selezionare il file da aggiungere, quindi selezionare **Aggiungi** per completare il processo.

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

### Struttura

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

Se l&#39;amministratore ha creato un profilo per gli attributi, questi verranno ottenuti insieme ai relativi valori configurati. Puoi anche assegnare gli attributi di visualizzazione configurati dall&#39;amministratore nella scheda **Attributi di visualizzazione** delle **Impostazioni**. Gli attributi definiti per un elemento vengono visualizzati nella vista Layout e Struttura.


Per ulteriori dettagli, visualizzare gli *attributi di visualizzazione* nella descrizione della funzionalità *Impostazioni* nella sezione [Pannello sinistro](#left-panel).

**Funzione di ricerca**

Utilizzando la funzione di ricerca, puoi cercare un elemento in base al suo nome, ID, testo o valore dell’attributo.

La ricerca non distingue tra maiuscole e minuscole e corrisponde esattamente alla stringa. I risultati della ricerca vengono ordinati in base alla posizione dell&#39;elemento nel documento.

È possibile cercare una stringa nell&#39;elemento se è visualizzata nella visualizzazione **Struttura**. Se, ad esempio, la stringa &quot;Adobe&quot; è presente nel testo dell&#39;elemento ed è visualizzata nel pannello Visualizzazione Struttura (come hai selezionato **Mostra testo** dal menu a discesa Opzioni visualizzazione), l&#39;elemento che la contiene viene filtrato. Tuttavia, se il testo non viene visualizzato nel pannello Visualizzazione Struttura (poiché non è stato selezionato **Mostra testo** dal menu a discesa Opzioni di visualizzazione), l&#39;elemento che lo contiene non viene filtrato. Allo stesso modo, se li hai selezionati, troverai la stringa nell’ID o negli attributi.

### Glossario

Experience Manager Guides consente di creare e utilizzare facilmente i documenti di tipo glossario. È possibile creare file di argomenti del glossario e quindi includerli in una mappa del glossario comune. Una volta aggiunta questa mappa come mappa principale, le voci del glossario vengono quindi visualizzate nel pannello Glossario.

![](images/glossary-panel.png){width="650" align="left"}

Per inserire un termine dal glossario, è sufficiente trascinare la voce dal pannello nella posizione desiderata nell’argomento. Il menu Opzioni di un termine del glossario ti consente di ottenere una **Anteprima** rapida del termine di ingresso, **Copia percorso** del file del termine di ingresso, oppure di individuare il file del termine di ingresso nell&#39;archivio.

Per cercare termini di testo e sostituirli con abbreviazioni del glossario, effettuare le seguenti operazioni:

1. Aprire l&#39;argomento o la mappa DITA in cui si desidera cercare e convertire il testo o i termini.
1. Selezionare il pannello glossario per visualizzare i termini del glossario presenti nella mappa principale. È possibile trascinare questi termini per aggiungerli all&#39;argomento aperto.
1. Selezionare lo strumento **Punto attivo** \( ![](images/hotspot-icon.svg)\) nel pannello Glossario per cercare e convertire termini di testo specifici in abbreviazioni di glossario collegate. Inoltre, viceversa, è possibile utilizzarlo per cercare abbreviazioni del glossario e convertirle in termini di testo.



È possibile configurare le seguenti impostazioni dello strumento Punto attivo:

![](images/glossary-hotspot-tool.png){width="300" align="left"}


- **Tasti glossario**: Selezionare i tasti del glossario dalla mappa DITA che si desidera utilizzare per la ricerca nell&#39;argomento selezionato. I tasti selezionati verranno visualizzati di seguito. È possibile rimuovere una chiave selezionata selezionando l&#39;icona **Rimuovi**.

- **Argomenti**: scegliere l&#39;**Argomento corrente** aperto nell&#39;editor, tutti i **Argomenti aperti** nella mappa corrente oppure la **Mappa corrente** modificata nell&#39;editor mappe per cercare i termini.
- **Filtra argomenti per stato**: è possibile limitare la ricerca agli argomenti con lo stato del documento selezionato. Gli argomenti possono essere in stato Bozza, Modifica, In revisione, Approvato, Rivisto, Fine o in uno qualsiasi degli stati configurati dall’organizzazione.
- **Azione**: è possibile scegliere di cercare manualmente le chiavi del glossario **per ogni argomento** o **Automaticamente per tutti gli argomenti**. Se si sceglie **Manualmente per ogni argomento**, verrà richiesto di confermare prima di convertire ogni termine in ogni argomento. If you choose **Automatically for all topics**, it converts all terms in all the topics automatically.
- **Converti**: è possibile convertire un **testo cercato in termine glossario** o un **termine glossario in testo.**
- **Opzioni**: è possibile selezionare una delle opzioni seguenti:
   - **Case-sensitive match**: Searches for a term to find the match which has the same casing. Ad esempio, &#39;USB&#39; non corrisponderà a &#39;usb&#39;.
   - **Convert only the first instance**: If multiple instances of the searched term are present in a topic, only the first instance is converted.
   - **Lock file before conversion**: The searched file is locked before the terms are converted.
   - **Create a new version after conversion**: A new version of the topic is created after the conversion of terms has been completed.
- Il pulsante **Avanti** viene visualizzato se si seleziona **Manualmente per ogni argomento**. Select **Next** to convert the terms for each topic on the basis of the selected settings. Richiede la conversione dei termini in ciascun argomento e passa al file successivo. Puoi scegliere di convertire un termine o saltarlo e passare al termine successivo.

  ![](images/manual-convert-skip.png){width="300" align="left"}

- **Convert** button appears if you select **Automatically for all topics** option. Selezionare **Converti** per convertire tutti i termini presenti nel documento in abbreviazioni di glossario collegate.

Viene visualizzato un elenco di **argomenti aggiornati** con i termini convertiti e **argomenti con errore**. Hover over the info icon near Topics with Error to view the details of the error.

>[!NOTE]
>
> Aggiornare l&#39;argomento per visualizzare i termini convertiti.

### Condizioni

Il pannello Condizioni visualizza gli attributi condizionali definiti dall&#39;amministratore nel profilo globale o a livello di cartella. Puoi aggiungere condizioni al contenuto semplicemente trascinando e rilasciando la condizione desiderata sul contenuto. Il contenuto condizionale viene evidenziato utilizzando il colore definito per la condizione per una facile identificazione.

Puoi anche applicare più condizioni a un elemento trascinando più condizioni su di esso. Quando applicate più condizioni a un elemento, il pannello Proprietà mostra le condizioni applicate separate da una virgola.

![](images/multiple-conditions-applied_cs.png){align="left"}

Tuttavia, nella vista Codice le condizioni vengono separate utilizzando un delimitatore di spazio. Quando aggiungi o modifichi una condizione nella vista Codice, accertati che più condizioni siano separate utilizzando uno spazio.

>[!IMPORTANT]
>
> La schermata seguente è di un utente con privilegi di amministratore. In qualità di utente con privilegi di amministratore, puoi aggiungere, modificare ed eliminare condizioni. Altrimenti, in qualità di autore normale, avrai la possibilità di applicare solo le condizioni.

![](images/conditional-content-through-panel_cs.png){align="left"}

To add or define a condition, select the + icon next to Conditions panel to bring up the Define Condition dialog box:

![](images/conditional-panel-create-cond.png){width="400" align="left"}

Dall&#39;elenco Attributo (Attribute), selezionate l&#39;attributo condizionale da definire, immettete un valore per la condizione, quindi specificate l&#39;etichetta visualizzata nel pannello Condizioni (Conditions). Definisci un gruppo per la condizione. You can add multiple conditions to a group. Puoi anche definire un colore per la condizione. Questo colore viene impostato come colore di sfondo del contenuto a cui viene applicata la condizione.

Puoi raggruppare le condizioni e strutturarle in cartelle nidificate. I gruppi consentono di creare condizioni a più livelli e di organizzarle meglio per l’utilizzo nel contenuto.

Ad esempio, puoi creare gruppi di condizioni di prodotti come *Acrobat* e *AEM Guides*. È possibile selezionare gli attributi condizionali per entrambi i gruppi. In ogni gruppo, puoi avere valori specifici come *Utente*, *Amministratore*, *Revisore* e *Autore*.

>[!NOTE]
>
> Digitare per creare un nuovo gruppo o selezionare un gruppo esistente per un determinato attributo.

You can use `/` and define sub-groups like `AEM Guides/Cloud Service`.



![condizioni organizzate in una gerarchia nidificata](images/conditions-nested-hierarchy.png){width="300" align="left"}


Per modificare una condizione, scegliere **Modifica** dal menu Opzioni. The Edit Condition dialog box is displayed:

![](images/conditional-panel-edit-cond.png){width="400" align="left"}

Specify the details in the same way as configured while defining a new condition.

### Schema soggetto

Subject scheme maps are a specialized form of DITA maps that are used to define taxonomic subjects and controlled values. Depending upon your requirements, you can create a subject scheme map and reference it within your root map file. Experience Manager Guides allows you to define the nested-level hierarchy of the subject definitions in your subject scheme.

You can easily create and then use the subject scheme in a subject scheme map. Once this map is added as your root map, the subject scheme is then shown in the Subject Scheme panel. The Subject scheme panel displays the available subject scheme in a nested or hierarchical manner.

Experience Manager Guides also supports nested level subject scheme maps, and you can have multiple subject schemes defined under the root subject scheme map.

The following example shows how to use subject scheme in Experience Manager Guides.

1. Create a subject scheme file in a tool of your choice. The following XML code creates subject scheme that binds values for the `platform` attribute.

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

1. Save the file with a.ditamap extension and upload it to any folder in DAM.

   >[!NOTE]
   >
   > You can add a reference to the subject scheme file in the parent DITA map.

   ![](images/subject-scheme-root-map-new.png){width="550" align="left"}

1. Set the parent map as the root map in the **User preferences**. Once this map is added as your root map, the subject scheme is then shown in the Subject scheme panel.

   ![](images/subject-scheme-user-preferences-new.png){width="650" align="left"}


1. In the Editor, open the file where you want to use the subject scheme definitions.
1. Apply the subject scheme to your content by simply dragging and dropping the desired subject scheme onto your content. The content is then highlighted in the defined color.




**Handling hierarchical definitions of subject definitions and enumerations**

Besides handling the enumerations and the subject definitions present in the same map, Experience Manager Guides also provides the feature to define enumerations and subject definitions in two separate maps. You can define one or more subject definitions in a map and the enumeration definitions in another map and then add the map reference. For example, the following XML code creates subject definitions and enumeration definitions in two separate maps.

The subject definitions are defined in `subject_scheme_map_1.ditamap`


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

The enumeration definition is present in    subject_scheme_map_2.ditamap.

```XML
<?xml version="1.0" encoding="UTF-8"?> 
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

Here subject definitions are defined in `subject_scheme_map_1.ditamap`  while the enumeration def is present in `subject_scheme_map_2.ditamap`. The reference to `subject_scheme_map_1.ditamap` is also added in `subject_scheme_map_2.ditamap`.

>[!NOTE]
>
> As the `subject_scheme_map_1.ditamap` and `subject_scheme_map_2.ditamap` are referenced with each other hence the subject schemes are getting resolved.

The subject-enumeration references are resolved in the following order of priority:

1. Same map
1. Referenced map


The references are not resolved if the enumeration is not found in the same map and the referenced map.

**Restrict the values to a specific element**

You can also restrict the conditions to some elements within a topic. Use the `<elementdef>` tag to define the element and the `<attributedef>` tag to define the condition that can be applied to the element.  If you don&#39;t add the `<elementdef>` tag, you can apply the conditions to all elements.
For example, use the following enumeration to restrict the `@platform` attribute to the `<shortdesc>` element.  The other conditions are visible for all elements.

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


**Attributes** drop-down

You can also change the value of the subject scheme using the **Attributes** dropdown from the **Content properties** panel in the **Author** view.

Perform the following steps to change the value:

1. Select an attribute from the **Attribute** dropdown.
1. Seleziona **Modifica**.
1. Select the required value from the **Value** dropdown.
1. Seleziona **Aggiorna**.

You can also apply values for an attribute by selecting multiple values from the dropdown.

**Source view**

You can also change the values from the attribute&#39;s drop-down in the Source view. The Source view also prevents you from adding any incorrect value.

![](images/subject-scheme-code-error.png){width="550" align="left"}

**View and apply the subject scheme from the Conditions panel**

You can also view and apply the subject scheme from the Conditions panel.

To view the subject scheme from the Conditions panel, your system administrator must select the **Show subject scheme in the Conditions panel** option under the General tab in Settings. For more details, view the **Settings** section in the [Tab bar](#tab-bar).

The Conditions panel displays the flat vertical structure of the subject definitions within the subject scheme.

You can add conditions to your content by dragging and dropping the desired condition onto your content. Il contenuto condizionale viene evidenziato utilizzando il colore definito per la condizione.

### Snippet

Snippets are small content fragments that can be reused across various topics in your documentation project. The Snippets panel shows a collection of content snippets that you have created. To insert a snippet, drag-and-drop the snippet from the panel to the desired location in your topic. Il pannello Snippet consente di aggiungere, modificare, eliminare, visualizzare in anteprima e inserire uno snippet.

>[!IMPORTANT]
>
> La schermata seguente è di un utente con privilegi di amministratore. In qualità di utente con privilegi di amministratore, puoi aggiungere, modificare ed eliminare snippet. Altrimenti, in qualità di autore normale, avrai accesso solo alle opzioni per visualizzare in anteprima e inserire uno snippet.

![](images/snippets-panel_cs.png){align="left"}

Per aggiungere uno snippet, utilizzare uno dei metodi seguenti:

- Seleziona l&#39;icona **+** accanto a Snippet per aprire la finestra di dialogo **Nuovo snippet**.

  ![](images/snippet-new-dialog.png){width="300" align="left"}

  Nella finestra di dialogo Nuovo frammento, specificate un titolo da visualizzare nel pannello Frammenti, una descrizione e il codice XML del contenuto del frammento che desiderate creare. Seleziona **Crea** per salvare e creare lo snippet.

- Nell&#39;area di modifica del contenuto fare clic con il pulsante destro del mouse sulla breadcrumb dell&#39;elemento che si desidera utilizzare come frammento e scegliere **Crea frammento** dal menu di scelta rapida. Viene visualizzata la finestra di dialogo Nuovo frammento con il codice XML dell&#39;elemento selezionato popolato nel campo **Contenuto**. Immetti il **Titolo** e la **Descrizione** per lo snippet e seleziona **Crea** per salvare lo snippet.

- Nell&#39;area di modifica del contenuto fare clic con il pulsante destro del mouse in un punto qualsiasi del contenuto che si desidera utilizzare come frammento e scegliere **Crea frammento** dal menu di scelta rapida. Viene visualizzata la finestra di dialogo Nuovo frammento con il codice XML dell&#39;elemento selezionato popolato nel campo **Contenuto**. Immetti il **Titolo** e la **Descrizione** per lo snippet e seleziona **Crea** per salvare lo snippet.

  La schermata seguente evidenzia la breadcrumb e l’area del contenuto da cui è possibile richiamare il menu di scelta rapida.

  ![](images/snippet-create-from-breadcrumb-content.png){width="350" align="left"}


Per inserire uno snippet, utilizzare uno dei metodi seguenti:

- Selezionate uno snippet dal pannello Snippet e trascinatelo nella posizione desiderata nell&#39;argomento.

- Posizionare il punto di inserimento nel punto in cui si desidera inserire lo snippet. Scegliere Inserisci snippet dal menu Opzioni dello snippet desiderato.


>[!NOTE]
>
> Dal menu di scelta rapida di una voce di frammento, è inoltre possibile scegliere di modificare, eliminare, ottenere un&#39;anteprima o inserire uno snippet.

### Modelli

Il pannello Modelli è disponibile solo per gli amministratori. Utilizzando questo pannello, l’amministratore può creare e gestire facilmente modelli che possono quindi essere utilizzati dagli autori. Per impostazione predefinita, i modelli sono classificati nei modelli di tipo *map* e *topic*.

![](images/templates-panel_cs.png){width="300" align="left"}

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un modello, è possibile visualizzare il titolo e il nome del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file nell’editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

To learn how to create custom templates, view [Create maps based on customized templates](./create-maps-customized-templates.md).

### Citazioni

In Experience Manager Guides, you can add and import citations and apply them to your content. È possibile aggiungere queste citazioni da qualsiasi origine di libri, siti Web e giornali.

For details, view [Add and manage citations in your content](./web-editor-apply-citations.md).

### Variabili di lingua

Experience Manager Guides provides the feature to use language variables in the Native PDF output. You can use language variables to define localized strings in the PDF output or to localize any static text in the output templates. You can use CSS styles to localize the strings coming from a CSS.

For details, view [Support for language variables](../native-pdf/native-pdf-language-variables.md).

### Variabili

Experience Manager Guides allows you to create and manage variables for Native PDF publishing. For details, view [Variables in the PDF output](../native-pdf/native-pdf-variables.md).


### Trova e sostituisci

The Find and replace icon is located at the bottom of the left panel. The Find and replace panel allows you to search for and replace text across files in a map or a folder within your repository. Puoi trovare e sostituire in tutti gli argomenti di una mappa così come gli argomenti presenti nelle mappe secondarie all&#39;interno della mappa.

![](images/map-find-replace.png){align="left"}

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> As an administrator, you can also choose to view the list of filenames in the Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

Per eseguire la ricerca e la sostituzione globali, effettuare le seguenti operazioni:

1. Open the global **Find and replace** panel.
1. Select the **Look into** dropdown and select one of the following options to perform the search.

   - **Mappa corrente**: per eseguire ricerche nella mappa aperta

     >[!NOTE]
     >
     > Questa opzione viene visualizzata se avete già aperto una mappa per la modifica.

   - **Percorso**: per eseguire una ricerca nel percorso selezionato
   - **Seleziona mappa**: per eseguire una ricerca nella mappa selezionata

1. You can use the **Options** dropdown and choose from the following options:

   - **Lock file before replace**: Select this option if you want to lock a file automatically before replacing the search term. This setting is more relevant in case your administrator has enabled the configuration to lock a file before editing. Con l’impostazione di back-end attivata, seleziona questa opzione. It will prevent the file lock dialog from prompting you to lock every file before making any change. Se non si seleziona questa opzione, prima di aprire un file per la modifica verrà visualizzato un messaggio.
   - **Whole words only**: Select this option if you want to search for the whole search string. Ad esempio, se si immette nella stringa di ricerca, il risultato della ricerca restituirà tutti i file contenenti parole come over e overview. Se si desidera limitare la ricerca per restituire il termine specificato, selezionare questa opzione.
   - **Create new version after replace**: Select this option if you want to create a new version of the topic in which you choose to replace the text. Puoi anche fornire commenti sulla versione che verranno aggiunti a ogni file aggiornato.

     Se non si seleziona questa opzione, le modifiche verranno salvate nella versione corrente dell&#39;argomento e non verrà creata alcuna nuova versione.

   - **Include indirect references**: Select this option if you want to search the string in the indirect references also within the DITA map. Per impostazione predefinita, questa opzione è disabilitata, pertanto la ricerca viene eseguita solo sui riferimenti diretti.

1. Immettere il termine di ricerca o il testo che si desidera trovare.
1. Immettere il testo con cui si desidera sostituire il termine di ricerca.
1. Premi Invio o seleziona l&#39;icona **Cerca** \( ![](images/search-icon.svg)\) per eseguire la ricerca.
1. Selezionare un file dall&#39;elenco dei risultati della ricerca. Il file viene aperto nell&#39;area di modifica del contenuto con il termine cercato evidenziato nel contenuto.

1. Select **Replace single occurrence** \( ![](images/replace-icon.svg)\) to replace the currently highlighted search term in the topic or select Next match ![](images/next-match-in-search.png) or ![](images/previous-match-in-search.png) Previous match to move to the next or previous occurrence of the text.
1. Select **Replace all** \( ![](images/replace-all-in-file-icon.svg)\)to replace all occurrences of the searched term in a single file with the replace term in a single click. You will be shown a notification after replacing all the occurrences in the selected file.

To enable the **Replace all** icon, your system administrator must select the option **Enable Replace All** under the **General** tab in **Settings**.

>[!NOTE]
>
> Passa il puntatore del mouse su un file dall&#39;elenco dei risultati di ricerca per visualizzare l&#39;icona Sostituisci tutto nel file sulla destra. Viene inoltre visualizzata l&#39;icona Ignora file per rimuovere il file dal risultato della ricerca. I file ignorati vengono rimossi dall&#39;elenco e il termine ricercato non viene sostituito.

È possibile eseguire una sola operazione di sostituzione alla volta nell&#39;intero sistema e, fino a quando non viene eseguita, verrà visualizzato lo stato &quot;Sostituisci tutto in corso&quot;. Puoi anche interrompere l’operazione Sostituisci tutto tra o visualizzare il rapporto del registro. Se si interrompe l&#39;operazione, si riceverà una notifica nella Posta in arrivo. Dopo la sostituzione di tutte le occorrenze nel file selezionato, verrà visualizzata una notifica di esito positivo.

![](images/replace-all-in-progress.png){width="300" align="left"}

È inoltre possibile utilizzare l&#39;opzione **Trova in mappa** dal menu **Opzioni** di una mappa per trovare e sostituire il testo in una mappa. Questa opzione viene visualizzata per una mappa aperta nel pannello del repository o nella vista mappa.

![](images/map-options-menu.png){width="550" align="left"}

### Modelli PDF

Consente di utilizzare diversi modelli di PDF. Per ulteriori dettagli, visualizzare [modelli di PDF](../native-pdf/pdf-template.md).

### Rivedere

In Experience Manager Guides è disponibile la funzione che consente di visualizzare tutte le attività di revisione nei progetti. Puoi visualizzare tutti i progetti di revisione e le attività di revisione attive nei progetti di revisione di cui fai parte dal pannello **Revisione**.  È quindi possibile aprire le attività di revisione per visualizzare i commenti dei vari revisori.

Nel pannello Revisione vengono visualizzate le attività di revisione. Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

In qualità di autore, puoi indirizzare i commenti in un argomento utilizzando l’Editor.

Per visualizzare i commenti di revisione nelle attività di revisione attive presenti nei progetti, effettuare le seguenti operazioni:

1. Seleziona Revisione nel pannello a sinistra. Viene aperto il pannello **Rivedi**.  Vengono visualizzati tutti i progetti di revisione e le attività di revisione attive all&#39;interno dei progetti di revisione di cui fai parte.

   ![](images/web-editor-review-panel.png){width="300" align="left"}
1. Selezionare un progetto di revisione e quindi selezionare un&#39;attività di revisione dall&#39;elenco per aprirla.
1. Puoi anche filtrare i progetti nei seguenti modi:

   - Immetti il termine o il testo da cercare nel titolo del progetto. Quindi premere Invio per eseguire la ricerca. Ad esempio, puoi cercare tutti i progetti il cui titolo contiene il termine &quot;spazio&quot;.

   - Selezionare ![](images/filter-search-icon.svg) per aprire la finestra di dialogo **Filtro**. Puoi selezionare tutti o solo progetti specifici. I progetti selezionati sono elencati nel pannello **Rivedi**.

     ![](images/active-review-select-project.png){width="300" align="left"}

     Abilita l&#39;opzione **Attività avviate da me** per visualizzare solo le attività avviate. Lo stato di attivazione o disattivazione di questa opzione viene mantenuto anche dopo l’aggiornamento della pagina. Abilita l&#39;opzione **Mostra solo attività attive** per filtrare l&#39;elenco dei progetti in modo da visualizzare le attività attualmente attive.

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


## Area di modifica dei contenuti

The content editing area is where the content of your topic or map is displayed. You make all content edits in this area. It gives a WYSIWYG view of the content you are editing.

At the bottom-left of the content editing area, you have the breadcrumb of the element at current cursor location. In the bottom-right corner, the available Editor views are displayed.

![](images/content-editing-area.png){align="left"}

To learn more about the Editor views available for a topic file in the content editing area, view [Editor views](./web-editor-views.md).

>[!NOTE]
>
> If you are working on a map file, then different options or views are displayed in the content editing area , including a **Layout** view for the map file. For more details, view [Map editor features](./map-editor-advanced-map-editor.md).

## Pannello a destra

The right panel contains information about the currently selected document.

>[!NOTE]
>
> The right panel is resizable. Per ridimensionare il pannello, posiziona il cursore sul bordo del pannello. Il cursore si trasforma in una freccia a due punte, seleziona e trascina per ridimensionare la larghezza del pannello.

The right panel gives you access to the following features:

- [Content properties](#content-properties)
- [Proprietà file](#file-properties)
- [Rivedere](#review-1)
- [Track changes](#track-changes)
- [Schematron](#schematron)

### Content properties

You can access the **Content properties** feature by selecting the **Content properties** icon in the right panel. The **Content properties** panel contains information about the type of currently selected element in the document and its attributes.

**Type**: You can view and select the tags of the complete hierarchy for the current tag from the dropdown.

**Attributi**: il pannello a discesa **Attributi** è disponibile nelle visualizzazioni Layout, Autore e Source. Puoi aggiungere, modificare o eliminare facilmente gli attributi.

1. Seleziona **Aggiungi**.

   ![attributi nelle proprietà del contenuto](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. Nel pannello a discesa **Attributo**, seleziona l&#39;attributo dall&#39;elenco a discesa e specifica il valore di un attributo.  Then select **Add**.

   ![pannello attributi con più attributi &#x200B;](images/attributes-multiple-properties.png){width="300" align="left"}

1. Per modificare l&#39;attributo, passa il puntatore su di esso e seleziona **Modifica** ![icona-modifica](images/edit_pencil_icon.svg).

1. Per eliminare l&#39;attributo, posizionare il puntatore del mouse su di esso e selezionare **Elimina** ![elimina-icona](images/Delete_icon.svg).


>[!NOTE]
>
> Anche se l&#39;argomento contiene contenuto di riferimento, è possibile aggiungervi attributi utilizzando il pannello delle proprietà.

Se l’amministratore ha creato un profilo per gli attributi, questi vengono ottenuti insieme ai relativi valori configurati. Utilizzando il pannello delle proprietà del contenuto, potete scegliere questi attributi e assegnarli al contenuto pertinente nell&#39;argomento. In questo modo puoi anche creare contenuto condizionale, che può quindi essere utilizzato per creare l’output condizionale. Per ulteriori informazioni sulla generazione dell&#39;output utilizzando i predefiniti condizionali, visualizzare [Usa predefiniti condizione](generate-output-use-condition-presets.md#).

### Proprietà file

Visualizzare le proprietà del file selezionato selezionando l&#39;icona Proprietà file nel pannello di destra. La funzione Proprietà file è disponibile in tutte e quattro le modalità o visualizzazioni: Layout, Autore, Source e Anteprima.

Le proprietà File sono suddivise nelle due sezioni seguenti:

**Generale**

La sezione Generale consente di accedere alle seguenti funzioni:

![proprietà-file](images/file-properties-general.png){width="300" align="left"}

- **Nome file**: visualizza il nome del file dell&#39;argomento selezionato. Il nome del file viene collegato alla pagina delle proprietà del file selezionato.
- **ID**: visualizza l&#39;ID dell&#39;argomento selezionato.
- **Tag**: questi sono i tag di metadati dell&#39;argomento. Vengono impostati dal campo tag della pagina delle proprietà. Puoi digitarli o selezionarli dal menu a discesa.  I tag vengono visualizzati sotto il menu a discesa. Per eliminare un tag, seleziona l’icona a forma di croce accanto al tag.
- **Modifica altre proprietà**: è possibile modificare altre proprietà dalla pagina delle proprietà del file.
- **Lingua**: mostra la lingua dell&#39;argomento. Viene impostato dal campo della lingua nella pagina delle proprietà.
- **Data creazione**: visualizza la data e l&#39;ora di creazione dell&#39;argomento.
- **Modificato il**: visualizza la data e l&#39;ora di modifica dell&#39;argomento.
- **Bloccato da**: mostra l&#39;utente che ha bloccato l&#39;argomento.
- **Stato documento**: è possibile selezionare e aggiornare lo stato del documento dell&#39;argomento attualmente aperto. Per ulteriori dettagli, visualizzare [Stato documento](web-editor-document-states.md#).

>[!NOTE]
>
> È possibile copiare negli Appunti i valori degli attributi dei vari campi delle proprietà File.

**Riferimenti**

La sezione Riferimenti (References) consente di accedere alle seguenti funzioni:

![](images/file-properties-references.png){width="300" align="left"}

- **Usato in**: Usato nei riferimenti elenca i documenti in cui viene fatto riferimento o utilizzato il file corrente.
- **Collegamenti in uscita:** I collegamenti in uscita elencano i documenti a cui si fa riferimento nel documento corrente.

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

>[!NOTE]
>
> Tutti i riferimenti utilizzati in e in uscita sono collegati ai documenti. È possibile aprire e modificare facilmente i documenti collegati.

Oltre ad aprire i file, è possibile eseguire molte azioni utilizzando il menu **Opzioni** nella sezione Riferimenti. Alcune delle azioni che puoi eseguire includono Modifica, Anteprima, Copia UUID, Copia percorso, Aggiungi a raccolte, Proprietà.

### Rivedere

Se si seleziona l&#39;icona Revisione, viene aperto il pannello Revisione in cui è possibile selezionare un task di revisione per il documento aperto e visualizzare i commenti.

![](images/review-panel-before-opening.png){width="300" align="left"}

Se hai creato più progetti di revisione, puoi selezionarne uno dal menu a discesa e accedere ai relativi commenti.

Il pannello Revisione consente di visualizzare e pubblicare le risposte ai commenti sull&#39;argomento. È possibile accettare o rifiutare i commenti singolarmente.

>[!NOTE]
>
> La casella dei commenti e la casella delle risposte supportano le voci su più righe e consentono agli utenti di espanderle in base alle esigenze per fornire commenti completi e risposte dettagliate ai commenti. È possibile utilizzare **Maiusc** + **Invio** per passare alla riga successiva durante la scrittura dei commenti o delle risposte.

Per ulteriori informazioni, visualizzare [Commenti sulla revisione degli indirizzi](review-address-review-comments.md#).

### Rileva modifiche

Utilizzando la funzione Tracked changes (Modifiche tracciate) del pannello di destra, potete visualizzare le informazioni di tutti gli aggiornamenti apportati in un documento. È inoltre possibile cercare qualsiasi aggiornamento specifico apportato al documento.

>[!NOTE]
>
> La funzionalità delle modifiche rilevate mostra tutti gli aggiornamenti rilevati tramite la funzionalità Attiva/Disattiva rilevamento modifiche della [barra delle schede](#tab-bar).

### Schematron

&quot;Schematron&quot; si riferisce a un linguaggio di convalida basato su regole utilizzato per definire test per un file XML. L&#39;editor supporta i file Schematron. Potete importare i file Schematron e modificarli nell&#39;Editor. Utilizzando un file Schematron è possibile definire determinate regole e quindi convalidarle per un argomento o una mappa DITA.

Scopri come utilizzare i file Schematron in Experience Manager Guides. Fai riferimento a [Supporto per i file Schematron](./support-schematron-file.md).



**Argomento padre**: [Introduzione all&#39;editor](web-editor.md)
