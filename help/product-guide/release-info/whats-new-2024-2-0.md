---
title: Note sulla versione | Novità di Adobe Experience Manager Guides, versione 2024.2.0
description: Scopri le funzioni nuove e migliorate della versione 2024.2.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 234d430a-d775-484a-aea8-6e422b0a01eb
TQID: https://experienceleague.adobe.com/WoykryIeK7-ZfAaJWVyWKrbibryba3Q-hKouqNRTyIo
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d6596f3f-92a7-43ec-b444-237db6adad05id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1063
ht-degree: 2%

---

# Novità della versione 2024.2.0

Questo articolo descrive le funzioni nuove e migliorate della versione 2024.2.0 di Adobe Experience Manager Guides.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2024.2.0](fixed-issues-2024-2-0.md).


Scopri le [istruzioni di aggiornamento per la versione 2024.2.0](upgrade-instructions-2024-2-0.md).



## Suggerimenti avanzati basati sull’intelligenza artificiale per aggiungere riferimenti ai contenuti durante la creazione dei contenuti

Ora è possibile migliorare il percorso di authoring con Smart Suggestions, una nuova funzione basata sull’intelligenza artificiale nell’editor web. Mentre si creano i contenuti, questa funzione intelligente offre suggerimenti in tempo reale per i riferimenti ai contenuti, migliorando il flusso di lavoro, aggiungendo precisione e garantendo un&#39;efficienza senza precedenti.


Per mantenere corretti e coerenti i contenuti, la ricerca e i suggerimenti sono limitati al contenuto di proprietà dell’organizzazione e strettamente correlati alle parole chiave cercate.

