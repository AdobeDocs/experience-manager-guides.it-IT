---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2026.08.0
description: Scopri le correzioni di bug nella versione 2026.08.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 9e4af58e571659d9ed92308d3629a193d5558417
workflow-type: tm+mt
source-wordcount: '1218'
ht-degree: 0%

---

# Sono stati risolti i problemi nella versione 2026.08.0 di

Questo articolo descrive i bug corretti nelle varie aree della versione 2026.08.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizza [Novità della versione 2026.08.0](whats-new-2026-08-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.08.0](upgrade-instructions-2026-08-0.md).

## Authoring

- Gli argomenti non possono essere aperti nell’editor quando si accede dai rapporti Argomento nel dashboard Mappa. (GUIDES-45277)


## Editor 2.0

- Quando un&#39;equazione MathML viene inserita come `conref`, il rendering non viene eseguito correttamente. (GUIDES-46601)
- Copiare e incollare `<keywords>` all&#39;interno di `<topicmeta>` in un `<keydef>` o `<topicref>` fa sì che le parole chiave vengano inserite all&#39;interno di tag esterni indesiderati. (GUIDES-45800)
- L&#39;utilizzo di `Ctrl+click` su un collegamento interrotto in un editor mappe genera un errore dell&#39;applicazione. (GUIDES-45544)
- Copiare una tabella da un foglio di calcolo di Excel e incollarla nel nuovo editor inserisce tutto il contenuto della cella copiato in una singola cella di tabella anziché distribuirlo tra le celle corrispondenti. (GUIDES-47435)
- Un pulsante **Esporta come PDF** personalizzato configurato tramite `editor_toolbar.json` esegue il rendering e rimane cliccabile in modalità Anteprima, ma non esegue alcuna azione quando si fa clic su di esso. (GUIDES-47402)
- Gli elementi MathML e SVG non eseguono il rendering del set completo di attributi, causando l’interruzione delle classi CSS personalizzate e degli attributi condizionali applicati a tali elementi. (GUIDES-46371)
- Quando si aprono alcuni argomenti contenenti tabelle, viene aggiunto un tag `<foreign>` imprevisto con due nuove colonne, anche quando non sono state apportate modifiche all&#39;argomento. (GUIDES-46748)
- L&#39;attributo **Scale** non è applicabile alle immagini nella visualizzazione Creazione. (GUIDES-45996)
- Se si trascina un elemento contenente un `keyref`, il valore `keyref` viene convertito in un percorso assoluto. (GUIDES-45701)
- L&#39;inserimento di un elemento nella posizione `tgroup` mostra un avviso **#text non consentito in questa posizione**, che impedisce l&#39;inserimento di una tabella normale in tale posizione. (GUIDES-47446)
- I termini alfanumerici aggiunti al dizionario vengono comunque contrassegnati dal correttore ortografico di AEM invece di essere ignorati. (GUIDES-48587)

## Gestione risorse

- L’elaborazione delle risorse in blocco include in modo errato le risorse dei frammenti di contenuto, causando errori nei registri e nell’elaborazione dei rapporti. (GUIDES-47085)
- Nel pannello Mappa, gli argomenti secondari non vengono caricati e l&#39;icona di espansione scompare quando la casella di controllo Mappa viene selezionata e deselezionata ripetutamente. (GUIDES-43546)

## Pubblicazione

**AEM Sites**

Quando si pubblica l’output di AEM Sites utilizzando la mappatura di componenti compositi:

- Quando si utilizza una nuova linea di base nel predefinito AEM Sites con mappatura di componenti compositi, viene visualizzato un **elenco argomenti** vuoto. (GUIDES-46480)
- I collegamenti tra riferimenti incrociati (`xref`) a risorse non DITA come PDF, ZIP, DOCX e file di immagine non vengono risolti correttamente, con conseguente interruzione dei collegamenti nella pagina generata. (GUIDES-44108)

Quando si pubblica l’output di AEM Sites utilizzando la mappatura dei componenti legacy:

- I nomi di file non inglesi nei nomi di pagina generati vengono sostituiti da trattini, rendendo difficile identificare l’argomento o il file a cui sono associati. (GUIDES-48387)

**PDF nativo**

- Nell&#39;output PDF nativo, i riferimenti ad argomenti contrassegnati con l&#39;attributo `toc="no"` sono ancora inclusi nel sommario, creando un sommario lungo e disordinato. (GUIDE-37940, GUIDE-20156)

**Mappatura di raccolte e attivazione in blocco**

