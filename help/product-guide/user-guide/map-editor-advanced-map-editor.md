---
title: Utilizzare l’Editor di mappe avanzato
description: Scopri come utilizzare l’editor di mappe avanzato nelle guide AEM. Conoscere le funzioni dell’Editor mappe avanzato. Modificare gli argomenti tramite una mappa DITA e utilizzare le visualizzazioni Layout, Autore e Anteprima.
exl-id: e58e3705-2c3b-48cc-b2c8-2596e9751c85
feature: Authoring, Map Editor
role: User
source-git-commit: 6201434d3dd8336bf9fe1bce6368d5dbb9c56162
workflow-type: tm+mt
source-wordcount: '3788'
ht-degree: 0%

---

# Utilizzare l’Editor di mappe avanzato {#id1942D0S0IHS}

L’Editor mappe avanzato è dotato di un’interfaccia utente intuitiva ed è simile all’Editor web. Quando si apre un file di mapping nell&#39;editor Web, viene visualizzata un&#39;opzione che consente di modificare il file di mapping tramite l&#39;interfaccia Editor mapping avanzato. L’Editor mappe avanzato consente di aggiungere riferimenti ad argomenti, riferimenti chiave, strutturare il contenuto e altro ancora.

Oltre a modificare i file di mapping direttamente dall&#39;editor Web, è possibile aprire i file degli argomenti in una mappa per modificare l&#39;editor Web. Questo argomento illustra le funzioni dell&#39;Editor mappe avanzate e le modalità di apertura e modifica dei file in una mappa DITA nell&#39;Editor Web.

## Aggiungere argomenti a un file di mappa

Per creare il file di mappa mediante l&#39;Editor mappe avanzato, effettuare le seguenti operazioni:

1. Nell’interfaccia utente Assets, individua il file di mappa da modificare.

   >[!NOTE]
   >
   > Assicurati di non aver attivato la modalità di selezione delle risorse.

1. Per ottenere un blocco esclusivo sul file mappa, selezionare il file mappa e fare clic su **Estrai**.

   >[!NOTE]
   >
   > Una volta impostato un blocco esclusivo su un file di mappa, gli altri utenti non potranno modificare la mappa. Tuttavia, sarebbero in grado di lavorare sugli argomenti all&#39;interno del file di mappa. Se l&#39;amministratore ha configurato l&#39;editor Web per estrarre i file prima di modificarli, non sarà possibile modificare un file finché non lo si estrae. Analogamente, se configurata, verrà richiesto di archiviare qualsiasi file estratto prima di chiuderlo

1. Con il file di mappa selezionato, fai clic su **Modifica argomenti**.

   ![](images/edit-map-main-menu.png){width="800" align="left"}

   Oppure, puoi anche selezionare **Modifica argomenti** opzione dal menu azione sul file mappa:

   ![](images/edit-map-action-menu.png){width="800" align="left"}

   Il file di mappa viene aperto per la modifica in nell’Editor web.

