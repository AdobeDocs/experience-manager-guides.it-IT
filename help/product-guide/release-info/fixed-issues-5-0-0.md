---
title: Note sulla versione | Sono stati risolti dei problemi in Adobe Experience Manager Guides, versione 5.0.0
description: Scopri le correzioni di bug nella versione 5.0.0 di Adobe Experience Manager Guides.
source-git-commit: 5ae05935d254b03ad99221bd5f65dbb6a3580c5f
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 1%

---

# Sono stati risolti i problemi nella versione 5.0.0 di (marzo 2025)

Questo articolo descrive i bug corretti in varie aree della versione 5.0.0 di Adobe Experience Manager Guides.


Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 5.0.0](whats-new-5-0-0.md).

Scopri le [istruzioni di aggiornamento per la versione 5.0.0](upgrade-instructions-5-0-0.md).


## Authoring

- Quando si aggiornano le condizioni dal profilo di cartella, tutti i gruppi di condizioni vengono persi e le condizioni vengono appiattite. (23526)
- La modifica del valore delle righe di intestazione per una tabella nel pannello **Proprietà contenuto** non applica il valore aggiornato. (23213)
- Per le successive transizioni dello stato del documento delle Guide, è necessario aggiornare la pagina. (19421)
- Quando si aggiungono argomenti nella mappa DITA utilizzando la finestra di dialogo **Riferimento argomento** nella visualizzazione **Autore**, gli argomenti selezionati vengono inseriti in ordine inverso rispetto alla selezione. (8031)
- Quando si passa dalla visualizzazione **Autore** alla visualizzazione **Source**, gli spazi iniziali negli elementi `<pre>` o `<codeblock>` vengono eliminati e il file viene salvato con questa eliminazione. (19987)
- Lo stato del documento contrassegnato come **Fine** viene ripristinato come **Bozza** prima di salvare una nuova versione. Lo stato **Fine** non persiste in nessuna versione del documento. (20006)
- Quando le voci di elenco vengono spostate all&#39;esterno del tag para, il contenuto delle voci di elenco viene perso. (22764)
- Quando si aggiungono argomenti nella mappa DITA utilizzando la finestra di dialogo **Riferimento argomento** nella visualizzazione **Autore**, gli argomenti selezionati vengono inseriti in ordine inverso rispetto alla selezione. (22858)
- Quando si aggiungono nuovi riferimenti ad argomenti nella mappa DITA utilizzando la finestra di dialogo dell&#39;elemento **Riferimento argomento** nella visualizzazione **Layout**, i riferimenti aggiunti vengono visualizzati come collegamenti interrotti. (22859)
- Quando si fa clic con il pulsante destro del mouse sul tag `<simpletable>` all&#39;interno di un argomento, l&#39;opzione **Rinomina** non viene visualizzata. (22860)
- Quando si inserisce un `xref` che utilizza riferimenti basati su chiave con testo di collegamento, il testo di collegamento non viene visualizzato in Experience Manager Guides. (18775)
- Se si trascina un&#39;immagine all&#39;interno di un argomento nella visualizzazione **Autore**, il riferimento all&#39;immagine verrà interrotto e i dati andranno perduti. (25769)
- Non è possibile selezionare più file durante la ricerca di file nel repository utilizzando la funzionalità **Ricerca e filtro**. (25104)
- Quando si copia un’immagine da un prodotto esterno (ad esempio, MS PowerPoint) e la si incolla nelle Guide, la funzionalità di caricamento rapido della risorsa per l’utilizzo nel file si interrompe. (24983)
- Se si trascina un elemento `topicref` su un altro elemento (nella visualizzazione **Autore** o **Layout**), viene richiesta una conferma per la sostituzione anziché per la nidificazione. Se si seleziona l&#39;elemento **No** nella finestra di dialogo di conferma, il contenuto verrà comunque sostituito e i dati andranno persi. (18602)
- Non è possibile aggiungere più collegamenti a un singolo evento, né un argomento a un evento quando viene attivato da un collegamento. (19066)
- Quando si ricarica il browser, viene riaperta la scheda dell’immagine precedentemente chiusa. (19267)
- Se si seleziona parzialmente il testo in un paragrafo o in un elemento elenco e lo si trascina all&#39;esterno dell&#39;elemento, si verifica una perdita di contenuto quando si passa da **Creazione** a **Source** visualizzazioni. (25790)

## Pubblicazione

