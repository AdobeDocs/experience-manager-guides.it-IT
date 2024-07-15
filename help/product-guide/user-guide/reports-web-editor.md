---
title: Report mappa DITA dall'editor Web
description: Generare rapporti di mappe DITA dall'editor Web in AEM Guides. Scopri come generare un file CSV per un elenco di argomenti, contenuti multimediali, metadati e rapporti sui collegamenti interrotti.
exl-id: 2f202b41-85d9-4a5a-aa28-e25715ce5e2e
feature: Report Generation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2366'
ht-degree: 0%

---

# Report mappa DITA dall&#39;editor Web {#id231HF0Z0NXA}

AEM Guides dispone di una funzione nell’editor web che consente di verificare l’integrità complessiva dei riferimenti e generare i relativi rapporti.

Puoi visualizzare l&#39;elenco degli argomenti, gestire i metadati di tutti i riferimenti e visualizzare l&#39;elenco multimediale per la mappa corrente dalla scheda **Rapporti** nell&#39;editor Web.

## Generare un file CSV dalla vista Elenco argomenti

La visualizzazione **Elenco argomenti** fornisce informazioni dettagliate sugli argomenti, ad esempio il tipo di riferimento, lo stato del documento e l&#39;autore.

Per creare un rapporto sugli argomenti, effettuare le seguenti operazioni:

1. Nel pannello **Archivio**, apri il file mappa DITA in Vista mappa.
1. Fare clic sulla scheda **Gestisci**.
1. Fare doppio clic su **Elenco argomenti** a sinistra. Viene visualizzato l&#39;elenco degli argomenti presenti nella mappa DITA.

   ![](images/web-editor-topiclist-panel.png){width="800" align="left"}

1. Dal pannello **Filtri** è possibile filtrare gli argomenti in base al **tipo di riferimento** \(diretto o indiretto\), **Stato documento** \(lo stato corrente degli argomenti. Ad esempio, se gli argomenti sono in stato Modifica, In-Review o Rivisto, sono elencati\) o il **Autore** dell&#39;argomento.

1. È inoltre possibile utilizzare le opzioni di filtro degli argomenti seguenti per scegliere di visualizzare le colonne seguenti nell&#39;elenco:

   - **Argomento** Il titolo dell&#39;argomento è specificato nella mappa DITA. È possibile fare clic sull&#39;argomento per modificarlo.
   - **Nome file** Nome del file.
   - **UUID** L&#39;identificatore univoco universale \(UUID\) del file.
   - **Percorso file** Percorso completo dell&#39;argomento.
   - **Tipo di riferimento** Il tipo di riferimento - diretto o indiretto.
   - **Stato documento** Lo stato corrente dell&#39;argomento.
   - **Autore** l&#39;ultimo utente che ha lavorato sull&#39;argomento.
   - **Mappa padre** L&#39;elenco di tutte le mappe in cui si fa riferimento direttamente all&#39;argomento.
   >[!NOTE]
   >
   > Fai clic su **Aggiorna** per ottenere un nuovo elenco di argomenti e visualizzare eventuali modifiche nel file di mappa o se viene aggiornato un riferimento nel file di argomenti.

1. Fare clic su **Scarica CSV** per scaricare lo snapshot corrente degli argomenti nella mappa DITA. Il file CSV contiene le colonne selezionate e gli argomenti filtrati nella visualizzazione **Elenco argomenti**. Puoi quindi aprire il file CSV dell’elenco di argomenti in qualsiasi editor CSV.

**Gestione in blocco dei metadati dal report metadati**

AEM Guides consente di assegnare tag al contenuto DITA dall’editor web. È possibile applicare tag a un singolo argomento oppure utilizzare la funzione di assegnazione tag in blocco per applicare più tag a più argomenti, a una mappa DITA o a una mappa secondaria. È inoltre possibile modificare lo stato del documento di tutti gli argomenti selezionati al successivo possibile stato comune del documento.

