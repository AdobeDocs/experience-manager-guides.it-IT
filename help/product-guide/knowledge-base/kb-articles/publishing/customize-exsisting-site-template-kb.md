---
title: Personalizzare i modelli di sito AEM esistenti per AEM Guides
description: Scopri come personalizzare i modelli di sito AEM esistenti per AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: d48709b8-f5b2-4545-ac65-838c5d8b1bae
source-git-commit: 4c564a0ffaa8f287bcaf012634d49dbf1e0682b4
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 1%

---

# Personalizzare i modelli di sito AEM esistenti per AEM Guides

Questa guida fornisce istruzioni dettagliate per personalizzare modelli di sito AEM esistenti da utilizzare con AEM Guides per generare AEM Sites da mappe e argomenti DITA.

Se utilizzi il modello predefinito AEM Guides (AEMG Docs), le configurazioni e i componenti sono già presenti e possono essere utilizzati così come sono per pubblicare i contenuti AEM Guides. Tuttavia, se desideri utilizzare i modelli AEM Sites esistenti con il branding personalizzato per pubblicare contenuti AEM Guides, segui i passaggi seguenti per allineare i modelli Sites ai requisiti di rendering di AEM Guides.


## Prerequisiti

- Disponi delle autorizzazioni appropriate e dell’accesso ai modelli di AEM.
- Comprendi i modelli modificabili di AEM e la struttura del sito AEM.
- È stata creata una gerarchia di siti esistente utilizzando modelli modificabili.
- Sono presenti almeno due modelli del progetto esistente:

   - **Modello per pagina contenitore documentazione** utilizzato per il rendering della mappa DITA come radice della documentazione.
   - **Modello per pagina argomenti** utilizzato per il rendering di singole pagine di argomenti DITA.

## Considerazioni sulla denominazione dei modelli

I nomi dei modelli variano in base alla configurazione del progetto. Ad esempio, nella configurazione OOTB AEMG Docs:

- Pagina contenitore documentazione: `/conf/AEMG-Docs-Site/settings/wcm/templates/kb-content`

- Pagina argomento: `/conf/AEMG-Docs-Site/settings/wcm/templates/topic-content`

**Personalizzazione:** Il processo di personalizzazione prevede due passaggi principali:

1. Configurazione del modello: identifica e configura i due modelli (contenitore e argomento).
2. Componenti delle guide di rendering: incorpora i componenti AEM Guides necessari per abilitare funzioni come TOC, navigazione e visualizzazione dei metadati.

## Configurazione del modello

Scegli e configura due modelli modificabili dal tuo sito AEM.

### Modello per pagina contenitore documentazione

Il modello Pagina contenitore documentazione viene utilizzato per creare la pagina contenitore documentazione prodotto con il rendering del contenuto di una mappa DITA.

- Funge da punto di ingresso o home page per un set specifico di documentazione (ad esempio, un manuale del prodotto o una guida).
- Aggiungi la proprietà id=&quot;category-page&quot; al jcr:content del nodo iniziale del modello. In questo modo tutte le pagine create da questo modello vengono trattate automaticamente come contenitori di documentazione da AEM Guides.

  ![Aggiunta id=&quot;category-page&quot;](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-id-category-page.png){width="650" align="left"}

- Aggiungi un componente Testo con la proprietà obbligatoria: text=&quot;$category.html$&quot;.

  ![Aggiunta componente testo](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component.png){width="650" align="left"}

- In genere include elementi di navigazione, come collegamenti a sezioni o argomenti all’interno della documentazione.
- Può essere personalizzato per includere branding, intestazioni, piè di pagina e altri elementi di progettazione.

**Caso d&#39;uso di esempio:**
Se si dispone di una mappa DITA per un manuale di prodotto, il modello di pagina del contenitore della documentazione genererà la home page per tale manuale, visualizzando una panoramica e i collegamenti ai singoli argomenti.

### Modello per pagina argomento

- Il modello **Pagina argomenti** viene utilizzato per creare pagine per singoli **argomenti DITA**.
- Ogni argomento di una mappa DITA viene visualizzato come una pagina separata che utilizza questo modello.
- Contiene un **componente testo** con la proprietà obbligatoria: text=&quot;$topic.content$&quot;.

  ![Aggiunta componente testo con proprietà obbligatoria](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component-mandatory-property.png){width="650" align="left"}

- Questo segnaposto viene sostituito con il contenuto effettivo dell&#39;argomento DITA durante la generazione del sito.
   - Il componente testo si trova in genere all&#39;interno di un **componente Container** per garantire layout e stile corretti.
   - Può essere personalizzato per includere intestazioni, piè di pagina ed elementi di navigazione coerenti in tutte le pagine degli argomenti.

