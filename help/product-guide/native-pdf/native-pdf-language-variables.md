---
title: Native PDF | Supporto per le variabili linguistiche
description: Utilizzare le variabili di lingua nei modelli di output e di output di PDF
exl-id: 2335a7d5-251b-4266-8bba-9c9935e7bbf4
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 0%

---

# Supporto per le variabili di lingua

Le guide dell’AEM forniscono la funzione di utilizzare le variabili di linguaggio. È possibile utilizzare le variabili di lingua per definire stringhe localizzate nell&#39;output di PDF o per localizzare qualsiasi testo statico nei modelli di output. È possibile utilizzare gli stili CSS per localizzare le stringhe provenienti da un CSS.

## Utilizzare le variabili di lingua nell’output di PDF

È possibile utilizzare le variabili di lingua per definire una versione localizzata delle etichette predefinite, ad esempio Nota, Avvertenza e Avvertenza, o del testo statico nell’output di PDF. Il nome della variabile è lo stesso per tutte le lingue, ma può avere valori diversi per le varie lingue. Puoi aggiornare il valore di queste variabili in una o più lingue, quindi il valore localizzato viene selezionato automaticamente nell’output di PDF.

Ad esempio, per presentare l’etichetta puoi procedere come segue `Note` nell’output di PDF:

- Inglese: Note

- Francese: Remarque

- Tedesco: Hinweis

<img alt= "output nel documento che contiene le variabili di lingua" src="./assets/language-variable-output.png" width="550">

*Nota di esempio in inglese, francese e tedesco.*

>[!NOTE]
>
> Se il valore di una variabile non è definito in una particolare lingua, AEM Guides seleziona la stringa dalla lingua dell’interfaccia utente (interfaccia utente dell’applicazione) come meccanismo di fallback.
>
> Se non hai definito il valore nella lingua dell’interfaccia utente, cerca l’inglese (`en_us`), altrimenti viene scelto l&#39;inglese(`en`) e visualizza lo stesso nell’output di PDF.

## Tipi di variabili di linguaggio

Le guide dell’AEM supportano due tipi di variabili: variabili di applicazione e variabili utente.

### Variabili dell’applicazione

Le guide AEM forniscono un set di variabili di applicazione predefinite o pronte all’uso. È possibile utilizzare queste variabili predefinite per aggiungere informazioni su un documento specifico delle guide AEM. Ad esempio, il `chapter-number` variabile, se inclusa in una pagina, visualizza il numero del capitolo a cui appartiene la pagina. Il `author-label` variabile visualizza il nome dell&#39;autore del documento.

>[!NOTE]
>
> È possibile sovrascrivere il valore di una variabile di applicazione.


### Variabili utente

Puoi anche creare nuove variabili di lingua. È ad esempio possibile creare una variabile utente Publisher per l&#39;etichetta dell&#39;autore del documento.

>[!NOTE]
>
>  È necessario disporre di privilegi di amministratore per creare variabili utente e modificare le variabili dell&#39;applicazione.

<img alt="finestra delle variabili di lingua" src="./assets/add-language-variables.png" width="550">

*Aggiungi e visualizza le variabili di lingua per una lingua selezionata.*

## Aggiungi una nuova variabile di lingua

1. Nell’editor web, passa alla scheda Output.
1. Seleziona **Variabili di lingua** <img src="./assets/language-variables.svg" width="25"> nel pannello a sinistra.
1. Seleziona **Modifica** per aprire **Variabili di lingua** finestra. L&#39;applicazione e le variabili utente presenti nella lingua selezionata sono elencate in ordine alfabetico. I valori vengono visualizzati in base alla lingua selezionata. Ad esempio, se si seleziona la lingua francese, &quot;Tip&quot; viene visualizzato come &quot;Conseil&quot;.
1. Dalla sezione **Lingua** , seleziona la lingua desiderata in cui desideri modificare una variabile.

   >[!NOTE]
   >
   > Se non visualizzi le lingue desiderate, abilita la lingua desiderata da **Impostazioni della variabile di lingua**. Seleziona impostazioni <img src="./assets/settings-icon.svg" width="25">  per aprire **Impostazioni delle variabili di lingua** .

1. Inserisci il nome della variabile nel **Nome** e il relativo valore nella **Valore** colonna.

   >[!NOTE]
   >
   >Puoi utilizzare qualsiasi contenuto HTML come valore variabile per visualizzare il valore della variabile in una formattazione specifica. Ad esempio, puoi aggiungere `<b>` per visualizzare il server di pubblicazione in grassetto.