## Visualizza metadati

Per visualizzare i metadati dei riferimenti nella mappa DITA corrente, effettuare le seguenti operazioni:

1. Nel pannello Repository, aprire il file mappa DITA in Vista mappa.
1. Fare clic sulla scheda **Gestisci**.
1. Fare doppio clic su **Metadati** a sinistra. Viene visualizzato l&#39;elenco dei metadati di tutti i riferimenti nella mappa DITA. Questo include anche i riferimenti multimediali.

   ![](images/web-editor-metadata-panel.png){width="800" align="left"}

1. Dal pannello **Filtri** è possibile filtrare gli argomenti in base al **Stato documento** \(lo stato corrente degli argomenti. Ad esempio, se gli argomenti sono in stato Modifica, In-Review o Rivisto, sono elencati\), **Riferimenti** \(diretti o indiretti\), **Tipo file** \(Mappa, Argomento e Immagine\) del riferimento.
1. È inoltre possibile scegliere di visualizzare solo i **file senza tag** oppure di scegliere tag specifici dal filtro **Tag** per visualizzare i file ad essi associati.
   1. È inoltre possibile utilizzare le opzioni di filtro degli argomenti seguenti per scegliere di visualizzare le colonne seguenti nell&#39;elenco metadati:
      - **Titolo** \(selezionato per impostazione predefinita\) Il titolo del file di riferimento è specificato nella mappa DITA. È possibile fare clic sul file per modificarlo.È inoltre possibile fare clic su e riprodurre un file audio o video nell&#39;editor Web. È possibile modificare il volume o la visualizzazione del video. Nel menu di scelta rapida sono inoltre disponibili le opzioni per il download, la modifica della velocità di riproduzione o la visualizzazione delle immagini nell&#39;immagine.

        >[!NOTE]
        >
        > Accanto al titolo di un file estratto viene visualizzata anche un&#39;icona di estrazione. Passa il cursore del mouse sull’icona per visualizzare il nome dell’utente.

      - **Nome file** Il nome del file.
      - **Posizione file** Percorso completo del file.
      - **Tag** \(selezionati per impostazione predefinita\) Tag applicati al file.

        >[!NOTE]
        >
        > Per impostazione predefinita, è possibile visualizzare due tag per un file. Per visualizzare altri tag, fare clic su **Mostra altri**. Fai clic su **Mostra meno** per comprimere nuovamente l&#39;elenco.

      - **Tipo di riferimento** Il tipo di riferimento - diretto o indiretto
      - **Stato documento** \(selezionato per impostazione predefinita\) Lo stato corrente del file di riferimento.
      - **Tipo file** \(selezionato per impostazione predefinita\) Tipo del file di origine. Le opzioni disponibili sono Mappa, Argomento e Immagine.
      - **Estratto da** Utente che ha estratto il file.
1. Fare clic su **Scarica CSV** per scaricare lo snapshot corrente dei riferimenti nella mappa DITA. Il file CSV contiene le colonne selezionate e i riferimenti filtrati nella vista Elenco argomenti. Puoi quindi aprire il file CSV dei metadati in qualsiasi editor CSV.

**Aggiornare i metadati**

1. Per aggiornare i metadati, selezionare i file da aggiornare.

   >[!NOTE]
   >
   > Non è possibile selezionare i file estratti. Accanto al titolo di un file estratto viene visualizzata anche un&#39;icona di estrazione. Passa il cursore del mouse sull’icona per visualizzare il nome dell’utente.

1. Seleziona **Gestisci** dall&#39;inizio.

   ![](images/web-editor-manage-metadata.png){width="350" align="left"}

1. Se desideri aggiungere nuovi tag, seleziona nuovi tag dall’elenco a discesa per applicarli a tutti gli argomenti selezionati. Puoi anche eliminare qualsiasi tag facendo clic sull’icona a forma di croce accanto al tag.

   >[!NOTE]
   >
   > Vengono elencati i tag comuni applicati a tutti gli argomenti selezionati.

