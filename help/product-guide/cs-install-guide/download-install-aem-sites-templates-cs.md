---
title: Scaricare e installare modelli AEM Sites
description: Scopri come scaricare e installare i modelli di AEM Sites
feature: Installation
role: Admin
level: Experienced
source-git-commit: f6e34c0bc57603b4251abd4859b43c95042e8819
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 0%

---


# Scaricare e installare modelli AEM Sites

Per scaricare e installare i modelli AEM Sites su Experience Manager Guides come Cloud Service, effettua le seguenti operazioni:

## Installazione del pacchetto{#package-installation}

Per utilizzare i modelli, installa il pacchetto dei componenti tramite la distribuzione cloud:
- [guides-components-all.zip](https://github.com/adobe/aemg-sites-components/releases/tag/v1.0.0)



Per creare un’AEM Sites utilizzando il modello, effettua le seguenti operazioni:


1. Crea AEM Sites utilizzando il modello:
1. Nell&#39;interfaccia utente di Sites, fai clic sul pulsante **Crea** nell&#39;angolo in alto a destra.
1. Seleziona **Sito da modello** dal menu a discesa **Crea**.

1. Importa modelli di siti: [aemg-docs-1.0.0.zip](https://github.com/adobe/aemg-sites-template/releases/tag/v1.0.0) utilizzando l&#39;opzione **Importa**.
1. Selezionare `AEMG Docs 1.0.0` e fare clic su **Avanti**.
1. Immettere `Site title` e `Site name`.
1. Fai clic su **Crea**. Il pacchetto viene installato e viene creato un modello di AEM Sites.

Ulteriori informazioni su [Aggiunta di un modello di sito all&#39;AEM](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/administering/site-creation/site-templates#adding).


>[!NOTE]
>
>Dopo aver creato la home page, puoi utilizzare questo percorso come **percorso Publish** per generare l&#39;output dei predefiniti di AEM Sites. Esempio: `aemg-docs-en/docs/product-abc`.


## Configurare i modelli da utilizzare con i predefiniti di AEM Sites

Una volta installato il pacchetto, nell&#39;interfaccia utente Sites viene creato un sito denominato **AEMG**. Questo sito di esempio mostra come impostare la struttura del sito per la generazione dell’output di AEM Sites. Questo è solo un esempio. Puoi creare siti personalizzati in base alle tue esigenze.

![Pagine di esempio AEMG Sites](assets/aemg-sites-sample-pages.png)


**AEMG** contiene i seguenti componenti.
- Nella cartella **AEMG** è presente una cartella per la lingua inglese (en). Puoi creare copie in lingua simili in base alle tue esigenze. Ad esempio, un sito web multilingue include copie in lingua inglese (en), tedesca (de) e francese (fr).  Ulteriori informazioni sulla creazione di una copia per lingua mediante la [Creazione guidata copia lingua](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/introduction/tc-wizard).
- All&#39;interno della cartella della lingua inglese (en), Experience Manager Guides fornisce molte pagine di esempio pronte all&#39;uso come **Ricerca**, **Accedi**, **Documenti** e **Supporto**.

- **Docs** è la home page della documentazione di esempio. Funge da posizione centrale per tutta la documentazione relativa al prodotto
e mostra ogni prodotto per il quale la documentazione è disponibile come singoli riquadri.

- Insieme alla home page della documentazione, sono disponibili pagine di esempio per **Ricerca**, **Accesso** e **Supporto**. Puoi personalizzare questi esempi in base alle tue esigenze.
- Puoi avere pagine iniziali per singoli prodotti, ad esempio Product1. Una pagina di esempio **Product1** è presente in **Docs**, che è la home page della documentazione.

- Experience Manager Guides fornisce anche i seguenti modelli predefiniti:

   - Modello **Pagina di contenuto**: utilizza questo modello per creare le pagine standard che contengono la maggior parte del contenuto del sito di prodotti. Possono includere testo, immagini, video e altri elementi di contenuto. Questo modello contiene solo l’intestazione e il piè di pagina. Personalizza e utilizzalo per creare qualsiasi pagina in base alle tue esigenze. Ad esempio, puoi creare la pagina di supporto o la pagina di accesso per il tuo prodotto.
   - Modello **Home page**: la pagina di destinazione principale di un sito Web, che include una panoramica, sezioni chiave come gli elementi e le funzionalità chiave e collegamenti di navigazione. Ad esempio, la pagina principale di un prodotto ABC si connette alle altre pagine di contenuto o funzionalità.
   - Modello **Pagina argomento**: pagine utilizzate per organizzare e presentare contenuti basati su argomenti. Ad esempio, una guida utente contiene diverse pagine di argomenti, ciascuna delle quali contiene un argomento specifico relativo alle funzioni e alla risoluzione dei problemi.

  ![Modello siti](assets/sites-ui-templates.png)

Utilizza questi esempi e modelli per generare gli output di AEM Sites:
- La home page di un prodotto corrisponde alla home page di una mappa e viene creata utilizzando il modello Home page. Seleziona questo percorso nel predefinito AEM Sites per pubblicare sotto di esso i contenuti della mappa. La home page del prodotto può includere altre home page.
- Ad esempio, un prodotto come Experience Manager Guides richiede tre manuali per utenti, amministratori e sviluppatori.  Creare una home page per ogni manuale utilizzando il modello Home Page, quindi selezionare la home page corrispondente nel predefinito di output di AEM Sites.

Ulteriori informazioni sulla creazione e la configurazione di [predefiniti AEM Sites nell&#39;editor Web](../user-guide/generate-output-aem-site-web-editor.md).

## Creare una home page utilizzando il modello{#create-a-home-page-using-the-template}

Per creare la home page del prodotto, effettua le seguenti operazioni:
1. Una volta installato il pacchetto, selezionare **Sites** dal pannello di navigazione globale.
1. Seleziona il modello &quot;AEMG Docs&quot; installato nell’interfaccia utente di Sites.
1. Nell&#39;interfaccia utente di Sites, fai clic sul pulsante **Crea** nell&#39;angolo in alto a destra.
1. Seleziona **Pagina** dal menu a discesa **Crea**.
1. Seleziona **Home page** e fai clic su **Avanti**.
1. Inserisci il titolo del sito e il nome del sito, quindi fai clic su **Crea** nell&#39;angolo in alto a destra. Un modello di sito AEM viene creato utilizzando il modello di sito **Home page**. È ad esempio possibile creare una home page per il prodotto `Product ABC`.


>[!NOTE]
>
>Dopo aver creato la home page, puoi utilizzare questo percorso come **percorso Publish** per generare l&#39;output dei predefiniti di AEM Sites. Esempio: `aemg-docs-en/docs/product-abc`.

## Modifica modelli di argomento per AEM Sites

Puoi anche personalizzare i modelli di argomento per il tuo AEM Sites. Puoi modificare il contenuto o configurare le proprietà dei diversi componenti AEM nel tuo argomento. Ad esempio, puoi aggiungere o rimuovere componenti in base alle tue esigenze.\
Per modificare i modelli di argomento, effettuare le seguenti operazioni:
1. Seleziona il modello da modificare.
1. Seleziona l&#39;icona **Modifica** in alto.

Viene aperto l’Editor modelli AEM. È possibile modificare il modello di argomento. Ulteriori informazioni sulla [creazione di modelli di pagina](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/authoring/siteandpage/templates#editing-a-template-structure-template-author).


## Personalizzare i modelli di AEM Sites esistenti {#customize-existing-aem-sites-templates}

Oltre ai modelli predefiniti, puoi utilizzare i modelli esistenti con i predefiniti di AEM Sites. Per personalizzare i modelli AEM Sites esistenti, effettua le seguenti operazioni:

### Configurazione modello

Sono necessari i due tipi di modelli seguenti:

- Categoria o modello di destinazione: questo modello viene utilizzato per la pagina di destinazione della documentazione del prodotto e corrisponde a una mappa DITA.  La pagina del sito AEM per una mappa DITA viene generata utilizzando questo modello. Puoi utilizzare questo modello a qualsiasi livello.
: aggiungi un componente testo al modello esistente. Il componente testo deve avere una proprietà obbligatoria, `text="$category.html$"`.
- Ad esempio, è possibile scegliere modelli di vendita al dettaglio e utilizzare il modello sezione-pagina come modello della pagina di destinazione per la mappa DITA. Per farlo, apporta le modifiche come mostrato nella schermata seguente:
  ![modello pagina sezione](assets/customize-existing-aem-templates-section.png)
   - Pagina dettagli o Modello pagina argomenti: utilizza questo modello per il contenuto degli argomenti di una mappa. Tutte le pagine Sites di contenuto DITA/XML vengono create utilizzando i modelli di pagina per argomento. Per creare questi modelli, sono disponibili due prerequisiti:
      - Aggiungi un componente testo al modello, contenuto in un componente contenitore, con una proprietà obbligatoria. `text="$topic.content$"`.
        ![modello pagina contenitore](assets/customize-existing-aem-templates-container.png)
      - Rifletti lo stesso contenitore e componente di testo nella struttura dello stesso modello, come mostrato nella schermata seguente:
        ![struttura del modello di contenitore](assets/customize-existing-aem-templates-structure.png)

### Assegna tag a pagina categoria come contenitore di documentazione

Se per le pagine della documentazione che utilizzano il modello precedente viene creata una gerarchia di siti, scegliere una delle pagine delle categorie create in tale gerarchia. Assegna un ID alla pagina della categoria come contenitore della documentazione.
A tale scopo, assegnare alla proprietà `id` un valore `category-page`. Fai riferimento alla schermata seguente:

![pagina categoria tag](assets/customize-existing-aem-templates-tagging.png)





