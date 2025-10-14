---
title: Note sulla versione | Novità di Adobe Experience Manager Guides, versione di dicembre 2023
description: Scopri le funzioni nuove e migliorate nella versione di dicembre 2023 di Adobe Experience Manager Guides as a Cloud Service.
feature: What's New
role: Leader
exl-id: bf8d98e9-97fe-4195-9286-60d8517ab19c
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 0%

---

# Novità della versione di dicembre 2023 di Adobe Experience Manager Guides as a Cloud Service

Questo articolo tratta le funzioni nuove e migliorate nella versione di dicembre 2023 di Adobe Experience Manager Guides (in seguito denominato *Experience Manager Guides as a Cloud Service*).

Per ulteriori dettagli sulle istruzioni di aggiornamento, sulla matrice di compatibilità e sui problemi risolti in questa versione, visualizzare le [note sulla versione](release-notes-2023-12-0.md).


## Utilizzare le variabili nell’output di PDF

È possibile utilizzare le variabili per inserire e gestire in modo dinamico le informazioni riutilizzabili. Experience Manager Guides consente di creare, modificare e visualizzare in anteprima le variabili durante la generazione dell’output PDF. È possibile modificare rapidamente i valori delle variabili e rendere i documenti facilmente trasferibili e aggiornabili.

![variabili pdf native](assets/add-variable-default.png){width="800" align="left"}

*Crea e gestisci variabili nell&#39;editor Web.*

Puoi anche creare set di variabili che sostituiscono i valori predefiniti e assegnare valori alternativi alle variabili. Inserire queste variabili all&#39;interno del layout di pagina e utilizzare lo stesso layout di PDF. Non è necessario creare layout separati per ogni insieme di valori. Ad esempio, puoi creare un set di variabili per ogni versione del prodotto. Questo set di variabili può essere costituito da variabili per diversi dettagli del prodotto come nome del prodotto, numero di versione e data di rilascio. Quindi puoi aggiungere valori diversi per queste variabili.

**Set di variabili 1: set di Adobi 1**

* Nome prodotto: Experience Manager Guides
* Numero di versione: 2311
* Data di rilascio: 11/02/2023

**Set di variabili 2: set di Adobi 2**

* Nome prodotto: Experience Manager Guides
* Numero di versione: 2310
* Data di rilascio: 09/27/2023



<img src="./assets/native-pdf-variable-output.png" alt="Piè di pagina nell’output di PDF" width="500" border="2px">

*Genera l&#39;output di PDF utilizzando le variabili nel layout di PDF.*

Per formattare le variabili è possibile applicare gli stili e utilizzare il markup HTML.  Puoi anche aggiornare rapidamente i valori per qualsiasi variabile ogni volta che sia necessario e rigenerare l’output. Ad esempio, se è necessario aggiornare i dettagli di una versione, è possibile modificare il valore della versione nella variabile VersionNumber e rigenerare l&#39;output.


Ulteriori informazioni sull&#39;utilizzo di [variabili nell&#39;output di PDF](../native-pdf/native-pdf-variables.md).





## Esperienza rinnovata per modificare gli attributi

Ora è possibile ottenere un&#39;esperienza rinnovata per aggiungere o modificare gli attributi di un elemento dal pannello **Proprietà contenuto** nell&#39;editor Web.

![Pannello Attributi](assets/attributes-multiple-properties.png){width="300" align="left"}

*Aggiungi attributi dal pannello Proprietà contenuto.*

È inoltre possibile modificare ed eliminare facilmente gli attributi.