1. Seleziona **Aggiungi variabile di lingua** <img src="./assets/add-language-variable.svg" width="25"> per aggiungere una nuova variabile di lingua alla lingua selezionata. L’aggiunta di una variabile a una lingua la aggiunge automaticamente a tutte le lingue. Non è possibile creare una variabile con lo stesso nome di una variabile esistente. Viene visualizzato un errore.

>[!NOTE]
>
> Se non selezioni **Aggiungi variabile di lingua**, la variabile non viene creata e aggiunta all’elenco

## Esportare e importare variabili di lingua

Guide di Experience Manager fornisce il supporto per esportare e importare le variabili di lingua presenti nella lingua selezionata. Puoi esportare facilmente tutte le variabili di lingua insieme ai valori definiti. Sono incluse sia le variabili dell’applicazione che quelle dell’utente. Utilizza il file esportato per apportare le modifiche desiderate nei valori o per localizzarli in altre lingue.

È inoltre possibile importare il file XML, che contiene le variabili di lingua. Experience Manager Guides importa solo le variabili del linguaggio già definite, incluse sia le variabili applicazione che quelle utente. Non importa variabili non ancora definite.

### Esporta variabili di lingua

Per esportare le variabili della lingua, seleziona la lingua dal menu a discesa e fai clic su **Esporta** <img src="./assets/language-variable-export-icon.svg" alt="icona esporta" width="25">.
Crea un file XML con il formato `language_variable_<ln>` dove `<ln>` è il codice della lingua selezionata Ad esempio: `language_variable_en.xml` per inglese e `language_variable_fr.xml` per il francese.

>[!NOTE]
> 
>Se nelle variabili di lingua sono presenti modifiche non salvate, non è possibile esportarle. Salva le modifiche per visualizzare il **Esporta** <img src="./assets/language-variable-export-icon.svg" alt="icona di importazione" width="25"> icona.

### Importa variabili di lingua

Per importare le variabili di lingua:

1. Seleziona una lingua dal menu a discesa e seleziona **Importa** <img src="./assets/language-variable-import-icon.svg" width="25">.
2. Sfoglia e seleziona l’XML, che contiene le variabili di lingua. Ad esempio, language_variable_en.xml.
È possibile importare file XML nel seguente formato:

```
<?xml version="1.0" encoding="UTF-8"?>
<variables>    
<variable id="note-important">Important: </variable>    
<variable id="note-caution">Avertir: </variable>    
<variable id="image-with-text">Text and image &lt;img src=&quot;/content/dam/assets/images/image_with_text.png&quot; /&gt; </variable> 
</variables> 
```

Le variabili con lo stesso ID vengono importate una volta importato il file. I valori delle variabili nella lingua selezionata vengono aggiornati con quelli del file XML.  Viene visualizzato un messaggio sul numero di variabili aggiornate.

>[!NOTE]
> 
><ul><li>Se il file non è un file XML o se il file contiene un formato non corretto che non è mappato con le variabili di lingua, viene visualizzato un errore che indica la presenza di un problema con il file XML. 
&gt;<li>Se il file non contiene variabili con lo stesso ID, viene visualizzato un avviso che informa che nel file importato non è stata trovata alcuna variabile di lingua corrispondente.

### Opzioni per una variabile di lingua

Passa il puntatore del mouse sulla variabile per visualizzare **Opzioni** menu per esso.

<img width="550" alt="menu delle opzioni per le variabili di lingua" src="./assets/language-variable-user-options.png">

*Utilizza il **Opzioni**per eliminare, visualizzare in anteprima o duplicare una variabile di lingua.*

Puoi visualizzare in anteprima sia le variabili dell’applicazione che quelle dell’utente. Per visualizzare come viene visualizzato il valore della variabile nell’output, seleziona **Anteprima** dal **Opzioni** della variabile selezionata.
Puoi anche scegliere di **Elimina** o **Duplica** le variabili utente. Se si elimina una variabile da una lingua, questa viene eliminata automaticamente da tutte le lingue.

### Modificare o ripristinare le variabili dell’applicazione

È inoltre possibile modificare i valori di una variabile di applicazione. In seguito, sarà possibile ripristinare il valore originale di una variabile di applicazione. **Ripristina variabile** <img src="./assets/application-variable-revert.svg" width="25">  viene visualizzato per una variabile di applicazione con un valore modificato.

## Utilizzare le variabili di lingua nei modelli di output

È necessario aggiungere variabili di lingua nei documenti localizzati. È possibile inserire queste variabili di lingua all&#39;interno del layout di pagina visualizzato in pagine diverse nei documenti localizzati. Ad esempio, puoi aggiungere la variabile di lingua per il `author-name` che viene visualizzato nell’area dell’intestazione del layout di pagina (o in qualsiasi altra parte come il piè di pagina o il corpo).



