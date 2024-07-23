---
title: Note sulla versione | Novità di Adobe Experience Manager Guides, versione 2024.06.0
description: Scopri le funzioni nuove e migliorate nella versione 2024.06.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: c885b8ba-5230-4d51-8f38-311b3a33fe0a
source-git-commit: 2455307ef747b2f2574666ee773d931b302f58ca
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 2%

---

# Novità della versione 2024.06.0

Questo articolo descrive le funzioni nuove e migliorate della versione 2024.06.0 di Adobe Experience Manager Guides.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2024.06.0](fixed-issues-2024-06-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2024.06.0](upgrade-instructions-2024-06-0.md).


## Publish di un argomento o dei relativi elementi in un frammento di esperienza

Un frammento di esperienza è un’unità di contenuto modulare all’interno di Adobe Experience Manager che integra contenuto e layout. I frammenti di esperienza sono fondamentali per creare esperienze coerenti e coinvolgenti, che possono essere ulteriormente riutilizzate su più canali.


Experience Manager Guides ora consente di pubblicare un argomento o i relativi elementi in un frammento di esperienza. Puoi creare una mappatura basata su JSON tra un argomento e i relativi elementi in un frammento di esperienza. Ad esempio, puoi creare frammenti di esperienza per intestazioni o piè di pagina con elementi di branding, banner promozionali, testimonianze di clienti e promozioni di eventi.




Per ulteriori dettagli, visualizza [Frammenti esperienza Publish](../user-guide/publish-experience-fragment.md).


## Miglioramenti nella pubblicazione dei frammenti di contenuto

Experience Manager Guides fornisce anche alcuni utili miglioramenti nei frammenti di contenuto:

- Puoi filtrare facilmente il contenuto con le condizioni durante la pubblicazione in un frammento di contenuto, utilizzando un file DITAVAL o attributi condizionali.
- Puoi anche pubblicare e visualizzare i frammenti di contenuto di un argomento dalla sezione **Output** nelle **Proprietà file**.

![scheda opzioni proprietà file](./assets/file-properties-outputs-tab.png){width="300" align="left"}

Per ulteriori dettagli, visualizzare [Frammenti di contenuto Publish](../user-guide/publish-content-fragment.md).


## Possibilità di passare metadati dalle proprietà del file argomento all&#39;output di PDF nativo

Ora Experience Manager Guides consente di aggiungere i metadati dalle proprietà del file di un argomento ai layout di pagina durante la generazione dell’output di Native PDF. Utilizza questa funzione per aggiungere ai layout di pagina metadati specifici per argomento, come il titolo, i tag e la descrizione. È inoltre possibile personalizzare il PDF pubblicato in base ai metadati dell&#39;argomento, ad esempio aggiungendo una filigrana allo sfondo dell&#39;argomento in base allo stato del documento dell&#39;argomento.

![aggiungi metadati pdf nativo](./assets/add-metadata-native-pdf.png) {width="300" align="left"}

*Aggiungi metadati ai campi nei layout di pagina.*

Scopri come [aggiungere campi e metadati](../native-pdf/design-page-layout.md#add-fields-metadata) in un layout di pagina.

## Seleziona il contenuto parziale tra gli elementi per le operazioni

Experience Manager Guides migliora l’esperienza di selezione dei contenuti tra gli elementi nell’editor web. Puoi selezionare facilmente il contenuto tra diversi elementi ed eseguire operazioni come renderlo in grassetto, corsivo e sottolineato. Questa funzione consente di applicare o rimuovere facilmente la formattazione per il contenuto parzialmente selezionato. Puoi anche eliminare rapidamente il contenuto selezionato tra gli elementi. Una volta eliminato il contenuto, se necessario, il contenuto rimanente viene unito automaticamente in un singolo elemento valido.

È inoltre possibile selezionare contenuto parziale tra gli elementi e quindi racchiudere il contenuto in un elemento DITA valido.
![finestra di dialogo elemento surround](./assets/surround-element.png) {width="300" align="left"}

*Racchiudere il contenuto selezionato in un elemento valido.*

Nel complesso, questi miglioramenti offrono un’esperienza migliore e consentono di migliorare l’efficienza durante la modifica dei documenti.

Per ulteriori dettagli, visualizzare [Selezione parziale del contenuto nell&#39;elemento](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).

## Supporto per i documenti Markdown nella pubblicazione di PDF nativi

Experience Manager Guides supporta anche i documenti Markdown nella pubblicazione Native PDF. Questa funzione è utile e consente di generare PDF per i file Markdown nella mappa DITA. Il supporto di Markdown nella pubblicazione di PDF nativi consente di creare, gestire e condividere facilmente i documenti.

Per ulteriori dettagli, visualizzare il [supporto per i documenti Markdown](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


## Prestazioni e scalabilità migliorate per progetti di traduzione di grandi dimensioni

La funzione di traduzione è più veloce e scalabile che mai. Viene fornita con una nuova architettura che offre prestazioni migliorate. Il tempo di creazione del progetto è ora più veloce di prima e i conflitti durante il processo sono quasi inesistenti. Queste prestazioni migliorate consentono di eseguire traduzioni più veloci, garantendo un funzionamento ottimale anche per progetti di traduzione di grandi dimensioni.

Questo miglioramento è molto utile in quanto migliora la produttività e l’esperienza complessiva.

Ulteriori informazioni su come [tradurre i documenti dall&#39;editor Web](../user-guide/translate-documents-web-editor.md).
