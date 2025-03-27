---
title: Traduci documenti dalla console Mappa
description: Traduci i contenuti in più lingue dall’editor web. Scopri come creare un progetto di traduzione, aggiungere regole, visualizzare le versioni e ignorare i file non sincronizzati in AEM Guides.
exl-id: 321c5442-92eb-4662-ab61-d4d4f05eeb39
feature: Authoring, Features of Web Editor, Translation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '2365'
ht-degree: 0%

---

# Traduci documenti dalla console Mappa {#id21BKF0Z0YZF}

>[!TIP]
>
> Si consiglia di utilizzare questa funzione di traduzione dall’editor se è stato effettuato l’aggiornamento ad Adobe Experience Manager Guides as a Cloud Service versione di febbraio 2022 o successiva.

Experience Manager Guides dispone di una potente funzione nell’editor che consente di tradurre il contenuto in più lingue. Puoi creare un nuovo progetto di traduzione e successivamente aggiungerlo al progetto esistente. Puoi anche creare un progetto di traduzione multilingue che include processi di traduzione per tutte le lingue selezionate.

>[!NOTE]
>
> L’amministratore può configurare la scheda Gestisci \(utilizzata per la traduzione\) nell’editor. Per ulteriori dettagli, visualizzare *Configurare la funzionalità di traduzione nella sezione Editor* dell&#39;installazione e configurare Adobe Experience Manager Guides as a Cloud Service.

## Prima di iniziare

Prima di eseguire i passaggi descritti in questa procedura, verificare di aver creato le cartelle principali e di destinazione della lingua richieste

1. Crea una cartella principale per archiviare il contenuto sorgente. La cartella principale deve essere creata con il nome della lingua \(ad esempio Inglese\) o il codice della lingua \(en\).
1. Crea le cartelle di destinazione in cui desideri tradurre il contenuto. Ad esempio, se desideri tradurre il contenuto in tedesco o francese, devi creare una cartella denominata -de \(per tedesco\) o -fr \(per francese\).

>[!NOTE]
>
> La cartella principale e le cartelle di destinazione devono essere create allo stesso livello.

## Crea un progetto di traduzione

1. Nel pannello **Archivio**, apri il file mappa DITA in Vista mappa.
1. Seleziona l&#39;icona **Apri nella console delle mappe**.
1. Nella pagina Mappa della console, passa alla scheda **Traduzione**. Il **pannello Traduzione** visualizza i gruppi di lingue disponibili.

1. In qualità di utente, puoi visualizzare i gruppi di lingue configurati nel tuo profilo di cartella. I gruppi di lingue visualizzano le cartelle della lingua insieme ai relativi codici di lingua. Ad esempio, il gruppo di lingue denominato G1 contiene le cartelle di lingua italiana \(it\), tedesca \(de\), francese \(fr\) e inglese \(en\).

   ![pannello di traduzione](images/translation-languages.png){width="300" align="left"}

   *Selezionare i gruppi di lingue o le lingue in cui tradurre i documenti.*


   >[!IMPORTANT]
   >
   > Puoi selezionare e tradurre solo nelle lingue per le quali hai creato la cartella di destinazione parallelamente alla lingua di origine. Non viene visualizzata neanche una cartella della lingua creata a qualsiasi altro livello, ad esempio a un livello inferiore rispetto alla cartella della lingua di origine. Assicurati di creare tutte le cartelle della lingua di destinazione allo stesso livello della cartella della lingua di origine.



1. Puoi selezionare qualsiasi gruppo di lingue come destinazione per la traduzione. Se **Seleziona tutti**, i file selezionati verranno tradotti in tutte le lingue disponibili all&#39;interno dei gruppi di lingue esistenti.

   L’opzione della cartella della lingua è disattivata e mostra un segnale di avviso:

   - Se manca la cartella di destinazione per una lingua.
   - Se la lingua di destinazione è la stessa della sorgente.


   >[!NOTE]
   >
   > Se crei la cartella di destinazione per una lingua dopo aver creato il gruppo di lingue, aggiorna il browser per abilitare la lingua nei gruppi di lingue.

1. Se si sceglie una determinata lingua, questa verrà visualizzata come selezionata in tutti i gruppi di lingue selezionati. Quindi, quando traducete in qualsiasi lingua, viene tradotto in una sola volta per tutti i gruppi linguistici. Ad esempio, se il tedesco è presente in entrambi i gruppi linguistici G1 e G2, viene selezionato per entrambi.

1. Da **Altre lingue** è possibile scegliere qualsiasi lingua per la quale è stata creata la cartella di destinazione, ma che non fa parte di alcun gruppo di lingue.

