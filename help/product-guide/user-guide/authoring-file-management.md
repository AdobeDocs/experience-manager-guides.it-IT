---
title: Gestione di file e cartelle
description: Scopri come gestire file e cartelle nelle Guide AEM. Copiare e incollare, trascinare e rilasciare, eliminare, spostare file e cartelle in blocco e cercare contenuti DITA.
exl-id: e5b44286-7ac3-49e4-9e6f-7bc8ae2fc935
feature: Content Management
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '3108'
ht-degree: 0%

---

# Gestione di file e cartelle {#id2116G0L08XA}

Questa sezione spiega come AEM Guides gestisce le operazioni di base dei file, ad esempio copia, incolla, trascina selezione ed elimina i file. Sono possibili i seguenti scenari:

## Copiare e incollare file

**Se il file ha un nome di file leggibile**

- *Se il file con lo stesso nome non esiste nella cartella di destinazione*: viene creata una nuova copia del file a cui viene assegnato anche un UUID. In questo caso, il nome del file è uguale al nome del file originale.
- *Se il file con lo stesso nome esiste già nella cartella di destinazione*: viene creata una nuova copia del file con il suffisso \(come nomefile0.extension\). Al file appena creato viene assegnato anche un UUID.


**Se il nome del file è basato su un pattern UUID**

- *Se il file con lo stesso nome non esiste nella cartella di destinazione*: viene creata una nuova copia del file e viene assegnato un nuovo UUID nella nuova posizione. In questo caso, il nome del file è uguale a UUID.
- *Se il file con lo stesso nome esiste già nella cartella di destinazione*: viene creata una nuova copia del file e viene assegnato un nuovo UUID. Il nome del file è uguale all’UUID.


## Copiare e incollare cartelle

**Copia e incolla la cartella nello stesso percorso**

- *La cartella contiene file con nomi di file leggibili dall&#39;utente*: viene creata una nuova copia della cartella con il suffisso \(come nome cartella0\). Ai file all’interno della cartella viene assegnato anche un nuovo UUID. Tuttavia, i nomi dei file non vengono modificati.

- *La cartella contiene file con nomi di file basati su un pattern UUID*: viene creata una nuova copia della cartella con il suffisso \(come nome cartella0\). Un nuovo UUID viene inoltre assegnato a tutti i file all’interno della nuova cartella. Anche i nomi dei file vengono modificati; i nomi dei file sono gli stessi del nuovo UUID.


**Copia e incolla cartella in un percorso diverso**

- *La cartella contiene file con nomi di file leggibili dall&#39;utente*: viene creata una nuova copia della cartella e viene assegnato un nuovo UUID a tutti i file all’interno della cartella nella nuova posizione. In questo caso, non vi è alcuna modifica nei nomi delle cartelle o dei file.

- *La cartella contiene file con nomi di file basati su un pattern UUID*: viene creata una nuova copia della cartella con lo stesso nome della cartella originale. Un nuovo UUID viene inoltre assegnato a tutti i file all’interno della nuova cartella. Anche i nomi dei file vengono modificati; i nomi dei file sono gli stessi del nuovo UUID.


## Trascinare i file

**Trascinamento della selezione con nomi di file leggibili**

