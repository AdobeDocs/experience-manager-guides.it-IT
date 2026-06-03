---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2026.05.0
description: Scopri le correzioni di bug nella versione 2026.05.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 4a22e6f8e2505a5e2a990ec38571913c838d0ea1
workflow-type: tm+mt
source-wordcount: '1255'
ht-degree: 0%

---

# Sono stati risolti i problemi nella versione 2026.05.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2026.05.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizza [Novità della versione 2026.05.0](whats-new-2026-05-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.05.0](upgrade-instructions-2026-05-0.md).

## Authoring

- Quando si seleziona un&#39;immagine nell&#39;editor utilizzando la finestra di dialogo **Seleziona file**, vengono visualizzati solo i formati raster (ad esempio JPG, PNG e GIF). I file vettoriali (ad esempio con estensione ai e eps) non vengono visualizzati e non possono essere selezionati. (GUIDES-45110)
- Al momento dell&#39;aggiornamento, l&#39;impostazione `tagsView` è disattivata per impostazione predefinita, anche se il suo valore predefinito in `ui_config.json` è impostato su `true`. (GUIDES-44651)
- Nell&#39;editor, i riferimenti ai file vengono visualizzati come GUID anziché come percorsi dei file nonostante la configurazione di `xmleditor.uuid`. (GUIDES-42438)
- Quando si applicano schemi Oggetto con valori chiave simili in un argomento DITA, questi vengono evidenziati con colori quasi identici, rendendo difficile distinguerli e identificare quale schema viene applicato. (GUIDES-38472)
- Quando si modifica una mappa Schema soggetti nella vista Autore, l&#39;aggiunta dell&#39;elemento `hasInstance` attiva automaticamente la finestra di dialogo di selezione del file, richiedendo agli autori di inserire un elemento `href` indesiderato che punta a una risorsa AEM. Inoltre, il pannello **Proprietà contenuto** non viene caricato per tali mappe, impedendo agli autori di aggiornare gli attributi degli elementi nella vista Autore e richiedendo loro di utilizzare la vista Source per l&#39;aggiornamento degli attributi. (GUIDES-38164)
- Quando si modifica un file `.ditaval`, tutti i commenti XML aggiunti nella visualizzazione Source vengono rimossi quando si passa alla visualizzazione Autore e quindi si torna alla visualizzazione Source. (GUIDES-33228)


## Gestione risorse

- Quando si crea un argomento in una cartella il cui nome contiene spazi, viene erroneamente creata una cartella duplicata in cui gli spazi vengono sostituiti da trattini e l&#39;argomento viene salvato in tale cartella anziché nella cartella originale. (GUIDES-41938)
- Durante la prima traduzione di mappe di grandi dimensioni, vengono creati file XML vuoti per la lingua di destinazione, con conseguente aumento del carico del server e rallentamento delle prestazioni. (GUIDES-41613)
- Negli ambienti basati su DB, i collegamenti DITA interni validi vengono visualizzati come collegamenti interrotti in **Proprietà risorsa**, anche se funzionano correttamente nell&#39;editor e nell&#39;output pubblicato. (GUIDES-35048)

## Pubblicazione

- Quando le modifiche a un predefinito di output in un profilo Cartella vengono applicate alle mappe esistenti, viene reimpostato il **Contesto di pubblicazione** salvato per il predefinito AEM Sites. (GUIDES-38377)
- Il simbolo del marchio (®) non viene visualizzato sulla copertina dell&#39;output del PDF nativo quando l&#39;elemento `tm` viene utilizzato all&#39;interno del titolo di una mappa o di un bookmap. (GUIDES-28832)
- Quando si pubblica una mappa utilizzando un modello PDF nativo, il **Titolo mappa** non include il contenuto degli elementi figlio utilizzati nella mappa `title` e il filtro del contenuto corrispondente non viene applicato al titolo.(GUIDES-33730)
- I collegamenti peer tra mappe nell&#39;output di AEM Sites non vengono risolti quando puntano a un `topicref` che utilizza `chunk="to-content"`. (GUIDES-37873)
- Durante la pubblicazione, i file associati ai contrassegni basati su DITAVAL vengono spostati in una nuova cartella generata dal sistema invece di rimanere nella posizione relativa prevista nell&#39;output. (GUIDES-37564)
- Quando si utilizzano più file DITAVAL con condizioni in conflitto, l&#39;output del PDF nativo non riesce. (GUIDES-37484)

## Riferimento

- I riferimenti ad argomenti all&#39;interno di una mappa vengono erroneamente visualizzati come indiretti quando si utilizza un oggetto DITA-OT personalizzato, anche se vi si fa riferimento direttamente. Questo problema è stato risolto con la nuova esperienza linea di base. (GUIDES-19286)
- I riferimenti con `scope="peer"` non vengono inclusi correttamente nel contesto di base e la pubblicazione richiede più tempo del previsto. Questo problema è stato risolto con la nuova esperienza linea di base. (GUIDES-30048)

## Platform

- Quando si aprono mappe o argomenti di grandi dimensioni, l&#39;istanza Autore non risponde e in alcuni casi è necessario riavviare il computer. (GUIDES-43547)

## Problemi risolti disponibili con Editor 2.0

