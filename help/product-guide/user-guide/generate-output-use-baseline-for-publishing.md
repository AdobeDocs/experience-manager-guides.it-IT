---
title: Utilizzare la previsione
description: Conoscere l’uso delle linee di base nelle guide AEM. Scopri come creare, visualizzare contenuti, modificare, duplicare, rimuovere, aggiungere etichette ed esportare baseline tradotte.
exl-id: 0554947f-3038-4fd2-8a62-ac0d4b858e94
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 0%

---

# Utilizzare la previsione {#id1825FI0J0PF}

La funzione Baseline consente di creare una versione degli argomenti e delle risorse che può essere utilizzata per la pubblicazione o la traduzione. Ad esempio, se la mappa DITA ha `topicA` e `imageA`, è possibile creare una baseline per utilizzare la terza versione di `topicA`, ma la quarta versione di `ImageA`. Dopo aver impostato una baseline, è possibile pubblicare o tradurre argomenti di versioni diverse con un solo clic.

La selezione di una baseline è facoltativa per i predefiniti di output e una mappa DITA può avere più di una baseline. Tuttavia, ogni predefinito di output all&#39;interno di una mappa DITA può essere associato a una sola baseline. Se al momento della pubblicazione non è specificata alcuna linea di base, l’output viene pubblicato utilizzando la versione più recente del contenuto.

Allo stesso modo, la selezione di una linea di base per tradurre il contenuto è facoltativa. Tuttavia, se si sceglie di tradurre il contenuto utilizzando una baseline, il contenuto della baseline viene salvato insieme alle copie tradotte. Puoi quindi utilizzare la linea di base tradotta per eseguire ulteriori operazioni, come condividerla con editori esterni o archiviarla. Per ulteriori informazioni sull&#39;esportazione di una baseline tradotta, vedere [Esporta previsione tradotta](#id196SE600GHS).

>[!TIP]
>
> Consulta la *Linea di base* sezione nella guida alle best practice per le best practice sull’utilizzo delle linee di base.

L’amministratore può configurare la scheda Baseline nel dashboard delle mappe. Per ulteriori dettagli, consulta *Scheda Configura baseline nel dashboard delle mappe DITA* nella Guida all&#39;installazione e alla configurazione.

Per accedere alla feature di baseline, effettuate le seguenti operazioni:

1. Nell’interfaccia utente Assets, passa a e fai clic sul file di mappa DITA.
1. Vai a **Linee di base** scheda.

Nella scheda Baseline è possibile eseguire le azioni riportate di seguito.