- *Trascinare nella stessa posizione*: sono disponibili le opzioni per **Sovrascrivi file esistenti\(s\)**, **Mantieni entrambi i file\(s\)** e un&#39;opzione per creare una versione della copia di lavoro esistente.

  ![](images/uuid-human-readable-drag-drop-same-location.PNG){width="650" align="center"}

  Se si sceglie **Sovrascrivi file esistenti\(s\)** , il file che viene caricato sostituisce la versione di lavoro corrente del file esistente nella posizione originale. L’UUID non viene creato o modificato.

  Se si sceglie **Mantieni entrambi i file\(s\)** , viene creata una nuova copia del file con il suffisso \(come nomefile0.extension\). Al file appena copiato viene assegnato anche un nuovo UUID.

  Con l&#39;opzione Sovrascrivi file esistente\(s\), se si sceglie di creare una versione dalla copia di lavoro esistente, viene creata anche una nuova versione dalla copia di lavoro del documento.

  >[!NOTE]
  >
  > **Crea nuova versione per file caricato** la funzionalità deve essere abilitata dall’amministratore. Se questa funzione è abilitata, viene creata una nuova versione per il file caricato. Se l’opzione è deselezionata, non viene creata una versione del file caricato. Per ulteriori dettagli, consulta *Crea nuova versione per file caricato* nella sezione Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

  Se un file è già stato estratto per essere modificato da un altro utente e si tenta di caricare e sovrascrivere il file esistente, il file non riesce e viene visualizzato un errore.

  >[!NOTE]
  >
  >Il **Sovrascrivi file estratto al caricamento** la funzionalità deve essere disabilitata dall&#39;amministratore. Se questa funzionalità è attivata, è possibile sovrascrivere i file estratti. Se la funzionalità non è abilitata, non è possibile sovrascrivere un file estratto. Per ulteriori dettagli, consulta *Sovrascrivi file estratto al caricamento* nella sezione Installare e configurare Adobe Experience Manager Guides as a Cloud Service.


- *Trascinare i file in una posizione diversa*: viene creata una nuova copia del file e viene assegnato un nuovo UUID nella nuova posizione. In questo caso, il nome del file è uguale al nome del file originale.


**Trascinamento della selezione con nomi di file basati su un pattern UUID**

*Trascinare il file nella stessa posizione*: sono disponibili le opzioni per **Sovrascrivi file esistenti\(s\)** insieme all&#39;opzione per creare una versione della copia di lavoro esistente.

![](images/uuid-drag-drop-same-location.PNG){width="650" align="center"}

Quando il file viene sovrascritto, il nome o l’UUID del file non vengono modificati.

Se si seleziona la **Crea versione per la copia di lavoro esistente** , quindi viene creata una nuova versione dalla copia di lavoro del documento; viene caricato il nuovo file, viene creata anche una nuova versione del file e viene creata come copia di lavoro del documento.

**Crea nuova versione per file caricato** la funzionalità deve essere abilitata dall’amministratore. Se questa funzione è abilitata, viene creata una nuova versione per il file caricato. Se l’opzione è deselezionata, non viene creata una versione del file caricato. Per ulteriori dettagli, consulta *Crea nuova versione per il file caricato* nella sezione Installare e configurare Adobe Experience Manager Guides as a Cloud Service.


*Trascinare il file in un percorso diverso*: sono disponibili le opzioni per **Sovrascrivi file esistenti\(s\)**, **Sposta file\(s\) nel nuovo percorso** e un&#39;opzione per creare una versione della copia di lavoro esistente.

![](images/uuid-drag-drop-different-location.PNG){width="650" align="center"}

Se si sceglie **Sovrascrivi file esistenti\(s\)** , il file che viene caricato sostituisce il file esistente nella posizione originale. L’UUID non viene creato o modificato.

Se si sceglie **Sposta file\(s\) nel nuovo percorso** , il file esistente viene spostato nella posizione corrente e quindi sovrascritto con il file caricato. Lo spostamento di un file nella nuova posizione non interrompe i riferimenti esistenti da o verso il file.

Con la sostituzione o lo spostamento dei file, se si sceglie di creare una versione dalla copia esistente, viene creata una nuova versione dalla copia di lavoro del documento. Il nuovo file viene sostituito nella posizione esistente o spostato nella nuova posizione.


## Spostare i file in blocco {#move-files-bulk}

