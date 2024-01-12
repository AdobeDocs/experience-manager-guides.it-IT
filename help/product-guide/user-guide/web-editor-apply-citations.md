---
title: Aggiungere e gestire le citazioni nel contenuto
description: Aggiungi e gestisci le citazioni nelle guide AEM. Scopri come applicare, importare, filtrare, cercare, modificare lo stile delle citazioni, modificare, visualizzare in anteprima, inserire, eliminare e generare l’output di contenuto con le citazioni.
exl-id: 685d747d-e017-4350-a6bf-822fd55c76e8
feature: Authoring, Features of Web Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Aggiungere e gestire le citazioni nel contenuto

Le citazioni sono riferimenti all’origine delle informazioni aggiunte al contenuto. Utilizzando le citazioni, è possibile accreditare gli autori delle informazioni di origine e aiutare i lettori a completare le informazioni di origine. L’aggiunta di citazioni rende il contenuto più affidabile e impedisce il plagio. Consentono inoltre di visualizzare contenuti di alta qualità.

Nelle guide AEM, puoi aggiungere e importare citazioni e applicarle al contenuto. È possibile aggiungere queste citazioni da qualsiasi origine di libri, siti Web e giornali.


Le guide AEM consentono di modificare, visualizzare in anteprima e ordinare le citazioni. Dopo aver aggiunto le citazioni nel contenuto, puoi generare l’output utilizzando Native PDF. Puoi anche aggiungere la bibliografia o la pagina dei riferimenti nell’output di Native PDF.

Le guide AEM supportano diversi stili di citazioni, come Modern Language Association (MLA), American Psychological Association (APA), Chicago, Institute for Electrical and Electronics Engineers (IEEE) e American Heart Association (AHA). La raccomandazione è di utilizzarli in modo chiaro e coerente.


>[!NOTE]
>
>Attualmente le guide AEM supportano solo il PDF nativo per le citazioni.


## Aggiungi citazioni

Per aggiungere le citazioni, effettua le seguenti operazioni:

1. Seleziona la **Citazioni** ![icona citazioni](images/citations-icon.svg) nel pannello a sinistra.
Il **Citazioni** viene visualizzato il pannello.

   ![](images/citation-panel.png){width="300" align="left"}

1. In **Citazioni** pannello, seleziona ![Icona Aggiungi](images/Add_icon.svg). Dal menu a discesa puoi scegliere di aggiungere una nuova citazione o di importarne una.

1. Seleziona **Nuova citazione** per aggiungere una nuova citazione.
Il **Aggiungi citazione** viene visualizzata.

   ![pannello citazioni nell’editor web](images/citation-add.png) {width="300" align="left"}


