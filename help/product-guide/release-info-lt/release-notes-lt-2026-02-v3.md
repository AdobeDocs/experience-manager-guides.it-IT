---
title: Note sulla versione | Novità della versione di febbraio 2026 dei contenuti di formazione e apprendimento sui prodotti
description: Scopri le funzioni nuove e migliorate nella versione di febbraio 2026 dei contenuti di formazione e apprendimento del prodotto
role: Leader
hidefromtoc: true
source-git-commit: 16e7f12ddc9e72e4344bf98e65718c0f3681b348
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 0%

---

# Versione di febbraio 2026 dei contenuti di formazione e apprendimento del prodotto

Questa nota sulla versione tratta i nuovi miglioramenti funzionali e i problemi risolti nella versione di febbraio 2026 dei contenuti di formazione e apprendimento del prodotto.

## Nuovi miglioramenti delle funzioni

Nella versione di febbraio 2026 dei contenuti di formazione e apprendimento sul prodotto sono state introdotte le seguenti funzioni:

- **Supporto per i sottotitoli**: ora puoi aggiungere sottotitoli al contenuto di apprendimento utilizzando la nuova opzione **Aggiungi sottotitoli** in **Proprietà file**. Ciò migliora la chiarezza e la facilità di ricerca nel contenuto del corso.

  Per ulteriori dettagli, visualizza [Aggiungi titolo e sottotitolo al contenuto di apprendimento](../learning-content/lc-basic-blocks.md#add-title-and-subtitle-to-learning-content).

  ![](assets/add-subtitles.png)

- **Attiva o disattiva il punteggio negativo finale**: durante la configurazione delle proprietà del quiz, è possibile controllare il punteggio negativo utilizzando l&#39;opzione **Consenti punteggio finale negativo**. Quando abilitati, gli Allievi ricevono un punteggio finale minimo pari a zero, anche se viene applicato il contrassegno negativo. In questo modo gli Allievi sono motivati dal fatto di non far mai scendere i punteggi sotto zero.

  Ulteriori informazioni sulle [proprietà quiz](../learning-content/quiz-properties.md).

  ![](assets/negative-scores-lc.png)

- **Elimina widget facendo clic con il pulsante destro del mouse**: oltre a eliminare le domande dei quiz, ora è possibile eliminare widget quali Accordions, Flip cards e altri widget con **Clic con il pulsante destro del mouse > Elimina elemento**. Questo miglioramento estende la funzionalità esistente *Elimina domanda* ai widget, consentendoti di rimuoverli con meno clic e una navigazione minima.

  Ulteriori informazioni su [Utilizzare widget interattivi](../learning-content/lc-widgets.md).

  ![](assets/delete-widget-items.png)
- **Aggiungi scelte di risposta**: è ora possibile fissare scelte di risposta specifiche in modo che la loro posizione rimanga invariata, anche quando le risposte sono randomizzate durante la generazione dell&#39;output SCORM. Questo è particolarmente utile per opzioni come *Tutte le precedenti* o *Nessuna delle precedenti*.

  Ulteriori informazioni sulle [proprietà domanda](../learning-content/quiz-insert-questions.md#question-properties).

  ![](assets/pin-question.png)
- **Tipo di risposta breve**: il tipo di domanda Risposta breve consente agli Allievi di rispondere utilizzando risposte alfanumeriche brevi e descrittive anziché selezionare opzioni predefinite. Questo tipo di domanda incoraggia i discenti a ricordare e articolare attivamente la loro comprensione nelle proprie parole, rendendo le valutazioni più coinvolgenti per i discenti.

  Ulteriori informazioni sui [tipi di domanda](../learning-content/quiz-insert-questions.md#question-types).


  ![](assets/short-answer.png)
- **Tentativo sequenziale per domande quiz**: è ora possibile applicare i tentativi di quiz sequenziali per l&#39;output SCORM utilizzando l&#39;opzione **Gli Allievi devono tentare ogni domanda per procedere** nel predefinito di output SCORM. Quando questa opzione è abilitata, gli Allievi devono rispondere a ciascuna domanda prima di passare a quella successiva, con una navigazione limitata fino al completamento della domanda corrente. In questo modo si garantisce un flusso di valutazione guidato, passo dopo passo e un’esperienza di apprendimento coerente.

  Per ulteriori dettagli, visualizzare [Configurare il predefinito di output SCORM](../learning-content/config-scorm-preset.md).

  ![](assets/scorm-general-tab-v3.png)

## Problemi risolti

Nella versione di febbraio 2026 dei contenuti di formazione e apprendimento sul prodotto sono stati risolti i seguenti problemi:

- Quando si pubblica l’output SCORM e lo si distribuisce in ALM, il rapporto Quiz L2 mostra punteggi totali e massimi non corretti per i quiz che utilizzano più tentativi e una selezione casuale della banca delle domande. (GUIDES-38855)
- Quando viene generato un corso sul server cloud, sotto il piè di pagina del copyright viene visualizzato uno spazio vuoto non desiderato a causa del foglio di stile `coralui3.css`, causando incoerenza del layout. (GUIDES-38853)
- Quando si accede al corso di apprendimento con un pannello a soffietto utilizzando la tastiera, il segno + o il titolo della scheda non vengono evidenziati, impedendo l’identificazione visiva dell’elemento attivo. (GUIDES-38852)
- Per i corsi generati utilizzando il modello di carbone SCORM o il modello predefinito, quando si accede a un dispositivo mobile in modalità orizzontale, il sommario (menu Corsi) non visualizza i collegamenti del modulo che impediscono la navigazione. (GUIDES-38851)
- Durante la replica della gerarchia per un corso in Experience Manager Guides, la creazione di un oggetto di apprendimento richiede innanzitutto la creazione di un gruppo di apprendimento, in quanto non sono supportate aggiunte a livello di oggetto. (GUIDES-38849)
- Tenta di accedere alle opzioni dell’elenco a discesa in Corrispondenza con il seguente tipo di domanda utilizzando la tastiera non riesce in quanto le opzioni non rispondono al tasto TAB o freccia che impedisce la navigazione. (GUIDES-38985)
- Se si applica un predefinito per lo stile di titolo, il testo selezionato scompare, probabilmente a causa del colore del carattere che diventa bianco, rendendo il testo non selezionabile e non visibile. (GUIDES-39981)
- Quando si utilizza Experience Manager Guides su Mozilla Firefox, la scheda Flip mostra il testo lato anteriore in senso inverso sul lato posteriore dopo aver riflesso. (GUIDES-39983)
- Quando fai clic sul sommario nel riquadro a sinistra del corso, il corso continua a mostrare lo stato di completamento anche se il quiz non è stato superato. (GUIDES-40398)
- Se si tenta di trovare in ALM una corrispondenza errata con il tipo di domanda seguente in un quiz, le opzioni selezionate non vengono visualizzate nel rapporto. (GUIDES-38640)
- Durante la generazione dell’output di PDF, gli stili di authoring applicati non vengono mantenuti, generando incoerenze nella progettazione. (GUIDES-38642)