AEM Guides viene fornito con Bulk Move Tool che consente all’amministratore di spostare una cartella con un numero elevato di file da una posizione all’altra. Questo strumento consente di spostare facilmente i file all&#39;interno di una o più cartelle in una cartella diversa nell&#39;archivio AEM. Una delle caratteristiche principali di questo strumento è che non solo sposta un numero elevato di file, ma mantiene anche i riferimenti a e dai file che vengono spostati. È possibile modificare il numero di file che è possibile spostare in batch senza ostacolare le attività di creazione e pubblicazione.

>[!NOTE]
>
> Lo strumento Sposta in blocco funziona solo a livello di cartella. Se desideri spostare singoli file argomento o mappa, utilizza lo strumento di spostamento normale dall’interfaccia utente di AEM Assets.

Di seguito sono riportate alcune delle funzioni fornite dallo strumento Spostamento in blocco:

- È possibile modificare il numero di file da elaborare in ogni batch. Questo potrebbe richiedere l’esecuzione di alcuni test prima di arrivare a un numero ottimale che il sistema può gestire facilmente.
- I servizi di authoring e pubblicazione vengono eseguiti senza interruzioni dall&#39;operazione di spostamento.
- Assicurare il controllo completo dell&#39;intervallo di tempo tra i successivi processi batch \(esecuzione di\). Questo intervallo di tempo assicura che l&#39;operazione di post-elaborazione venga completata prima di avviare il successivo batch di file.

- Gestione automatica delle cartelle con lo stesso nome. Questa funzione assicura che le cartelle che vengono spostate con lo stesso nome non vengano sovrascritte.

- Gestione automatica dei riferimenti ai file che vengono spostati.


Prima di eseguire il processo batch, è necessario considerare i punti seguenti:

- Se si prevede di spostare gli argomenti attualmente in revisione, è necessario chiudere il processo di revisione su tutti questi argomenti prima di spostarli. Se non si chiude l&#39;attività di revisione, il processo di revisione verrà interrotto.
- È necessario eseguire una sola operazione di spostamento in blocco sul sistema in qualsiasi momento. In questo modo si garantisce la corretta gestione dei riferimenti da e verso gli argomenti spostati.