- La pubblicazione in Salesforce non riesce se il contenuto contiene spazi unificatori. (23664)
- Per le mappe con collegamenti interrotti, la pubblicazione di Salesforce non riesce e la barra di avanzamento viene visualizzata a tempo indeterminato. (24963)
- Per gli argomenti che presentano errori come i collegamenti interrotti, la pubblicazione di Salesforce non riesce e la barra di avanzamento viene visualizzata a tempo indeterminato. (22985)
- Pubblicazione PDF nativa non riuscita per l&#39;opzione di conformità **PDF/X-4**. Errore: **i documenti PDF/X-4 richiedono un titolo non vuoto**. (16904)
- Quando si utilizza il testo segnaposto, i riferimenti incrociati che utilizzano `<keyref>` in PDF nativo non vengono risolti. (19365)
- Generazione nativa di PDF non riuscita per il contenuto con **attributo chunk** impostato su **to-content**. (21772)
- Durante la generazione di un output PDF nativo, l&#39;elemento `ditavalref` non è supportato. (16320)
- Quando si modifica un file CSS di grandi dimensioni nell’editor CSS nativo di PDF, si osserva un ritardo significativo. (16915)
- Per la pubblicazione basata su HTML5, il flag DITA-OT generate.copy.outer viene applicato automaticamente. (24299)
- Il riferimento incrociato viene convertito in collegamento relativo anche quando l&#39;**ambito** del collegamento è impostato su **esterno**. (23059)
- Quando un file ICC è disponibile in un percorso interno, non può essere selezionato nelle impostazioni **Stampa** per il predefinito PDF nativo. (14741)
- Quando si avviano più richieste di pubblicazione per mappe diverse utilizzando lo stesso predefinito di profilo di cartella, la pubblicazione non riesce. (18800)
- Per gli argomenti con metadati/proprietà multivalore quando passati a DITA OT, la pubblicazione non riesce. (19001)
- La finestra di dialogo **Modifica proprietà** per una baseline non mostra i criteri salvati in precedenza per la baseline dinamica.  (23964)
- La baseline non include riferimenti indiretti quando il contenuto è nello stato finale del documento. (19148)
- L&#39;impostazione **Sanitize page names &amp; filenames for AEM Sites &amp; other output formats** è applicabile a tutti i formati di output. (7651)
- Se un collegamento esterno contiene un UUID, viene inserito nella fase di post-elaborazione e converte il collegamento esterno in un collegamento UUID, interrompendo in tal modo il collegamento nell’editor web e anche nei siti di pubblicazione. (22574)


## Gestione

- Il titolo e l&#39;icona della finestra di dialogo **Forza eliminazione** non sono allineati nell&#39;interfaccia utente di Assets. (21933)
- Quando un JSON viene aggiornato nel profilo di cartella per la configurazione dell&#39;editor XML, l&#39;operazione di salvataggio interrompe la configurazione dell&#39;editor XML. (22414)
- Quando si duplica un profilo di cartella, anche il relativo elenco di utenti amministratori viene copiato dal profilo di cartella originale. (19067)
- Si verifica un errore durante lo spostamento di cartelle di grandi dimensioni (contenenti un volume elevato di contenuti DITA, fino a 200.000 elementi) dall’interfaccia utente di Assets. (20107)
- Se si modifica il profilo **Cartella** con la shell unificata abilitata, l&#39;interfaccia utente risulterà vuota. (22212)
- Quando si eliminano cartelle contenenti un numero elevato di file, l’operazione non riesce. (17107)
- Quando annulli/elimini il processo di traduzione o elimini il progetto, nel dashboard di traduzione viene visualizzato lo stato **In corso**. (18417)
- Quando invii due versioni di un argomento non tradotto contemporaneamente utilizzando una traduzione non legacy e approvi la seconda versione prima della prima, il progetto di traduzione con la prima versione viene interrotto. (22200)


## Rivedi

- Quando si selezionano più argomenti da esaminare in una mappa, la notifica e-mail ricevuta dal revisore indica che tutti gli argomenti nella mappa sono disponibili per la revisione, anziché solo quelli selezionati. (23214)
- Il titolo e l’icona dell’argomento non sono allineati nell’interfaccia di creazione della revisione. (11670)


## API di

- Errore durante la creazione di una **Baseline** utilizzando l&#39;API Guide tramite l&#39;attivazione del servizio **BaslinUtlis**. (19385)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 5.0.0:

- In alcuni casi, la funzionalità di blocco per i file CSS non funziona come previsto, consentendo ad altri utenti di modificare e salvare i file anche quando sono bloccati da un altro utente.
- Impossibile uscire dalla visualizzazione della console Mappa quando la linea di base è danneggiata e il salvataggio automatico è abilitato.
- Se il nome del predefinito contiene caratteri maiuscoli, le modifiche apportate all&#39;impostazione del predefinito non vengono applicate ai predefiniti già creati nella mappa.
- La posizione del colore di sfondo non è allineata nell&#39;interfaccia utente del pannello **Condizione**.
- Quando si utilizza l&#39;immagine come `<keyref>`, il **tipo di riferimento** dell&#39;immagine non viene visualizzato nel **report multimediale**.
- Quando si utilizzano le immagini come variabili nel modello PDF, queste non vengono risolte nell’output.
- Nei report **Elenco argomenti**, l&#39;ordinamento per titolo non riesce per le risorse con `<conref>` o `<conkeyref>` nel titolo, causando la visualizzazione di queste voci sempre nella parte superiore.
- Il passaggio al profilo di cartella non riflette immediatamente le modifiche apportate all’interfaccia utente senza aggiornare il browser.
- Le personalizzazioni del framework di estensione effettuate prima della versione 5.0.0 delle Guide potrebbero non funzionare come previsto.
- Il sommario completo della mappa non viene aggiornato quando si pubblicano selettivamente argomenti dalla mappa.
- La pubblicazione di una mappa contenente un file Markdown con riferimenti immagine interni ha esito negativo sui server Windows.
- L’elenco puntato non può essere convertito in elenco numerato in Markdown.
- La pubblicazione sul sito AEM nativo non riesce quando si fa riferimento ai file markdown in una mappa.


