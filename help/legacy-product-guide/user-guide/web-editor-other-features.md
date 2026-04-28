---
title: Altre funzioni dell’editor web
description: Esplora altre funzioni dell’editor web in AEM Guides. Scopri come utilizzare queste funzioni per migliorare l’authoring in AEM Guides.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 7639fa76-b319-44b5-9ff8-2b8c1a716b7b
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '2564'
ht-degree: 0%

---

# Altre funzioni dell’editor web {#id2056B0B0YPF}

Nell&#39;editor Web sono disponibili altre funzioni utili che è possibile utilizzare:

**Funzioni del menu di scelta rapida nella scheda di un file**

Quando si apre un file nell&#39;Editor Web, è possibile eseguire varie azioni dal menu di scelta rapida. È possibile che vengano visualizzate opzioni diverse a seconda che si apra un file multimediale, un singolo file DITA o più file.

**File multimediale**

Nel menu di scelta rapida della scheda di un file multimediale aperto vengono visualizzate le seguenti funzioni:

![](images/media-file-context-menu.png){width="300" align="left"}

**File DITA singolo**

Nel menu di scelta rapida della scheda di un file aperto vengono visualizzate le seguenti funzioni:

:   ![](images/single-file-context-menu.png){width="300" align="left"}

**Più file**

Quando sono aperti più file, nel menu di scelta rapida vengono visualizzate altre opzioni:

![](images/multiple-files-context-menu.png){width="550" align="left"}

Di seguito sono illustrate le varie opzioni del menu di scelta rapida:

***Salva***: puoi scegliere tra le seguenti opzioni:

- **Salva**: per salvare un file senza creare una nuova versione, selezionare **Salva**. Ogni volta che crei un nuovo argomento, in DAM viene creata una copia di lavoro senza versione dell’argomento. Il salvataggio del documento aggiorna la copia di lavoro del documento in DAM. Se si esegue un semplice salvataggio su questa versione, non viene creata una nuova versione di un argomento. Se l&#39;argomento è in revisione, il salvataggio di un argomento non consente ai revisori di accedere al contenuto dell&#39;argomento modificato.

- **Salva tutto**: se nell&#39;editor Web sono aperti più documenti, è disponibile anche un&#39;opzione per **Salva tutti** i documenti aperti.


***Salva come nuova versione***