1. Selezionare un nuovo stato del documento per modificare lo stato di tutti i riferimenti selezionati. Il menu a discesa mostra lo stato comune possibile per tutti gli argomenti selezionati. Ad esempio, se lo stato corrente degli argomenti è In revisione, è possibile visualizzare lo stato Bozza, Approvato o Rivisto.
1. Fai clic su **Aggiorna** per aggiornare i metadati. Viene visualizzato un messaggio di conferma per i metadati, indipendentemente dal fatto che siano stati aggiornati correttamente o con aggiornamenti non riusciti. Fai clic anche su **Scarica rapporto** per scaricare il CSV dei metadati dalla finestra di dialogo di conferma. Questo CSV contiene i dettagli dello stato di aggiornamento per i riferimenti selezionati.

## Generare un rapporto multimediale

Il report **Multimedia** fornisce informazioni dettagliate sugli elementi multimediali utilizzati nella mappa, ad esempio il titolo, il tipo \(audio, video e immagini\), i file in cui vengono utilizzati gli elementi multimediali e il tipo di riferimento dei file in cui sono stati utilizzati. Puoi anche visualizzare l’UUID e la posizione del contenuto multimediale all’interno dell’archivio. È possibile creare un report del contenuto multimediale eseguendo le operazioni seguenti:

1. Nel pannello **Archivio**, apri il file mappa DITA in Vista mappa.
1. Fare clic sulla scheda **Gestisci**.
1. Fare doppio clic su **Multimedia** a sinistra. Viene visualizzato l&#39;elenco degli elementi multimediali presenti nella mappa DITA.
1. Dal pannello **Filtri** è possibile ordinare l&#39;elenco per file multimediali o in base ai nomi di utilizzati nei riferimenti.

   - Quando si ordina per **Multimedia**, il nome del contenuto multimediale viene visualizzato **** prima colonna e quindi i nomi di tutti i riferimenti in cui sono stati utilizzati vengono visualizzati in un&#39;altra colonna sulla stessa riga. Ad esempio, la schermata seguente mostra il file multimediale WarmCoolForC.gif nella prima colonna e tre riferimenti in cui viene utilizzato sono visualizzati nella terza colonna sulla stessa riga.

     ![](images/multimedia-report-file-order.png){width="650" align="left"}

   - Se si ordina per la colonna **Usato in**, verrà visualizzata la vista trasposta in cui i nomi dei riferimenti in cui sono stati utilizzati i contenuti multimediali sono elencati nella prima colonna, mentre i nomi dei contenuti multimediali sono elencati in un&#39;altra colonna su righe separate. Ad esempio, la schermata seguente mostra i nomi dei tre riferimenti \(Regolare la temperatura del sedile, Modificare la visualizzazione della temperatura del sedile e l&#39;area dell&#39;equipaggio\) nella prima colonna e il file multimediale WarmCoolForC.gif viene visualizzato nella terza colonna su tre righe separate.

     ![](images/multimedia-report-used-in-order.png){width="650" align="left"}

1. Puoi filtrare i contenuti multimediali in base al **Tipo di contenuti multimediali** e al **Tipo di riferimento**. L’elenco dei file multimediali viene visualizzato in base alla selezione effettuata nel menu a discesa. Ad esempio, è possibile scegliere di visualizzare solo i riferimenti audio nella mappa DITA e un file mostra solo i riferimenti audio utilizzati.

   >[!NOTE]
   >
   > A seconda del tipo di elementi multimediali utilizzati nella mappa, Immagine, Video e Audio sono elencati nel menu a discesa **Tipo di elemento multimediale** e Diretto o Indiretto nel menu a discesa **Tipo di riferimento**.