I seguenti problemi sono stati risolti e non si verificano più quando si utilizza l’Editor 2.0 (o Nuovo Editor):

- Quando due o più colonne vengono eliminate da una tabella, la struttura della tabella diventa incoerente o danneggiata. (GUIDES-35438)
- Quando si elimina una colonna da una tabella contenente celle unite, viene aggiunta una nuova colonna vuota. (GUIDES-30147)
- Quando si inserisce una nuova riga in una tabella esistente dal menu delle breadcrumb, la struttura della tabella cambia in modo imprevisto, con la conseguente perdita di bordi e l’aggiunta di una colonna. (GUIDES-29194)
- Nella vista Autore, se si copia e incolla una riga di tabella, il contenuto viene posizionato all&#39;esterno della tabella anziché essere inserito come nuova riga all&#39;interno della tabella. (GUIDES-24372)
- Quando un elemento di sezione selezionato mediante trascinamento del mouse in modalità Creazione viene copiato e incollato, viene convertito in elementi di paragrafo `(<p>)` invece di mantenere la struttura di sezione. (GUIDES-30023)
- Quando si modifica il testo evidenziato all&#39;interno di elementi quali step o uicontrol, il testo selezionato non viene sostituito correttamente e viene aggiunto o anteposto, generando errori di convalida. (GUIDES-24371)
- Quando la larghezza delle colonne di una tabella viene impostata utilizzando valori relativi, le colonne rimanenti non vengono regolate in modo proporzionale, causando un layout di tabella non allineato. (GUIDES-26109)
- Quando un titolo di argomento copiato viene incollato con i tag disattivati, al primo incolla viene applicato uno stile errato e il tipo nelle proprietà del contenuto viene assegnato come argomento invece che come titolo. (GUIDES-28838)
- Quando si modificano sezioni di contenuto di grandi dimensioni, lo scorrimento involontario fa sì che la vista Editor si sposti dal contenuto attivo. (GUIDES-35436)
- Quando si utilizza Backspace sugli elementi, l&#39;Editor scorre fino alla parte superiore dell&#39;argomento indipendentemente dalla posizione del cursore. (GUIDES-32520)
- Quando si utilizza il tasto freccia sinistra o freccia destra per spostarsi all’esterno dei tag in linea, il cursore si sposta inaspettatamente al primo tentativo. (GUIDES-26363)
- AEM Spellcheck funziona solo per la lingua en-US predefinita e non rispetta altre lingue. (GUIDES-14731)
- Quando nell&#39;Editor vengono sbloccati argomenti DITA di grandi dimensioni, lo stesso argomento viene riaperto in una scheda duplicata. Inoltre, viene attivato un avviso relativo al limite di tag in cui viene visualizzato `NaN` invece del numero effettivo di tag. (GUIDES-34008)
- I suggerimenti Acrolinx non vengono evidenziati correttamente nell&#39;Editor per gli argomenti di sola lettura o bloccati. (GUIDES-29614)
- Quando si crea un nuovo elemento `reltable` senza una riga di intestazione nella visualizzazione Autore, il layout della tabella cambia dopo l&#39;aggiunta di un argomento alla prima cella, causando la compressione della colonna successiva e rendendo difficile l&#39;inserimento di argomenti correlati. (GUIDES-19555)
- Quando si aggiunge un collegamento `xref` a una cella di una tabella in modalità Creazione, il collegamento non rimane contenuto all&#39;interno della cella e viene visualizzato tra celle adiacenti nella stessa riga. (GUIDES-5489)
- Quando si passa dalla visualizzazione Autore alla visualizzazione Source, la posizione del cursore non viene mantenuta e l&#39;editor torna in alto. Inoltre, negli argomenti lunghi, la posizione del cursore viene persa e si sposta in modo casuale al centro o in alto quando si passa dalla visualizzazione Autore a quella Source. (GUIDE-18114, GUIDE-21164)
- Premendo *Invio* all&#39;interno di un elemento `<li>` viene creato un nuovo elemento `<li>`, ma tornando a un elemento `<li>` precedente e premendo *Invio* il contenuto dell&#39;elemento corrente viene convertito in un elemento `<p>`, interrompendo la struttura dell&#39;elenco. (GUIDES-27505)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2026.05.0:

- Quando una mappa contiene un `topicref` esterno che punta a una risorsa non DITA (ad esempio `.html` o `.htm`), la relativa anteprima non viene visualizzata nell&#39;interfaccia utente di Assets. (GUIDES-45409)
- Nell&#39;interfaccia utente di Assets, il contenuto a cui si fa riferimento utilizzando `conref` non viene visualizzato per gli argomenti DITA, anche se viene eseguito correttamente il rendering nell&#39;anteprima dell&#39;editor. (GUIDES-45505)<br>**Soluzione**: per tali contenuti è possibile utilizzare l&#39;anteprima dell&#39;editor.
- Quando la proprietà `xmleditor.uniquefilenames` è abilitata, i nuovi argomenti creati utilizzando un modello non includono il titolo dell&#39;argomento. (GUIDES-44737)
- Le API `getAsset`, `startAssetProcessing` e `getAssetProcessingStatus` non sono disponibili per l&#39;utilizzo tramite Java SDK.