Per creare una nuova versione del file, selezionare **Salva come nuova versione**. Per ulteriori dettagli su **Salva** e **Salva come nuova versione**, vedere [Conoscere le funzionalità dell&#39;editor Web](web-editor-features.md#).

***Copia***: puoi scegliere tra le seguenti opzioni:

- **Copia UUID**: per copiare negli Appunti l&#39;UUID del file attualmente attivo, selezionare **Copia \> Copia UUID**.
- **Copia percorso**: per copiare negli Appunti il percorso completo del file attualmente attivo, selezionare **Copia \> Copia percorso**.


***Individua in***: è possibile scegliere tra le opzioni seguenti:

- **Mappa**: se hai aperto una mappa DITA di grandi dimensioni e desideri trovare la posizione esatta di un file nella mappa, seleziona **Individua in \> Mappa**. Quando si seleziona l&#39;opzione Individua nella mappa, il file \(da cui viene richiamata l&#39;opzione\) viene posizionato ed evidenziato nella gerarchia della mappa. Per poter utilizzare questa funzionalità, è necessario aprire il file di mapping nell&#39;editor Web. Se la vista mappa è nascosta, quando si richiama questa funzione viene visualizzata la vista mappa e il file viene evidenziato nella gerarchia delle mappe.

- **Archivio**: simile a Individua in mappa, **Individua in \> Archivio** mostra la posizione del file nel repository \(o DAM\). Viene aperta la vista Archivio e il file selezionato viene evidenziato nel repository. Se il file si trova all&#39;interno di una cartella, quest&#39;ultima viene espansa per mostrare la posizione del file selezionato nel repository.


***Aggiungi a***: è possibile scegliere tra le opzioni seguenti:

- **Preferiti**: per aggiungere il file selezionato alla raccolta preferita, selezionare **Aggiungi a \> Preferiti**. Per ulteriori dettagli, vedere la descrizione della funzionalità **Preferiti** nella sezione [Pannello sinistro](web-editor-features.md#id2051EA0M0HS).



- **Contenuti riutilizzabili**: per copiare il file selezionato nell&#39;elenco dei contenuti riutilizzabili, selezionare **Aggiungi a \> Contenuti riutilizzabili**. Per ulteriori dettagli, vedere la descrizione della funzionalità **Contenuti riutilizzabili** nella sezione [Pannello sinistro](web-editor-features.md#id2051EA0M0HS).




***Proprietà***

Per visualizzare la pagina delle proprietà di AEM del file selezionato, selezionare **Proprietà**.

***Dividi***: puoi scegliere tra le seguenti opzioni:

**Su, Giù, Sinistra o Destra**

Per impostazione predefinita, l&#39;Editor Web consente di visualizzare un argomento alla volta. In alcuni casi potrebbe essere utile visualizzare due o più argomenti contemporaneamente. La suddivisione della schermata dell&#39;editor consente di visualizzare più argomenti contemporaneamente. Ad esempio, se hai due argomenti: A e B aperti nell’editor. Facendo clic con il pulsante destro del mouse sull&#39;argomento B e scegliendo **Dividi \> Su**, la finestra dell&#39;editor viene divisa in due parti. L&#39;argomento B viene visualizzato nella metà superiore e l&#39;argomento A nella metà inferiore. Allo stesso modo, è possibile dividere lo schermo orizzontalmente selezionando **Dividi \> Sinistra** o **Dividi \> Destra**. Nella schermata seguente dell&#39;Editor Web vengono visualizzati gli argomenti suddivisi orizzontalmente e verticalmente. In ogni suddivisione è possibile avere una visualizzazione diversa. Ad esempio, nella schermata seguente, la schermata 1 è in modalità di visualizzazione Source, la schermata 2 contiene due documenti aperti in modalità Creazione e la schermata 3 è in modalità Anteprima. È possibile spostare i documenti da una schermata all&#39;altra trascinando la scheda del file e rilasciandola sulla schermata in cui si desidera posizionarla. Analogamente, è possibile riordinare le schede dei file trascinandole e spostandole in base alle proprie preferenze.

![](images/split-editor.png){width="800" align="left"}

***Generazione rapida***

Genera l&#39;output per il file selezionato. L&#39;output può essere generato solo per i file che fanno parte di un predefinito di output. Per ulteriori dettagli, vedere [Pubblicazione basata su articolo dall&#39;editor Web](web-editor-article-publishing.md#id218CK0U019I).

***Chiudi***: è possibile scegliere tra le opzioni seguenti:

**Chiudi**, **Chiudi altri** o **Chiudi tutti**

Se si desidera chiudere il file da cui è stato richiamato il menu di scelta rapida, selezionare **Chiudi \> Chiudi**. Utilizzare **Chiudi \> Chiudi altri** per chiudere tutti gli altri file aperti ad eccezione del file attivo. Per chiudere tutti i file aperti, selezionare l&#39;opzione **Chiudi \> Chiudi tutto** dal menu di scelta rapida oppure è possibile scegliere di chiudere l&#39;editor Web. Se nella sessione sono presenti file non salvati, viene richiesto di salvarli.

**Scenari di chiusura e salvataggio dei file**

Quando si tenta di chiudere un file aperto nell&#39;editor Web utilizzando il pulsante **Chiudi** nella scheda del file o l&#39;opzione **Chiudi** nel menu Opzioni, AEM Guides richiede di salvare le modifiche e sbloccare un file bloccato.

Le richieste di conferma si basano sulle seguenti configurazioni selezionate dall’amministratore:

- **Richiedi archiviazione alla chiusura:** È possibile archiviare il file \(che è stato estratto\) alla chiusura dell&#39;editor.
- **Richiedi nuova versione alla chiusura**: è possibile salvare il file \(che è stato modificato\) come nuova versione alla chiusura dell&#39;editor.

L’esperienza di salvataggio dei file dipenderà dai tre scenari seguenti, in cui disponi di:

- Nessuna modifica apportata al contenuto.
- Ha modificato il contenuto e ha salvato le modifiche.
- Edited the content but not saved the changes.

You may see the following options depending on whether the file is locked/unlocked and has saved or unsaved changes:

- **Unlock and Close**: The lock on the file is released, and the file gets closed.

  ![](images/file-close-unlock-file.png){width="400" align="left"}

- **Save as a New Version**: This will save the changes you have made in your content and create a new version of your file. You can also add labels and comments for the newly saved version. Per ulteriori informazioni sul salvataggio di una nuova versione, vedere [Salva come nuova versione](web-editor-features.md#save-as-new-version-id209ME400GXA).

- **Unlock the File**: If you choose to unlock a file, it will release the lock on your file and the changes are saved in the current version of the file.

  >[!NOTE]
  >
  > If you deselect the option to unlock the file, you also get an option to close the file without saving the changes.

  For example, one of the prompts is shown in the following screenshot:

  ![](images/file-close-save-changes-unlock.png){width="400" align="left"}

**Visual cues for broken references**

- If your topic contains broken cross-references or content references, they are shown in red text.

**Smart copy-paste**

- You can easily copy paste content within and across topics. The source element structure is maintained at the destination. Also, if the copied content contains content references, then even those are copied.

**Remember last browsed location**

- The Web Editor provides a smart file browse dialog. The editor remembers the last used location while inserting a reference or content. The first time you invoke the file browse dialog \(via Insert Reference or Insert Reuse Content\), then you are taken to the location where the current document is saved. In the same session, if you try to insert another reference, then the file browse dialog automatically navigates to the location from where you inserted the last reference.

>[!NOTE]
>
> In case of an image, audio, or video file, the file browse dialog defaults to the file&#39;s location and not the last used location.

**Support for article-based publishing**

- From the Web Editor, you can generate the output for one or more topics, or the entire DITA map. You need to create output presets for your DITA map and then you can easily generate the output for one or more topics. If you have updated a few topics in your map, you can also generate the output only for those topics from the Web Editor. Per ulteriori dettagli, vedere [Pubblicazione basata su articolo dall&#39;editor Web](web-editor-article-publishing.md#id218CK0U019I).

**Supporto per i documenti Markdown**

- L&#39;Editor Web consente di utilizzare i documenti Markdown \(.md\) insieme ai documenti DITA. È possibile creare e visualizzare in anteprima un documento Markdown nell&#39;Editor Web e aggiungerlo nel file di mappa tramite l&#39;editor di mappe DITA. Per ulteriori dettagli, vedere [Creare documenti Markdown dall&#39;editor Web](web-editor-markdown-topic.md#).

**Supporto per l&#39;argomento termine glossario DITA**

- L&#39;editor Web supporta i termini del glossario DITA che è possibile inserire aggiungendo `term` o `abbreviated-form` elementi.

**Inserisci equazioni MathML**

- Experience Manager Guides offre un supporto predefinito per l&#39;inserimento di equazioni di MathML tramite l&#39;integrazione con l&#39;applicazione [MathType Web](https://docs.wiris.com/en/mathtype/mathtype_web/intro). Per inserire un&#39;equazione di MathML, selezionare l&#39;icona **Inserisci elemento** e digitare mathml. Quando si seleziona l&#39;elemento matml dall&#39;elenco, viene visualizzata la finestra di dialogo **Inserisci MathML**:

![inserire l&#39;equazione mathml nell&#39;editor mathml](images/insert-mathml-equation.png){width="550" align="left"}

Utilizzando gli strumenti di equazione di MathML, creare l&#39;equazione e fare clic su **Inserisci** per aggiungerla al documento. L&#39;equazione viene inserita con uno sfondo grigio chiaro, come illustrato di seguito:

![equazione di esempio](images/sample-mathml-equation.PNG){width="400" align="left"}

In qualsiasi momento è possibile aggiornare un&#39;equazione facendo clic con il pulsante destro del mouse su un&#39;equazione esistente e selezionando **Modifica MathML** dal menu di scelta rapida.

- **Convalida delle equazioni nell&#39;editor di MathML**

  Experience Manager Guides convalida le equazioni di MathML quando si salva un argomento che le contiene.
Quando si inserisce un&#39;equazione utilizzando l&#39;editor di MathML, in caso di problemi di sintassi Experience Manager Guides evidenzia l&#39;equazione in rosso. È possibile correggerla prima di inserirla. Se non si apportano modifiche ma si seleziona **Inserisci**, verrà visualizzato un avviso.

  ![convalida equazione matematica](images/validate-mathml-equation.png){width="400" align="left"}

  Se si inserisce l&#39;equazione di MathML che contiene un errore di sintassi, quando si tenta di salvare l&#39;argomento si verifica un errore di convalida.


**Inserisci note a piè di pagina**

- Inserire una nota a piè di pagina nel contenuto utilizzando l&#39;elemento `fn`. Nella modalità di creazione, il valore della nota a piè di pagina viene visualizzato in linea con il contenuto. Tuttavia, quando si passa alla modalità Anteprima o si pubblica il documento, la nota a piè di pagina viene visualizzata alla fine dell&#39;argomento.


**Rinominare o sostituire un elemento**

- L’editor web visualizza la breadcrumb dell’elemento nella parte superiore dell’argomento. Se desideri scambiare o sostituire un elemento con un altro elemento, puoi farlo dal menu di scelta rapida della breadcrumb. Ad esempio, è possibile scambiare l&#39;elemento `p` con `note` o qualsiasi altro elemento valido nel contesto.

![](images/rename-element.png){width="400" align="left"}

Nella breadcrumb, fai clic con il pulsante destro del mouse sul nome di un elemento che desideri sostituire, quindi seleziona Rinomina elemento dal menu di scelta rapida. Nella finestra di dialogo Rinomina elemento vengono visualizzati tutti gli elementi validi consentiti nella posizione corrente. Dalla finestra di dialogo Rinomina elemento, seleziona l’elemento che desideri utilizzare. L’elemento originale viene sostituito con il nuovo elemento.

Oltre al menu di scelta rapida della breadcrumb, è possibile accedere alla finestra di dialogo Rinomina elemento da altre posizioni:

- Fai clic sul nome dell’elemento nella breadcrumb per selezionare il contenuto dell’elemento, quindi fai clic con il pulsante destro del mouse sul contenuto selezionato per visualizzare il menu di scelta rapida.

- Abilita la visualizzazione Tag, fai clic sul tag di apertura di qualsiasi elemento, quindi fai clic con il pulsante destro del mouse sul contenuto selezionato per visualizzare il menu di scelta rapida.

- Potete accedere alla finestra di dialogo Rinomina elemento (Rename Element) richiamando il menu Opzioni (Options) di un elemento nel pannello Struttura.



**Racchiudi un elemento**

- La disposizione di un elemento consente di aggiungere un tag elemento al testo selezionato. È possibile racchiudere il testo in qualsiasi elemento figlio seguendo gli standard DITA. Ad esempio, se il testo si trova sotto un elemento `note`, è possibile racchiuderlo in un elemento `p`.

  L&#39;opzione **Wrap Element** è disponibile nel menu di scelta rapida della breadcrumb dell&#39;argomento. Per racchiudere un elemento, fai clic con il pulsante destro del mouse sull’elemento e apri il menu di scelta rapida. Selezionare l&#39;elemento dalla finestra di dialogo **Elemento a capo**. Il testo viene visualizzato nel nuovo elemento.

  È inoltre possibile selezionare il testo o l&#39;elemento nel contenuto e quindi selezionare l&#39;opzione **Elemento a capo** dal menu di scelta rapida.

**Annullamento del wrapping di un elemento**

- L’apertura di un elemento consente di rimuovere il tag elemento dal testo selezionato e di unirlo al relativo elemento padre. Se ad esempio si dispone di un elemento `p` all&#39;interno di un elemento `note`, è possibile annullare il wrapping dell&#39;elemento `p` per unire il testo direttamente all&#39;interno dell&#39;elemento `note`. L&#39;opzione **Annulla wrapping elemento** è disponibile nel menu di scelta rapida della breadcrumb dell&#39;argomento. Per annullare il wrapping di un elemento, fare clic con il pulsante destro del mouse sull&#39;elemento per aprire il menu di scelta rapida, quindi selezionare **Annulla wrapping elemento** per rimuovere l&#39;elemento e unire il testo dell&#39;elemento con l&#39;elemento padre.

**Gestione dello spazio vuoto per gli elementi DITA**

- In XML, gli spazi vuoti includono spazi, tabulazioni, ritorni a capo e righe vuote. Experience Manager Guides converte più spazi vuoti conseguenti in un unico spazio. In questo modo è possibile mantenere la visualizzazione WYSIWYG dell&#39;editor Web.

  >[!NOTE]
  >
  >In alcuni elementi in cui gli spazi bianchi devono essere conservati secondo le regole DITA, vengono mantenuti i molteplici spazi bianchi conseguenti. Ad esempio, `<pre>` e `<codeblock>` elementi.


**Mantenimento delle interruzioni di riga e del rientro**

- Gli elementi DITA che contengono interruzioni di riga e spazi sono supportati e renderizzati in base alla loro definizione nelle modalità Autore, Source o Anteprima e anche nell’output finale pubblicato. La schermata seguente mostra il contenuto all&#39;interno dell&#39;elemento `msgblock` in cui sono stati mantenuti le interruzioni di riga e gli spazi \(rientro\):

![](images/new-line-support_cs.png){width="500" align="left"}



**Gestione di spazi unificatori nell&#39;editor Web**

- Puoi inserire spazi unificatori nel documento utilizzando l&#39;icona **Inserisci caratteri speciali** ![Inserisci caratteri speciali](images/insert-special-chars-icon.svg) o i tasti di scelta rapida **Alt** + **Spazio**.  Questi spazi unificatori vengono visualizzati come indicatori durante la modifica di un argomento nell&#39;Editor Web. È possibile disattivare la visualizzazione degli spazi unificatori con l&#39;opzione **Mostra indicatore di spazio unificatore in modalità di creazione** dalla scheda **Aspetto** della **Preferenze utente** ![Icona Preferenze utente](images/user_preference_editor_icon.svg).

- Se si copia e si incolla contenuto con uno spazio unificatore da qualsiasi origine esterna nella visualizzazione **Autore**, lo spazio unificatore viene convertito in uno spazio.
Tuttavia, se copi e incolla contenuto con uno spazio unificatore dalla visualizzazione **Autore**, questo verrà mantenuto.


**ID elemento generato automaticamente**

- È possibile generare automaticamente gli ID per gli elementi nell&#39;argomento DITA. Questi ID sono univoci in un argomento DITA. Ad esempio, se generi ID per un elemento paragrafo, gli ID saranno p\_1, p2, p\_3 e così via. Puoi selezionare più elementi e generare ID per ciascun elemento selezionato.

Per generare automaticamente l’ID per uno o più elementi, effettua le seguenti operazioni:

1. Apri l’argomento nell’editor web.
1. Seleziona il contenuto a cui assegnare gli ID.
1. Fare clic con il pulsante destro del mouse e selezionare **Genera ID dal menu di scelta rapida.**

   In alternativa, puoi fare clic con il pulsante destro del mouse nella breadcrumb e selezionare **Genera ID**.


**Argomento padre:**[ Utilizzare l&#39;editor Web](web-editor.md)