1. È inoltre possibile utilizzare le seguenti opzioni di filtro per scegliere di visualizzare le colonne seguenti nell&#39;elenco:

   - **Multimedia** \(selezionato per impostazione predefinita\) Il titolo del contenuto multimediale è specificato nella mappa DITA. È possibile fare clic sull&#39;elemento multimediale per modificarlo.
   - **Posizione multimedia** Percorso completo del contenuto multimediale.
   - **UUID multimedia** L&#39;identificatore univoco universale \(UUID\) del file.
   - **Tipo multimediale** \(selezionato per impostazione predefinita\) Tipo del file multimediale. Le opzioni disponibili sono Audio, Video o Immagine.
   - **Usato In** \(selezionato per impostazione predefinita\) I riferimenti in cui è stato utilizzato il contenuto multimediale. Potete fare clic sul riferimento per modificarlo.
   - **Tipo di riferimento** \(selezionato per impostazione predefinita\) Il tipo di riferimento - diretto o indiretto.
   >[!NOTE]
   >
   > Fai clic su **Aggiorna** per ottenere un nuovo elenco di elementi multimediali e visualizzare eventuali modifiche nel file di mappa o se eventuali elementi multimediali presenti nella mappa DITA vengono aggiornati.

1. È inoltre possibile fare clic su un file audio o video e riprodurlo nell&#39;editor Web. È possibile modificare il volume o la visualizzazione del video. Nel menu di scelta rapida sono inoltre disponibili le opzioni per il download, la modifica della velocità di riproduzione o la visualizzazione delle immagini nell&#39;immagine.

   ![](images/video-web-editor.png){width="800" align="left"}

1. Fare clic su **Scarica CSV** per scaricare lo snapshot corrente del file multimediale nella mappa DITA. Il file CSV contiene le colonne selezionate e i file multimediali filtrati nella visualizzazione **File multimediali**. Puoi quindi aprire questo file CSV multimediale in qualsiasi editor CSV.


## Visualizzare e correggere i collegamenti interrotti{#report-broken-links}

**Collegamenti interrotti** è un report utile che fornisce i dettagli dei collegamenti interrotti presenti nella mappa corrente. È possibile visualizzare i collegamenti interrotti, che possono essere per argomenti DITA, riferimenti a file multimediali, riferimenti a chiavi di contenuto e così via. È anche possibile correggerli qui.
Il report fornisce informazioni dettagliate quali il collegamento interrotto, il tipo di collegamento, i file in cui viene utilizzato il riferimento e il tipo di file in cui sono stati utilizzati.
Per visualizzare il rapporto relativo ai collegamenti interrotti, eseguire la procedura seguente:
1. Nel pannello **Archivio**, apri il file mappa DITA in Vista mappa.
1. Fare clic sulla scheda **Gestisci**.
1. Fare doppio clic su **Collegamenti interrotti** a sinistra. Viene visualizzato l&#39;elenco dei collegamenti o dei riferimenti interrotti presenti nella mappa DITA.
1. Dal pannello **Filtri** è possibile ordinare l&#39;elenco in base ai collegamenti o ai nomi di utilizzati nei riferimenti.

   - Quando si ordina per **Collegamento interrotto**, i percorsi dei collegamenti interrotti vengono visualizzati nella prima colonna e quindi i nomi di tutti i riferimenti in cui sono stati utilizzati vengono visualizzati in un&#39;altra colonna su righe separate. Se lo stesso collegamento interrotto viene utilizzato in più file, questi vengono visualizzati su una riga e vengono mostrati come raggruppati o sotto-righe. La schermata seguente, ad esempio, mostra tre collegamenti interrotti nella prima colonna e il riferimento in cui sono utilizzati. `TestMap.ditamap` viene visualizzato nella terza colonna in tre righe separate.
   ![](images/broken-link-report.png){width="800" align="left"}

   - Se ordini per colonna **Usato in**, verrà visualizzata la visualizzazione trasposta in cui i nomi dei riferimenti in cui sono stati utilizzati i collegamenti interrotti sono elencati nella prima colonna, mentre i collegamenti interrotti sono elencati in un&#39;altra colonna sulla stessa riga. Ad esempio, la schermata seguente mostra il riferimento (in cui viene utilizzato il collegamento interrotto) `TestMap.ditamap` nella prima colonna e i collegamenti interrotti vengono visualizzati nella terza colonna sulla stessa riga.
   ![](images/broken-link-filter-usedin.png){width="800" align="left"}
