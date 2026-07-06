---
title: Note sulla versione per Adobe Experience Manager Guides 3.8 e 3.8.5
description: Nuove funzioni e miglioramenti principali nelle versioni 3.8 e 3.8.5 di Adobe Experience Manager Guides (precedentemente nota come soluzione XML Documentation).
source-git-commit: ff3d35832b80f6221f1261498934ab74261b282b
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 0%

---


# Note sulla versione | Adobe Experience Manager Guides 3.8

**Dichiarazione di non responsabilità**:

*Adobe Experience Manager Guides* era precedentemente contrassegnato come *XML Documentation per Adobe Experience Manager*. Tieni presente che alcuni riferimenti all’interno della documentazione possono ancora fare riferimento al branding precedente, ma sono ancora applicabili all’offerta corrente.

In queste note sulla versione sono elencate le nuove funzioni e i miglioramenti principali introdotti nella versione 3.8.x di XML Documentation for Adobe Experience Manager.

## Nuove funzioni e miglioramenti nella versione 3.8.5

### Correzioni di bug

I bug risolti nella versione 3.8.5 sono elencati di seguito:

- Supporto della linea di base mancante per l’output PDF tramite FrameMaker Publishing Server.
- L&#39;API di check-out e check-in per FrameMaker o ossigeno non funziona correttamente se le autorizzazioni a livello di cartella sono state impostate per vari gruppi in AEM.
- L’anteprima del contenuto non viene visualizzata dalla pagina dell’interfaccia utente di Assets.
- Il pulsante &quot;Source&quot; non funziona sulla pagina dell’interfaccia utente di Assets.
- Quando un&#39;immagine viene inserita tramite la funzione Inserisci immagine dell&#39;editor Web, il percorso relativo dell&#39;immagine inserita viene modificato nel relativo percorso assoluto.
- L’elenco a discesa del predefinito FMPS non viene visualizzato nell’interfaccia utente con la versione 3.8 più recente.
- Il pannello Preferiti non viene visualizzato se contiene un numero elevato di risorse in DAM e viene aggiunto un nuovo elemento preferito dall’editor Web XML.
- Il reindirizzamento interno *sling:mapping* che reindirizza tutti i collegamenti non funziona e visualizza URL lunghi (con percorsi interni) invece degli URL brevi per le pagine Web.
- Nella Vista a elenco, nella colonna Modificato viene visualizzato &quot;Utente esterno&quot; invece del nome utente quando le risorse vengono caricate o importate dalla pagina dell’interfaccia utente di Assets (eccetto tramite Gestione pacchetti).
- Il titolo non viene visualizzato correttamente nella scheda Argomenti della dashboard Mappa.
- Attivando la funzione di appiattimento del nodo, alcuni caratteri indesiderati vengono memorizzati nell’output di HTML.
- Le modifiche apportate al profilo della cartella in base alle preferenze utente non vengono ricaricate automaticamente per un file già aperto, ma è necessario aggiornare il browser.
- L’output generato tramite l’opzione Scarica mappa presenta alcuni argomenti mancanti in caso di errori di convalida.

## Nuove funzioni e miglioramenti nella versione 3.8

### Aggiornamenti alla configurazione della denominazione dei file

Durante la creazione di argomenti DITA nella soluzione XML Documentation, gli utenti possono utilizzare caratteri speciali come parte dei nomi dei file. Questo comportava URL codificati nella generazione di pagine del sito AEM. Per evitare questa conversione in URL, la versione 3.8 delle soluzioni XML Documentation consente a un amministratore di definire un elenco di caratteri speciali diversi dalle configurazioni dei nomi di file valide predefinite (a-z A-Z 0-9 - _). Questo implica che, anche se è possibile configurare un elenco di caratteri speciali in un nome di file che include uno spazio, verrà sostituito con un trattino (-).

### Modifiche alla generazione del nome della pagina del sito AEM

Durante l’authoring, è possibile usare lo stesso nome di file per uno o più file in cartelle diverse. Durante il processo di pubblicazione del sito AEM, ai nomi delle pagine veniva aggiunto un suffisso quando era presente almeno un nome di file duplicato. Con la versione 3.8 della soluzione XML Documentation, il processo di generazione dei nomi delle pagine del sito AEM è stato corretto. Il suffisso viene aggiunto al nome della pagina generata solo se è presente un nome di file duplicato.