1. Fai clic su **Modifica** icona.

   ![](images/edit-map-icon.png){width="550" align="left"}

   La mappa viene aperta nell’interfaccia dell’Editor mappe avanzato. Se hai aperto un nuovo file di mappa, nell’editor viene visualizzato solo il titolo della mappa.

   ![](images/new-map-file-in-editor.png){width="800" align="left"}

   - **A** - \(*Barra degli strumenti principale*\): simile alla barra degli strumenti principale dell’editor web. Consulta [Barra degli strumenti principale](web-editor-features.md#id2051EA0G05Z) nell’editor web per ulteriori dettagli.

   - **B** - \(*Barra degli strumenti secondaria*\) Questa è la barra degli strumenti Secondaria che consente di lavorare con i file di mappa. Per ulteriori informazioni sulle funzionalità disponibili nella barra degli strumenti Secondaria, vedi [Funzioni disponibili nella barra degli strumenti dell’Editor mappe avanzate](#id205DEC0005Z).

   - **C** - \(*Visualizzazioni mappa*\): consente di passare dall’Editor mappa a Layout, Author, Source e Preview e viceversa. Il **Layout** consente di organizzare gli argomenti in una mappa DITA. In questo modo viene visualizzata la struttura o la struttura gerarchica della mappa. Il **Autore** consente di modificare gli argomenti nell’Editor mappa. Questo offre anche la visualizzazione WYSIWYG del file di mappa. Il **Sorgente** visualizzazione consente di utilizzare l&#39;XML sottostante del file di mapping. L&#39;anteprima offre una visualizzazione consolidata di tutti gli argomenti e delle mappe secondarie all&#39;interno del file di mappa. Il **Chiudi** link chiude il file di mappa.

   - **D** - \(*Pannello sinistro*\): consente di accedere al pannello a sinistra, che consente di accedere a Preferiti, Archivio, Mappa, Struttura e altre funzioni. Per espanderla o comprimerla, fai clic sull’icona Espandi barra laterale \(![](images/sidebar-expand-icon.svg)\). Per ulteriori dettagli sulle funzioni disponibili nel pannello a sinistra, vedi [Pannello sinistro](web-editor-features.md#id2051EA0M0HS) nell&#39;editor Web.

   - **E** - \(*Area centrale*\): area di modifica contenuto mappa.

   - **F** - \(*Pannello a destra*\): consente di accedere al pannello Proprietà. Puoi visualizzare le proprietà del contenuto e le proprietà della mappa dell’argomento o della mappa selezionata. Per ulteriori dettagli sulle funzionalità disponibili in questo pannello, vedi [Pannello a destra](web-editor-features.md#id2051EB003YK) nell&#39;editor Web.

1. Nel pannello a sinistra, passa a **Vista archivio**.

1. Nel repository AEM passare alla cartella contenente gli argomenti o le mappe secondarie che si desidera aggiungere.

1. Selezionare l&#39;argomento o il file di mappa in **Vista archivio** e trascinarlo nell’area di modifica del contenuto delle mappe \(middle\).

   L&#39;argomento viene aggiunto nella mappa.

   ![aggiungi argomento editor mappe](images/map-editor-add-topic.png){width="800" align="left"}

1. Per aggiungere argomenti successivi o una mappa secondaria, trascinare l&#39;argomento o la mappa secondaria nella posizione desiderata nella mappa.

   Durante la creazione del file di mappa, considera i punti seguenti:

   - Il file viene aggiunto in un punto in cui la barra orizzontale viene visualizzata nell&#39;area di modifica delle mappe. Nella schermata seguente, *Panoramica* L&#39;argomento verrà aggiunto tra *Descrizione generale* e *Launch e sito di destinazione* argomenti.

     ![](images/horizontal-line-in-adv-map-editor.png){width="350" align="left"}

   - Per sostituire un argomento, posizionare l&#39;argomento in alto, a sinistra o a destra dell&#39;argomento che si desidera sostituire. Una barra verticale a sinistra o a destra di un argomento indica che verrà sostituito con l&#39;argomento che viene rilasciato su di esso.

     ![](images/vertical-bar-left-right.png){width="550" align="left"}

     Tuttavia, prima di sostituire un argomento, viene visualizzata una richiesta di conferma. L’argomento viene sostituito solo dopo la conferma.

     ![](images/replace-topic-confirm.png){width="300" align="left"}

   - Se si aggiunge una mappa secondaria alla mappa DITA, questa verrà visualizzata come collegamento nella mappa DITA. Per visualizzare tutti gli argomenti della mappa secondaria, fare clic sul collegamento corrispondente. Il contenuto della mappa secondaria viene visualizzato in una nuova scheda. Allo stesso modo, per aprire un argomento dalla mappa DITA, fare clic sul collegamento dell&#39;argomento e aprirlo nella nuova scheda.

   - È possibile utilizzare i tasti di scelta rapida CTRL+Z e CTRL+Y o le rispettive icone nella barra degli strumenti per annullare o ripristinare eventuali modifiche apportate alla mappa.

   - Per modificare la posizione di un argomento, selezionare l&#39;argomento \(facendo clic sull&#39;icona dell&#39;argomento\), quindi trascinarlo nella posizione desiderata nel file di mappa. Verificare che la barra orizzontale sia visibile nel punto in cui si desidera inserire l&#39;argomento. Nella schermata seguente, l’argomento *Launch e sito di destinazione* viene spostato dopo il *Panoramica* argomento.

     ![](images/move-topic-adv-map-editor.png){width="350" align="left"}

   - Per verificare le proprietà del file mappa, fare clic con il pulsante destro del mouse in un punto qualsiasi dell&#39;area di modifica della mappa e scegliere **Proprietà** dal menu di scelta rapida. In base alla versione dell’AEM in uso, puoi visualizzare proprietà quali metadati, pianificazione \(de\)attivazione, riferimenti, stato del documento e altro ancora.

1. Fai clic su **Salva**.


## Funzioni disponibili nella barra degli strumenti dell’Editor mappe avanzate {#id205DEC0005Z}

La barra degli strumenti nell&#39;Editor mapping avanzato è simile all&#39;argomento Editor Web. Le operazioni di base, come l’attivazione del pannello sinistro, il salvataggio della mappa, la creazione di una nuova versione della mappa, l’annullamento/ripristino dell’ultima operazione e l’eliminazione degli elementi selezionati, sono comuni in entrambi gli editor. Per informazioni dettagliate sul funzionamento di queste operazioni, consulta [Conoscere le funzioni dell’editor web](web-editor-features.md#) sezione.

Nella barra degli strumenti delle viste Layout e Autore sono disponibili anche le seguenti operazioni specifiche per le mappe:

## Vista Layout {#id205DEC0005Z_layout_view}

Quando si apre una mappa per la modifica, viene aperta la vista Layout dell&#39;Editor mappa.La vista Layout visualizza la gerarchia della mappa in una vista a struttura e consente di organizzare gli argomenti in una mappa.

>[!NOTE]
>
> Nella vista Layout vengono visualizzati solo i riferimenti presenti in una mappa. Se alcuni riferimenti sono interrotti, a sinistra del riferimento viene visualizzato un piccolo simbolo di croce

Nella vista Layout potete eseguire le seguenti operazioni:

**Inserisci riferimento argomento** - ![](images/insert-topic-reference.png)

Visualizza la finestra di dialogo di ricerca dell&#39;argomento. Passare al file argomento/mappa che si desidera inserire e fare clic su Seleziona per aggiungerlo alla mappa.
![](images/insert-topic-reference-dialog.png){width="800" align="left"}


**Inserisci gruppo di argomenti** - ![](images/insert-topic-group.png)

Inserisci il `topicgroup` elemento. Per ulteriori informazioni sul raggruppamento degli argomenti, vedere [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) documentazione in Specifiche della lingua OASIS DITA.

**Inserisci definizione chiave** - ![](images/Key_icon.svg)

Visualizza la finestra di dialogo Inserisci keydef. Utilizzare questa finestra di dialogo per definire qualsiasi definizione di chiave che si desidera utilizzare nella mappa.

![](images/insert-key-definition-dialog.png){width="300" align="left"}

**Inserisci prima/Inserisci dopo** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Visualizza la finestra di dialogo Inserisci elemento. Selezionare l&#39;elemento che si desidera inserire nella mappa. A seconda dell&#39;operazione, il nuovo elemento viene inserito prima o dopo l&#39;elemento corrente nella mappa.

**Inserisci argomento anteriore** - ![](images/frontmatter.svg)

Questa icona viene visualizzata quando apri una mappa segnalibro per la modifica. È possibile inserire componenti all&#39;inizio del libro come un sommario, un indice e un elenco di tabelle.

**Inserisci argomento posteriore** - ![](images/backmatter.svg)

Questa icona viene visualizzata quando apri una mappa segnalibro per la modifica. È possibile inserire componenti per una fine del libro, ad esempio un indice, un glossario e un elenco di figure.

**Sposta l&#39;elemento selezionato a sinistra/destra** - ![](images/left-arrow-icon.png) / ![](images/right-arrow-icon.png)

Fare clic sulla freccia sinistra per spostare l&#39;argomento verso il lato sinistro nella gerarchia. Questo essenzialmente promuove il rispettivo argomento di un livello superiore nella gerarchia. Ad esempio, se si fa clic sulla freccia sinistra mentre è selezionato un argomento figlio, l&#39;argomento diventa di pari livello rispetto all&#39;argomento precedente. Analogamente, se si fa clic sulla freccia destra, l&#39;argomento viene spinto verso destra, rendendolo l&#39;elemento figlio dell&#39;argomento al di sopra di esso.

**Sposta l&#39;elemento selezionato su/giù![](images/arrowup.svg)** - / ![](images/arrowdown.svg)

Fare clic sulle icone della freccia su o giù per spostare l&#39;argomento verso l&#39;alto o verso il basso nella gerarchia.

>[!NOTE]
>
> Potete anche trascinare i riferimenti per spostarli in una mappa.

**Blocca/Sblocca** - ![](images/LockClosed_icon.svg) / ![](images/LockOpen_icon.svg)

Ottiene un blocco sul file mappa e lo rilascia. Se nel file di mappa sono presenti modifiche non salvate, al momento del rilascio del blocco viene richiesto di salvare il file di mappa. Le modifiche vengono salvate nella versione corrente del file di mappa.

**Unisci** - ![](images/merge-icon.svg)

Per ulteriori dettagli sull’unione di contenuto di una versione diversa dello stesso file o di un file diverso, consulta [Unisci](web-editor-features.md#id205DF04E0HS) nell&#39;editor Web.

**Cronologia versioni** - ![](images/version-history-web-editor-ico.svg)

Controlla le versioni e le etichette disponibili nell’argomento attivo e ripristina qualsiasi versione dall’editor stesso.

**Etichetta versione** - ![](images/version-label-icon.svg)

Visualizza la finestra di dialogo Gestione etichette versione. Seleziona una versione dall’elenco a discesa. Scegli l’etichetta da applicare alla versione selezionata e fai clic su **Aggiungi etichetta** per aggiungerlo.

**Opzioni di visualizzazione** - ![](images/view-options.svg)

Visualizza un elenco a discesa che consente di scegliere Mostra numeri di riga, Mostra casella di controllo e Mostra nome file.

- **Mostra numeri di riga**

Mostra o nasconde il numero di riga per ciascun argomento. I numeri di riga vengono visualizzati a seconda del livello nella gerarchia.

- **Mostra casella di controllo**

Mostra o nasconde una casella di controllo per ciascun argomento. È possibile utilizzare la casella di controllo per selezionare l&#39;argomento\(s\) ed eseguire varie attività utilizzando il menu Opzioni. Per ulteriori dettagli, vedi [Opzioni](#id228ID8006H8) menu.

- **Mostra nome file**

Mostra il nome del file dei titoli degli argomenti.

>[!NOTE]
>
> Quando si posiziona il puntatore del mouse sul titolo di un argomento, viene visualizzato il percorso del file.


**Visualizza argomenti basati su filtri condizionali** Se hai applicato una condizione a un argomento, a destra dell’argomento viene visualizzata un’icona di filtro. Quando passi il puntatore del mouse su un’icona di filtro, viene visualizzata la condizione applicata e il relativo valore di attributo.

**Menu Opzioni nella vista Layout**

Oltre ad organizzare gli argomenti nel file mappa, è possibile eseguire le azioni seguenti utilizzando il menu Opzioni disponibile per un elemento nella vista Layout:

![](images/map-editor-options-menu.png){width="650" align="left"}

- **Aggiungi**: puoi scegliere di aggiungere un nuovo argomento o un riferimento vuoto dall’Editor mappa:
   - **Riferimento vuoto**: questa opzione consente di aggiungere un riferimento vuoto nella mappa DITA. In seguito è possibile fare doppio clic sul riferimento vuoto inserito e aggiungere i dettagli dell&#39;argomento. Per ulteriori dettagli, vedi [Creare un argomento](web-editor-features.md#id228ICI0105U) nell&#39;editor Web.
   - **Nuovo argomento**: quando scegli di creare un nuovo argomento dal menu, viene visualizzata la finestra di dialogo Crea nuovo argomento. Nella finestra di dialogo Crea nuovo argomento, fornisci i dettagli richiesti e fai clic su Crea. Per ulteriori dettagli, vedi [Creare un argomento](web-editor-features.md#id228ICI0105U) nell&#39;editor Web.
- **Sposta**: puoi scegliere di spostare un argomento verso l’alto/il basso/a destra/a sinistra nella gerarchia.Puoi anche trascinare e rilasciare un argomento o una mappa dal pannello dell’archivio alla mappa aperta nell’Editor mappe.
- **Annulla**: annulla l’ultima operazione nella vista Layout.
- **Ripeti**: ripete l’ultima operazione nella vista Layout.
- **Copia**: copia il riferimento selezionato dal file mappa.

  >[!NOTE]
  >
  > Potete visualizzare e quindi selezionare le caselle di controllo per copiare più riferimenti.

- **Incolla**: incolla i riferimenti copiati nella posizione corrente nella gerarchia.
- **Elimina**: elimina i riferimenti selezionati dal file di mappa.

  >[!NOTE]
  >
  > È possibile visualizzare e quindi selezionare le caselle di controllo per eliminare più riferimenti.


## Pannello a destra nell’editor mappa

Nel pannello di destra vengono visualizzate le Proprietà contenuto e le Proprietà mappa nella vista Layout dell’Editor mappa.

**Proprietà contenuto**

Il pannello Proprietà contenuto contiene informazioni sul tipo di argomento attualmente selezionato nella mappa, il relativo URL di collegamento e i relativi attributi. Per ulteriori dettagli, consulta [Proprietà contenuto](web-editor-features.md#id228IDB00HMM) nell&#39;editor Web.

- **Altri attributi** Se l&#39;amministratore ha creato un profilo per gli attributi, questi verranno ottenuti insieme ai relativi valori configurati. Utilizzando il pannello delle proprietà del contenuto, potete scegliere questi attributi e assegnarli al contenuto pertinente nell&#39;argomento. Puoi anche assegnare gli attributi configurati dall’amministratore nella sezione **Visualizza attributi** nelle impostazioni dell’editor. Gli attributi definiti per un elemento vengono visualizzati nella vista Layout e Struttura. Questo consente di esaminare rapidamente tutti gli argomenti di una mappa per cui è definito un attributo specifico. Ad esempio, tutti gli argomenti per i quali l’attributo platform è definito come &quot;Android&quot;.

  ![vista layout](images/layout-inline-attributes.png){width="650" align="left"}


  Per ulteriori dettagli, vedi *Visualizza attributi* all&#39;interno del *Impostazioni editor* descrizione della funzione in [Pannello sinistro](web-editor-features.md#id2051EA0M0HS) sezione.

- **Metadati** Utilizzando i metadati , puoi impostare le informazioni sui metadati. Puoi definire il Titolo navigazione, il Testo collegamento, la Descrizione breve e le Parole chiave.

Per ulteriori informazioni sugli attributi e i metadati standard dell&#39;argomento, vedere [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) documentazione in Specifiche della lingua OASIS DITA.

**Proprietà mappa**

Visualizza la finestra di dialogo Proprietà mappa, in cui è possibile impostare gli attributi e le informazioni sui metadati per la mappa.

## Visualizzazione Autore {#id205DEC0005Z_author_view}

Il **Autore** visualizzazione consente di modificare la mappa DITA nell&#39;Editor Web. Questa mostra la vista WYSIWYG dell’Editor mappe e alcune delle icone visualizzate nella vista Author sono uguali alla vista Layout. Per ulteriori dettagli, consulta [Vista Layout](#id205DEC0005Z_layout_view). Inoltre, è possibile visualizzare le icone seguenti ed eseguire le attività correlate dalla vista Autore:

**Inserisci prima/Inserisci dopo** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Visualizza la finestra di dialogo Inserisci elemento. Selezionare l&#39;elemento che si desidera inserire nella mappa. A seconda dell&#39;operazione, il nuovo elemento viene inserito prima o dopo l&#39;elemento corrente nella mappa.

**Inserisci elemento** - ![](images/Add_icon.svg)

Visualizza la finestra di dialogo Inserisci elemento. Seleziona l’elemento da inserire. È possibile utilizzare la tastiera per scorrere l&#39;elenco degli elementi e premere Invio per inserire l&#39;elemento richiesto. In alternativa, puoi fare clic direttamente sull’elemento per inserirlo nella mappa.

**Inserisci tabella di relazione** - ![](images/relationship_table_icon.svg)

Inserisce una tabella di relazioni nella mappa. Poiché il concetto di utilizzo della tabella delle relazioni è identico a quello descritto nella sezione Editor mappe di base, vedere [Utilizzare le tabelle di relazione nell&#39;Editor mapping di base](map-editor-basic-map-editor.md#id1944B0I0COB) per ulteriori dettagli.

**Inserisci contenuto riutilizzabile** - ![](images/content-reuse-icon.png)

Visualizza la finestra di dialogo Riutilizza contenuto. Utilizzare questa finestra di dialogo per inserire il contenuto che si desidera riutilizzare nella mappa.

**Aggiorna attributo titolo navigazione** - ![](images/navtitle-refresh-icon.svg)

sincronizza il `title` elemento di un file di riferimento in una mappa con il valore specificato nel relativo `@navtitle` attributo. È possibile aggiungere diversi tipi di file di riferimento in una mappa, ad esempio mappe di argomenti, riferimenti, attività, sottomappe e così via. La maggior parte di questi file supporta `@navtitle` attributo. Se un file contiene `@navtitle` , quindi il `@navtitle` viene aggiornato l’attributo per lo stesso file nella mappa. Se il valore `@navtitle` l&#39;attributo non è presente, quindi il `@navtitle` l&#39;attributo viene aggiunto al file di riferimento e ai relativi `title` viene aggiornato anche per visualizzare `@navtitle`.

>[!NOTE]
>
> L’amministratore può configurare l’aggiunta automatica `@navtitle` a ogni file di riferimento aggiunto a una mappa. Per ulteriori dettagli sulla configurazione dell’aggiunta automatica `@navtitle` , vedere *Includi attributo @navtitle per impostazione predefinita* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

Fai clic sull’icona Aggiorna attributo titolo navigazione per sincronizzare la `title` e dell&#39;elemento `@navtitle` valori dell&#39;attributo.

**Attiva/Disattiva visualizzazione tag** - ![](images/Label_icon.svg)

Mostra o nasconde i tag XML. I tag fungono da segnali visivi che indicano il limite di un elemento. In questa modalità, se desideri inserire un riferimento ad argomento/mappa, trascina il file desiderato prima o dopo il tag. La barra orizzontale non viene visualizzata nella modalità Visualizzazione tag.

**Attiva/Disattiva rilevamento modifiche** - ![](images/track-change-icon.svg)

È possibile tenere traccia di tutti gli aggiornamenti effettuati nel file di mappa attivando la modalità Revisioni. Dopo aver abilitato le modifiche di traccia, tutti gli inserimenti e le eliminazioni vengono acquisiti nel documento. Per ulteriori dettagli, consulta [Attiva/Disattiva rilevamento modifiche](web-editor-features.md#id205DF0203Y4) nell&#39;editor Web.

**Crea attività di revisione** - ![](images/create-review-task-icon.svg)

È possibile creare un&#39;attività di revisione dell&#39;argomento corrente o un file di mapping direttamente dall&#39;editor Web. Aprire il file per il quale si desidera creare l&#39;attività di revisione e fare clic su Crea attività di revisione per avviare il processo di creazione della revisione. Seguire le istruzioni fornite nella [Rivedi argomenti o mappe](review.md#) per ulteriori dettagli.

## Modifica argomenti tramite mappa DITA {#id17ACJ0F0FHS}

La modifica di un singolo argomento non fornisce all&#39;autore il contesto completo. L&#39;autore non dispone di informazioni sulla posizione di un argomento in una mappa DITA. Senza queste informazioni contestuali, per gli autori diventa un po’ difficile creare contenuti.

Le guide AEM consentono agli autori di aprire una mappa DITA nell&#39;editor Web e di visualizzare il posizionamento degli argomenti nella mappa. In questo modo gli autori possono sapere esattamente dove si trova l’argomento all’interno della mappa e creare contenuti più rilevanti. Inoltre, se più autori lavorano a un progetto, possono sapere quali argomenti sono disponibili nella mappa e riutilizzare il contenuto, se necessario.

Per modificare gli argomenti tramite una mappa DITA, effettuare le seguenti operazioni:

1. Nell&#39;interfaccia utente Assets passare alla mappa DITA contenente gli argomenti che si desidera modificare.
1. Fare clic sulla mappa DITA per aprirla nella console delle mappe DITA.
1. Seleziona la **Argomenti** per visualizzare un elenco di argomenti disponibili nella mappa DITA.

   >[!TIP]
   >
   > La scheda Argomenti consente di scaricare il file mappa con i relativi dipendenti. Per ulteriori dettagli, consulta [Esportare un file di mapping DITA](authoring-download-assets.md#id218UBA00IXA).

1. Nella barra degli strumenti principale, fai clic su **Modifica argomenti**.

   La mappa DITA viene visualizzata nell&#39;Editor Web.

   >[!NOTE]
   >
   > Puoi anche selezionare il file di mappa DITA nell’interfaccia utente Assets e fare clic su **Modifica argomenti** nella barra degli strumenti principale per avviare l’editor web.

   ![](images/web-editor-map-view_cs.png){width="350" align="left"}

1. \(*Facoltativo*\) È inoltre possibile selezionare un argomento dalla mappa ed estrarre il file prima di modificarlo. Per estrarre il file\(s\), selezionare uno o più file dal riquadro di sinistra e fare clic su **Pagamento**. È inoltre possibile rilasciare il blocco su qualsiasi file selezionando il file estratto e facendo clic sul pulsante **Annulla estrazione e sblocco** nella vista Mappa.

   >[!IMPORTANT]
   >
   > Se l&#39;amministratore ha configurato **Disattiva modifica senza estrazione** , è necessario estrarre il file prima di modificarlo. Se non si estrae il file, il documento verrà aperto nell&#39;editor in modalità di sola lettura.

   Nella schermata seguente vengono evidenziate le icone per Check-Out e Blocco \(A\), Annulla Check-Out e Sblocca \(B\), Salva come nuova versione e Sblocca \(C\), Modifica \(D\), Anteprima \(E\), icone diverse che mostrano i diversi tipi di file DITA \(F\) e i file estratti \(G\).

   ![](images/file-checkout-map-editor.png){width="550" align="left"}

1. Fare clic su un collegamento di argomento per aprirlo nell&#39;editor Web per la modifica.

   È possibile aprire più argomenti nell&#39;editor e ogni argomento viene aperto in una nuova scheda nell&#39;editor. Anche se la mappa DITA contiene mappe secondarie, gli argomenti delle mappe secondarie vengono aperti in una nuova scheda per la modifica. Se si desidera visualizzare gli argomenti sotto una mappa secondaria, è possibile fare clic su ed espandere la mappa secondaria.

   ![](images/web-editor-multiple-topics.png){width="800" align="left"}

   Se si fa clic su un file di mappa, la mappa viene aperta in una nuova scheda del browser Web.

1. Dopo aver modificato gli argomenti, puoi effettuare le seguenti operazioni:

   - Puoi salvarli singolarmente. Se si fa clic su **Chiudi senza salvare** negli argomenti verrà visualizzata una finestra di dialogo in cui viene richiesto di salvare gli argomenti non salvati:

     ![](images/save-multiple-topics.PNG){width="550" align="left"}

     È possibile scegliere di salvare tutti gli argomenti selezionati o deselezionare gli argomenti che non si desidera salvare.

   - È possibile archiviare l&#39;argomento utilizzando **Salva come nuova versione e sblocca** pulsante. Quando si salva una versione dell&#39;argomento, viene creata una nuova versione e viene rilasciato anche il blocco.

     Si consiglia di salvare le modifiche prima di archiviare i file.  Quando si salvano le modifiche, il file XML viene convalidato.

   - È inoltre possibile selezionare e archiviare più argomenti utilizzando **Salva come nuova versione e sblocca** pulsante. Quando si salva una versione degli argomenti, viene creata una nuova versione per ciascun argomento e viene rilasciato anche il blocco. È inoltre possibile visualizzare l&#39;avanzamento del check-in degli argomenti dalla **Salva come nuova versione e sblocca** . Al momento del check-in dei file viene visualizzato un messaggio di operazione riuscita.

   - Se l&#39;amministratore ha attivato l&#39;opzione di archiviazione dei file alla chiusura, verrà richiesto di salvare i file alla chiusura dei file estratti. Se questa opzione è attivata, quando si chiude l&#39;editor con i file modificati, viene visualizzato l&#39;elenco dei file estratti che devono essere salvati. I file estratti vengono visualizzati con un&#39;icona di blocco:

     ![](images/save-on-close.PNG){width="550" align="left"}

      - Clic su **Chiudi senza salvare** chiude i file senza salvare le modifiche.

      - Facendo clic su **Salva** salva le modifiche, ma non archivia i file.

      - Selezione del **Controllo dei file** e quindi facendo clic sul pulsante **Salva** button archivia i file \(crea un&#39;altra versione\) e salva anche i file.


## Visualizzare l’anteprima di una mappa

Oltre a poter visualizzare la posizione di ciascun file argomento all&#39;interno di una mappa, è consigliabile visualizzare il contenuto della mappa in un unico flusso consecutivo. La funzione Anteprima mappa consente di visualizzare l&#39;intero contenuto del file mappa con un solo clic. Non è necessario generare un output del file di mappa per vedere come si presenterà l’intera mappa dopo la pubblicazione. Potete semplicemente accedere all&#39;anteprima della mappa e tutti gli argomenti e le mappe secondarie vengono visualizzati sotto forma di libro.

Puoi accedere all’anteprima di una mappa da:

- **Interfaccia utente Assets**: nell’interfaccia utente Assets, passa alla posizione della mappa, seleziona il file della mappa e scegli **Anteprima mappa** sulla barra degli strumenti. L’anteprima della mappa viene visualizzata in una nuova scheda. È possibile visualizzare il contenuto di tutti gli argomenti nella modalità anteprima. In questa visualizzazione non è possibile modificare alcun argomento.

  >[!NOTE]
  >
  > Se il *Anteprima mappa* non è visibile nella barra degli strumenti principale, potrebbe essere stata spostata **Altro** barra degli strumenti.

- **Editor mappe avanzato**: nell’Editor mappe avanzato, fai clic sull’icona Anteprima per visualizzare l’anteprima della mappa corrente.

  ![](images/map-preview-icon.png){width="350" align="left"}

  Nella modalità di anteprima puoi eseguire le seguenti attività aggiuntive:

   - Fare clic con il pulsante destro del mouse su un argomento e selezionare **Modifica** per aprire l&#39;argomento per la modifica in una nuova scheda.

     >[!NOTE]
     >
     > Se non si dispone dei diritti di modifica, l&#39;argomento verrà aperto in modalità di sola lettura.

   - Passa all’argomento desiderato facendo clic sul titolo dell’argomento nella struttura ad albero della mappa \(nel pannello a sinistra\).

   - L&#39;argomento corrente nell&#39;anteprima della mappa viene evidenziato anche nella struttura della mappa.


**Argomento padre:**[ Utilizzare l’Editor mappa](map-editor.md)
