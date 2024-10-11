---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2024.10.0
description: Scopri le correzioni di bug nella versione 2024.10.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 64c5318a064d28a42f3f11d2fe5b7d8548e341d8
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 2%

---

# Sono stati risolti i problemi nella versione 2024.10.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2024.10.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2024.10.0](whats-new-2024-10-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2024.10.0](upgrade-instructions-2024-10-0.md).


## Authoring

- L&#39;opzione **Trova** non funziona nella visualizzazione **Source**. (18610)
- L&#39;elemento `<title>` viene aggiunto automaticamente quando l&#39;elemento `<fig>` viene inserito come snippet. (18562)
- La rigenerazione dell&#39;argomento non riesce a causa di un errore OOTB Regenerate Topic (Rigenera argomento OOTB) o incrementale dell&#39;API di pubblicazione. (18452)
- L’istanza di Experience Manager Guides diventa instabile e le dimensioni dei registri di errore aumentano fino a 30-40 GB dopo l’accesso all’interfaccia utente di Assets. (18414)
- **Estrai** e **Archivia** le icone vengono visualizzate insieme quando `autocheckout` è configurato in xmleditor. (18088)
- La funzione di copia e incolla delle immagini dalla vista Author non funziona nella versione 2024.06.0 di Adobe Experience Manager Guides as a Cloud Service.(18062)
- `<conref>` per un argomento a cui si fa riferimento all&#39;interno di una mappa DITA non viene riflesso nell&#39;anteprima all&#39;interno dell&#39;editor. (17794)
- Le mappe DITA di grandi dimensioni vengono caricate lentamente e richiedono tempo per passare alla visualizzazione **Layout**. (17590)
- La versione DITA visualizza erroneamente il nome utente nell&#39;interfaccia utente di Assets. (17580)
- Gli errori relativi agli ID immagine duplicati negli argomenti impediscono all&#39;utente di salvare o creare un argomento. (17528)
- Si verificano dei problemi durante il caricamento di un numero elevato di file con set di dati densi in Experience Manager Guides.(17008)
- Si verificano errori intermittenti con la funzionalità di rendering PDF in Experience Manager Guides as a Cloud Service. (16966)
- Durante la creazione di una mappa DITA basata su un modello, il flusso di lavoro DXML OOTB causa interruzioni del processo e provoca 503 errori inutilizzabili. (16529)
- **I caratteri speciali** scritti con caratteri di escape vengono rimossi dall&#39;argomento dopo il caricamento in Experience Manager Guides. (16495)
- Il messaggio di errore File estratto da &quot;&quot; non viene visualizzato correttamente quando si modificano file spostati da un&#39;altra scheda, quando i token sono scaduti o quando l&#39;utente è disconnesso. (15223)
- I file di grandi dimensioni non vengono caricati nell’editor web e il browser viene bloccato. (13227)
- `<Topicref>` aggiunto utilizzando `<keyref>` non viene visualizzato in Native PDF. (11974)
- Il percorso del componente `/libs/fmdita/components/versions` è hardcoded e gli utenti non possono sovrapporlo. (8779)
- L&#39;apertura di un argomento o di una mappa DITA in una nuova scheda per la modifica blocca la navigazione della selezione nell&#39;interfaccia utente di Assets. (4992)
- Il download di una mappa DITA con file video di grandi dimensioni genera un errore di memoria insufficiente nei registri e non riesce nell’interfaccia utente. (18884)
- Quando si inserisce un&#39;equazione di MathML contenente il simbolo &quot;&lt;&quot;, viene generato un errore di **carattere non valido**. (18742)
- Una generazione UUID errata durante il processo di acquisizione dei contenuti causa la rottura dei riferimenti delle mappe secondarie nella mappa acquisita. (18308)
- In alcuni casi, si osservano ritardi nell&#39;elaborazione di un nuovo argomento DITA quando viene creato dall&#39;editor Web. (16836)
- La ricerca dei file nel **repository** all&#39;interno dell&#39;editor Web richiede troppo tempo e talvolta non riesce a caricare i risultati. (16837)

## Pubblicazione