**Caso d&#39;uso di esempio:**
Se si dispone di un argomento DITA relativo alle &quot;Istruzioni di installazione&quot;, il modello di pagina dell&#39;argomento genererà una pagina che visualizza il contenuto dell&#39;argomento.

**Componente contenitore:**

![Aggiunta del componente contenitore](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-component.png){width="650" align="left"}

>[!NOTE]
>
> Assicurarsi che i componenti che utilizzano Sling:resourceType in `wcm/foundation/components` siano migrati al `core/wcm/components` corrispondente.

Aggiungi lo stesso (contenitore e componente testo) nella struttura dello stesso modello:

![Aggiunta del contenitore e del componente testo](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-and-text-component.png){width="650" align="left"}

## Componenti delle guide di rendering nei modelli personalizzati

Per abilitare le funzioni dei componenti core di AEM Guides, come il sommario, il reindirizzamento delle pagine, la navigazione e la visualizzazione dei metadati, è necessario includere componenti AEM Guides specifici nei modelli personalizzati. Questi componenti devono essere aggiunti esplicitamente ai corrispondenti modelli modificabili (Pagina contenitore documentazione o Pagina argomento) per garantire che la funzionalità prevista sia disponibile durante la generazione del sito e il runtime.

Per l’elenco dei componenti e del loro utilizzo, consulta la tabella seguente:

| Funzione | Nome componente | Descrizione | Modello consigliato |
|---|---|---|---|
| Sommario | guidesienavigation | Riproduce il sommario completo dalla mappa DITA | Contenitore documentazione |
| Reindirizzamento pagina | childredirect | Reindirizza alla prima pagina dell&#39;argomento della mappa | Contenitore documentazione |
| Mini sommario | minitoc | Visualizza il sommario dell&#39;argomento corrente | Pagina argomento |
| Ultimo aggiornamento | pageproperty | Visualizza la data dell’ultima modifica | Pagina argomento |
| Cercapersone | cercapersone | Consente la navigazione tra le pagine degli argomenti precedenti e successivi | Pagina argomento |
| Navigazione lingua | languagenavigation | Consente di passare da una versione all&#39;altra della lingua | Entrambi i modelli |


## Casi di utilizzo dei componenti

- **Componente di reindirizzamento (childredirect):** Aggiungerlo al modello di pagina del contenitore della documentazione in modo che la home page del prodotto generata dalla mappa DITA venga automaticamente reindirizzata alla prima pagina dell&#39;argomento. Se la pagina del contenitore della documentazione è progettata per fungere da pagina home indipendente con componenti e layout personalizzati, questo componente non è richiesto.

- **Sommario (guida alla navigazione):** Aggiungilo al modello della pagina dell&#39;argomento per visualizzare un sommario navigabile insieme al contenuto dell&#39;argomento. Il sommario è derivato dalla mappa DITA e consente agli utenti di spostarsi tra gli argomenti di pari livello.


## Abilitazione delle librerie client delle guide

Per impostazione predefinita, le librerie client (clientlibs) fornite nel pacchetto di componenti AEM Guides non vengono applicate ai modelli personalizzati. Per abilitarli:

1. **Modifica modello:**

   1. Apri **Pagina prodotto** in **Modalità editor**.
   2. Seleziona **Modifica modello** (verrà aperto un URL come conf/settings/wcm/templates/structure.html).

      ![Modifica modello](/help/product-guide/knowledge-base/kb-articles/assets/publishing/edit-template.png){width="650" align="left"}

2. **Aggiorna criterio pagina:**

   1. Vai al pulsante **Informazioni pagina** e seleziona **Criterio pagina**.
   2. Aggiungi le seguenti librerie client:
      - **Librerie client**
      - **Intestazione pagina JavaScript per librerie client**

3. **Salva modifiche:** Salva il modello dopo l&#39;aggiunta delle librerie client richieste.

   ![Aggiungi librerie client](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-client-libraries.png){width="650" align="left"}


>[!NOTE]
>
> Assicurati che i modelli siano testati in un ambiente non di produzione prima di distribuirli in produzione.<br><br>Per ulteriori informazioni, consulta la documentazione ufficiale di [AEM Guides](https://experienceleague.adobe.com/it/docs/experience-manager-guides/using/overview) e [AEM Sites](https://experienceleague.adobe.com/it/docs/experience-manager-core-components/using/get-started/authoring).