I seguenti problemi sono stati risolti con la funzionalità [Nuova raccolta mappe](../user-guide/generate-output-use-new-map-collection-output-generation.md#use-new-map-collection-for-output-generation-beta) disponibile nella versione 2020.08.0 di Experience Manager Guides:

- Impossibile caricare una raccolta di mappe con più di 100 voci di mappa a causa di un errore di rete. (GUIDES-34007)
- Impossibile selezionare più mappe alla volta da una cartella nell’interfaccia utente di Map Collection. (GUIDES-29581)
- Impossibile cercare o filtrare le raccolte di mappe nell’interfaccia utente delle raccolte di mappe. (GUIDES-27723)
- Impossibile chiudere il dashboard di pubblicazione/attivazione in blocco o tornare a **Strumenti** o alla home page senza utilizzare il pulsante Indietro del browser. (GUIDES-26797)
- Impossibilità di gestire facilmente le raccolte di mappe con un numero elevato di mappe o lingue. (GUIDES-21735)
- Impossibile visualizzare o pubblicare l’output generato direttamente dalle interfacce Map Collection (Raccolta mappe) o Bulk Activation Dashboard (Dashboard di attivazione in blocco). (GUIDES-18712)
- Impossibile utilizzare una singola raccolta per generare e attivare le mappe, poiché le raccolte delle mappe e il dashboard di attivazione in blocco gestiscono set separati di raccolte. (GUIDES-12730)

## Rivedere

- Nell’interfaccia utente Revisione, l’elenco dei tag mostra tutti gli utenti nell’attività di revisione, rendendo difficile selezionare l’utente corretto in un commento o in una risposta. (GUIDES-33420)
- Quando si apre la visualizzazione **affiancata** nel pannello Commenti, la copia di lavoro viene visualizzata accanto alla versione con commenti, ma i riquadri non scorrono sincronizzati orizzontalmente e quando si fa clic su un commento il cursore non viene spostato nel testo corrispondente. (GUIDES-44083)

## Database

- `DatabaseConfiguratorService` genera un errore nei registri anche quando non è configurato o abilitato. (GUIDES-43481)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2026.08.0:

## Authoring

- La chiusura di un file DITAVAL che è stato spostato in una posizione diversa genera un messaggio di errore `ERROR IN FETCHING VERSION DETAILS`. (GUIDES-51420)

## Editor 2.0


- L’API in conflitto non riesce e genera un errore di applicazione quando il percorso della cartella dell’archivio termina con una barra. (GUIDES-51006)
- Quando si seleziona un elemento di istruzione di elaborazione nella vista Struttura, viene evidenziato l&#39;intero tag padre anziché l&#39;elemento selezionato. (GUIDES-48318)
- La modifica di una parola chiave all&#39;interno di un `keyref` nella visualizzazione di origine interrompe la parola chiave quando si passa a un&#39;altra visualizzazione. (GUIDES-49998)
- Un&#39;equazione MathML racchiusa in un blocco `foreign` e `equation` genera una spaziatura indesiderata e la digitazione all&#39;interno dell&#39;equazione causa problemi anche dopo aver regolato il rientro. (GUIDES-46606)
- Impossibile posizionare un cursore all&#39;interno di un `topicref` all&#39;interno di un `reltable` se l&#39;opzione **Mostra tag** è abilitata e l&#39;opzione **Visualizza attributi** è disabilitata nelle impostazioni dell&#39;editor. (GUIDES-46565)
- Se si trascina un riferimento in un `keydef` vuoto, viene aggiunto un elemento `topicref` invece di aggiornare il riferimento. (GUIDES-45068)
- Spazio vuoto immesso immediatamente prima dell&#39;eliminazione di un tag in linea nella cella di una tabella `<entry>`. (GUIDES-49144)

## Pubblicazione

- Se si seleziona **Visualizza output** dopo la generazione dell&#39;output di Edge Delivery Services, viene aperto un URL `hlx.live` che restituisce un errore 403 non consentito anziché l&#39;URL `aem.live`. (GUIDES-51572)
- I componenti non validi vengono visualizzati nella pagina `common.plt` quando si aggiunge un&#39;immagine, un collegamento ipertestuale o un iframe dalla barra degli strumenti di un modello. (GUIDES-51165)
- Quando si pubblica una mappa che fa riferimento a un argomento utilizzando l&#39;attributo `copy-to`, il collegamento all&#39;ambito peer viene rimosso dall&#39;argomento corrispondente nella mappa di origine. (GUIDES-50701)
- Quando si fa riferimento a un PDF come `xref` con ambito impostato su `Peer`, questo viene pubblicato sul sito AEM (utilizzando la mappatura dei componenti legacy) invece di essere originato dalla cross map. (GUIDES-50213)

**Mappa raccolte**

- Talvolta l’eliminazione di una raccolta mappe ha esito negativo se si cambia scheda (ad esempio Archivio o Panoramica) e quindi si torna alla pagina Mappa raccolta prima di eliminarla. (GUIDES-50997)
- Quando si genera lo stesso predefinito mentre è in corso una generazione precedente, non viene più visualizzato un messaggio che indica che la generazione precedente è in corso. (GUIDES-50523)
- L’indicatore orario dell’ultima generazione non viene visualizzato o aggiornato nell’interfaccia utente di Map Collection dopo la generazione di una mappa; la reaggiunta di un predefinito precedentemente rimosso fa sì che la cronologia della generazione venga persa di nuovo. (GUIDES-50511)
- La pubblicazione dalla **Cronologia generazione** pubblica sempre l&#39;output più recente di un predefinito invece della generazione selezionata. (GUIDES-50508)
- Lo stato di pubblicazione non viene aggiornato automaticamente per le nuove raccolte mappe create. (GUIDES-50367)

## Traduzione

- L&#39;avvio di una traduzione con l&#39;opzione **Crea solo struttura** restituisce un errore. (GUIDES-51261)

## Rivedere

- Anche l’esecuzione di una barratura utilizzando una scelta rapida da tastiera su un testo che include contenuto condizionale nascosto interferisce con il contenuto nascosto. (GUIDES-49837)


