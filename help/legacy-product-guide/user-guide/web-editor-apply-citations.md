---
title: Aggiungere e gestire le citazioni nel contenuto
description: Aggiungere e gestire le citazioni in AEM Guides. Scopri come applicare, importare, filtrare, cercare, modificare lo stile delle citazioni, modificare, visualizzare in anteprima, inserire, eliminare e generare l’output di contenuto con le citazioni.
feature: Authoring, Features of Web Editor
role: User
hide: true
exl-id: 832dbc5d-85f7-41fd-8f5d-789732b46f80
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '1896'
ht-degree: 1%

---

# Aggiungere e gestire le citazioni nel contenuto

Le citazioni sono riferimenti all’origine delle informazioni aggiunte al contenuto. Utilizzando le citazioni, è possibile accreditare gli autori delle informazioni di origine e aiutare i lettori a completare le informazioni di origine. L’aggiunta di citazioni rende il contenuto più affidabile e impedisce il plagio. Consentono inoltre di visualizzare contenuti di alta qualità.

In AEM Guides, puoi aggiungere e importare citazioni e applicarle al contenuto. È possibile aggiungere queste citazioni da qualsiasi origine di libri, siti Web e giornali.


AEM Guides consente di modificare, visualizzare in anteprima e ordinare le citazioni. Dopo aver aggiunto le citazioni nel contenuto, puoi generare l’output utilizzando PDF nativo. Puoi anche aggiungere la bibliografia o la pagina dei riferimenti nell’output del PDF nativo.

AEM Guides supporta più stili di citazioni, come Modern Language Association (MLA), American Psychological Association (APA), Chicago, Institute for Electrical and Electronics Engineers (IEEE) e American Heart Association (AHA). La raccomandazione è di utilizzarli in modo chiaro e coerente.


>[!NOTE]
>
>Attualmente AEM Guides supporta solo PDF nativo per le citazioni.


## Aggiungi citazioni

Per aggiungere le citazioni, effettua le seguenti operazioni:

1. Seleziona l&#39;icona **Citazioni** ![icona citazioni](images/citations-icon.svg) nel pannello a sinistra.
Viene aperto il pannello **Citazioni**.

   ![](images/citation-panel.png){width="300" align="left"}

1. Nel pannello **Citazioni**, seleziona ![Aggiungi icona](images/Add_icon.svg). Dal menu a discesa puoi scegliere di aggiungere una nuova citazione o di importarne una.

