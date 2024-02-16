---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides versione 4.4.0
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione 4.4.0 delle guide di Adobe Experience Manager
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1808'
ht-degree: 0%

---

# Versione 4.4.0 delle guide di Adobe Experience Manager (febbraio 2024)

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione 4.4.0 delle Guide di Adobe Experience Manager (in seguito denominate *Guide Experience Manager*).

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 4.4.0 delle guide di Adobe Experience Manager](./whats-new-4-4.md).

## Aggiornamento alla versione 4.4.0 delle guide di Experience Manager


È possibile aggiornare facilmente la versione corrente delle Guide alla versione 4.4.0. Prima di procedere con l&#39;aggiornamento alla versione 4.4.0 di Experience Manager Guides, è necessario considerare i seguenti punti:


- Se utilizzi le versioni 4.3.1, 4.3.0 o 4.2.1 (Hotfix 4.2.1.3), puoi eseguire direttamente l’aggiornamento alla versione 4.4.0.
- Se utilizzi le versioni 4.2, 4.1 o 4.1.x, devi effettuare l’aggiornamento alla versione 4.3.1, 4.3.0 o 4.2.1 (Hotfix 4.2.1.3) prima di eseguire l’aggiornamento alla versione 4.4.0.
- Se utilizzi la versione 4.0, devi effettuare l’aggiornamento alla versione 4.2 prima di passare alla versione 4.3.x.
- Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
- Se utilizzi una versione precedente alla 3.8.5, consulta la sezione Guide per l’aggiornamento degli Experienci Manager nella guida all’installazione specifica per il prodotto.



>[!NOTE]
>
>È necessario installare il service pack per l’AEM prima di aggiornare la versione delle guide Experienci Manager.

Per ulteriori informazioni, consulta [Istruzioni per l’aggiornamento](../install-guide/upgrade-xml-documentation.md).

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate dalla versione 4.4.0 delle Guide di Experience Manager.

### Adobe Experience Manager

**4.4.0 Non UUID**
Versione 6.5 Service Pack 19, 18, 17

**4.4.0 UUID**
Versione 6.5 Service Pack 19, 18, 17