Per spostare i file in blocco, effettuare le seguenti operazioni:

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti.
1. Fai clic sul pulsante **Strumento Sposta in Blocco** affiancare.
1. La pagina Bulk Move Tool (Strumento Spostamento di massa) viene visualizzata in base alla configurazione. Fornisci i seguenti dettagli su **Strumento Sposta in Blocco** pagina:

   <details>

   <summary> Cloud Service e file system locale basato su UUID </summary>

   ![](images/bulk-move-tool-uuid.png){width="650" align="center"}

   >[!TIP]
   >
   > Seleziona <img src="images/info-icon.svg" width="25">   vicino a qualsiasi campo per visualizzare ulteriori dettagli su di esso.


   - **Aggiungi suffisso alle cartelle duplicate**: se stai spostando cartelle con lo stesso nome, devi selezionare questa opzione. Ad esempio, nella schermata precedente, **Percorso di origine** contiene il nome delle cartelle da spostare. La cartella denominata topic esiste in due posizioni diverse, test-A e test-B. Quando selezioni questa opzione, le cartelle verranno spostate correttamente. La prima cartella spostata sarà denominata topic, mentre la seconda sarà denominata topic0. L&#39;operazione di spostamento aggiunge un suffisso nelle serie sequenziali \(0, 1, 2 e così via\) alle cartelle con lo stesso nome.

     Se si spostano cartelle con lo stesso nome senza selezionare questa opzione, l&#39;operazione verrà interrotta con un messaggio.

   - **Percorso origine\(s\)**: specifica il percorso delle cartelle da spostare.

      - Seleziona  **Sfoglia cartella**  <img src="images/browse-folder-icon.svg" width="25">    per aprire la finestra di dialogo sfoglia file. Seleziona le cartelle da spostare e fai clic su **Seleziona** per completare il processo.

      - È inoltre possibile digitare o copiare e incollare il percorso di origine. Premi Invio per aggiungere la cartella all’elenco.

        Le cartelle selezionate vengono elencate insieme al relativo percorso. Passa il puntatore del mouse sul tag della cartella per visualizzare il percorso completo.
      - Puoi anche rimuovere qualsiasi cartella facendo clic su **Rimuovi** <img src="images/remove-folder.svg" width="25"> vicino alla cartella.


   - **Percorso di destinazione**: specifica il percorso in cui spostare le cartelle di origine.

      - Seleziona  **Sfoglia cartella** <img src="images/browse-folder-icon.svg" width="25"> per aprire la finestra di dialogo sfoglia file. Selezionare il percorso in cui si desidera spostare le cartelle di origine. e fare clic su Seleziona per completare il processo.
      - È inoltre possibile digitare o copiare e incollare il percorso di destinazione.

     La cartella selezionata viene visualizzata insieme al relativo percorso nella casella di testo.


   - Clic **Spostamento in blocco**.

     Il sistema inizia lo spostamento dei file dal percorso di origine a quello di destinazione. Al termine del processo, a destra della pagina viene visualizzato un riepilogo del processo di spostamento.

     ![](images/bulk-move-summary-uuid.png){width="650" align="center"}

   </details>

   <details>

   <summary> File system locale non basato su UUID </summary>

   ![](images/bulk-move-tool-non-uuid.png){width="650" align="center"}

   >[!TIP]
   >
   > Seleziona <img src="images/info-icon.svg" width="25">   vicino a qualsiasi campo per visualizzare ulteriori dettagli su di esso.

   - **Dimensione batch**: specifica il numero di file da spostare in un singolo batch. I valori predefiniti per 50 file.
   - **Intervallo di sospensione**: specifica il tempo di attesa in secondi del processo prima di avviare il batch successivo. Durante questo intervallo di sospensione, il sistema corregge i riferimenti ai file spostati e da essi. L&#39;intervallo di sospensione predefinito è di 60 secondi.


   - **Aggiungi suffisso alle cartelle duplicate**: se stai spostando cartelle con lo stesso nome, devi selezionare questa opzione. Ad esempio, nella schermata precedente, **Percorso di origine** contiene il nome delle cartelle da spostare. La cartella denominata topic esiste in due posizioni diverse, test-A e test-B. Quando selezioni questa opzione, le cartelle verranno spostate correttamente. La prima cartella spostata sarà denominata topic, mentre la seconda sarà denominata topic0. L&#39;operazione di spostamento aggiunge un suffisso nelle serie sequenziali \(0, 1, 2 e così via\) alle cartelle con lo stesso nome.

     Se si spostano cartelle con lo stesso nome senza selezionare questa opzione, l&#39;operazione verrà interrotta con un messaggio.

   - **Aggiornare i riferimenti dei file estratti**: se si spostano cartelle contenenti file estratti, si consiglia di selezionare questa opzione. Se si seleziona questa opzione, tutti i file estratti verranno salvati e archiviati con una nuova revisione. Questa nuova revisione viene quindi spostata nel percorso di destinazione.

     Se non si seleziona questa opzione, i file estratti vengono spostati nella cartella di destinazione con lo stesso stato estratto. Tuttavia, potrebbe verificarsi una perdita di dati in questo processo in movimento.


   - **Percorso origine\(s\)**: specifica il percorso delle cartelle da spostare.

      - Seleziona  **Sfoglia cartella**  <img src="images/browse-folder-icon.svg" width="25">    per aprire la finestra di dialogo sfoglia file. Seleziona le cartelle da spostare e fai clic su **Seleziona** per completare il processo.

      - È inoltre possibile digitare o copiare e incollare il percorso di origine. Premi Invio per aggiungere la cartella all’elenco.

        Le cartelle selezionate vengono elencate insieme al relativo percorso. Passa il puntatore del mouse sul tag della cartella per visualizzare il percorso completo.
      - Puoi anche rimuovere qualsiasi cartella facendo clic su **Rimuovi** <img src="images/remove-folder.svg" width="25"> vicino alla cartella.


   - **Percorso di destinazione**: specifica il percorso in cui spostare le cartelle di origine.

      - Seleziona  **Sfoglia cartella** <img src="images/browse-folder-icon.svg" width="25"> per aprire la finestra di dialogo sfoglia file. Selezionare il percorso in cui si desidera spostare le cartelle di origine. e fare clic su Seleziona per completare il processo.
      - È inoltre possibile digitare o copiare e incollare il percorso di destinazione.

        La cartella selezionata viene visualizzata insieme al relativo percorso nella casella di testo.

   - Clic **Spostamento in blocco**.

     Il sistema inizia lo spostamento dei file dal percorso di origine a quello di destinazione. Al termine del processo, a destra della pagina viene visualizzato un riepilogo del processo di spostamento.
     ![](images/bulk-move-summary-non-uuid.png){width="650" align="center"}