1. Selezionare **Nuova citazione** per aggiungere una nuova citazione.
Viene visualizzata la finestra di dialogo **Aggiungi citazione**.

   ![pannello citazioni nell&#39;editor Web](images/citation-add.png) {width="300" align="left"}


1. Compila i campi nella finestra di dialogo **Aggiungi citazione**.

   >[!NOTE]
   >
   >Puoi anche aggiungere l’ID ISBN, DOI o PubMed. AEM Guides compila automaticamente gli altri campi.

   | Libro | Sito Web | Diario |
   | --- | ---|---|
   | **Source** <br> Dall&#39;elenco a discesa, selezionare l&#39;origine della citazione come registro. | **Source**<br> Selezionare l&#39;origine della citazione come sito Web dall&#39;elenco a discesa. | **Source** <br> Selezionare l&#39;origine della citazione come diario dal menu a discesa. |
   | **Cerca per** <br> Seleziona **ISBN** o **DOI** dal menu a discesa per cercare l&#39;ID digitale collegato alla citazione.  <br> DOI: Identificatore oggetto digitale <br> ISBN: Identificatore univoco registro numerico | **Cerca per** <br> Seleziona **DOI** dal menu a discesa per cercare l&#39;ID digitale collegato alla citazione. | **Cerca per** <br> Seleziona **DOI** o ID PubMed dall&#39;elenco a discesa per cercare l&#39;ID digitale collegato alla citazione. <br>  <br> |
   | **Autore** <br> Aggiungere il nome e il cognome dell&#39;autore della citazione. Selezionare ![](images/Add_icon.svg) per aggiungere altri nomi. | **Autore** <br> Aggiungere il nome e il cognome dell&#39;autore della citazione. Selezionare ![](images/Add_icon.svg) per aggiungere altri nomi. | **Autore** <br> Aggiungere il nome e il cognome dell&#39;autore della citazione. Selezionare ![](images/Add_icon.svg) per aggiungere altri nomi. |
   | **Titolo** <br> Aggiungi il titolo del libro. | **Titolo** <br> Aggiungi il titolo della pagina Web. | **Titolo** <br> Aggiungi il titolo dell&#39;articolo. |
   | **Editor** <br> Aggiungi l&#39;editor del libro. | **Nome sito Web** <br> Aggiungere il nome del sito Web. | **Titolo diario** <br> Aggiungi il titolo del lavoro in cui è stato trovato l&#39;articolo. |
   | **Edizione** <br> Aggiungi l&#39;edizione del libro. | **URL** <br> Aggiungi il collegamento Web del sito Web per sfogliare il contenuto. | **Anno** <br> Aggiungi l&#39;anno di pubblicazione dell&#39;articolo. |
   | **Città** <br> Aggiungi la città della pubblicazione. | **Data di accesso**<br> Aggiungere la data di accesso al contenuto del sito Web. | **Volume** <br> Aggiungere il volume del lavoro nella serie. |
   | **Editore** <br> Aggiungere il nome dell&#39;editore del libro. | **Data pubblicazione** <br> Aggiungere la data di pubblicazione del contenuto del sito Web. | **Numero** <br> Aggiungere il numero del volume all&#39;interno della serie. |
   | **Anno** <br> Aggiungere l&#39;anno di pubblicazione del libro. | **Data aggiornamento** <br> Aggiungere la data di aggiornamento del contenuto del sito Web. | **Pagine** <br> Aggiungi il numero di pagina o l&#39;intervallo di pagine in cui è stato trovato l&#39;articolo. |
   | **Versione** <br> Aggiungi la versione del libro. | **ID univoco** <br> Aggiungi un ID univoco per la citazione. Un ID univoco è un identificatore univoco della citazione. | **URL** <br>Aggiungi il collegamento Web al giornale di registrazione. |
   | **Serie** <br>Aggiungi la serie del libro. |  | **ID univoco** <br> Aggiungi un ID univoco per la citazione. Un ID univoco è un identificatore univoco per la citazione. |
   | **URL** <br> Aggiungi il collegamento Web al registro. |  |  |
   | **ID univoco** <br> Aggiungi un ID univoco per la citazione. Un ID univoco è un identificatore univoco della citazione. |  |  |





1. Seleziona **Fine**.

   Viene aggiunta una nuova citazione al pannello Citazione.

>[!NOTE]
>
> L’aggiunta di un ID univoco per il campo della citazione è obbligatoria.  Una volta aggiunta la citazione, non è possibile modificare l’ID univoco.

## Importa citazioni

Per importare le citazioni, eseguire la procedura seguente:

1. Nel pannello a sinistra, seleziona **Citazioni** ![icona citazioni](images/citations-icon.svg).

   Viene aperto il pannello **Citazioni**.

1. In the **Citations** panel, select ![Add icon](images/Add_icon.svg), and then select **Import** from the dropdown.
1. Browse a .bib file from your system and import it .

   >[!TIP]
   >
   > A .bib filename extension is a BibTeX Bibliographical Database file. It&#39;s a specially formatted text file that lists references about a particular source of information.

   Once the file is imported successfully, you can view the references in the citations panel.

   >[!NOTE]
   > <ol><li> AEM Guides imports only those citations which are unique and not already present.
   > &gt; <li> AEM Guides can import citations from a Book, Journal, or a Website. Currently it does not support citations from other sources.

## Manage citations

The citations are sorted alphabetically in the left panel. Search for the citations according to the sources to use in your topic.

### Filtro

Select the **Filter** ![](images/filter-search-icon.svg) icon next to the search bar and select the source options from the drop-down to filter the citation list. It allows both single and multiple selections.

* **All Sources**: It shows a complete list of citations, including all the sources.

* **Book**: It shows the list of citations sourced from books.

* **Website**: It shows the list of citations sourced from websites.

* **Journal**: It shows the list of citations sourced from journals.

### Ricerca

Search the citation for your content.

1. In the left panel, select Citations.
Viene aperto il pannello **Citazioni**.

1. Use the Search bar to search for the appropriate citation from a long list.

### Change citation style {#change-citation-style}

Your system administrator can change the style of citations from the **Citations**  dropdown in the **General Settings** tab in the **Editor Settings**.
These styles determine the way how citations appear in the preview pane or the Native PDF output.

The following options are available in the dropdown:

| MLA | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| Stile associazione lingua moderna <br> | Stile associazione psicologica americana | Manuale di stile di Chicago | Stile dell&#39;Institute for Electrical and Electronics Engineers | Stile American Heart Association |
| Esempio:<br> Crawford, Claire, et al. *Contenuto emotivo di memorie oscure*.Modificato da Memory, vol 16, 2010, Amsterdam. | Esempio: <br> Crawford, C., J., &amp; , C. (2010). *Contenuto emotivo di memorie oscure* (505-16 ed.). 10.1080/ 09658210902067289 | Esempio: <br> Crawford, Claire, et al. *Contenuto emotivo di memorie oscure*. 505-16, 2010. | Esempio: <br> C. Crawford, J. , e C. , *Contenuto emotivo di memorie oscure*. Amsterdam, 2010. | Esempio: <br> C. Crawford, J. , e C. , *Contenuto emotivo di memorie oscure*. Amsterdam, 2010. |


## Modificare una citazione

Per modificare la citazione, effettuare le seguenti operazioni:

1. Passa il puntatore del mouse sul nome della citazione dall’elenco. Selezionare ![](images/options.svg) l&#39;icona **Opzioni**.

1. Seleziona **Modifica**.

Viene visualizzata la finestra di dialogo **Modifica citazione**.

1. Apporta le modifiche necessarie. Seleziona **Fine**.
La citazione selezionata viene modificata.

>[!NOTE]
>
>Una volta aggiunta la citazione, non è possibile modificare l’ID univoco.

## Anteprima di una citazione

Per visualizzare l&#39;anteprima di una citazione, effettuare le seguenti operazioni:

Passa il puntatore del mouse sul nome della citazione dall’elenco. Seleziona     Icona ![](images/options.svg) **Opzioni**.

1. Seleziona **Anteprima**.
È possibile visualizzare in anteprima il contenuto e il formato della citazione nel riquadro di anteprima.

   >[!NOTE]
   >
   >L&#39;anteprima si basa sullo stile di citazione selezionato dall&#39;amministratore nelle **Impostazioni editor**.

1. Fai clic in un punto qualsiasi dello schermo per chiudere la casella di anteprima.

   ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]