1. Puoi filtrare i collegamenti interrotti in base al **tipo di file** e al **tipo di collegamento**. L’elenco dei collegamenti interrotti viene visualizzato in base alla selezione effettuata nel menu a discesa. Ad esempio, è possibile scegliere di visualizzare solo i riferimenti di contenuto nella mappa DITA e un file mostra solo i riferimenti di contenuto utilizzati nella mappa.

   A seconda del tipo di riferimenti utilizzati nella mappa, Riferimento file, Riferimento chiave, Riferimento contenuto, Riferimento chiave contenuto, Riferimento immagine e Riferimento file multimediale sono elencati nel menu a discesa **Tipo di collegamento** e **Argomento DITA** o **Mappa DITA** sono elencati nel menu a discesa **Tipo file**.
1. È inoltre possibile utilizzare le seguenti opzioni di filtro per scegliere di visualizzare le colonne seguenti nell&#39;elenco:

   - **Collegamento interrotto** (selezionato per impostazione predefinita) Il percorso del collegamento interrotto è specificato nella mappa DITA.

   - **Tipo di collegamento** (selezionato per impostazione predefinita) Il tipo di collegamento. Le opzioni disponibili sono Riferimento chiave contenuto, Riferimento contenuto, Argomento DITA, Riferimento file, Riferimento immagine, Riferimento chiave e Riferimento file multimediale.

   - **Usato In** (selezionato per impostazione predefinita) I riferimenti in cui è stato utilizzato il collegamento interrotto. Puoi fare clic sul riferimento per visualizzarlo in modalità di authoring.

   - **Tipo file** (selezionato per impostazione predefinita) Il tipo di riferimento - Mappa DITA o Argomento DITA.
Fai clic su **Aggiorna** per ottenere un nuovo elenco di collegamenti interrotti e visualizzare eventuali modifiche nel file di mappa o se eventuali collegamenti interrotti nella mappa DITA vengono aggiornati.
1. È possibile fare clic sull&#39;icona **Collegamento di correzione** (![](images/fix-broken-link.svg)) per correggere il collegamento interrotto.

   >[!NOTE]
   >
   > Passa il puntatore del mouse sul percorso del collegamento interrotto nella colonna Collegamento interrotto per visualizzare l&#39;icona Correggi collegamento (![](images/fix-broken-link.svg)).

   È possibile correggere un collegamento in entrambe le visualizzazioni se sono stati ordinati **Collegamenti interrotti** o **Usati in**.

   >[!NOTE]
   >
   > Quando si corregge un collegamento interrotto mentre è stato ordinato per collegamenti interrotti, il collegamento verrà corretto in tutti i file in cui viene utilizzato (raggruppati in un&#39;unica riga).

1. È necessario aggiornare i dettagli di riferimento richiesti nella finestra di dialogo **Aggiorna collegamento**. I dettagli richiesti nella finestra di dialogo **Aggiorna collegamento** dipendono dal tipo di riferimento.\
   Una volta corretto un collegamento, questo non viene visualizzato nell’elenco dei collegamenti interrotti. È invece possibile visualizzarlo in Elenco argomenti o Metadati.

1. Fare clic su **Scarica CSV** per scaricare lo snapshot corrente dei collegamenti interrotti nella mappa DITA. Il file CSV contiene le colonne selezionate e i collegamenti interrotti filtrati nella visualizzazione Collegamenti interrotti. Puoi quindi aprire e visualizzare questo file CSV in qualsiasi editor CSV.


**Argomento padre:**[ Report](reports-intro.md)