![Pannello suggerimenti avanzati nell&#39;editor Web ](assets/web-editor-smart-suggestion.png) {width="800"}


*Visualizza suggerimenti avanzati per trovare e aggiungere riferimenti ai contenuti corrispondenti dall&#39;archivio dei contenuti.*

Puoi anche confrontare il contenuto corrente con contenuti simili negli altri argomenti. Puoi quindi scegliere facilmente le parti di contenuto da vari argomenti e aggiungerle come riferimenti al contenuto nell’argomento corrente. L’aggiunta dei riferimenti ai contenuti rende gli aggiornamenti più gestibili, soprattutto nei progetti di documentazione più grandi. Ad esempio, stai creando una brochure sulle funzioni più recenti del prodotto. In tal caso, è possibile aggiungere rapidamente le specifiche aggiornate come riferimenti al contenuto dai documenti delle funzioni correlate.

Questa funzione intelligente consente di semplificare la ricerca manuale dei contenuti correlati e di concentrarsi sulla creazione di nuovi contenuti.  Consente inoltre di mantenere la coerenza e di migliorare la collaborazione tra i team.

Ulteriori informazioni sui [suggerimenti avanzati basati sull&#39;intelligenza artificiale per l&#39;authoring dei contenuti](../user-guide/authoring-ai-based-smart-suggestions.md).

## Funzione di cronologia delle versioni rinnovata nell’editor web

Ora Experience Manager Guides offre una funzione avanzata di cronologia delle versioni che consente di confrontare le modifiche apportate a un documento nel tempo. Nella nuova visualizzazione affiancata è possibile confrontare facilmente il contenuto e i metadati della versione corrente con qualsiasi versione precedente dello stesso documento. Puoi anche visualizzare le etichette e i commenti per le versioni confrontate. In qualità di amministratore, puoi controllare i metadati della versione dell&#39;argomento e i relativi valori da visualizzare nella finestra di dialogo **Cronologia versioni**.

![Finestra di dialogo Cronologia versioni](assets/version-history-dialog-web-editor.png){width="800"}
*Visualizzare in anteprima le modifiche nelle diverse versioni di un argomento.*


Ulteriori informazioni sulla descrizione della funzionalità **Cronologia versioni** nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Miglioramento dell’esperienza utente nel pannello Traduzione

Il pannello **Traduzione** è stato migliorato.  Puoi visualizzare l&#39;elenco **Lingue disponibili** e selezionare rapidamente le impostazioni locali in cui tradurre il progetto. Con una sola selezione, puoi anche scegliere **Seleziona tutti** per tradurre il progetto in tutte le lingue disponibili.

![pannello di traduzione](assets/translation-languages-4.4.png){width="300"}

*Selezionare le lingue in cui tradurre il progetto. Scegliere l&#39;impostazione predefinita, la baseline o la versione più recente dei file per la traduzione.*

Ulteriori informazioni su come [tradurre il contenuto](../user-guide/translation.md).


## Miglioramento della logica di ricerca nella finestra di dialogo Inserisci elemento

È ora possibile trovare facilmente gli elementi nella finestra di dialogo Inserisci elemento.  È possibile digitare una stringa nella casella di ricerca e ottenere un elenco di tutti gli elementi validi che iniziano con la stringa immessa.

Ad esempio, durante la modifica di un paragrafo che desideri inserire un elemento, puoi cercare un carattere &quot;t&quot; per ottenere
tutti gli elementi validi che iniziano con &quot;t&quot;.


![Finestra di dialogo Inserisci](assets/insert-element.png){width="300"}

*Digitare un carattere per cercare tutti gli elementi validi che iniziano con il carattere.*


Per ulteriori dettagli, visualizzare la descrizione della funzionalità **Inserisci elemento** nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).


## Possibilità di dividere l&#39;elenco corrente e iniziare con una nuova voce di elenco allo stesso livello

Ora è possibile suddividere facilmente l&#39;elenco nell&#39;Editor Web. Selezionare l&#39;opzione **Dividi elenco** dal menu di scelta rapida di una voce di elenco per dividere l&#39;elenco corrente. Viene creato un nuovo elenco allo stesso livello, a partire dalla voce di elenco selezionata per la suddivisione.

![pannello di traduzione](assets/context-menu-split-list.png){width="300"}

*Selezionare l&#39;opzione per dividere l&#39;elenco corrente.*

Per ulteriori dettagli, visualizzare la descrizione della funzionalità **Inserisci elenco** nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Accedere alle proprietà del file nella modalità di origine dell&#39;authoring

Ora puoi accedere alla funzionalità **Proprietà file** del pannello di destra in tutte e quattro le modalità o visualizzazioni: Layout, Autore, Source e Anteprima.  In questo modo è possibile visualizzare le proprietà del file anche quando si passa da una modalità all&#39;altra.

Per ulteriori dettagli, visualizzare la descrizione della funzionalità **Proprietà file** nella sezione [Pannello destro](../user-guide/web-editor-features.md#id2051EB003YK).

## Possibilità di pubblicare più predefiniti di output con linee di base dinamiche in parallelo

Experience Manager fornisce la funzione di creare linee di base scegliendo automaticamente gli argomenti in base all’etichetta ad esse applicata. Ora è anche possibile pubblicare facilmente più predefiniti di output con linee di base automatiche della stessa mappa DITA. Non è necessario pubblicare un solo predefinito alla volta, ma è possibile pubblicare facilmente più predefiniti di output in parallelo.


## Miglioramenti della versione nativa di PDF

I seguenti miglioramenti al PDF nativo sono stati apportati nella versione 2024.2.0:

### Trasmettere i metadati delle risorse all’output PDF

Experience Manager ora fornisce la funzionalità di passare le proprietà dei metadati delle risorse dalla mappa DITA all’output PDF.
Dal predefinito di output PDF nativo, puoi scegliere i metadati che desideri trasmettere al processo di pubblicazione PDF. Puoi selezionare sia le proprietà personalizzate che quelle predefinite.  Le proprietà dei metadati selezionate vengono passate al file PDF generato utilizzando PDF nativo.

Questa funzione è utile in quanto consente di mantenere coerenti le proprietà della risorsa, ad esempio l’autore, la data di creazione o il titolo del documento. Ciò semplifica l&#39;organizzazione, la ricerca e la classificazione dei documenti.

Per ulteriori dettagli, visualizzare le impostazioni **Avanzate** nell&#39;output [Pubblica PDF](../web-editor/native-pdf-web-editor.md).


### Usa i metadati aggiunti nell&#39;elemento `topicmeta` per l&#39;output PDF

La funzione metadati nella pubblicazione nativa di PDF facilita la gestione dei contenuti e la ricerca di file su Internet.
<img src="assets/pdf-metadata-4-4.png" alt="scheda metadati" width="800">

*Selezionare un&#39;opzione per aggiungere e personalizzare le opzioni dei metadati.*

Ora Experience Manager Guides offre l&#39;opzione di utilizzare i metadati aggiunti nell&#39;elemento `topicmeta` della mappa DITA per popolare i campi metadati dell&#39;output PDF. Questa opzione è selezionata per impostazione predefinita.

Questa funzione consente una migliore gestione dei documenti, garantisce coerenza e rende i documenti ricercabili.

Per ulteriori informazioni, visualizzare la scheda **Metadati** nell&#39;output [Pubblica PDF](../web-editor/native-pdf-web-editor.md).
