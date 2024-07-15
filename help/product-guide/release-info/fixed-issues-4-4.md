---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides versione 4.4.0
description: Scopri le correzioni di bug nella versione 4.4.0 di Adobe Experience Manager Guides
role: Leader
exl-id: ff3083d3-062b-4a79-875f-86991978a18e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 0%

---

# Sono stati risolti i problemi nella versione 4.4.0 di (gennaio 2024)


Questo articolo descrive i bug corretti in varie aree della versione 4.4.0 di Adobe Experience Manager Guides.

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizzare [Novità della versione 4.4.0](./whats-new-4-4.md).

Scopri le [istruzioni di aggiornamento per la versione 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Authoring

- Il controllo ortografico nell’editor non consente la selezione di suggerimenti. (15045)
- Il pulsante di navigazione globale non funziona e il dashboard non viene caricato. (14968)
- Nell’editor web, la funzione di download mappa non attiva una notifica pop-up quando è pronto per il download. (14626)
- Nell&#39;editor Web, la funzionalità di download mappa non consente di scaricare una mappa con linea di base. (14622)
- Errore DTD non valido in Experience Manager Guides. (14482)
- Il titolo nella scheda Editor Web viene troncato dopo un punto (.) aggiuntivo. (14372)
- La messaggistica degli errori per i nomi di mappe duplicati nell’interfaccia utente di Assets non viene aggiornata. (14320)
- Si verifica un errore nella logica di creazione della versione durante il trascinamento della selezione delle risorse. (14291)
- Il contenuto riutilizzabile ignora gli ID degli elementi. (14213)
- Manca il controllo impostazione per nascondere il pannello **Variabili di lingua** nella scheda **Output**. (14194)
- L&#39;editor Web genera errori di applicazione quando si aggiunge un nuovo riferimento o argomento utilizzando uno schema specializzato nella visualizzazione **Layout**. (14094)
- Lo spazio dopo l&#39;elemento conref `<ph>` scompare quando si salva l&#39;argomento. (13642)
- Si verifica un errore dell&#39;applicazione quando si tenta di salvare i file DITA prima del completamento della post-elaborazione. (13571)
- Un collegamento di ancoraggio a un elemento `<dlentry>` o `<dt>` non riesce a visualizzare il testo del collegamento. (13543)
- Impossibile caricare la raccolta **Preferiti** nell&#39;editor Web. (13495)
- Se il titolo di un argomento contiene una barra `/`, nella scheda dell&#39;editor Web verranno visualizzate solo le lettere successive. (13455)
- L’anteprima dell’immagine non scompare dopo averla visualizzata nell’editor web. (13454)
- Le citazioni visualizzano collegamenti non cliccabili quando vengono create con un ID univoco con spazi. (13447)
- Quando si chiude un argomento dopo averlo modificato, si viene reindirizzati alla home page dell&#39;AEM invece di tornare alla visualizzazione cartella. (13306)
- La finestra a comparsa Inserisci parola chiave non viene visualizzata quando si utilizzano i tasti definiti dalla mappa principale in altri argomenti. (12950)
- Le icone di chiusura non sono visibili quando le immagini molto alte vengono visualizzate in anteprima nel pannello **Cronologia versioni**. (12867)
- Impossibile modificare il fuso orario della colonna **Versione creata il** per le linee di base. (12711)
- I file ZIP non vengono riconosciuti nell&#39;editor Web e non è possibile trascinarli. (12709)
- Il pannello **Cronologia versioni** nell&#39;interfaccia utente di Assets mostra una marca temporale non corretta per il campo **Corrente**. (12624)
- Nella visualizzazione **Layout** per una mappa di Segnalibro, utilizzando **Sposta a destra** per rendere non valido un sottoelemento per un capitolo selezionato. (12567)
- La creazione di un file DITA da un modello con un nome file che inizia con caratteri numerici genera un errore relativo allo spazio dei nomi. (12188)
- L&#39;impostazione della rootmap viene mantenuta nell&#39;editor Web anche se l&#39;utente non l&#39;ha impostata esplicitamente dalle **preferenze utente**. (11551)
- Il contenuto con alcuni attributi applicati non viene evidenziato nella modalità **Autore** o **Anteprima**. (11063)
- Nell&#39;editor Web viene visualizzata la finestra **Riferimenti chiave** quando si inserisce il tag `varname`. (10940)
- Trascinare un argomento del glossario dal repository in una mappa del glossario crea `topicref`. (10767)
- La finestra Anteprima dell&#39;editor XML viene troncata nei browser Google Chrome e Microsoft Edge. (10755)
- Nell’editor web non è possibile racchiudere un elemento all’interno dei possibili elementi principali. (8791)
- L’editor web viene disinstallato dopo la reinstallazione di Adobe Experience Manager Guides versione 4.3.1. (14519)
- Il programma di installazione della versione 4.3.1 rileva un conflitto di filtri che provoca l&#39;override di `apps/cq/core/content/projects/properties`. (14517)
- Nell&#39;elenco di **collegamenti interrotti** nei report viene visualizzato un collegamento di riferimento autonomo. (13539)
- La schermata di anteprima dei frammenti è bloccata. (14840)
- I caratteri interrotti vengono visualizzati durante la creazione dei frammenti in coreano. (13489)

## Pubblicazione

- La pubblicazione di AEM Sites non riesce e causa errori di ambito per i file con `xref` nel file DITA che iniziano con &quot;HTTP&quot;. (15154)
- Nella pubblicazione nativa di PDF non è possibile utilizzare le proprietà dei metadati delle mappe DITA per popolare i metadati per l&#39;output di file PDF. (15159)
- Nella pubblicazione di PDF nativi, gli attributi personalizzati nei predefiniti di condizione non funzionano per la pubblicazione di PDF nativi. (14943)
- Impossibile aggiungere un modello personalizzato dalla scheda **Output** nell&#39;editor. (14846)
- Il predefinito per il sito **AEM** non funziona a causa di un percorso modello vuoto. (14804)
- La rigenerazione del sito AEM non riesce per le mappe DITA con argomenti che contengono equazioni MathML. (14790)
- Nella pubblicazione nativa di PDF, la generazione di PDF genera errori nell&#39;ottenere dipendenze per la pubblicazione di `Node.js`. (14445)
- Il predefinito **Sito AEM** non consente la selezione di un modello esterno alla gerarchia `/content` nell&#39;editor Web. (14260)
- La funzionalità di pubblicazione come frammento di contenuto non funziona per i file elencati nei risultati di ricerca. (14090)
- I componenti Fmdita hanno un percorso hardcoded di `delegator.jsp`, che impedisce la sovrapposizione dei componenti AEM Sites. (13993)
- La visualizzazione con tag del reattore PDF nell’output di pubblicazione nativa di PDF non funziona come previsto. (13622)
- Nella pubblicazione di PDF nativi, la selezione del colore di sfondo nel layout **Modello** richiede il ricaricamento della pagina quando si torna a `None`. (13621)
- La pubblicazione di siti AEM rileva un problema quando si esegue il commit nell’archivio dati per mappe di grandi dimensioni con collegamenti tra pari dell’ambito. (13531)
- Si verifica un problema durante il commit nell’archivio dati per una mappa DITA di grandi dimensioni con collegamenti peer per l’ambito nella pubblicazione di siti AEM. (13530)
- Nella barra degli strumenti **Layout di pagina** dei modelli utilizzati nella pubblicazione di PDF nativi vengono visualizzate icone e descrizioni comandi errate per l&#39;opzione **Modifica contenuto**. (13492)
- Impossibile attivare un sito con Experience Manager Guides **Bulk Publish Dashboard**. (13439)
- Nella pubblicazione di PDF nativi, l’accessibilità è compromessa in quanto le immagini nell’intestazione e nel piè di pagina non visualizzano testo alternativo. (12829)
- Nell&#39;output di AEM Sites, lo stile o le interruzioni di riga sono stati persi per l&#39;elemento `<lines>` con elementi secondari.(12542)
- La duplicazione del layout di pagina in Native PDF non funziona con nessuna estensione aggiunta automaticamente. (12534)
- La localizzazione delle etichette degli elementi non funziona correttamente nell’output di AEM Sites. (12144)
- I metadati personalizzati non sono disponibili nell’output finale. (12116)
- `fmdita rewriter` è in conflitto con la configurazione del rewriter dell&#39;utente e comporta la visualizzazione di URL lunghi invece dei collegamenti. (12076)
- Opzione **ditaval** mancante nei predefiniti di output a livello di profilo della cartella creati tramite l&#39;interfaccia utente dell&#39;editor Web. (11903)
- Nel predefinito **Sito AEM**, l&#39;opzione per **Generare PDF separati per ogni argomento** non è funzionale. (11555)
- La pubblicazione PDF nativa non supporta la conversione dello spazio colore CMYK. (10754)
- Quando si esegue l’aggiornamento alla versione 4.3.1, si verificano alcune eccezioni nel nodo PDF nativo. (14492)
- Quando si genera l’output di PDF con la pubblicazione di PDF nativi, il nome del file viene troncato dopo un punto. (13620)


## Gestione

- Il riferimento al contenuto viene interrotto quando si copiano e incollano i file DITA con collegamenti di riferimento automatico senza GUID. (13540)
- **I file del filtro della linea di base** non funzionano con il nome file nell&#39;editor Web. (13486)
- Nell&#39;editor Web, la baseline mostra il titolo della versione precedente anziché della versione selezionata del file DITA. (13444)
- La disattivazione dell&#39;indicizzazione della mappa DITA padre per ottenere prestazioni migliori può influire sulle funzionalità di alcune funzionalità.(12213)
- Non vengono creati predefiniti di condizione per mappe DITA di grandi dimensioni. (10936)
- Impossibile modificare i predefiniti per le prime mappe della raccolta durante la modifica di una raccolta di mappe. (10649)
- Le etichette del file `labels.json` vengono visualizzate in ordine casuale nell&#39;editor Web. (10508)
- Le chiamate della linea di base dinamica utilizzano il nome invece del titolo, il che si traduce in un errore di esportazione dell’API mappa DITA. (14268)

## Rivedi

- Il menu di scelta rapida visualizzato facendo clic con il pulsante destro del mouse non funziona per **Accept** o **Reject** track changes. (14607)
- Nella versione 4.3.1 di Adobe Experience Manager Guides, attivare o disattivare la chiusura degli argomenti DITA nella schermata di revisione. (14537)
- I problemi di simmetria si verificano nei pannelli di revisione affiancata delle versioni precedenti e correnti nell&#39;editor Web. (14156)
- La personalizzazione dei modelli e-mail per il flusso di lavoro di revisione non funziona con la sovrapposizione. (13954)
- Gli allegati coreani nella schermata Experience Manager Guides Review non sono selezionabili. (13436)
- Il titolo della mappa viene tagliato nella schermata di revisione e collaborazione, senza opzione per visualizzare il titolo completo. (13012)

## Traduzione

- I pulsanti **Accetta/Rifiuta** non vengono visualizzati correttamente per la traduzione umana approvata automaticamente. (14318)
- I problemi di internazionalizzazione (i18n) si verificano durante la trasformazione di file DITA non inglesi in pagine AEM. (14286)
- L&#39;approvazione automatica a volte non funziona e si verificano eccezioni se in **Stato traduzione** è impostato un valore non corretto. (13607)
- La linea di base esportata dal dashboard di traduzione non riesce e non si apre nella lingua di destinazione. (12993)
- I contenuti tradotti non possono essere sincronizzati da progetti di traduzione temporanei e la traduzione guidata dell&#39;editor XML DITA mostra erroneamente lo stato **In corso** per i processi approvati. (9938)

## Problema noto

L’Adobe ha identificato il seguente problema noto per la versione 4.4.0:

- La versione 1.0 non viene visualizzata nell&#39;interfaccia utente del file DITA duplicato.