### Nuove funzioni e miglioramenti

Sono state introdotte diverse nuove funzioni e miglioramenti nelle seguenti aree del prodotto.

#### Editor web

- È ora possibile scegliere un&#39;etichetta da un elenco a discesa durante la creazione di una versione di un argomento dall&#39;Editor Web.

  ![Etichette in un elenco a discesa](assets/labels-drop-down-saving-topic-res.avif)

- Il pannello Revisione nell’editor web è ora più potente e consente di ripristinare una versione condivisa per la revisione di un argomento. È possibile incorporare facilmente i commenti di revisione nella versione rivista senza dover ricordare quale versione dell&#39;argomento è stata condivisa per la revisione.

  ![Ripristina argomento per revisione versione](assets/revert-review-topic.avif)

- È stato introdotto un nuovo segnale visivo per indicare se si sta lavorando sulla versione più recente di un argomento o su una versione precedente.

  ![Cue versione](assets/old-version-icon.avif)

- In questa versione è stata introdotta una nuova funzione Cronologia versioni. Utilizzare la funzione Cronologia versioni per:
   - Visualizza un elenco di tutte le versioni dell&#39;argomento attualmente attivo con le etichette aggiunte per ogni versione.
   - Ripristinare una versione precedente dell&#39;argomento.

  ![Cronologia versioni](assets/version-history.avif)

- È stata aggiunta una nuova funzione di gestione delle etichette delle versioni che consente di applicare etichette alle versioni correnti o precedenti di un argomento.

  ![Gestione etichette versione](assets/version-label-management.avif)

- È stata aggiunta la nuova funzione: &quot;Approva per la pubblicazione&quot;, con cui un autore può contrassegnare una risorsa come approvata e bloccarla ulteriormente per la modifica.
- Quando si avvia un processo di revisione, è ora possibile filtrare gli argomenti in base al loro stato.

  ![Seleziona gli argomenti di revisione in base al loro stato](assets/review-select-topic-on-state.avif)

- `<navtitle>` in una mappa viene compilato automaticamente con il titolo di un argomento aggiunto al file mappa. È inoltre possibile aggiornare facilmente `<navtitle>` dall&#39;editor Web.
- L’anteprima di una tabella con un numero elevato di colonne viene ora visualizzata nell’area della pagina.
- Potete applicare più classi di output contemporaneamente dal pannello Proprietà (selezione multipla).
- Quando visualizzi l’anteprima di un argomento, puoi anche generare un output PDF incondizionato di un singolo argomento direttamente dall’editor web.

  ![Output PDF da anteprima](assets/pdf-output-from-preview.avif)

- Blocca una richiesta di pubblicazione se è in corso la generazione dell’output dello stesso predefinito.
- È stata aggiunta la possibilità solo per un set di utenti con privilegi di eliminare le risorse che hanno riferimenti retroattivi attivi.
- È stata aggiunta una funzione per visualizzare o copiare il codice XML dalla vista Source dall’interfaccia utente di Assets anche se il file è stato estratto da un altro utente.

  ![Visualizzazione Source XML](assets/xml-source-view-from-assets-ui.avif)

- Il nome del file viene ora sostituito con il titolo del file nella finestra di dialogo Salva, nel pannello Contenuto riutilizzabile e nel pannello Trova e sostituisci.

#### Pubblicazione

- **Consenti la configurazione delle regole di pulizia per le pagine del sito generate**: in qualità di amministratore, puoi definire le regole di pulizia per i nomi dei file del sito AEM o dell&#39;output DITA-OT generato. Ogni volta che si genera un output o un output di AEM Site utilizzando DITA-OT, è possibile configurare le regole seguenti per bonificare gli URL o i nomi di file generati dall&#39;output:
   - Converti tutti i caratteri in minuscolo.
   - Sostituisci i caratteri speciali con un separatore.
   - Limitare un nome di file lungo a un numero predefinito di caratteri.