Per ulteriori dettagli, consulta la descrizione della funzione **Proprietà contenuto** nella sezione [Pannello destro](../user-guide/web-editor-features.md#id2051EB003YK).


## Modificare i metadati durante l’authoring

Ora, durante l&#39;authoring, puoi aggiornare i tag di metadati del file utilizzando il menu a discesa dalle **Proprietà file** nel pannello di destra. Puoi anche selezionare **Modifica altre proprietà** per aggiornare altri metadati.

![proprietà-file](assets/file-properties-general.png){width="300" align="left"}

*Aggiorna i metadati e modifica le proprietà del file dal pannello di destra.*

Per ulteriori dettagli, fare riferimento alla descrizione della funzionalità **Proprietà file** nella sezione [Pannello destro](../user-guide/web-editor-features.md#id2051EB003YK).

## Possibilità di pubblicare contenuti nella Knowledge Base di ServiceNow

È ora possibile pubblicare i contenuti anche sulla piattaforma della knowledge base ServiceNow.

Con la versione di dicembre 2023, in qualità di amministratore, puoi creare un profilo di pubblicazione per il server della knowledge base ServiceNow. Quindi, in qualità di autore o editore, puoi scegliere il profilo di pubblicazione ServiceNow nel predefinito di output per pubblicare l’output nella knowledge base specificata.

Questa funzione consente di pubblicare contenuti come testo, video e immagini sulla piattaforma della knowledge base ServiceNow e di gestire un archivio completo.


![servizio ora predefinito knowledge base](assets/knowledgebase--output-preset.png){width="300" align="left"}

*Creare un predefinito di output per la Knowledge Base ServiceNow.*

Ulteriori informazioni sui predefiniti di output [Knowledge Base](../user-guide/generate-output-knowledge-base.md).

## Dashboard di raccolta mappe migliorato

Experience Manager Guides fornisce un dashboard avanzato per la raccolta mappe. In una raccolta di mappe, è possibile configurare rapidamente le proprietà dei metadati in blocco per le mappe DITA. Questa funzione è utile in quanto non è necessario aggiornare le proprietà dei metadati per ogni singola mappa DITA.

È ora possibile visualizzare il nome del file della mappa DITA. È inoltre possibile visualizzare le baseline. Questo consente di trovare rapidamente la linea di base utilizzata per un predefinito.

![Mappa dashboard raccolta](assets/map-collection-dashboard.png){width="800" align="left"}

*Visualizza, modifica e genera output dal dashboard della raccolta mappe.*

Scopri come [utilizzare la raccolta mappe per la generazione dell&#39;output](../user-guide/generate-output-use-map-collection-output-generation.md).

## Visualizzare gli attributi chiave nella vista Mappa

Quando definite gli attributi chiave per i riferimenti argomento o mappa, potete anche visualizzare il titolo, l&#39;icona corrispondente e il tasto nel pannello sinistro. La chiave viene visualizzata come `key=<key-name>`.

Per ulteriori dettagli, consulta la descrizione della funzione **Vista mappa** nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).

![chiavi nella vista mappa](assets/view-key-title-map-view.png) {width="300" align="left"}

*Visualizza l&#39;attributo chiave nella visualizzazione mappa.*

## Possibilità di duplicare una linea di base in base all’etichetta

Experience Manager Guides offre ora un’esperienza utente migliorata per la creazione delle linee di base dall’editor web.\
![crea nuova previsione](assets/create-new-baseline.png) {width="300" align="left"}
*Crea una baseline dall&#39;editor Web.*

Consente inoltre di duplicare una baseline basata sull&#39;etichetta. La versione di riferimento viene scelta in base all&#39;etichetta specificata (se esiste) durante la duplicazione, oppure seleziona la versione dalla baseline duplicata.


![duplicare una baseline &#x200B;](assets/duplicate-baseline.png) {width="300" align="left"}

*Duplicare una baseline in base a un&#39;etichetta o creare una copia esatta.*

Ulteriori informazioni su come [creare e gestire le baseline dall&#39;editor Web](../user-guide/web-editor-baseline.md).

## Risoluzione dei collegamenti incrociati nell’output del sito AEM

Il rendering dei collegamenti delle mappe incrociate (XREF con peer ambito) nell&#39;output del sito AEM viene ora risolto in base al titolo del file del contesto di pubblicazione impostato per la mappa generata.


## Configura l’URL dell’output del sito AEM per utilizzare il titolo del documento

In qualità di amministratore, Experience Manager Guides ti consente di configurare l’URL dell’output del sito AEM. Se il nome del file non esiste o contiene tutti i caratteri speciali, puoi configurare per sostituirli con un separatore nell’URL dell’output del sito AEM. È inoltre possibile sostituirli con il nome del primo argomento secondario. Scopri come [configurare l&#39;URL dell&#39;output del sito AEM per utilizzare il titolo del documento](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).
