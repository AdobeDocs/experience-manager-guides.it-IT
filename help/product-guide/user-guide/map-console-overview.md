---
title: Console mappe in Adobe Experience Manager Guides
description: Scopri la console Mappa e le varie funzioni disponibili che consentono di pubblicare e gestire le mappe in Adobe Experience Manager Guides.
feature: Publishing
role: User
exl-id: b273b1ae-fbb2-4b35-abce-0df78eeb2e11
TQID: https://experienceleague.adobe.com/RFlLBJ4tFUBVo2FyGFur21uIResNd0qFWpKszJbnBIk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
  - id: fd456af4-cb12-4a34-8cc4-b74adf885626
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 773
ht-degree: 0%

---

# Panoramica della console delle mappe

Adobe Experience Manager Guides offre una console dedicata, nota come **console Mappe**, per semplificare tutte le attività di gestione delle mappe e pubblicazione. Questa interfaccia centralizzata migliora la produttività e l&#39;accuratezza delle attività correlate alle mappe, fornendo opzioni per generare output, tradurre contenuti, accedere ai report e altro ancora, il tutto in un&#39;unica posizione.

![scheda opzioni proprietà file](./images/map-console-screen.png)

L&#39;interfaccia della console Mappa è principalmente divisa in due sezioni: **Barra di navigazione** e **Pannello sinistro**.

![Nuovo](images/map-console-sections.png)

- (**A**) **Barra di spostamento**: la barra di spostamento visualizza gli strumenti per passare da una visualizzazione all&#39;altra, modificare la visualizzazione della pagina e visualizzare il nome del file di mappa selezionato.

  Le funzioni disponibili nella barra di navigazione sono illustrate come segue:

   - **Commutatore navigazione**: consente la navigazione diretta ad altre pagine - Editor o Home page:
   - **File mappa selezionato**: visualizza il nome del file mappa attualmente selezionato. Puoi aprirlo nell’editor o scegliere un file di mappa diverso per la console Mappa.
   - **Altre azioni**: fornisce opzioni per passare alla **interfaccia utente di Assets** e alle **impostazioni Workspace**. Per ulteriori dettagli, visualizzare la [barra delle schede](./web-editor-tab-bar.md).

  >[!NOTE]
  >
  > Se si utilizza Adobe Experience Manager Guides in una configurazione locale, l&#39;opzione Impostazioni Workspace continua a essere visualizzata come **Impostazioni** nel menu Altre azioni.

   - **Espandi visualizzazione**: consente di espandere la visualizzazione della pagina utilizzando l&#39;icona **Espandi**. In questa visualizzazione, la barra dell’intestazione è nascosta e lo spazio disponibile risulta quindi notevolmente ridotto. Per tornare alla visualizzazione standard, utilizzare l&#39;icona **Esci dalla visualizzazione espansa**.

  >[!NOTE]
  >
  > Se utilizzi Adobe Experience Manager Guides as a Cloud Service, nella barra di navigazione verrà visualizzata una funzionalità aggiuntiva [Assistente IA](./ai-assistant.md).

- (**B**) **Pannello sinistro**: il pannello sinistro consente di accedere rapidamente alle funzioni Generazione output, Creazione e gestione report, Baseline, Predefiniti condizione, Traduzione contenuto e Workfront (solo se configurata).

  Per ulteriori dettagli, consulta la sezione [Funzioni della console mappa](#map-console-features) di seguito.

## Funzioni della console mappa

Le seguenti funzionalità sono disponibili nel pannello sinistro quando si [apre un file di mappa DITA nella console Mappa](./open-files-map-console.md).

**Generazione output**

Con la console Map, puoi generare in modo efficiente output in vari formati, tra cui AEM Sites, PDF, HTML5, EPUB, JSON e output personalizzato tramite DITA-OT, la pubblicazione nativa su PDF e FMPS. È possibile generare l&#39;output per un&#39;intera mappa DITA oppure pubblicare selettivamente solo alcuni argomenti aggiornati. È inoltre possibile utilizzare la funzione di pubblicazione della linea di base per pubblicare selettivamente una versione specifica della mappa o dell&#39;argomento DITA.

Per ulteriori dettagli, visualizzare [Generazione output](./generate-output.md).

**Creazione e gestione dei report**

In una configurazione organizzativa, desideri verificare la completezza complessiva della documentazione tecnica prima di iniziare a lavorarci o a inviare i documenti in diretta. Tale esigenza diventa ancora più essenziale in ambienti multiutente e su larga scala. Con la console Map puoi accedere ai rapporti di Experience Manager Guides che forniscono un utile insight sullo stato complessivo del contenuto nell’archivio e sul modo in cui il contenuto viene utilizzato nel processo di documentazione.

Per ulteriori dettagli, visualizzare [i report in Experience Manager Guides](./reports-intro.md).

**Previsione**

Experience Manager Guides offre la funzione Baseline che consente di creare una versione degli argomenti e delle risorse da utilizzare per la pubblicazione o la traduzione. È inoltre possibile pubblicare più predefiniti di output della stessa mappa DITA in parallelo.

Scopri come [creare e gestire le baseline in Experience Manager Guides](./web-editor-baseline.md).

**Predefiniti condizione**

Experience Manager Guides consente di definire gli attributi negli argomenti DITA e di utilizzare il predefinito di condizione per specificare cosa accade con l&#39;attributo nell&#39;output finale. Ad esempio, puoi aggiungere nel contenuto attributi come versione 1.0 e versione 2.0 e utilizzare un predefinito di condizione per includere la versione 1.0 per la versione 1.0 ed escludere la versione 2.0. Allo stesso modo, è possibile aggiungere al contenuto attributi come OS Windows e OS Linux e quindi includere o escludere il contenuto rilevante per l&#39;output finale in base al sistema operativo.

Ulteriori informazioni su [Predefiniti condizione](./generate-output-use-condition-presets.md).

**Traduzione del contenuto**

Experience Manager Guides offre funzionalità avanzate che consentono di tradurre i contenuti in più lingue. I flussi di lavoro di traduzione umana e automatica sono supportati da Experience Manager Guides.

Nella console Mappa puoi accedere a tutte le opzioni necessarie per iniziare a utilizzare i flussi di lavoro di traduzione. Per ulteriori dettagli, visualizzare [Traduci contenuto](./translation.md).


**Workfront**

La funzione Workfront è presente anche nella console Mappa, che consente di lavorare con le attività di Adobe Workfront direttamente da Experience Manager Guides.

Scopri l&#39;integrazione di [Adobe Workfront in Experience Manager Guides](./workfront-integration.md).

Puoi accedere a questa funzione solo se l&#39;amministratore ha configurato l&#39;integrazione di **Adobe Workfront** nella tua istanza di Experience Manager Guides.
