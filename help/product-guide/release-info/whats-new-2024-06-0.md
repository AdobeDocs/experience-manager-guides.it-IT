---
title: Note sulla versione | Novità di Adobe Experience Manager Guides, versione 2024.06.0
description: Scopri le funzioni nuove e migliorate della versione 2024.06.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: c885b8ba-5230-4d51-8f38-311b3a33fe0a
TQID: https://experienceleague.adobe.com/yw75NaMre6IwRbTBHS-V-XdZgVqdhY3H2-GDrB3ZRcQ
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 649
ht-degree: 2%

---

# Novità della versione 2024.06.0

Questo articolo descrive le funzioni nuove e migliorate della versione 2024.06.0 di Adobe Experience Manager Guides.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2024.06.0](fixed-issues-2024-06-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2024.06.0](upgrade-instructions-2024-06-0.md).


## Pubblicare un argomento o i relativi elementi in un frammento di esperienza

Un frammento di esperienza è un’unità di contenuto modulare all’interno di Adobe Experience Manager che integra contenuto e layout. I frammenti di esperienza sono fondamentali per creare esperienze coerenti e coinvolgenti, che possono essere ulteriormente riutilizzate su più canali.


Experience Manager Guides ora consente di pubblicare un argomento o i relativi elementi in un frammento di esperienza. Puoi creare una mappatura basata su JSON tra un argomento e i relativi elementi in un frammento di esperienza. Ad esempio, puoi creare frammenti di esperienza per intestazioni o piè di pagina con elementi di branding, banner promozionali, testimonianze di clienti e promozioni di eventi.




Per ulteriori dettagli, visualizza [Pubblica frammenti esperienza](../user-guide/publish-experience-fragment.md).


## Miglioramenti nella pubblicazione dei frammenti di contenuto

Experience Manager Guides fornisce anche alcuni utili miglioramenti nei frammenti di contenuto:

- Puoi filtrare facilmente il contenuto con le condizioni durante la pubblicazione in un frammento di contenuto, utilizzando un file DITAVAL o attributi condizionali.
- Puoi anche pubblicare e visualizzare i frammenti di contenuto di un argomento dalla sezione **Output** nelle **Proprietà file**.

![scheda opzioni proprietà file](./assets/file-properties-outputs-tab.png){width="300"}

Per ulteriori dettagli, visualizzare [Pubblica frammenti di contenuto](../user-guide/publish-content-fragment.md).


## Possibilità di passare metadati dalle proprietà del file argomento all&#39;output PDF nativo

Ora Experience Manager Guides consente di aggiungere ai layout di pagina i metadati delle proprietà del file di un argomento durante la generazione dell’output del PDF nativo. Utilizza questa funzione per aggiungere ai layout di pagina metadati specifici per argomento, come il titolo, i tag e la descrizione. È inoltre possibile personalizzare il PDF pubblicato in base ai metadati dell&#39;argomento, ad esempio aggiungendo una filigrana allo sfondo dell&#39;argomento in base allo stato del documento dell&#39;argomento.

![aggiungi metadati pdf nativo](./assets/add-metadata-native-pdf.png) {width="300"}

*Aggiungi metadati ai campi nei layout di pagina.*

Scopri come [aggiungere campi e metadati](../native-pdf/design-page-layout.md#add-fields-metadata) in un layout di pagina.

## Seleziona il contenuto parziale tra gli elementi per le operazioni

Experience Manager Guides migliora l’esperienza di selezione dei contenuti tra gli elementi nell’editor web. Puoi selezionare facilmente il contenuto tra diversi elementi ed eseguire operazioni come renderlo in grassetto, corsivo e sottolineato. Questa funzione consente di applicare o rimuovere facilmente la formattazione per il contenuto parzialmente selezionato. Puoi anche eliminare rapidamente il contenuto selezionato tra gli elementi. Una volta eliminato il contenuto, se necessario, il contenuto rimanente viene unito automaticamente in un singolo elemento valido.

È inoltre possibile selezionare contenuto parziale tra gli elementi e quindi racchiudere il contenuto in un elemento DITA valido.
![finestra di dialogo elemento surround](./assets/surround-element.png) {width="300"}

*Racchiudere il contenuto selezionato in un elemento valido.*

Nel complesso, questi miglioramenti offrono un’esperienza migliore e consentono di migliorare l’efficienza durante la modifica dei documenti.

Per ulteriori dettagli, visualizzare [Selezione parziale del contenuto nell&#39;elemento](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).

## Supporto per i documenti Markdown nella pubblicazione nativa di PDF

Experience Manager Guides supporta anche i documenti Markdown nella pubblicazione nativa di PDF. Questa funzione è utile e consente di generare PDF per i file Markdown nella mappa DITA. Il supporto Markdown nella pubblicazione nativa di PDF consente di creare, gestire e condividere facilmente i documenti.

Per ulteriori dettagli, visualizzare il [supporto per i documenti Markdown](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


## Prestazioni e scalabilità migliorate per progetti di traduzione di grandi dimensioni

La funzione di traduzione è più veloce e scalabile che mai. Viene fornita con una nuova architettura che offre prestazioni migliorate. Il tempo di creazione del progetto è ora più veloce di prima e i conflitti durante il processo sono quasi inesistenti. Queste prestazioni migliorate consentono di eseguire traduzioni più veloci, garantendo un funzionamento ottimale anche per progetti di traduzione di grandi dimensioni.

Questo miglioramento è molto utile in quanto migliora la produttività e l’esperienza complessiva.

Ulteriori informazioni su come [tradurre i documenti dall&#39;editor Web](../user-guide/translate-documents-web-editor.md).