>
> Puoi anche visualizzare in anteprima una citazione inserita in un argomento dall’interfaccia utente di Assets o dalla scheda Anteprima dell’editor web.

## Inserisci citazioni

Per inserire citazioni in un argomento, effettuare le seguenti operazioni:
1. Selezionare l&#39;argomento nel pannello del repository, quindi fare doppio clic per aprirlo nella finestra di modifica.
1. Posizionare il cursore nel punto in cui si desidera aggiungere la citazione.



È possibile inserire le citazioni per l&#39;argomento dalla barra degli strumenti principale o dal pannello sinistro.

### Dalla barra degli strumenti principale

1. Selezionare l&#39;icona **Citazioni** ![icona citazioni &#x200B;](images/citations-icon.svg) nella barra degli strumenti principale.
1. Nella finestra di dialogo **Citazioni**, scegli la citazione. È inoltre possibile selezionare più citazioni.
   ![finestra di dialogo citazione](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. È possibile filtrare le citazioni digitando i primi alfabeti nel pannello di ricerca della finestra di dialogo **Citazione**.

1. Fai clic su **Fine**.
La citazione selezionata viene aggiunta nella posizione del cursore nell&#39;argomento.


### Dal pannello a sinistra

>[!NOTE]
> 
>Per visualizzare l&#39;icona **Citazioni** dal pannello sinistro, l&#39;amministratore di sistema deve selezionare l&#39;opzione **Citazioni** nella scheda **Pannelli** in **Impostazioni editor**.

1. Seleziona **Citazioni** ![icona citazioni &#x200B;](images/citations-icon.svg) nel pannello a sinistra.
1. Trascina la citazione dal pannello **Citazioni** e rilasciala nella posizione appropriata nell&#39;argomento.

   È inoltre possibile selezionare **Inserisci** da ![](images/options.svg) **Opzioni** per inserire una citazione.

   ![inserisci citazioni](images/citation-panel-insert.png)
1. Per selezionare più citazioni, fare clic con il pulsante destro del mouse su una citazione nell&#39;argomento e selezionare **Modifica citazione** dal menu di scelta rapida.
1. Selezionare le citazioni che si desidera inserire dalla finestra di dialogo **citazione**.
1. Seleziona **Fine** per aggiungerli all&#39;argomento.

Dopo aver inserito le citazioni nell&#39;argomento, è possibile visualizzarne l&#39;anteprima nell&#39;editor Web. Puoi anche pubblicare contenuti con citazioni utilizzando il PDF nativo.



## Eliminare una citazione

È possibile eliminare una citazione dal pannello Citazioni o da un argomento in cui è stata inserita.

### Eliminare un citazione dal pannello Citazioni

Per eliminare una citazione dal pannello Citazioni, effettuate le seguenti operazioni:

1. Passa il puntatore del mouse sul nome della citazione dall’elenco.
1. Selezionare l&#39;icona ![](images/options.svg) **Opzioni**.
1. Seleziona la   **Elimina** ![](images/Delete_icon.svg).
Viene visualizzata la finestra di dialogo di conferma.
1. Selezionare **Sì**.
La citazione selezionata viene eliminata dal pannello citazioni.



### Eliminare una citazione da un argomento

To delete a citation that is already used in the topic, follow these steps:

In the topic, place your cursor at the end of the citation.

1. Right-click a citation in the topic and select **Modify Citation** from the shortcut menu. The Citation dialog opens.
   ![shortcut menu of a citation](./images/modify-citation.png)

1. You can choose the citations you want to insert into the document.

   >[!NOTE]
   >
   >The citations that are already used in the topic are replaced with the ciations that you select from the dialog.


1. Seleziona **Fine**.

## Generate output of content with citations

Once you have inserted citations in the topic, you can publish content with citations using Native PDF.

In the Native PDF output, the citations appear within the content where you have inserted them. You can also create a Bibliography page. When you click any citation, you are redirected to the bibliography page.

Create a **Citations** page layout in the PDF templates, and include it in your document. All the citations used in the book get listed on one page that appears in the PDF output. To learn more about creating a page layout, view [Create a page layout](/help/product-guide/native-pdf/components-pdf-template.md#create-page-layout).


To change the view and feel of the citation page, view [Customize PDF templates](/help/product-guide/native-pdf/pdf-template.md).



### Apply content style to a citation

Apply formatting to the citation when added to the topic.

1. Select **Stylesheets** in the **Templates** panel of a Native PDF output preset.   It opens the **STYLES** panel that contains all the styling options.

1. In the Search panel, search for `<cite>`.

To learn more about styles, view [Work with the common content styles](/help/product-guide/native-pdf/stylesheet.md).