Per ulteriori dettagli, vedi *Requisiti tecnici* nella guida Installare e configurare Adobe Experience Manager Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.4.0 (non UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.3 o versione successiva |
| 4.4.0 (UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.4 o versione successiva |
| | | | |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.4.0 (non UUID) | 2,7-regular-1 | 2,7-regular-1 | 1,6 | 1,6 |
| 4.4.0 (UUID) | 3,4-uuid-1 | 3,4-uuid-1 | 2,3 | 2,3 |
|  |  |   |



### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti dei componenti Experience Manager Guides per il Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Il controllo ortografico nell’editor non consente la selezione di suggerimenti. (15045)
- Il pulsante di navigazione globale non funziona e il dashboard non viene caricato. (14968)
- Nell’editor web, la funzione di download mappa non attiva una notifica pop-up quando è pronto per il download. (14626)
- Nell&#39;editor Web, la funzionalità di download mappa non consente di scaricare una mappa con linea di base. (14622)
- Errore DTD non valido nelle guide Experience Manager. (14482)
- Il titolo nella scheda Editor Web viene troncato dopo un punto (.) aggiuntivo. (14372)
- La messaggistica degli errori per i nomi di mappe duplicati nell’interfaccia utente Assets non viene aggiornata. (14320)
- Si verifica un errore nella logica di creazione della versione durante il trascinamento della selezione delle risorse. (14291)
- Il contenuto riutilizzabile ignora gli ID degli elementi. (14213)
- Controllo impostazione da nascondere **Variabili di lingua** pannello in **Output** scheda mancante. (14194)
- L’editor web genera errori di applicazione quando si aggiunge un nuovo riferimento o argomento utilizzando uno schema specializzato in **Layout** visualizzazione. (14094)
- Spazio dopo la conversione `<ph>` scompare quando si salva l&#39;argomento. (13642)
- Si verifica un errore dell&#39;applicazione quando si tenta di salvare i file DITA prima del completamento della post-elaborazione. (13571)
- Un collegamento di ancoraggio a `<dlentry>` o `<dt>` L&#39;elemento non riesce a visualizzare il testo del collegamento. (13543)
- Il **Preferiti** Impossibile caricare la raccolta nell&#39;editor Web. (13495)
- Se il titolo di un argomento contiene una barra `/`, nella scheda dell’Editor web vengono visualizzate solo le lettere che le seguono. (13455)
- L’anteprima dell’immagine non scompare dopo averla visualizzata nell’editor web. (13454)
- Le citazioni visualizzano collegamenti non cliccabili quando vengono create con un ID univoco con spazi. (13447)
- Quando si chiude un argomento dopo averlo modificato, si viene reindirizzati alla home page dell&#39;AEM invece di tornare alla visualizzazione cartella. (13306)
- La finestra a comparsa Inserisci parola chiave non viene visualizzata quando si utilizzano i tasti definiti dalla mappa principale in altri argomenti. (12950)
- Le icone di chiusura non sono visibili quando nella **Cronologia versioni** pannello. (12867)
- Impossibile modificare il fuso orario di **Versione creata il** per le baseline. (12711)
- I file ZIP non vengono riconosciuti nell&#39;editor Web e non è possibile trascinarli. (12709)
- Il **Cronologia versioni** Nell’interfaccia utente Assets, il pannello mostra una marca temporale errata per **Corrente** campo. (12624)
- In **Layout** visualizzare una mappa di registro, utilizzando **Sposta a Destra** per rendere un capitolo selezionato un sottoelemento non funziona. (12567)
- La creazione di un file DITA da un modello con un nome file che inizia con caratteri numerici genera un errore relativo allo spazio dei nomi. (12188)
- L’impostazione della rootmap viene mantenuta nell’editor web anche se l’utente non l’ha impostata esplicitamente da **Preferenze utente**. (11551)
- Il contenuto con alcuni attributi applicati non viene evidenziato in **Autore** o **Anteprima** modalità. (11063)
- Nell&#39;editor Web, il **Riferimenti chiave** viene visualizzata una finestra quando si inserisce `varname` tag. (10940)
- Trascinare un argomento del glossario dal repository in una mappa del glossario crea `topicref`. (10767)
- La finestra Anteprima dell&#39;editor XML viene troncata nei browser Google Chrome e Microsoft Edge. (10755)
- Nell’editor web non è possibile racchiudere un elemento all’interno dei possibili elementi principali. (8791)
- L&#39;editor Web viene disinstallato dopo la reinstallazione di Adobe Experience Manager Guides versione 4.3.1. (14519)
- Il programma di installazione della versione 4.3.1 rileva un conflitto di filtri che determina l’esclusione di `apps/cq/core/content/projects/properties`. (14517)
- Viene visualizzato un collegamento di riferimento autonomo sotto l&#39;elenco di **Collegamenti interrotti** in Rapporti. (13539)
- La schermata di anteprima dei frammenti è bloccata. (14840)
- I caratteri interrotti vengono visualizzati durante la creazione dei frammenti in coreano. (13489)

### Pubblicazione

- La pubblicazione di AEM Sites non riesce e causa errori di ambito per i file con `xref` nel file DITA che inizia con &quot;HTTP&quot;. (15154)
- Nella pubblicazione nativa di PDF non è possibile utilizzare le proprietà dei metadati delle mappe DITA per popolare i metadati per l&#39;output di file PDF. (15159)
- Nella pubblicazione di PDF nativi, gli attributi personalizzati nei predefiniti di condizione non funzionano per la pubblicazione di PDF nativi. (14943)
- Impossibile aggiungere un modello personalizzato da **Uscite** nell&#39;editor. (14846)
- **Sito AEM** il predefinito non funziona a causa di un percorso del modello vuoto. (14804)
- La rigenerazione del sito AEM non riesce per le mappe DITA con argomenti che contengono equazioni MathML. (14790)
- Nella pubblicazione nativa di PDF, la generazione di PDF genera errori nell’ottenere dipendenze per `Node.js` pubblicazione. (14445)
- **Sito AEM** non consente la selezione di un modello all&#39;esterno del `/content` gerarchia nell&#39;editor Web. (14260)
- La funzionalità di pubblicazione come frammento di contenuto non funziona per i file elencati nei risultati di ricerca. (14090)
- I componenti Fmdita hanno un percorso hardcoded di `delegator.jsp`, evitando la sovrapposizione dei componenti di AEM Sites. (13993)
- La visualizzazione con tag del reattore PDF nell’output di pubblicazione nativa di PDF non funziona come previsto. (13622)
- Nella pubblicazione di PDF nativi, la selezione del colore di sfondo nella **Modello** il layout richiede un ricaricamento della pagina quando si ripristina `None`. (13621)
- La pubblicazione di siti AEM rileva un problema quando si esegue il commit nell’archivio dati per mappe di grandi dimensioni con collegamenti tra pari dell’ambito. (13531)
- Si verifica un problema durante il commit nell’archivio dati per una mappa DITA di grandi dimensioni con collegamenti peer per l’ambito nella pubblicazione di siti AEM. (13530)
- Icona e descrizione non corrette per  **Modifica contenuto** opzione in **Layout di pagina** della barra degli strumenti Modelli utilizzati nella pubblicazione di PDF nativi. (13492)
- Impossibile attivare un sito con Experience Manager Guides **Dashboard pubblicazione in blocco**. (13439)
- Nella pubblicazione di PDF nativi, l’accessibilità è compromessa in quanto le immagini nell’intestazione e nel piè di pagina non visualizzano testo alternativo. (12829)
- Nell’output di AEM Sites, lo stile o le interruzioni di riga venivano persi per `<lines>` elemento con sottoelementi.(12542)
- La duplicazione del layout di pagina in Native PDF non funziona con nessuna estensione aggiunta automaticamente. (12534)
- La localizzazione delle etichette degli elementi non funziona correttamente nell’output di AEM Sites. (12144)
- I metadati personalizzati non sono disponibili nell’output finale. (12116)
- `fmdita rewriter` è in conflitto con la configurazione del rewriter dell’utente e comporta la visualizzazione di URL lunghi invece dei collegamenti. (12076)
- Mancante **ditaval** opzione nei predefiniti di output a livello di profilo della cartella creati tramite l’interfaccia utente dell’editor web. (11903)
- In **Sito AEM**  predefinito, l&#39;opzione per **Genera PDF separati per ogni argomento** non è funzionale. (11555)
- La pubblicazione PDF nativa non supporta la conversione dello spazio colore CMYK. (10754)
- Quando si esegue l’aggiornamento alla versione 4.3.1, si verificano alcune eccezioni nel nodo PDF nativo. (14492)
- Quando si genera l’output di PDF con la pubblicazione di PDF nativi, il nome del file viene troncato dopo un punto. (13620)


### Gestione

- Il riferimento al contenuto viene interrotto quando si copiano e incollano i file DITA con collegamenti di riferimento automatico senza GUID. (13540)
- **Filtro linea di base** I file non funzionano con Nome file nell&#39;editor Web. (13486)
- Nell&#39;editor Web, la baseline mostra il titolo della versione precedente anziché della versione selezionata del file DITA. (13444)
- La disattivazione dell&#39;indicizzazione della mappa DITA padre per ottenere prestazioni migliori può influire sulle funzionalità di alcune funzionalità.(12213)
- Non vengono creati predefiniti di condizione per mappe DITA di grandi dimensioni. (10936)
- Impossibile modificare i predefiniti per le prime mappe della raccolta durante la modifica di una raccolta di mappe. (10649)
- Etichette da `labels.json` I file vengono visualizzati in ordine casuale nell&#39;editor Web. (10508)
- Le chiamate della linea di base dinamica utilizzano il nome invece del titolo, il che si traduce in un errore di esportazione dell’API mappa DITA. (14268)

### Rivedi

- Il menu di scelta rapida non funziona per **Accetta** o **Rifiuta** tenere traccia delle modifiche. (14607)
- Per chiudere gli argomenti DITA nella finestra Revisione, attivare o disattivare la versione 4.3.1 delle Guide di Adobe Experience Manager. (14537)
- I problemi di simmetria si verificano nei pannelli di revisione affiancata delle versioni precedenti e correnti nell&#39;editor Web. (14156)
- La personalizzazione dei modelli e-mail per il flusso di lavoro di revisione non funziona con la sovrapposizione. (13954)
- Gli allegati coreani nella schermata di revisione delle guide Experienci Manager non sono selezionabili. (13436)
- Il titolo della mappa viene tagliato nella schermata di revisione e collaborazione, senza opzione per visualizzare il titolo completo. (13012)

### Traduzione

- Il **Accetta/Rifiuta** I pulsanti vengono visualizzati erroneamente per la traduzione umana approvata automaticamente. (14318)
- I problemi di internazionalizzazione (i18n) si verificano durante la trasformazione di file DITA non inglesi in pagine AEM. (14286)
- L&#39;approvazione automatica a volte non funziona e si verificano eccezioni se su è impostato un valore errato **Stato traduzione**. (13607)
- La linea di base esportata dal dashboard di traduzione non riesce e non si apre nella lingua di destinazione. (12993)
- I contenuti tradotti non possono essere sincronizzati da progetti di traduzione temporanei e la traduzione guidata dell&#39;editor XML DITA non viene visualizzata correttamente **In corso** stato dei processi approvati. (9938)

## Problema noto

L’Adobe ha identificato il seguente problema noto per la versione 4.4.0:

- La versione 1.0 non viene visualizzata nell&#39;interfaccia utente del file DITA duplicato.