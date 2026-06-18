---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides versione 4.4.0
description: Scopri le correzioni di bug nella versione 4.4.0 di Adobe Experience Manager Guides
role: Leader
exl-id: ff3083d3-062b-4a79-875f-86991978a18e
TQID: https://experienceleague.adobe.com/0mdTs2Pg1Zos-Y-jMaYUEasFRhyF2kzl6Sz8MBisJ5Q
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d6596f3f-92a7-43ec-b444-237db6adad05id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 1421
ht-degree: 6%

---

# Sono stati risolti i problemi nella versione 4.4.0 di (gennaio 2024)


Questo articolo descrive i bug corretti in varie aree della versione 4.4.0 di Adobe Experience Manager Guides.

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizzare [Novità della versione 4.4.0](./whats-new-4-4.md).

Scopri le [istruzioni di aggiornamento per la versione 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Authoring

- Il controllo ortografico nell’editor non consente la selezione di suggerimenti. (15045)
- Il pulsante di navigazione globale non funziona e il dashboard non viene caricato. (14968)
- Nell’editor, la funzione di download mappa non attiva una notifica pop-up quando è pronto per il download. (14626)
- Nell’editor, la funzione di download della mappa non riesce a scaricare una mappa con la linea di base. (14622)
- Errore DTD non valido in Experience Manager Guides. (14482)
- Il titolo nella scheda Editor viene troncato dopo un punto (.) carattere. (14372)
- La messaggistica degli errori per i nomi di mappe duplicati nell’interfaccia utente di Assets non viene aggiornata. (14320)
- Si verifica un errore nella logica di creazione della versione durante il trascinamento della selezione delle risorse. (14291)
- Il contenuto riutilizzabile ignora gli ID degli elementi. (14213)
- Manca il controllo impostazione per nascondere il pannello **Variabili di lingua** nella scheda **Output**. (14194)
- L&#39;editor genera errori di applicazione quando si aggiunge un nuovo riferimento o argomento utilizzando uno schema specializzato nella visualizzazione **Layout**. (14094)
- Lo spazio dopo l&#39;elemento conref `<ph>` scompare quando si salva l&#39;argomento. (13642)
- Si verifica un errore dell&#39;applicazione quando si tenta di salvare i file DITA prima del completamento della post-elaborazione. (13571)
- Un collegamento di ancoraggio a un elemento `<dlentry>` o `<dt>` non riesce a visualizzare il testo del collegamento. (13543)
- Impossibile caricare la raccolta **Preferiti** nell&#39;editor. (13495)
- Se il titolo di un argomento contiene una barra `/`, nella scheda dell&#39;editor verranno visualizzate solo le lettere successive. (13455)
- L&#39;anteprima dell&#39;immagine non scompare dopo averla visualizzata nell&#39;editor. (13454)
- Le citazioni visualizzano collegamenti non cliccabili quando vengono create con un ID univoco con spazi. (13447)
- Quando si chiude un argomento dopo averlo modificato, si viene reindirizzati alla home page di AEM invece di tornare alla vista cartelle. (13306)
- La finestra a comparsa Inserisci parola chiave non viene visualizzata quando si utilizzano i tasti definiti dalla mappa principale in altri argomenti. (12950)
- Le icone di chiusura non sono visibili quando le immagini molto alte vengono visualizzate in anteprima nel pannello **Cronologia versioni**. (12867)
- Impossibile modificare il fuso orario della colonna **Versione creata il** per le linee di base. (12711)
- I file ZIP non vengono riconosciuti nell&#39;editor e non è possibile trascinarli. (12709)
- Il pannello **Cronologia versioni** nell&#39;interfaccia utente di Assets mostra una marca temporale non corretta per il campo **Corrente**. (12624)
- Nella visualizzazione **Layout** per una mappa di Segnalibro, utilizzando **Sposta a destra** per rendere non valido un sottoelemento per un capitolo selezionato. (12567)
- La creazione di un file DITA da un modello con un nome file che inizia con caratteri numerici genera un errore relativo allo spazio dei nomi. (12188)
- L&#39;impostazione della rootmap viene mantenuta nell&#39;editor anche se l&#39;utente non l&#39;ha impostata esplicitamente dalle **preferenze utente**. (11551)
- Il contenuto con alcuni attributi applicati non viene evidenziato nella modalità **Autore** o **Anteprima**. (11063)
- Nell&#39;editor verrà visualizzata la finestra **Riferimenti chiave** quando si inserisce il tag `varname`. (10940)
- Trascinare un argomento del glossario dal repository in una mappa del glossario crea `topicref`. (10767)
- La finestra Anteprima dell&#39;editor XML viene troncata nei browser Google Chrome e Microsoft Edge. (10755)
- L’editor non è in grado di racchiudere un elemento all’interno dei possibili elementi principali. (8791)
- L’editor viene disinstallato dopo la reinstallazione di Adobe Experience Manager Guides versione 4.3.1. (14519)
- Il programma di installazione della versione 4.3.1 rileva un conflitto di filtri che provoca l&#39;override di `apps/cq/core/content/projects/properties`. (14517)
- Nell&#39;elenco di **collegamenti interrotti** nei report viene visualizzato un collegamento di riferimento autonomo. (13539)
- La schermata di anteprima dei frammenti è bloccata. (14840)
- I caratteri interrotti vengono visualizzati durante la creazione dei frammenti in coreano. (13489)

## Pubblicazione

- La pubblicazione di AEM Sites non riesce e causa errori di ambito per i file con `xref` nel file DITA che iniziano con &quot;HTTP&quot;. (15154)
- Nella pubblicazione nativa di PDF non è possibile utilizzare le proprietà dei metadati delle mappe DITA per popolare i metadati per l&#39;output di file PDF. (15159)
- Nella pubblicazione nativa in PDF, gli attributi personalizzati nei predefiniti per le condizioni non funzionano per la pubblicazione nativa in PDF. (14943)
- Impossibile aggiungere un modello personalizzato dalla scheda **Output** nell&#39;editor. (14846)
- Il predefinito per **Sito AEM** non funziona a causa di un percorso di modello vuoto. (14804)
- La rigenerazione del sito AEM ha esito negativo per le mappe DITA con argomenti che contengono equazioni di MathML. (14790)
- Nella pubblicazione nativa di PDF, la generazione di PDF genera errori nell&#39;ottenere le dipendenze per la pubblicazione di `Node.js`. (14445)
- Il predefinito **Sito AEM** non consente la selezione di un modello esterno alla gerarchia `/content` nell&#39;editor. (14260)
- La funzionalità di pubblicazione come frammento di contenuto non funziona per i file elencati nei risultati di ricerca. (14090)
- I componenti Fmdita hanno un percorso hardcoded di `delegator.jsp`, che impedisce la sovrapposizione dei componenti AEM Sites. (13993)
- La visualizzazione con tag del reattore PDF nell’output di pubblicazione nativo di PDF non funziona come previsto. (13622)
- Nella pubblicazione nativa in PDF, la selezione del colore di sfondo nel layout **Modello** richiede il ricaricamento della pagina quando si torna a `None`. (13621)
- La pubblicazione di siti AEM rileva un problema quando si esegue il commit nell’archivio dati per mappe di grandi dimensioni con collegamenti peer di ambito. (13531)
- Si verifica un problema durante il commit nell’archivio dati per una mappa DITA di grandi dimensioni con collegamenti peer per l’ambito nella pubblicazione di siti AEM. (13530)
- Nella barra degli strumenti **Layout di pagina** della funzionalità Modelli utilizzata nella pubblicazione nativa di PDF vengono visualizzate icone e descrizioni comandi errate per l&#39;opzione **Modifica contenuto**. (13492)
- Impossibile attivare un sito con Experience Manager Guides **Bulk Publish Dashboard**. (13439)
- Nella pubblicazione nativa in PDF, l’accessibilità è compromessa in quanto le immagini nell’intestazione e nel piè di pagina non visualizzano testo alternativo. (12829)
- Nell&#39;output di AEM Sites, lo stile o le interruzioni di riga sono stati persi per l&#39;elemento `<lines>` con sottoelementi.(12542)
- La duplicazione del layout di pagina in PDF nativo non funziona con nessuna estensione aggiunta automaticamente. (12534)
- La localizzazione delle etichette degli elementi non funziona correttamente nell’output di AEM Sites. (12144)
- I metadati personalizzati non sono disponibili nell’output finale. (12116)
- `fmdita rewriter` è in conflitto con la configurazione del rewriter dell&#39;utente e comporta la visualizzazione di URL lunghi invece dei collegamenti. (12076)
- Opzione **ditaval** mancante nei predefiniti di output a livello di profilo della cartella creati tramite l&#39;interfaccia utente dell&#39;editor. (11903)
- Nel predefinito **Sito AEM**, l&#39;opzione **Genera PDF separato per ogni argomento** non funziona. (11555)
- La pubblicazione nativa su PDF non supporta la conversione dello spazio colore CMYK. (10754)
- Durante l’aggiornamento alla versione 4.3.1, si verificano alcune eccezioni nel nodo PDF nativo. (14492)
- Quando si genera l’output di PDF con la pubblicazione PDF nativa, il nome del file viene troncato dopo un punto. (13620)


## Gestione

- Il riferimento al contenuto viene interrotto quando si copiano e incollano i file DITA con collegamenti di riferimento automatico senza GUID. (13540)
- **I file del filtro della linea di base** non funzionano con il nome file nell&#39;editor. (13486)
- Nell&#39;editor, la linea di base mostra il titolo della versione precedente invece della versione selezionata del file DITA. (13444)
- La disattivazione dell&#39;indicizzazione della mappa DITA padre per ottenere prestazioni migliori può influire sulle funzionalità di alcune funzionalità.(12213)
- Non vengono creati predefiniti di condizione per mappe DITA di grandi dimensioni. (10936)
- Impossibile modificare i predefiniti per le prime mappe della raccolta durante la modifica di una raccolta di mappe. (10649)
- Le etichette del file `labels.json` vengono visualizzate in ordine casuale nell&#39;editor. (10508)
- Le chiamate della linea di base dinamica utilizzano il nome invece del titolo, il che si traduce in un errore di esportazione dell’API mappa DITA. (14268)

## Rivedere

- Il menu di scelta rapida visualizzato facendo clic con il pulsante destro del mouse non funziona per **Accept** o **Reject** track changes. (14607)
- Nella versione 4.3.1 di Adobe Experience Manager Guides, attivare o disattivare la chiusura degli argomenti DITA nella schermata di revisione. (14537)
- I problemi di simmetria si verificano nei pannelli di revisione affiancata delle versioni precedenti e correnti nell’editor. (14156)
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

Adobe ha identificato il seguente problema noto per la versione 4.4.0:

- La versione 1.0 non viene visualizzata nell&#39;interfaccia utente del file DITA duplicato.
