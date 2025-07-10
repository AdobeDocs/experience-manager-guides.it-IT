---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2025.07.0
description: Scopri le correzioni di bug nella versione 2025.07.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: bf8b295444a1e21fc19bfbc04efaa20fe78f71bb
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# Sono stati risolti i problemi nella versione 2025.07.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2025.07.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2025.07.0](whats-new-2025-07-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.07.0](upgrade-instructions-2025-07-0.md).

## Authoring

- Quando si aggiunge un commento XML all&#39;interno di un elemento nella visualizzazione Source, gli spazi iniziali e finali attorno al commento vengono persi quando si passa da una visualizzazione all&#39;altra. (GUIDES-29781)
- Le opzioni multimediali non funzionano se sono presenti nell&#39;icona con i puntini di sospensione (il menu **Altro**) nella barra degli strumenti. (GUIDES-29583)
- Quando si crea un nuovo argomento tramite l&#39;interfaccia utente o l&#39;editor di Assets, l&#39;argomento non si apre automaticamente nell&#39;editor se l&#39;impostazione `xmleditor.uniquefilenames` è impostata su true in `XMLEditorConfig`. (GUIDES-28171)
- Gli spazi aggiunti all’interno di un’equazione MathML nella vista Source non vengono mantenuti quando si passa da una vista dell’editor all’altra. (GUIDES-26111)

## Gestione risorse

- Quando aprite un argomento nella vista Autore dopo un aggiornamento del browser, i tag applicati in precedenza nel pannello Proprietà file non vengono mantenuti e l&#39;aggiunta di nuovi tag sovrascrive quelli esistenti, in particolare quando è disponibile un numero elevato di tag da selezionare. (GUIDES-29078)
- Quando si genera un report metadati per una mappa DITA contenente un numero elevato di risorse, il pulsante **Gestisci** non risponde o mostra una risposta ritardata. (GUIDES-28443)

## Rivedere

- I tentativi di creare attività di revisione tramite il flusso di lavoro di AEM hanno esito negativo in quanto il nodo di revisione non viene creato. (GUIDES-28214)

## Pubblicazione

- Errore di qualità del codice durante la distribuzione del pacchetto dei componenti di pubblicazione di AEM Sites `guides-components.all-1.3.0.zip` tramite Cloud Manager. (GUIDES-28873)
- La pubblicazione di una mappa DITA con l&#39;attributo `chunk=to-content` crea nodi JCR duplicati nel nuovo output di AEM Sites, determinando una struttura di contenuto ridondante in AEM Sites. (GUIDES-28104)
- Quando si pubblica una mappa DITA utilizzando il nuovo output di AEM Sites, se un argomento ha l&#39;attributo `chunk =to-content` e l&#39;output è impostato per l&#39;utilizzo dei titoli degli argomenti come nomi di pagina, il nome della pagina generata visualizza erroneamente la parola **chunk** invece di mantenere il nome dell&#39;argomento originale. (GUIDES-28102)
- La proprietà `cq:template` impostata nel modello di argomento di AEM Guides per la nuova pubblicazione AEM Sites visualizza un valore non corretto che influisce sulla struttura del modello e sul rendering del contenuto. (GUIDES-27789)


## Platform

- Quando si lavora con raccolte di grandi dimensioni, si verificano problemi di prestazioni quali tempi di caricamento più lunghi e timeout intermittenti. (GUIDE-29065, GUIDE-28793)
- Le vulnerabilità associate alla libreria Guava obsoleta vengono utilizzate nei componenti AEM Guides caricati su Experience Manager Guides.(GUIDES-27402)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2025.07.0:

- Quando si utilizzano gli argomenti di Markdown, nella barra degli strumenti dell&#39;editor viene visualizzato un pulsante **Riferimento argomento** che tuttavia non funziona. (GUIDES-31038)
- Quando si caricano cartelle con nomi in maiuscolo tramite l’app desktop Adobe Experience Manager, l’uso di maiuscole e minuscole non viene mantenuto e i nomi vengono visualizzati in minuscolo nell’editor. (GUIDES-30909)
- Nella finestra di dialogo **Unisci**, l&#39;elenco a discesa visualizza in modo errato **Contenuto principale** invece di mostrare le versioni disponibili dell&#39;argomento selezionato. (GUIDES-30820)
- Quando si apre una mappa DITA con la shell unificata abilitata, l&#39;editor viene aggiornato in modo intermittente.(GUIDES-26919)