</details>

## Cerca contenuto DITA

Per impostazione predefinita, l&#39;AEM non riconosce il contenuto DITA, pertanto non fornisce alcun meccanismo per eseguire ricerche nel contenuto DITA all&#39;interno del relativo archivio. Le guide AEM aggiungono un livello sopra l&#39;AEM, che consente all&#39;AEM di comprendere ed elaborare i contenuti DITA. La funzione Cerca contenuto DITA nelle guide AEM consente di cercare contenuto DITA all&#39;interno dell&#39;archivio AEM.

>[!NOTE]
>
>L&#39;amministratore di sistema può configurare **Elemento DITA** componente di ricerca, quindi puoi utilizzare la funzione dall’interfaccia utente di AEM Assets. Per maggiori dettagli vedi, *Aggiungere il componente di ricerca degli elementi DITA nell’interfaccia utente Assets* sezione in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

Utilizzando la funzione di ricerca, potete effettuare le seguenti operazioni:

- Cercare contenuto DITA in base a un valore di elemento, ad esempio `author`= xml
- Cerca contenuto DITA in base a un valore di attributo; ad esempio, `@platform`= finestre
- Utilizza una combinazione di elemento DITA e valore di attributo; ad esempio, `author`= xml `AND` `@platform`= finestre

Per cercare contenuto DITA nell&#39;archivio AEM, effettuare le seguenti operazioni:

1. Apri l’interfaccia utente Assets.

1. Nella barra a sinistra, seleziona **Filtri**.

   ![](images/left-rail-filter.png){width="450" align="center"}

   Le opzioni di filtro del contenuto sono visualizzate nella barra a sinistra. È inoltre disponibile l&#39;opzione di filtro Elemento DITA, utilizzata per filtrare il contenuto DITA.

   ![](images/dita-element-search.png){width="450" align="center"}

1. *\(Facoltativo\)* In **Seleziona directory di ricerca** , individuare la posizione in cui si desidera eseguire la ricerca.

1. In **Elemento DITA** , fornisci **Nome elemento**, **Attributo** e un valore da cercare. Ad esempio, per cercare documenti che hanno `author` elemento di `@type` creatore devi fornire le informazioni come mostrato nella schermata seguente:

   ![](images/search-params.png){width="650" align="center"}

   I criteri di ricerca immessi nel **Elemento DITA** nella parte superiore della barra di ricerca. I file che corrispondono ai criteri di ricerca sono visualizzati nella **Risultati di ricerca** area.

   Quando si specificano i criteri di ricerca, prendere in considerazione i punti seguenti:

   - Per cercare una frase esatta, immetti la frase nel campo Valore tra virgolette `"`ricerca di frasi`"`.
   - È possibile aggiungere fino a 3 criteri di ricerca di elementi DITA.
   - Se specifichi più criteri di ricerca, tutti verranno combinati utilizzando la logica AND.
   - Non è possibile utilizzare caratteri jolly nei criteri di ricerca. Ad esempio, per cercare la piattaforma \(attribute\) con il valore di Windows, non è possibile specificare \*form o Windo?s.

