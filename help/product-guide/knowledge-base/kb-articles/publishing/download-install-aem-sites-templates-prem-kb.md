---
title: Scarica e installa modelli AEM Sites per On-Premise Services
description: Scopri come scaricare e installare i modelli di AEM Sites per in Prem Services
feature: Installation
role: Admin
level: Experienced
source-git-commit: 20ba7f4582f1d155e555c9ff3ac58e1e3c400765
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Scaricare e installare modelli di AEM Sites (servizi on-premise)

Questa guida fornisce istruzioni dettagliate per impostare e configurare il modello AEM Guides più recente per la generazione di AEM Sites. Segui questi passaggi per installare i pacchetti richiesti, creare e configurare i predefiniti e generare AEM Sites.

## Prerequisiti

Prima di procedere con la configurazione, verifica che siano soddisfatti i seguenti prerequisiti:

- **Adobe Experience Manager (AEM):** un&#39;istanza in esecuzione di **AEM 6.5** con **Service Pack** 21, 20 e 19 e **AEM Guides 4.6.0** o versioni successive installate.

- **Autorizzazioni richieste**: assicurati di disporre delle seguenti autorizzazioni:

   - Accedi a **Portale di distribuzione software** per scaricare i pacchetti richiesti
   - Accedi a **Gestione pacchetti CRX** per installare i pacchetti in AEM.
   - Autorizzazioni per creare e modificare i predefiniti in AEM Guides.

- **Scarica pacchetti**: scarica i seguenti pacchetti da **Portale di distribuzione software**:

   - Pacchetto componenti: on-prem-guides-components.all-1.x.0.zip
   - Pacchetto Sites: aemg-docs.all-1.x.0.zip

## Installazione dei pacchetti tramite Gestione pacchetti di CRX

1. **Installare il pacchetto componenti:**
   1. Passare a [**Gestione pacchetti CRX**](http://&lt;tua-istanza-aem>/crx/packmgr).
   2. Carica e installa il pacchetto on-prem-guides-components.all-1.x.0.zip.

2. **Installare il pacchetto Sites:** Caricare e installare il pacchetto aemg-docs.all-1.x.0.zip utilizzando Gestione pacchetti di CRX.


## Creare e configurare il predefinito per sito AEM

1. **Crea un nuovo predefinito:**
   1. Apri una mappa DITA in AEM Guides e passa al pannello **Output**.
   2. Selezionare **Crea predefinito**.
   3. Seleziona il tipo come **AEM Sites**.
   4. Immettere un nome per il predefinito.
   5. Deseleziona l&#39;impostazione **Usa mapping di componenti legacy**.
   6. Seleziona **Aggiungi** per creare il predefinito.

      ![Finestra di dialogo Nuovo predefinito di output](/help/product-guide/knowledge-base/kb-articles/assets/publishing/new-output-preset.png){width="350" align="left"}


2. **Configura predefinito per sito AEM:** Sono disponibili due opzioni per configurare il sito preconfigurato:

   **Opzione 1: utilizzare il menu a discesa Sito**

   1. Seleziona **Sito** come **Documenti AEMG**.
   2. Verificare che il **percorso di pubblicazione** e il **modello pagina argomento** siano impostati automaticamente su:
      - Percorso di pubblicazione: aemg-docs/en/docs/product1
      - Modello pagina argomento: pagina argomento.

      ![Usa elenco a discesa del sito](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown.png){width="350" align="left"}

   **Opzione 2: utilizzare il percorso del sito**

   1. Imposta il **percorso sito** manualmente come /content/aemg-docs/en/docs/product1.
   2. Verificare che il **modello pagina argomento** sia impostato automaticamente su Pagina argomento.

      ![Usa percorso sito](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path.png){width="350" align="left"}

3. **Salva il predefinito:** Salva le modifiche apportate al predefinito.

## Generare AEM Sites

1. **Genera sito:**
   1. Con il predefinito configurato, ora puoi generare il sito AEM per la mappa DITA corrispondente.
   2. Il sito generato sarà disponibile nel percorso: /content/aemg-docs/en/docs/product1.
2. **Modificare il percorso di generazione predefinito (facoltativo):** Se si desidera modificare il percorso predefinito per la generazione del sito, effettuare le seguenti operazioni:

   1. Passa a **AEM Sites**.
   2. Crea una nuova pagina di prodotto nella struttura del sito OOTB.
   3. Passa a **Documenti AEMG** > **Inglese** > **Documenti**.

      ![Crea pagina nella struttura del sito AEM ](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-page.png){width="350" align="left"}

   4. Selezionare il riquadro **Home page**, quindi selezionare **Avanti**.

      ![Seleziona riquadro pagina iniziale](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-page-tile.png){width="350" align="left"}

   5. Immetti il **Titolo** e il **Nome** per la pagina.
   6. Seleziona **Crea**.