- Il riferimento incrociato alla chiave non viene risolto nell’output di Native PDF. (18087)
- L&#39;errore **duplicate_value** si verifica in modo intermittente durante la ripubblicazione di un articolo esistente in Salesforce. (17932)
- La formattazione dello stile e del contenuto nei modelli del cliente cambia automaticamente quando il layout include campi di metadati, causando una formattazione errata nei PDF pubblicati. (17900)
- La convalida della connessione Salesforce non riesce con l’URL fulmine. (17797)
- Il PDF di riferimento non è attivato dal **dashboard di Publish in blocco** durante l&#39;attivazione in blocco del contenuto pubblicato. (17793)
- L’attivazione in blocco del contenuto pubblicato non funziona per le mappe localizzate. (17638)
- Quando si seleziona l&#39;opzione **Usa metadati aggiunti nell&#39;elemento topicmeta**, le proprietà dei metadati non vengono propagate nelle proprietà del documento dell&#39;output di PDF nativo. (17283)
- Il filtro delle condizioni nell&#39;output di PDF nativo non funziona come previsto rispetto a DITA-OT. (17095)
- Il sommario non rispetta i tag `<sub>` o `<sup>` nell&#39;output Native PDF. (17028)
- La generazione del sito AEM e l’API di pubblicazione incrementale non funzionano come previsto. (16666)
- La generazione nativa di PDF non riesce e viene restituito un errore relativo all’ottenimento delle dipendenze per Node.js. (14445)
- `<Conref>` non viene risolto nella modalità `Preview` dell&#39;editor Web e dell&#39;output di PDF nativo. (17827)
- I riferimenti al contenuto non vengono risolti correttamente per l&#39;output di PDF nativo se il file contenente le definizioni chiave non si trova nella stessa cartella della mappa DITA. (15062)
- Quando una mappa DITA contiene livelli di intestazione fino a 7 o superiori, l&#39;intestazione di livello 7 viene erroneamente trattata come intestazione di livello 1 nell&#39;output di Native PDF. (19698)
- Quando un contenuto (testo) viene disposto all&#39;interno di un elemento, gli spazi prima e dopo il testo non vengono visualizzati nei formati Anteprima o Output. (19308)
- I flussi di lavoro di post-generazione attivati manualmente non riescono a causa di un’ECCEZIONE NULL POINTER nel flusso di lavoro, che comporta il caricamento del contenuto 11 volte. (18880)
- **La dashboard di Publish in blocco** è vuota per le mappe ancora in fase di traduzione. (19352)


## Gestione

- Il percorso della funzionalità di sovrapposizione è hardcoded per il file in lingua coreana e non è selezionato correttamente. (17089)
- Le modifiche o le personalizzazioni apportate alla finestra di dialogo **Salva versione** non vengono applicate quando si utilizza il framework di estensione delle guide. (17828)
- La conversione da InDesign a DITA ha un percorso di configurazione hardcoded, pertanto i file di configurazione personalizzati non vengono scelti. (16891)
- I riferimenti/risorse completi non vengono scaricati quando una mappa DITA contenente dipendenze/riferimenti di grandi dimensioni viene scaricata utilizzando la linea di base. (19099)


### Rivedi

- Il recupero dell’elenco utenti durante la creazione di un’attività di revisione ha esito negativo se il numero di utenti supera i 25. (17329)
- Se un argomento dell&#39;attività contiene il tag `<cmd>` in uno o più passaggi, il pannello di revisione visualizza l&#39;attributo `importance` come prefisso in tutti i passaggi che contengono il tag. (19699)

## Traduzione

- I riferimenti delle risorse tradotte non vengono aggiornati. (18086)
- I riferimenti non vengono filtrati correttamente come diretti o indiretti durante la traduzione in più lingue. (17891)
- Impossibile creare progetti XLIFF con traduzione umana. (16964)
- L’aggiunta di un argomento aggiornato in un progetto di traduzione attivo genera un argomento duplicato e il processo non riesce. (7688)
- Ai progetti di traduzione creati selezionando l&#39;opzione **Crea solo struttura** non sono assegnati UUID. (18980)
- Quando si seleziona un progetto di traduzione con **Stato traduzione** come **In corso**, viene visualizzata una pagina errata. (13248)
- Il titolo con `<conref>` non viene risolto nelle dashboard di Baseline e Traduzione dell&#39;editor Web. (16961)

## Problemi noti

- L’apertura di un predefinito di AEM Sites (non legacy) contrassegna l’argomento come danneggiato.
- Il pannello selezionato non viene mantenuto durante l’aggiornamento del browser dalla scheda Output.
- Impossibile trascinare l&#39;argomento tra due argomenti nella visualizzazione **Autore**.
- Il filtro delle condizioni applicato nel predefinito non viene applicato tramite **Scarica come PDF**.
- La generazione di un singolo argomento dal pannello Mappa genera tutti gli argomenti selezionati nel predefinito di AEM Sites (non legacy).
- Il riferimento dell&#39;argomento risulta interrotto nell&#39;interfaccia utente quando viene inserito dalla barra degli strumenti superiore della mappa DITA.
- La generazione di PDF nativi ha esito negativo per una mappa DITA se sono presenti riferimenti mancanti.
- La pubblicazione di un singolo argomento del sito AEM con condizioni non riesce nell’ambiente abilitato per i microservizi.
- Una volta aggiornato lo stato del documento di un argomento a **Fine**, l&#39;icona **Avvia una nuova versione** è disponibile solo nella modalità **Anteprima** dell&#39;argomento.
