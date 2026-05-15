---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2025.07.0
description: Scopri le correzioni di bug nella versione 2025.07.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 0744e821-5aee-432b-a6c8-7ed6538935db
TQID: https://experienceleague.adobe.com/xzYzEvtyVvvIpq3tfLftkCDuiC08hahdNhr5ZXcQPo8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: ce44533e-8ec8-4e11-a9e9-78b0fe561832
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 520
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
- Vulnerabilità associate alla libreria Guava obsoleta utilizzata nei componenti AEM Guides caricati su Experience Manager Guides.(GUIDES-27402)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2025.07.0:

- Quando si utilizzano gli argomenti di Markdown, nella barra degli strumenti dell&#39;editor viene visualizzato un pulsante **Riferimento argomento** che tuttavia non funziona. (GUIDES-31038)
- I nomi dei nodi delle cartelle non vengono visualizzati correttamente al posto dei titoli delle cartelle nell’editor. (GUIDES-30909)
- Nella finestra di dialogo **Unisci**, l&#39;elenco a discesa visualizza in modo errato **Contenuto principale** invece di mostrare le versioni disponibili dell&#39;argomento selezionato. (GUIDES-30820)
- Quando si apre una mappa DITA con la shell unificata attivata, l&#39;editor viene aggiornato in modo intermittente.(GUIDES-26919)
