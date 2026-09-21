---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Scopri le correzioni di bug nella versione 5.2.0 Service Pack 1 di Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 429d2abf0aad8722ac30c08c9c9d134be0759ff4
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 0%
---
# Sono stati risolti i problemi nella versione 5.2.0 Service Pack 1 (settembre 2026)

Questo articolo descrive i bug corretti in varie aree della versione 5.2.0 Service Pack 1 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 5.2.0 Service Pack 1](upgrade-instructions-5-2-0-sp1.md).

## Authoring

- Nelle schermate a bassa risoluzione, la finestra di dialogo Inserisci parola chiave non viene visualizzata quando si inserisce una parola chiave dalla barra degli strumenti, mentre si apre come previsto quando si utilizza l&#39;opzione **Altro**. (GUIDES-48304)
- L&#39;inserimento di un rimando tramite l&#39;opzione **Collegamento Web** aggiunge un collegamento `scope=local` e modifica il valore `href`, anziché inserire un collegamento `scope=external` come previsto. (GUIDES-48457)
- Il salvataggio di una mappa di riferimento determina un riferimento interrotto invece di risolverlo nella mappa corretta quando un autore sposta la mappa di riferimento mentre un altro sta aggiungendo contemporaneamente un riferimento a essa in una mappa non salvata. (GUIDES-47467)
- I termini alfanumerici aggiunti al dizionario vengono comunque contrassegnati dal correttore ortografico di AEM invece di essere ignorati. (GUIDES-48587)
- Quando si attiva tra i campi **Larghezza** e **Altezza** nella finestra di dialogo delle proprietà dell&#39;immagine utilizzando dimensioni basate su unità come `in`, `mm` o `px`, i valori continuano ad aumentare in modo incrementale invece di rimanere stabili. (GUIDES-45929)

## Editor 2.0

- Spazio vuoto immesso immediatamente prima dell&#39;eliminazione di un tag in linea nella cella di una tabella `<entry>`. (GUIDES-49144)
- L&#39;inserimento di un elemento nella posizione `tgroup` mostra un avviso **#text non consentito in questa posizione**, che impedisce l&#39;inserimento di una tabella normale in tale posizione. (GUIDES-47446)
- Copiare una tabella da un foglio di calcolo di Excel e incollarla nel nuovo editor inserisce tutto il contenuto della cella copiato in una singola cella di tabella anziché distribuirlo tra le celle corrispondenti. (GUIDES-47435)
- Un pulsante **Esporta come PDF** personalizzato configurato tramite `editor_toolbar.json` esegue il rendering e rimane cliccabile in modalità Anteprima, ma non esegue alcuna azione quando si fa clic su di esso. (GUIDES-47402)
- Quando si aprono alcuni argomenti contenenti tabelle, viene aggiunto un tag `<foreign>` imprevisto con due nuove colonne, anche quando non sono state apportate modifiche all&#39;argomento. (GUIDES-46748)
- Quando un&#39;equazione MathML viene inserita come `conref`, il rendering non viene eseguito correttamente. (GUIDES-46601)
- Gli elementi MathML e SVG non eseguono il rendering del set completo di attributi, causando l’interruzione delle classi CSS personalizzate e degli attributi condizionali applicati a tali elementi. (GUIDES-46371)
- L&#39;attributo **Scale** non è applicabile alle immagini nella visualizzazione Creazione. (GUIDES-45996)
- L&#39;applicazione di un attributo `scale` a una tabella non esegue il rendering della tabella alle dimensioni configurate nelle modalità Creazione e Anteprima. (GUIDES-45984)
- Incollando le immagini copiate da fonti esterne come Paint o lo strumento di cattura, l&#39;immagine non viene inserita nell&#39;argomento. (GUIDES-45983)
- Copiare e incollare `<keywords>` all&#39;interno di `<topicmeta>` in un `<keydef>` o `<topicref>` fa sì che le parole chiave vengano inserite all&#39;interno di tag esterni indesiderati. (GUIDES-45800)
- Nella visualizzazione Tag di una tabella, premendo il tasto freccia su quando il cursore è posizionato nella cella direttamente sotto un tag di immissione compresso, il tag compresso viene ignorato e il cursore viene spostato all&#39;inizio del documento. (GUIDES-45408)
- Quando si esegue un&#39;operazione dalla barra degli strumenti contestuale della tabella, la barra degli strumenti viene chiusa in modo imprevisto, interrompendo le operazioni successive della tabella. (GUIDES-45405)
- L&#39;opzione **Modifica MathML** non viene visualizzata correttamente in modalità di sola lettura o quando un file viene estratto da un altro utente, consentendo agli utenti di aggiornare il contenuto di MathML anche se il file non dovrebbe essere modificabile. (GUIDES-45172)
- Dopo aver utilizzato **Inserisci dopo** o **Inserisci prima** dalla visualizzazione Struttura o dalla breadcrumb, il cursore si sposta in una posizione arbitraria anziché all&#39;interno del tag appena aggiunto. (GUIDES-45147)
- Quando si esegue un trascinamento della selezione con la vista Tag attivata, la selezione del contenuto insieme a tag XML o DITA parziali lascia indietro i tag orfani indesiderati, causando la visualizzazione o il contenuto errati. (GUIDES-28191)