- [Creare una baseline](#id195FI0I0MUQ)
- [Visualizzare il contenuto di una baseline](#id195FI0I0TLN)
- [Modificare, duplicare o rimuovere le baseline](#id195FI0I0YJL)
- [Aggiungere etichette a una baseline](#id184KD0T305Z)

## Creare una baseline {#id195FI0I0MUQ}

È possibile creare una baseline con una versione specifica degli argomenti e del contenuto di riferimento disponibile in una data e un&#39;ora specifiche oppure con un&#39;etichetta definita per una versione degli argomenti. È possibile specificare singolarmente le versioni degli argomenti selezionati in una baseline in modo che ogni volta che si applica la baseline nel flusso di lavoro di pubblicazione o traduzione, gli argomenti selezionati e le relative versioni corrispondenti vengano inclusi per la generazione dell&#39;output o la traduzione.

Per creare una baseline, effettuare le operazioni riportate di seguito.

1. Nella pagina Baseline fare clic su **Crea**.
1. Immettere un nome per la baseline in **Nome linea di base**.
   ![creare una baseline](images/create-baseline.png){width="800" align="left"}
1. In entrata **Imposta la versione in base a**, seleziona una delle opzioni seguenti:

   - **Etichetta**: seleziona questa opzione per scegliere gli argomenti in base all’etichetta ad essi applicata. Immettere un&#39;etichetta per filtrare l&#39;elenco in base alla stringa immessa. Dall’elenco delle risorse filtrate, puoi scegliere un’etichetta per selezionare gli argomenti e le altre risorse con l’etichetta specificata.

   Quando selezioni **Etichetta** Inoltre, è disponibile un&#39;opzione aggiuntiva per utilizzare la versione più recente degli argomenti a cui non è stata applicata l&#39;etichetta specificata. Se non si seleziona questa opzione e sono presenti file di argomento o file multimediali senza l&#39;etichetta specificata, il processo di creazione della linea di base avrà esito negativo. Per ulteriori informazioni sull&#39;aggiunta di etichette, vedere [Usa etichette](web-editor-use-label.md#).

   - **Versione su** &lt;*timestamp*\>: seleziona la versione degli argomenti in base alla data e all&#39;ora specificate. L’ora specificata qui corrisponde al fuso orario del server AEM. Se il server si trova in un fuso orario diverso, gli argomenti verranno selezionati in base al fuso orario del server e non a quello locale.

   Dopo aver selezionato un&#39;etichetta o una versione come alla data, tutti gli argomenti e i file multimediali a cui si fa riferimento nella mappa vengono selezionati di conseguenza. Questa selezione di argomenti non viene visualizzata nell&#39;interfaccia utente, ma viene salvata nel back-end.

   >[!NOTE]
   >
   >Si consiglia di non utilizzare il **Sfoglia tutti gli argomenti** durante la creazione di una baseline.

1. Fai clic su **Salva**.

## Visualizzare il contenuto di una baseline {#id195FI0I0TLN}

È possibile visualizzare il contenuto di una baseline esistente facendo clic sulla scheda Baseline e selezionando la versione della baseline desiderata dall&#39;elenco. La pagina Baseline è divisa in tre parti: file mappa DITA, contenuto o argomenti della mappa e contenuto di riferimento. Se la mappa contiene mappe secondarie, gli argomenti a cui si fa riferimento dalla mappa secondaria vengono visualizzati anche nella sezione Contenuto. Di seguito sono descritte le varie colonne della pagina Baseline:

- **Nome**: elenca la mappa DITA o il titolo dell’argomento oppure il nome della risorsa, ad esempio il nome di file di un’immagine.

- **Tipo**: elenca il tipo di risorsa nella mappa, ad esempio mappa DITA, argomento DITA o formato immagine.

- **Versione**: elenca la versione della risorsa disponibile nella linea di base.

- **Data e ora versione**: elenca la data e l’ora di creazione della risorsa per la versione selezionata.

- **Più recente**: elenca se la versione più recente della risorsa viene utilizzata nella linea di base.

- **Mappa padre**: se il file di mappa contiene mappe secondarie, questa colonna contiene il nome della mappa in cui si fa riferimento a un argomento.

- **Etichetta**: elenca l&#39;etichetta applicata alla versione dell&#39;argomento.

- **Con riferimento da**: questa colonna è disponibile solo per il contenuto di riferimento. Indica l’argomento principale della risorsa di riferimento. Se più argomenti fanno riferimento a una risorsa, questi vengono separati da virgole.

## Modificare, duplicare o rimuovere le baseline {#id195FI0I0YJL}

**Modifica linee di base**

Per modificare una baseline esistente, effettuare le operazioni riportate di seguito.

1. Selezionare la baseline e fare clic su **Modifica**.
1. Apportare le modifiche necessarie nella baseline. È possibile modificare il nome e la versione dell&#39;argomento o del contenuto di riferimento.
1. Se si desidera utilizzare una versione diversa per uno o più argomenti, è possibile selezionare manualmente tali argomenti. Clic **Sfoglia argomento**, selezionare l&#39;argomento per il quale si desidera utilizzare una versione diversa. Dall&#39;elenco a discesa Seleziona una versione per l&#39;argomento selezionato, selezionare una versione dell&#39;argomento che si desidera utilizzare nella baseline e fare clic su **OK**.

   ![](images/baseline-select-version-drop-down.png){width="800" align="left"}

   Le informazioni sull&#39;argomento e sulla versione selezionata vengono memorizzate nel back-end. È possibile ripetere questo passaggio per modificare la versione selezionata per più argomenti.

1. Per caricare tutti gli argomenti e i file multimediali a cui si fa riferimento dalla mappa DITA, fare clic sul pulsante **Sfoglia tutti gli argomenti** collegamento. L’UUID degli argomenti e dei file multimediali è riportato anche sotto il titolo dell’argomento o il nome del file \(media\).

   >[!NOTE]
   >
   > Se nella mappa DITA è presente un set di file molto grande, con mappe e argomenti nidificati, il caricamento di tutti i file potrebbe richiedere del tempo se si fa clic su Sfoglia tutti gli argomenti.

   Il contenuto della mappa è presentato nelle tre sezioni seguenti: File mappa, Contenuto \(riferimenti argomento\) e Contenuto di riferimento \(argomenti nidificati, mappe e altre risorse\). Una volta disponibili tutti i contenuti a cui si fa riferimento, è possibile selezionare singolarmente la versione dell&#39;argomento che si desidera utilizzare nella baseline.

   Il **Versione** elenco a discesa mostra le versioni disponibili degli argomenti o del contenuto a cui si fa riferimento. Per il contenuto a cui si fa riferimento, è possibile scegliere automaticamente una versione.

   Se si sceglie **Scegli automaticamente** per il contenuto di riferimento, il sistema seleziona automaticamente la versione del contenuto di riferimento corrispondente alla versione del contenuto in cui viene fatto riferimento. Ad esempio, supponiamo che un argomento A abbia un riferimento a un’immagine B. Quando è stata creata la versione 1.5 dell’argomento A, la versione dell’immagine B era 1.2 nell’archivio. Ora, quando si crea una linea di base con la versione 1.5 dell’argomento A, con l’immagine B impostata su **Scegli automaticamente**, il sistema sceglierà automaticamente la versione 1.2 dell&#39;immagine B.

   Se si crea una baseline utilizzando le etichette, **Scegli automaticamente** viene applicato alla versione di tutto il contenuto a cui si fa riferimento.

   Se il contenuto o le risorse a cui si fa riferimento (argomento, mappe secondarie, immagini o video\) non hanno versioni \ (ad esempio, contenuto appena caricato\), la creazione di una baseline creerà una versione per tali file. Tuttavia, se i file sono stati sottoposti a controllo delle versioni, non viene creata alcuna versione incrementale per tali file. Questo comportamento è controllato dall’impostazione di creazione automatica della versione, abilitata per impostazione predefinita. Ciò è necessario anche per la traduzione del contenuto in cui il processo di traduzione si aspetta che tutti i file abbiano una versione.

   >[!NOTE]
   >
   > Se desideri specificare una versione diversa per una particolare risorsa, puoi farlo scegliendo la versione desiderata da **Versione** elenco a discesa.
1. Fai clic su **Salva**.

**Duplica linee di base**

Selezionare la baseline e fare clic su **Duplica** per creare una copia di una baseline esistente. Specificare un nome diverso per la linea di base, scegliere il numero di versione per gli argomenti e il contenuto di riferimento e fare clic su **Salva**.

**Rimuovi linee di base**

Seleziona la versione delle baseline e fai clic su **Rimuovi** per rimuovere una baseline.

## Aggiungere etichette a una baseline {#id184KD0T305Z}

L&#39;aggiunta di etichette a ogni argomento può richiedere molto tempo. Le guide AEM consentono di aggiungere etichette a più argomenti e al contenuto di riferimento in una mappa DITA con un solo clic.

Per aggiungere un&#39;etichetta a più argomenti e al contenuto di riferimento in una mappa DITA, effettuare le seguenti operazioni:

1. Nella pagina Baseline selezionare una baseline contenente gli argomenti e il contenuto di riferimento a cui si desidera aggiungere un&#39;etichetta.

   >[!NOTE]
   >
   > Assicurati che la linea di base non contenga la versione più recente di alcun argomento o risorsa. È possibile aggiungere un’etichetta solo a un argomento o a una risorsa con versione.

1. Clic **Aggiungi etichette**.

   ![](images/add-label-baseline-uuid.png){width="800" align="left"}

1. In **Aggiungi etichetta** , specificare un&#39;etichetta univoca da associare alla baseline.

   Se l’amministratore ha configurato delle etichette predefinite, queste vengono visualizzate in un elenco a discesa. È necessario scegliere un’etichetta dall’elenco.

1. Se desideri applicare l’etichetta agli argomenti a cui si fa riferimento dalle mappe secondarie, seleziona **Applica etichetta a mappe figlio e dipendenti** opzione.

   - Clic **Aggiungi**.
L&#39;etichetta specificata viene aggiunta alla mappa DITA e agli argomenti e al contenuto a cui si fa riferimento.

     ![](images/label-added-baseline-uuid.png){width="650" align="left"}


## Esporta previsione tradotta {#id196SE600GHS}

Puoi utilizzare la Linea di base per tradurre i contenuti. Ad esempio, puoi creare una linea di base per la versione 1.1 pronta per la traduzione in francese. Nella scheda Traduzione, devi utilizzare Linea di base per filtrare il contenuto, quindi selezionare la Linea di base per la versione 1.1 del contenuto. L’utilizzo di Baseline per la traduzione dei contenuti facilita la gestione dei contenuti.

Una volta tradotti i contenuti, puoi esportare la linea di base tradotta per l’archiviazione o condividerla con i diversi team dell’organizzazione. Prima di esportare una baseline tradotta, è necessario considerare i punti seguenti:

- L&#39;esportazione di una baseline è possibile solo dopo la traduzione del contenuto nella baseline. Se si tenta di esportare una baseline per la quale la traduzione non è stata avviata o non è stata completata, verrà visualizzato un errore.
- È possibile trasferire la baseline solo per una versione già tradotta. Ad esempio, se hai creato una previsione per la versione 1.1 del contenuto e lo stesso è tradotto, puoi esportare questa previsione. Tuttavia, se avete creato una baseline per la versione 1.2, che non è stata tradotta, non potete esportarla.
- Se una baseline è già stata esportata, è possibile sovrascrivere la baseline esistente selezionando *Sovrascrivi baseline esistente* durante l&#39;esportazione.

Per esportare una baseline tradotta, effettuare le seguenti operazioni:

1. Aprire la mappa DITA contenente la baseline tradotta.

1. In **Traduzione** , espandere la scheda **Linea di base** disponibile nella barra a sinistra.

   ![](images/export-baseline.png){width="800" align="left"}

1. Seleziona la **Usa linea di base** e scegliere la baseline da esportare.

1. Clic **Esporta previsione**.

   Viene visualizzato lo stato di esportazione. Se il processo ha esito positivo, viene visualizzato un messaggio che indica la lingua per la quale viene esportata la baseline. In caso di guasto, viene visualizzata la causa del guasto.

   Se si tenta di esportare la baseline già esportata, viene visualizzato anche il messaggio di errore di creazione della baseline.

1. \(Facoltativo\) Per esportare una baseline già esportata, selezionare **Sovrascrivi baseline esistente** e quindi fare clic su **Esporta previsione**.


**Argomento padre:**[ Generazione di output](generate-output.md)