1. Per tradurre il progetto, puoi anche selezionare una delle seguenti opzioni:

   **Nessuno** Selezionare questa opzione per tradurre le versioni predefinite dei file. Questa opzione è selezionata per impostazione predefinita.

   **Usa previsione:** Puoi selezionare una previsione per tradurre il progetto. Selezionare **Usa baseline** e scegliere una baseline creata sulla mappa. Tutti i file che fanno parte della baseline selezionata vengono visualizzati nella pagina Traduzione. Una volta tradotti i contenuti, puoi esportare la linea di base tradotta. Per ulteriori dettagli sull&#39;esportazione della baseline tradotta, visualizzare [Esporta baseline tradotta](generate-output-use-baseline-for-publishing.md#id196SE600GHS).

   **Usa versione più recente come in data**: scegliere di filtrare la versione degli argomenti in base alla data e all&#39;ora di creazione. Quando si seleziona una data e un&#39;ora, viene visualizzata solo la versione più recente dei file creati in corrispondenza o prima della data e dell&#39;ora selezionate.

1. Selezionare **Applica**. Viene visualizzato un elenco con i dettagli degli argomenti e delle risorse associate.
1. Seleziona gli argomenti da inviare per la traduzione. È inoltre possibile utilizzare le opzioni di filtro degli argomenti per le colonne seguenti:

   - **Titolo**: titolo del file di origine.  Passa il cursore del mouse sul titolo del file di origine per visualizzare il titolo del file di destinazione o tradotto.
   - **Nome file**: nome del file di origine
   - **Tipo file**: tipo del file di origine. Le opzioni disponibili sono Mappa, Argomento e Immagine.
   - **Tipo di riferimento**: riferimenti diretti o indiretti
   - **Versione**: numero di versione del file di origine
   - **Etichetta versione**: etichetta per la versione selezionata del file di origine
   - **Versione di destinazione**: numero di versione del file di destinazione
   - **Stato documento**: stato del file di origine. Le opzioni disponibili sono Bozza, In revisione e Rivisto.
   - **Lingua di destinazione**: lingua in cui tradurre il file di origine
   - **Stato traduzione**: le opzioni disponibili sono: Non sincronizzato, Copia mancante, In corso e In sincronia.
   - **Etichetta destinazione**: etichetta per la versione selezionata del file di destinazione
1. Seleziona **Invia per traduzione** nell&#39;angolo superiore destro.

   ![](images/translation-send.png){align="left"}

1. Dal menu a discesa, seleziona **Crea un nuovo progetto di traduzione**.

   ![](images/translation-project-types.png){width="350" align="left"}

   Oltre a un nuovo progetto di traduzione, puoi selezionare tra le seguenti opzioni:

   - Puoi scegliere di **creare solo la struttura** per il progetto di traduzione.
   - È possibile scegliere di **creare un nuovo progetto di traduzione XLIFF** per convertire il contenuto XML nel formato XLIFF (XML Localization Interchange File Format). XLIFF è un formato aperto basato su XML utilizzato per standardizzare il trasferimento di dati tra vari strumenti utilizzati nel processo di traduzione dei contenuti. Experience Manager Guides supporta XLIFF versione 1.2.
In un progetto XLIFF, il contenuto viene esportato nel formato XLIFF standard, che può essere fornito ai fornitori di servizi di traduzione. Il formato XLIFF consente il potenziale riutilizzo dei segmenti già tradotti durante la fase di traduzione.\
     Una volta tradotto, il contenuto XLIFF può essere importato in Experience Manager Guides, creando una versione tradotta del progetto DITA originale.

   >[!NOTE]
   >
   > L’esportazione XLIFF funziona solo con la configurazione di traduzione umana.

   - È possibile selezionare **Crea un nuovo progetto di traduzione multilingue** che includerà i processi di traduzione per tutte le lingue selezionate per la traduzione. Ad esempio, se hai selezionato francese, tedesco e spagnolo, verrà creato un progetto che contiene processi di traduzione per tutte e tre le lingue.
   - Se disponi già di un progetto di traduzione, puoi aggiungere argomenti a tale progetto. Selezionare **Aggiungi al progetto di traduzione esistente** dall&#39;elenco Progetto e scegliere un progetto dall&#39;elenco Progetto di traduzione esistente. Puoi ordinare questi progetti in base all’ordine più recente, crescente o decrescente.

   - Se si seleziona **Aggiungi al progetto di traduzione esistente**, questa operazione aggiorna la voce della risorsa esistente nel progetto se la risorsa è già stata aggiunta e lo stato del processo di traduzione correlato è *Bozza*.
      - Se la lingua di destinazione non è presente nel progetto, viene creato un nuovo progetto per il progetto di traduzione in una sola lingua e un nuovo processo per il progetto di traduzione in più lingue.

      - Se il processo è già presente per la lingua di destinazione e lo stato del processo non è *Bozza*, viene creato un nuovo processo nello stesso progetto per aggiungere le risorse per la traduzione.

   >[!NOTE]
   >
   > Se il progetto esistente è un progetto con ambito, al suo nome viene aggiunto &quot;\(Ambito\)&quot;.

   - Se devi creare l&#39;ambito per un progetto da tradurre, puoi selezionare **Crea un nuovo progetto di traduzione dell&#39;ambito**. Questo non invierà le copie per la traduzione e lo stato di traduzione originale dei file viene mantenuto. Non vi è alcun impatto sulla copia nella lingua di destinazione degli argomenti trattati che vengono inviati per l’ambito.