**Filtro dello stato di estrazione nella ricerca**

Oltre al filtro Elemento DITA, le guide AEM consentono anche di cercare contenuti in base al loro stato di checkout. Questa opzione è utile quando si desidera filtrare rapidamente i file attualmente estratti dall&#39;utente e archiviarli nuovamente.

Per cercare i file in base al loro stato di estrazione, effettuare le seguenti operazioni:

1. Apri l’interfaccia utente Assets.

1. Clic **Filtro** nella barra a sinistra.
1. Immetti la parola chiave da cercare nella barra di ricerca.
1. Applica i filtri richiesti dalla barra a sinistra.

   Ad esempio, puoi applicare **Stato ritiro** filtro per visualizzare gli argomenti sottoposti a Check-Out o Check-In. È possibile perfezionare ulteriormente l&#39;elenco scegliendo l&#39;utente o il gruppo dall&#39;elenco Estratto da.

   Viene visualizzato il risultato della ricerca.


## Elimina file

L’eliminazione dei file dal repository dell’AEM è una funzione soggetta a restrizioni, controllata dall’amministratore di sistema. In base alle configurazioni, l’eliminazione dei file potrebbe essere soggetta a restrizioni se:

- Ritirato
- Hanno riferimenti in entrata o in uscita

È inoltre possibile eliminare i file solo se si appartiene a un gruppo di utenti specifico che dispone dei privilegi per eliminare i file.

>[!NOTE]
>
> Per ulteriori dettagli sulle configurazioni di gestione dei file, consulta *Impedisci l&#39;eliminazione dei file estratti* e *Impedisci l&#39;eliminazione dei file di riferimento* nelle sezioni dell’as a Cloud Service Installare e configurare Adobe Experience Manager Guides.

Se l&#39;amministratore ha concesso l&#39;autorizzazione di eliminazione file a tutti gli utenti, quando si eliminano file contenenti riferimenti viene visualizzato il seguente messaggio:

![](images/allow_unsafe_delete-force-delete.PNG){width="650" align="center"}

In questo scenario, è possibile eliminare forzatamente i file senza rimuovere i riferimenti in entrata o in uscita dai file.

Se le autorizzazioni di eliminazione sono assegnate a un gruppo di utenti specifico, verrà visualizzato anche il messaggio precedente per gli utenti appartenenti a tale gruppo. Tuttavia, per gli altri utenti, viene visualizzato il seguente messaggio:

![](images/allow_unsafe_delete_for_delete_assets_group.PNG){width="650" align="center"}

In questo scenario, agli utenti non sarà consentito eliminare i file finché non saranno stati rimossi tutti i riferimenti in entrata e in uscita.

## Utilizzare i file multimediali

I file multimediali come immagini e video sono parte integrante del contenuto. Durante il caricamento e la gestione dei contenuti, è possibile utilizzare anche i file multimediali.

Se il file multimediale è stato modificato, è possibile trovare e visualizzare in anteprima i file nel **Cronologia versioni**.Per individuare le modifiche nelle diverse versioni di un file multimediale:

1. Accedere al file in **Interfaccia utente Assets**.
1. Selezionare il file per il quale si desidera visualizzare la cronologia delle versioni.
1. Nella barra a sinistra, fai clic su **Cronologia versioni** e seleziona una versione.
1. Puoi anche vedere le miniature delle diverse versioni in Cronologia versioni.

   ![](images/media-version-history-icon.png){width="800" align="center"}

1. Dalle versioni elencate, seleziona quella che desideri utilizzare come versione di base e fai clic su **Anteprima versione**. L&#39;anteprima della versione selezionata viene visualizzata nella finestra Anteprima versione.

   ![](images/media-version-preview.png){width="650" align="center"}


**Argomento padre:**[ Gestire i contenuti](authoring.md)