1. Compila i campi nel **Aggiungi citazione** .

   >[!NOTE]
   >
   >Puoi anche aggiungere l’ID ISBN, DOI o PubMed. Le guide AEM compilano automaticamente gli altri campi.

   | Libro | Sito Web | Diario |
   | --- | ---|---|
   | **Sorgente** <br> Dall’elenco a discesa, seleziona l’origine della citazione come Libro. | **Sorgente**<br> Dall’elenco a discesa, seleziona l’origine della citazione come sito web. | **Sorgente** <br> Dall&#39;elenco a discesa, selezionare l&#39;origine della citazione come diario. |
   | **Cerca per** <br> Seleziona **ISBN** o **DOI** dall’elenco a discesa, per cercare l’ID digitale collegato alla citazione.  <br> DOI: Identificatore oggetto digitale <br> ISBN: Identificatore numerico univoco del registro | **Cerca per** <br> Seleziona **DOI** dall’elenco a discesa, per cercare l’ID digitale collegato alla citazione. | **Cerca per** <br> Seleziona **DOI** o PubMed ID dal menu a discesa per cercare l’ID digitale collegato alla citazione. <br>  <br> |
   | **Autore** <br> Aggiungere il nome e il cognome dell&#39;autore della citazione. Seleziona ![](images/Add_icon.svg) per aggiungere altri nomi. | **Autore** <br> Aggiungere il nome e il cognome dell&#39;autore della citazione. Seleziona ![](images/Add_icon.svg)  per aggiungere altri nomi. | **Autore** <br> Aggiungere il nome e il cognome dell&#39;autore della citazione. Seleziona ![](images/Add_icon.svg)per aggiungere altri nomi. |
   | **Titolo** <br> Aggiungi il titolo del libro. | **Titolo** <br> Aggiungi il titolo della pagina web. | **Titolo** <br> Aggiungi il titolo dell’articolo. |
   | **Editor** <br> Aggiungi l&#39;editore del libro. | **Nome sito Web** <br> Aggiungi il nome del sito web. | **Titolo diario** <br> Aggiungi il titolo dell’opera in cui si trova l’articolo. |
   | **Edizione** <br> Aggiungi l&#39;edizione del libro. | **URL** <br> Aggiungi il collegamento web del sito web per sfogliare il contenuto. | **Anno** <br> Aggiungi l’anno in cui viene pubblicato l’articolo. |
   | **Città** <br> Aggiungi la città della pubblicazione. | **Data di accesso**<br> Aggiungi la data in cui è possibile accedere al contenuto del sito web. | **Volume** <br> Aggiungere il volume del lavoro della serie. |
   | **Editore** <br> Aggiungi il nome dell’editore del libro. | **Data pubblicazione** <br> Aggiungi la data di pubblicazione del contenuto del sito web. | **Numero** <br> Aggiungere il numero del volume all&#39;interno della serie. |
   | **Anno** <br> Aggiungi l’anno in cui viene pubblicato il libro. | **Data aggiornamento** <br> Aggiungi la data in cui il contenuto del sito web viene aggiornato. | **Pagine** <br> Aggiungi il numero di pagina o l’intervallo di pagine in cui si trova l’articolo. |
   | **Versione** <br> Aggiungi la versione del libro. | **ID univoco** <br> Aggiungi un ID univoco per la citazione. Un ID univoco è un identificatore univoco della citazione. | **URL** <br>Aggiungi il collegamento web al giornale di registrazione. |
   | **Serie** <br>Aggiungi la serie del libro. |  | **ID univoco** <br> Aggiungi un ID univoco per la citazione. Un ID univoco è un identificatore univoco per la citazione. |
   | **URL**  <br>  Aggiungi il collegamento web al libro. |
   | **ID univoco** <br> Aggiungi un ID univoco per la citazione. Un ID univoco è un identificatore univoco della citazione. |





1. Seleziona **Fine**.

   Viene aggiunta una nuova citazione al pannello Citazione.

>[!NOTE]
>
> L’aggiunta di un ID univoco per il campo della citazione è obbligatoria.  Una volta aggiunta la citazione, non è possibile modificare l’ID univoco.

## Importa citazioni

Per importare le citazioni, eseguire la procedura seguente:

1. Nel pannello a sinistra, seleziona **Citazioni** ![icona citazioni](images/citations-icon.svg).

   Il **Citazioni** viene visualizzato il pannello.

1. In **Citazioni** pannello, seleziona ![Icona Aggiungi](images/Add_icon.svg)e quindi selezionare **Importa** dal menu a discesa.
1. Sfoglia un file .bib dal tuo sistema e importalo.

   >[!TIP]
   >
   > L&#39;estensione del nome file .bib è un file del database bibliografico BibTeX. Si tratta di un file di testo formattato appositamente che elenca i riferimenti relativi a una particolare fonte di informazioni.

   Una volta importato correttamente il file, potete visualizzare i riferimenti nel pannello delle citazioni.

   >[!NOTE]
   > <ol><li> Le guide AEM importano solo le citazioni che sono univoche e non sono già presenti.
    &gt; <li> Le guide AEM possono importare citazioni da un libro, un diario o un sito Web. Attualmente non supporta citazioni provenienti da altre fonti.

## Gestire le citazioni

Le citazioni sono ordinate alfabeticamente nel pannello a sinistra. Cercare le citazioni in base alle fonti da utilizzare nell&#39;argomento.