1. Nel campo **Titolo progetto**, inserisci un titolo.
1. Seleziona **Invia** per creare un nuovo progetto di traduzione.

Viene creato un nuovo progetto di traduzione con la versione selezionata degli argomenti. In questo momento, viene visualizzato un messaggio pop-up che conferma la creazione del progetto di traduzione. Una volta che tutte le copie per lingua di destinazione sono disponibili nel progetto di traduzione, si riceve una notifica nella casella in entrata. Una volta che le copie per lingua di destinazione sono disponibili nel progetto di traduzione, puoi procedere e avviare il processo di traduzione. Per visualizzare i dettagli, [Avvia il processo di traduzione](translation-first-time.md#id225IK030OE8).

>[!NOTE]
>
> Se si rifiuta la traduzione di uno o più argomenti in un processo di traduzione, lo stato di traduzione **In corso** di tutti gli argomenti rifiutati viene ripristinato allo stato originale. Lo stato degli argomenti indicati viene controllato e ripristinato in base all’ultimo stato di traduzione. Inoltre, i file di traduzione creati nel progetto di destinazione non vengono eliminati anche se la traduzione viene rifiutata per essi.

## Aggiungere le regole di traduzione

Experience Manager Guides consente agli amministratori di configurare le regole di traduzione. Il formato SRX (Segmentation Rules eXchange) è uno standard per lo scambio di regole di segmentazione tra utenti e ambienti di traduzione diversi. È possibile creare una cartella e aggiungervi file SRX personalizzati.

I file SRX devono essere denominati come `<language-code>.srx`. Ad esempio, en-US o ar-AE.

>[!NOTE]
> 
> Il titolo non distingue tra maiuscole e minuscole, quindi puoi avere &quot;en-US&quot; o &quot;en-us&quot; o &quot;EN-us&quot;. Inoltre, Experience Manager Guides può risolvere &quot;-&quot; (trattino) o &quot;_&quot; (trattino basso). Quindi, puoi avere &quot;en-US&quot; o &quot;en_US&quot;.

Inoltre, è possibile inserire questi file in qualsiasi cartella nella directory principale delle risorse di Adobe Experience Manager che è `./content/dam`.

Dopo aver creato la cartella che contiene i file SRX, è possibile aggiungere il percorso della cartella nella configurazione del percorso SRX di traduzione all&#39;interno del profilo della cartella.

Per migliorare le prestazioni, si consiglia di mantenere solo i file SRX nella cartella configurata nel profilo della cartella.

Experience Manager Guides seleziona le regole SRX in base alla lingua di origine del progetto di traduzione. Cerca un file SRX personalizzato per una lingua e, se non definisci un file SRX personalizzato, seleziona le regole in base alle regole di traduzione predefinite.

Per informazioni dettagliate sulla configurazione di profili globali e a livello di cartella, consulta la sezione *Configurare i modelli di authoring* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

## Passa l’etichetta della versione alla versione di destinazione

Experience Manager Guides consente di passare l’etichetta del file di origine al file di destinazione. Questo ti aiuterà a identificare facilmente la versione sorgente del file tradotto.

Per aggiungere l&#39;etichetta della versione di origine nella copia di destinazione, l&#39;amministratore di sistema deve abilitare l&#39;opzione **Propaga le etichette della versione di origine alla versione di destinazione** nella scheda **Traduzione** in **Impostazioni**.

Ad esempio, se ad alcuni file di origine è stata applicata l&#39;etichetta di versione `Release 1.0`, è possibile passare anche l&#39;etichetta di origine \(`Release 1.0`\) al file tradotto.

![](images/translation-pass-source-label.png){width="650" align="left"}

>[!NOTE]
>
> L’etichetta di origine è associata a una sola versione di destinazione. Se sposti l’etichetta di origine in un’altra versione, questa si riflette automaticamente nell’etichetta di destinazione più recente.

## Visualizza differenza di versione per file non sincronizzati 

In Experience Manager Guides è disponibile la funzione che consente di verificare le differenze tra la versione selezionata e l&#39;ultima versione di origine tradotta degli argomenti. Puoi scegliere di tradurre i **file non sincronizzati** in base alle modifiche apportate.

![](images/translation-version-diff.png){width="650" align="left"}

Selezionare **Mostra differenza** icona \(![](images/show-difference-icon.svg)\) per un argomento per visualizzare le differenze tra l&#39;ultima versione tradotta e la versione corrente del file selezionato.

>[!NOTE]
>
> **Mostra differenza** icona \(![](images/show-difference-icon.svg)\) viene visualizzata solo per i file DITA con stato di traduzione **Non sincronizzato**.

Viene visualizzata la finestra di dialogo **Differenza versione**. Mostra il numero di versione **Ultima versione tradotta** e il numero di versione **Selezionata** a sinistra. Nella finestra di anteprima vengono visualizzate le differenze tra l&#39;ultima versione tradotta e la versione selezionata dell&#39;argomento.

![](images/version-diff.png){width="650" align="left"}

## Ignora risorse non sincronizzate

Se apporti modifiche ad alcune delle risorse, queste diventano non sincronizzate. Puoi tradurre nuovamente le risorse modificate o scegliere di ignorare lo stato Non sincronizzato. Ad esempio, se hai apportato alcune modifiche molto piccole che non richiedono alcuna traduzione, puoi contrassegnarne lo stato su In sincronia.

Per ignorare lo stato Non sincronizzato, effettuare le seguenti operazioni:

1. Seleziona le risorse non sincronizzate per le quali desideri modificare lo stato.
1. Selezionare il pulsante **Segna in sincronia** \(![](images/translation-mark-in-sync-icon.svg)\) in alto. Viene visualizzata la finestra di dialogo **Segna in sincronia**.

   ![](images/translation-mark-in-sync.png){width="550" align="left"}

1. Selezionare **Forza sincronizzazione**. Imposta lo stato su In sincronia per le risorse non sincronizzate selezionate.

>[!NOTE]
>
> **Il pulsante Contrassegna in sincronizzazione** \(![](images/translation-mark-in-sync-icon.svg)\) viene visualizzato solo per le risorse con stato di traduzione Non sincronizzato.

## Visualizza progetti di traduzione in corso per una mappa o un argomento

Alcuni dei riferimenti nel dashboard di traduzione potrebbero essere in stato di avanzamento. Questi riferimenti hanno un collegamento **In corso** nella colonna **Stato traduzione**. Quando selezioni il collegamento, viene visualizzata la finestra di dialogo **Progetti in corso**. Nella finestra di dialogo, puoi visualizzare l’elenco di tutti i progetti di traduzione In corso \(insieme alla lingua di destinazione\) che contengono il riferimento selezionato.

>[!NOTE]
>
> Puoi visualizzare il collegamento In corso per i progetti tradotti creati in Adobe Experience Manager Guides as a Cloud Service versione di febbraio 2023 o successiva.

Selezionate il nome del riferimento nella finestra di dialogo per aprirlo in modalità anteprima. Puoi anche selezionare il progetto di traduzione per avviare la traduzione.

![](images/translation-in-progress.png){width="550" align="left"}


## Eliminare o disattivare automaticamente un progetto di traduzione completato

>[!NOTE]
> 
>Questa funzione è disponibile per i nuovi progetti di traduzione creati con Experience Manager Guides versione 2404 o successiva.  Non avrà alcun impatto sui progetti esistenti.

L&#39;amministratore può configurare l&#39;opzione **Pulizia progetti di traduzione dopo il completamento** nella scheda **Traduzione** in **Impostazioni editor** per disabilitare o eliminare automaticamente i progetti di traduzione.

Per la gestione dei documenti, Experience Manager Guides consente di eliminare i progetti di traduzione una volta completata la traduzione.

Puoi anche disabilitare i progetti di traduzione se desideri utilizzarli in un secondo momento. Se si elimina un progetto, vengono eliminati anche tutti i file e le cartelle presenti nel progetto. La disattivazione di un progetto non ne comporta l’eliminazione ma ne mantiene la gestione nell’archivio. Ma non puoi aggiornare o modificare un progetto disabilitato.  L’eliminazione o la disabilitazione di un progetto non influisce sullo stato di traduzione di alcun riferimento.


**Argomento padre:**[ Introduzione all&#39;editor](web-editor.md)