- Invia facilmente l’output dall’istanza di authoring all’istanza di pubblicazione utilizzando la dashboard di attivazione in blocco. È possibile utilizzare una singola mappa o una raccolta di mappe e scegliere il predefinito di output da utilizzare per la pubblicazione.

  ![Dashboard per pubblicazione in blocco](assets/bulk-publish-dashboard.avif)

#### Miglioramenti delle prestazioni

- Appiattimento dei nodi per l’output di AEM Sites: in precedenza, la struttura dei nodi del sito dell’output di AEM Sites era troppo profonda. Ora puoi appiattire la struttura dei nodi per ottenere prestazioni migliori.
- Supporto per la versione più recente di FrameMaker Publishing Server dell’estate 2020.
- I file temporanei generati durante la traduzione vengono ora rimossi, il che migliora il processo di traduzione.

#### Altri miglioramenti

- La dipendenza del flusso di lavoro Risorsa di aggiornamento DAM durante la post-elaborazione del contenuto DITA è stata rimossa. Se sono presenti passaggi di processo personalizzati definiti nel flusso di lavoro Risorsa di aggiornamento DAM, devi aggiornarli per eseguirli al termine della post-elaborazione.
- L’iniziatore del processo di traduzione ora riceve una notifica nella casella in entrata quando il processo di traduzione viene creato correttamente.

### Correzioni di bug

I bug risolti nella versione 3.8 sono elencati di seguito:

- Gli oggetti audio non vengono visualizzati nell&#39;output di HTML.
- La finestra Forza eliminazione visualizzata all&#39;eliminazione di un argomento DITA mostra più pulsanti &#39;Forza eliminazione&#39;.
- Il trasferimento della baseline alle copie per lingua non funziona per la baseline creata utilizzando la vista lato server.
- A volte, la versione 3.0 di un argomento viene visualizzata come 3 nella visualizzazione affiancata, non consentendo l’importazione di commenti di revisione.
- Lento caricamento dei dettagli del contenuto di riferimento nella scheda Baseline per la mappa DITA spostata.
- Il ripristino di una versione precedente non funziona per le risorse non dita.
- Vengono creati molti nodi di _testo vuoti con la generazione dell’output di AEM Sites.
- Editor XML - Risoluzione dei collegamenti nelle mappe immagine dopo la generazione della pagina non funziona.
- Applica etichette dalla scheda Baseline non aggiunge etichette al contenuto di riferimento, come le immagini.
- I file SVG vengono scaricati in formato non corretto tramite l’opzione Download Map (Scarica mappa).
- Impossibile modificare il frammento di contenuto in una vista a elenco.
- Impossibile estrarre e aprire i file in Oxygen XML Author utilizzando il connettore.
- Il testo dell&#39;elemento `<alt>` non è visibile nella visualizzazione di creazione.
- La risorsa immagine viene sempre visualizzata come Non aggiornato anche se è presente una copia tradotta.
- Il titolo del modello di mappa personalizzato non è corretto e la miniatura non viene visualizzata.
- Gli elementi dei marchi applicati non vengono visualizzati nella visualizzazione per l’authoring dell’editor web.
- Le note a piè di pagina collegate non sono visibili nel contenuto.
- La codifica dei colori nell&#39;Editor Web non funziona con attributi condizionali specializzati.
- L’elenco a discesa di @keyref non è semplice da usare e può essere considerato quasi inutilizzabile dai clienti con un numero elevato di @keyref.
- Il testo della variabile a cui fa riferimento il @keyref non viene renderizzato.
- Connettore ossigeno || Il pulsante &quot;Modifica in ossigeno&quot; ora apre il file in modalità di modifica anche se il file non è estratto.
- I predefiniti di output personalizzati non vengono creati con un modello di mappa personalizzato.
- La conversione da Microsoft Word (.docx) a DITA non crea un nodo jcr:content e consente l&#39;utilizzo di caratteri speciali per i nomi delle cartelle.
- Una volta spostata una MAPPA (con più di 150 riferimenti), i riferimenti si interrompono e si verificano errori durante l&#39;apertura degli argomenti.
- La risoluzione di un&#39;immagine non viene calcolata correttamente quando si modifica la larghezza dell&#39;immagine.
- Quando un&#39;immagine viene aggiunta in un `<codeblock>`, nell&#39;output del sito AEM vengono trovati spazi vuoti indesiderati.