### Filtro

Seleziona la **Filtro** ![](images/filter-search-icon.svg) accanto alla barra di ricerca e seleziona le opzioni di origine dal menu a discesa per filtrare l’elenco delle citazioni. Consente selezioni sia singole che multiple.

* **Tutte le origini**: mostra un elenco completo delle citazioni, comprese tutte le sorgenti.

* **Libro**: mostra l’elenco delle citazioni estratte dai libri.

* **Sito Web**: mostra l’elenco delle citazioni provenienti dai siti web.

* **Diario**: mostra l’elenco delle citazioni provenienti dai giornali di registrazione.

### Ricerca

Cerca il contenuto nella citazione.

1. Nel pannello a sinistra, seleziona Citazioni.
Il **Citazioni** viene visualizzato il pannello.

1. Utilizzare la barra di ricerca per cercare la citazione appropriata da un elenco lungo.

### Cambia stile citazione {#change-citation-style}

L&#39;amministratore di sistema può modificare lo stile delle citazioni dal **Citazioni**  menu a discesa nella **Impostazioni generali** scheda in **Impostazioni editor**.
Questi stili determinano il modo in cui le citazioni vengono visualizzate nel riquadro di anteprima o nell&#39;output di Native PDF.

Nel menu a discesa sono disponibili le seguenti opzioni:

| MLA | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| Stile associazione lingua moderna <br> | Stile associazione psicologica americana | Manuale di stile di Chicago | Stile dell&#39;Institute for Electrical and Electronics Engineers | Stile American Heart Association |
| Esempio:<br> Crawford, Claire, ecc. *Contenuto emotivo di ricordi scuri*.Edited by Memory, vol 16, 2010, Amsterdam. | Esempio: <br> Crawford, C., J., &amp; , C. (2010). *Contenuto emotivo di ricordi scuri* (505-16 ed.) 10,1080/09658210902067289 | Esempio: <br> Crawford, Claire, ecc. *Contenuto emotivo di ricordi scuri*. 505-16, 2010. | Esempio: <br> C. Crawford, J. , e C. , *Contenuto emotivo di ricordi scuri*. Amsterdam, 2010. | Esempio: <br> C. Crawford, J. , e C. , *Contenuto emotivo di ricordi scuri*. Amsterdam, 2010. |


## Modificare una citazione

Per modificare la citazione, effettuare le seguenti operazioni:

1. Passa il puntatore del mouse sul nome della citazione dall’elenco. Seleziona  ![](images/options.svg) il **Opzioni** icona.

1. Seleziona  **Modifica**.

Il **Modifica citazione** viene visualizzata.

1. Apporta le modifiche necessarie. Seleziona **Fine**.
La citazione selezionata viene modificata.

>[!NOTE]
>
>Una volta aggiunta la citazione, non è possibile modificare l’ID univoco.

## Anteprima di una citazione

Per visualizzare l&#39;anteprima di una citazione, effettuare le seguenti operazioni:

Passa il puntatore del mouse sul nome della citazione dall’elenco. Seleziona     ![](images/options.svg) **Opzioni** icona.

1. Seleziona **Anteprima**.
È possibile visualizzare in anteprima il contenuto e il formato della citazione nel riquadro di anteprima.

   >[!NOTE]
   >
   >L&#39;anteprima si basa sullo stile di citazione selezionato dall&#39;amministratore nel **Impostazioni editor**.

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