<img alt="layout di pagina di un pdf" src="./assets/language-variable-page-layout.png" width="550">


*L’autore e il nome del brand localizzati nell’output PDF generato per la lingua francese.*

Per inserire una variabile di lingua come `copyright-label` nell’area dell’intestazione, effettua le seguenti operazioni:

1. Apri il layout di pagina richiesto per la modifica.

   >[!NOTE]
   >
   > Visualizza [Personalizzare il layout di una pagina](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) sezione per aprire un layout di pagina per la personalizzazione o la modifica.

1. Seleziona l’intestazione per rendere attiva l’inserimento di una variabile.
1. Seleziona **Inserisci variabile**  <img src="./assets/insert-language-variable.svg" width="25"> nella barra degli strumenti.
1. In **Inserisci variabile** , selezionare il nome della variabile di lingua da inserire e fare clic su **Inserisci** per inserirlo nell&#39;area intestazione.

   >[!NOTE]
   >
   > È inoltre possibile immettere la stringa di ricerca nella casella di testo. I nomi delle variabili contenenti la stringa specificata vengono filtrati e visualizzati nell’elenco.
   > La variabile di lingua selezionata viene inserita nell’area dell’intestazione.



<img alt="inserisci variabile nell’area dell’intestazione" src="./assets/language-variable-header.png" width="550">

*Il `copyright-label` aggiunto nell’area dell’intestazione.*

### Applicare lo stile del contenuto alle variabili di lingua

Oltre al valore assegnato a una variabile di lingua, puoi anche utilizzare i tag HTML per visualizzare il valore della variabile in una formattazione specifica. Ad esempio, puoi visualizzare il valore della proprietà `publisher-label` in grassetto.

- È inoltre possibile formattare gli stili dei valori utilizzando <span> tag. Ad esempio, utilizzando la variabile di lingua del numero di pagina, è possibile visualizzare il numero di pagina in formato numero romano in inglese e specificare il formato per altre lingue.

  Valore per inglese:
  `<span data-field="page-number" data-format="upper-roman">1</span>`

  Valore per Tamil:
  `<span data-field="page-number" data-format="tamil">1</span>`

Analogamente, è possibile aggiungere variabili di lingua e formattare altri campi elencati nella funzione Inserisci campi dei layout di pagina. Per ulteriori dettagli sull’aggiunta di campi, vedi [Aggiungere campi e metadati](../native-pdf/design-page-layout.md#add-fields-metadata).

- È inoltre possibile aggiungere immagini localizzate nei valori. Ad esempio, puoi aggiungere un’icona immagine nel linguaggio del numero di capitolo e ottenere immagini localizzate dell’icona nell’output di PDF.

  Per l’inglese, il valore della variabile di un’immagine può essere simile a `<img src="banner-en.jpg">`, e per la stessa variabile in tedesco, può essere `<img src="banner-de.jpg">`. Quindi, seleziona le immagini a seconda del linguaggio.

## Localizzare le stringhe utilizzando gli stili CSS

Utilizzando gli stili CSS, puoi anche localizzare le stringhe utilizzate in Numerazione automatica come Capitolo, Sezione, Figura e Tabella. Poiché queste stringhe provengono da file CSS, non è possibile localizzarle utilizzando variabili di linguaggio. Per localizzare queste stringhe, puoi creare stili CSS per ogni lingua in cui desideri localizzarle.
Ad esempio, puoi utilizzare il seguente CSS per visualizzare il prefisso del capitolo e il formato numerico corrispondente in varie lingue.
Ad esempio, puoi utilizzare il seguente CSS per visualizzare il capitolo come Hoofdstuk in tedesco e il numero del capitolo in formato decimale. Mentre per il giapponese, è possibile utilizzare il formato numerico giapponese per visualizzare i numeri dei capitoli nel sommario.

```
// for English
h1:before {
  counter-increment: h11;
  content: "Chapter " counter(h11, decimal)".";
}

// for German
:root:lang(de) h1:before {
  content: "Hoofdstuk " counter(h11, decimal)".";
}

// for Japanese
:root:lang(ja) h1:before {
  content: "章 " counter(h11, japanese-formal)".";
}
```

Le schermate seguenti mostrano le stringhe localizzate nell’output PDF in tedesco e giapponese.

<img alt=" output giapponese con variabile di lingua" src="./assets/localize-chapter-german.png" width="550">



<img alt="Output tedesco con variabile di lingua" src="./assets/localize-chapter-japanese.png" width="550">



### Formattare i prefissi

Utilizzando gli stili CSS, puoi anche formattare i prefissi. Ad esempio, puoi formattare l’etichetta `Note` di colore rosso nell&#39;output PDF di varie lingue.

```
.note .prefix-content 
{
color: red;
} 
```