## Gestione risorse

- L&#39;utility di eliminazione della versione non viene completata in diversi scenari, tra cui alcuni tipi di file, risorse con metadati mancanti e report di grandi dimensioni, invece di completare l&#39;eliminazione e generare un report accurato. (GUIDES-43453)

## Pubblicazione

- I nomi di file non inglesi nei nomi di pagina generati vengono sostituiti da trattini, rendendo difficile identificare l’argomento o il file a cui sono associati quando si pubblica l’output di AEM Sites utilizzando la mappatura di componenti legacy. (GUIDES-48387)
- Sono stati identificati `jackson-databind` JAR vulnerabili (versione 2.9.8) in bundle con AEM Guides nel pacchetto DITA-OT. (GUIDES-43081)

## Rivedere

- Quando si apre la visualizzazione **affiancata** nel pannello Commenti, la copia di lavoro viene visualizzata accanto alla versione con commenti, ma i riquadri non scorrono sincronizzati orizzontalmente e quando si fa clic su un commento il cursore non viene spostato nel testo corrispondente. (GUIDES-44083)

## Platform

- Se si utilizza `scope="external"` come riferimento al contenuto DAM in un argomento o in una mappa, il percorso relativo della risorsa viene sostituito da un GUID. (GUIDES-35605)
- Per il contenuto creato prima della migrazione UUID, il download di una mappa con le opzioni **Mantieni gerarchia file** e **Usa nome file effettivo** selezionate converte in modo errato i valori `href` di `topicref`, `xref` e `conref` elementi con `scope="external"` in nomi di file basati su GUID invece di mantenere i relativi percorsi di file originali. Di conseguenza, i riferimenti esterni vengono interrotti. (GUIDES-46526)
- Quando si caricano le risorse tramite l’interfaccia utente di Assets, lo stato di caricamento non viene visualizzato. (GUIDES-7207)

## Problemi noti

- Quando si esegue un&#39;operazione di revisione all&#39;interno di un blocco di codice, al primo tentativo viene visualizzato un avviso **Operazione non consentita**, ma l&#39;operazione viene eseguita correttamente se ripetuta. (GUIDES-56749)
- Quando si crea un&#39;attività di revisione per contenuto contenente un `code block`, la formattazione barrata non viene applicata correttamente dopo l&#39;importazione e il contenuto evidenziato non è presente nella visualizzazione di confronto affiancato. (GUIDES-56811)
- In alcuni casi, la scheda **Elenco argomenti** nel pannello Rapporti non visualizza alcun risultato, anche quando la mappa contiene più argomenti. (GUIDES-56893) <br> **Soluzione:** reindicizzare il contenuto interessato per ricreare le relazioni padre-mappa. Gli argomenti vengono quindi visualizzati come previsto nella scheda Elenco argomenti.
- Quando si seleziona un elemento di istruzione di elaborazione nella vista Struttura, viene evidenziato l&#39;intero tag padre anziché l&#39;elemento selezionato. (GUIDES-48318)
- Durante l’esecuzione di operazioni di eliminazione, è possibile che si verifichino alcune incongruenze minori nello spostamento e nella navigazione del cursore tra mappe immagine, elementi strutturati, tag di formattazione in linea e blocchi non unificabili, che occasionalmente possono causare un comportamento imprevisto del cursore o dell’eliminazione. (GUIDES-46756)
- Un&#39;equazione MathML racchiusa in un blocco `foreign` e `equation` genera una spaziatura indesiderata e la digitazione all&#39;interno dell&#39;equazione causa problemi anche dopo aver regolato il rientro. (GUIDES-46606)
- Impossibile posizionare un cursore all&#39;interno di un `topicref` all&#39;interno di un `reltable` se l&#39;opzione **Mostra tag** è abilitata e l&#39;opzione **Visualizza attributi** è disabilitata nelle impostazioni dell&#39;editor. (GUIDES-46565)
- Premendo backspace all’inizio di un paragrafo immediatamente successivo al contenuto di sola lettura (ad esempio un paragrafo di riferimento) è possibile eliminare o unire in modo imprevisto il paragrafo modificabile, causando l’eliminazione imprevista del paragrafo modificabile. (GUIDES-45049)
- Quando un tag in linea viene rinominato utilizzando l’opzione Rinomina elemento, la breadcrumb non viene aggiornata immediatamente e riflette la modifica solo dopo lo spostamento del cursore nel tag o la modifica della modalità di visualizzazione. (GUIDES-44993)<br>**Soluzione alternativa:** Aggiorna il browser dopo aver rinominato il tag in linea per aggiornare la breadcrumb.
- Quando gli indicatori di condizione vengono applicati a elementi come bodydiv, si verifica un overflow degli indicatori nei tag adiacenti in Visualizzazione tag completa, con conseguente rendering visivo errato. (GUIDES-44971)