1. Seleziona la **Citazioni** ![icona citazioni ](images/citations-icon.svg) nella barra degli strumenti principale.
1. In **Citazioni** scegliere la citazione. È inoltre possibile selezionare più citazioni.
   ![finestra di dialogo citazione](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. È possibile filtrare le citazioni digitando i primi alfabeti nel pannello di ricerca del **Citazione** .

1. Clic **Fine**.
La citazione selezionata viene aggiunta nella posizione del cursore nell&#39;argomento.


### Dal pannello a sinistra

>[!NOTE]
> 
>Per visualizzare **Citazioni** dal pannello a sinistra, l’amministratore di sistema deve selezionare l’opzione **Citazioni** opzione in **Pannelli** scheda in **Impostazioni editor**.

1. Seleziona **Citazioni** ![icona citazioni ](images/citations-icon.svg) nel pannello a sinistra.
1. Trascina la citazione da **Citazioni** e rilasciarlo nella posizione appropriata nell’argomento.

   Puoi anche selezionare **Inserisci** da  ![](images/options.svg) **Opzioni** per inserire una citazione.

   ![inserisci citazioni](images/citation-panel-insert.png)
1. Per selezionare più citazioni, fare clic con il pulsante destro del mouse su una citazione nell&#39;argomento e selezionare **Modifica citazione** dal menu di scelta rapida.
1. Selezionare le citazioni che si desidera inserire dalla **Citazione** .
1. Seleziona **Fine** per aggiungerle all&#39;argomento.

Dopo aver inserito le citazioni nell&#39;argomento, è possibile visualizzarne l&#39;anteprima nell&#39;editor Web. Puoi anche pubblicare i contenuti con le citazioni utilizzando Native PDF.



## Eliminare una citazione

È possibile eliminare una citazione dal pannello Citazioni o da un argomento in cui è stata inserita.

### Eliminare un citazione dal pannello Citazioni

Per eliminare una citazione dal pannello Citazioni, effettuate le seguenti operazioni:

1. Passa il puntatore del mouse sul nome della citazione dall’elenco.
1. Seleziona la ![](images/options.svg) **Opzioni** icona.
1. Seleziona la   **Elimina** ![](images/Delete_icon.svg).
Viene visualizzata la finestra di dialogo di conferma.
1. Seleziona **Sì**.
La citazione selezionata viene eliminata dal pannello citazioni.



### Eliminare una citazione da un argomento

Per eliminare una citazione già utilizzata nell&#39;argomento, eseguire la procedura seguente:

Nell&#39;argomento posizionare il cursore alla fine della citazione.

1. Fare clic con il pulsante destro del mouse su una citazione nell&#39;argomento e selezionare **Modifica citazione** dal menu di scelta rapida. Viene visualizzata la finestra di dialogo Citazione.
   ![menu di scelta rapida di una citazione](./images/modify-citation.png)

1. È possibile scegliere le citazioni da inserire nel documento.

   >[!NOTE]
   >
   >Le citazioni già utilizzate nell’argomento vengono sostituite con le citazioni selezionate nella finestra di dialogo.


1. Seleziona **Fine**.

## Genera output di contenuto con citazioni

Dopo aver inserito le citazioni nell’argomento, puoi pubblicare il contenuto con le citazioni utilizzando Native PDF.

Nell’output di PDF nativo, le citazioni vengono visualizzate all’interno del contenuto in cui sono state inserite. Puoi anche creare una pagina di bibliografia. Quando fai clic su una citazione, vieni reindirizzato alla pagina della bibliografia.

Creare un **Citazioni** layout di pagina nei modelli di PDF e includerlo nel documento. Tutte le citazioni utilizzate nel libro vengono elencate in una pagina che appare nell&#39;output PDF. Per ulteriori informazioni sulla creazione di un layout di pagina, vedere [Creare un layout di pagina](../native-pdf/components-pdf-template.md#create-page-layout).


Per modificare la visualizzazione e l&#39;aspetto della pagina della citazione, visualizzare [Personalizzare i modelli di PDF](../native-pdf/pdf-template.md).



### Applicare lo stile del contenuto a una citazione

Applica la formattazione alla citazione quando viene aggiunta all&#39;argomento.

1. Seleziona **Fogli di stile** nel **Modelli** di un predefinito di output di Native PDF.   Apre il **STILI** che contiene tutte le opzioni di stile.

1. Nel pannello Ricerca, cerca `<cite>`.

Per ulteriori informazioni sugli stili, vedere [Utilizzare gli stili di contenuto comuni](../native-pdf/stylesheet.md).
