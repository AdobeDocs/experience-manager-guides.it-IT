---
title: Scarica e installa modelli AEM Sites per Cloud Services
description: Scopri come scaricare e installare i modelli di AEM Sites per i servizi cloud
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 0%

---

# Scaricare e installare modelli AEM Sites

Questa guida fornisce istruzioni dettagliate per impostare e configurare il modello AEM Guides più recente per la generazione di pagine AEM Sites in un ambiente cloud. Segui questi passaggi per installare i pacchetti richiesti, creare e configurare i predefiniti e generare AEM Sites.

## Prerequisiti

Le schede seguenti forniscono i prerequisiti necessari in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

- **Adobe Experience Manager (AEM) Cloud**: istanza in esecuzione di **AEM as a Cloud Service** con **AEM Guides 2502 o versioni successive**.

- **Autorizzazioni richieste**: è necessario disporre delle seguenti autorizzazioni:

   - Accedi a **Cloud Manager** per distribuire i pacchetti.
   - Accesso a **Archivio Git** associato al tuo ambiente.
   - Autorizzazioni per creare e modificare i predefiniti in AEM Guides.

- **Scarica pacchetti**: scarica i seguenti pacchetti dal portale di distribuzione software:

   - Pacchetto componenti: guides-components.all-1.x.0.zip
   - Modello siti: aemg-docs-1.x.0.zip

>[!TAB On-Premise]

- **Adobe Experience Manager (AEM):** un&#39;istanza in esecuzione di **AEM 6.5** con **Service Pack** 21, 20 e 19 e **AEM Guides 4.6.0** o versioni successive installate.

- **Autorizzazioni richieste**: assicurati di disporre delle seguenti autorizzazioni:

   - Accedi a **Portale di distribuzione software** per scaricare i pacchetti richiesti
   - Accedi a **Gestione pacchetti CRX** per installare i pacchetti in AEM.
   - Autorizzazioni per creare e modificare i predefiniti in AEM Guides.

- **Scarica pacchetti**: scarica i seguenti pacchetti da **Portale di distribuzione software**:

   - Pacchetto componenti: on-prem-guides-components.all-1.x.0.zip
   - Pacchetto Sites: aemg-docs.all-1.x.0.zip

>[!ENDTABS]


## Installazione del pacchetto

Le seguenti schede forniscono istruzioni per l’installazione del pacchetto in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Installa il pacchetto **Components (guides-components.all-1.x.x.zip)** ed esegui i seguenti passaggi

1. **Clona archivio Git:**
   1. Passa a **Archivi** nel pannello a sinistra di Cloud Manager.
   2. Seleziona **Accedi a dati archivio** e copia il comando di clonazione Git.

      ![Seleziona informazioni archivio di accesso](/help/product-guide/knowledge-base/kb-articles/assets/publishing/access-repo.png){width="350" align="left"}

   3. Clona l’archivio sul sistema locale utilizzando il nome utente e la password forniti (genera la password se richiesta).
2. **Aggiungi pacchetto al bundle Maven:**
   1. Nell’archivio clonato localmente, crea un nuovo bundle Maven o aggiungilo a uno esistente.
   2. Verificare che l&#39;installazione della struttura `/jcr_root/apps/fmdita/` esista nel progetto Maven.

      ![Struttura nel progetto Maven](/help/product-guide/knowledge-base/kb-articles/assets/publishing/maven-structure.png){width="650" align="left"}


   3. Inserisci il file guides-components.all-1.x.x.zip scaricato nella cartella di installazione.

3. **Aggiorna filters.xml:**

   1. Aprire il file filters.xml che si trova nella cartella META-INF della directory del contenuto padre.
   2. Aggiungi il seguente filtro: radice filtro=`/apps/fmdita` modalità=`merge`/


      ![Aggiungi filtro](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-filter-xml.png){width="650" align="left"}


4. **Configura pom.xml:** Aggiorna il file pom.xml in base ai requisiti dell&#39;ambiente.
5. **Invia modifiche ed esegui pipeline:**
   1. Invia le modifiche all’archivio Git principale.
   2. Passa a **Pipeline** in Cloud Manager ed esegui la pipeline per l’ambiente desiderato.
6. **Verifica l&#39;installazione:** Una volta completata la distribuzione, il pacchetto dei componenti verrà installato nell&#39;ambiente AEM Cloud.

>[!TAB On-Premise]

1. **Installare il pacchetto componenti:**
   1. Passare a [**Gestione pacchetti CRX**](http://&lt;tua-istanza-aem>/crx/packmgr).
   2. Carica e installa il pacchetto on-prem-guides-components.all-1.x.0.zip.

2. **Installare il pacchetto Sites:** Caricare e installare il pacchetto aemg-docs.all-1.x.0.zip utilizzando Gestione pacchetti di CRX.

>[!ENDTABS]

## Crea sito utilizzando i modelli installati (per Cloud Service)

1. **Importa modello siti:**
   1. Vai alla pagina AEM Sites (servername/sites.html/content).
   2. Seleziona **Crea** > **Sito** dal modello.
   3. Importa il modello Sites aemg-docs-1.x.x.zip utilizzando l&#39;opzione **Importa**.
2. **Seleziona modello:** Seleziona **Documenti AEMG 1.x.x**, quindi seleziona **Successivo**.
3. **Immetti i dettagli del sito:** Immetti il **Titolo sito** e il **Nome sito**.

   ![Crea sito](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-site.png){width="350" align="left"}

4. Seleziona **Crea**.

## Crea predefinito per sito AEM

1. **Crea un nuovo predefinito:**
   1. Apri una mappa DITA in AEM Guides e passa al pannello **Output**.
   2. Selezionare **Crea predefinito**.
   3. Seleziona il tipo come **AEM Sites**.
   4. Immettere un nome per il predefinito.
   5. Deseleziona l&#39;impostazione **Usa mapping di componenti legacy**.
   6. Seleziona **Aggiungi** per creare il predefinito.

      ![Crea nuovo predefinito per sito AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/new-output-preset.png){width="350" align="left"}


2. **Configura predefinito per sito AEM:** Sono disponibili due opzioni per configurare il sito preconfigurato:

   **Opzione 1: utilizzare il menu a discesa Sito**

   1. Seleziona **Sito** come creato in precedenza (ad esempio, Sito documenti AEMG).
   2. Verificare che il percorso di pubblicazione **1&rbrace; e il modello di pagina** Argomento **siano impostati automaticamente su:**
      - Percorso di pubblicazione: Cloud Service: `/content/AEMG-Docs-Site/en/docs/product` e On-Premise: `aemg-docs/en/docs/product1`
      - Modello pagina argomento: pagina argomento

      ![Utilizza il menu a discesa del sito per configurare il sito AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown-cs.png){width="350" align="left"}

   **Opzione 2: utilizzare il percorso del sito**

   1. Impostare il **percorso sito** manualmente come `/content/AEMG-Docs-Site/en/docs/product` per Cloud Service e `/content/aemg-docs/en/docs/product1` per On-Premise.
   2. Verificare che il modello **Pagina argomento** sia impostato automaticamente su Pagina argomento.

      Per Cloud Service:

      ![Utilizzare il percorso del sito per configurare il sito AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path-cs.png){width="650" align="left"}

      Per On-Premise:

      ![Usa percorso sito](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path.png){width="350" align="left"}

3. **Salva il predefinito:** Salva le modifiche apportate al predefinito.

## Generare AEM Sites

1. **Genera sito:**
   1. Con il predefinito configurato, genera il sito AEM per la mappa DITA corrispondente.
   2. Il sito generato sarà disponibile nel percorso `/content/AEMG-Docs-Site/en/docs/product` per Cloud Service e `/content/aemg-docs/en/docs/product1` per On-Premise.
2. **Modificare il percorso di generazione predefinito (facoltativo):** Se si desidera modificare il percorso predefinito per la generazione del sito, effettuare le seguenti operazioni:
   1. Passa a **AEM Sites**.
   2. Crea una nuova pagina di prodotto nella struttura del sito OOTB.
   3. Passa a **Documenti AEMG** > **Inglese** > **Documenti**.

      ![Crea pagina](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-page-cs.png){width="650" align="left"}

   4. Selezionare il riquadro **Home page**, quindi selezionare **Avanti**.

      ![Seleziona riquadro principale](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-tile-cs.png){width="650" align="left"}

   5. Immetti il **Titolo** e il **Nome** per la pagina.
   6. Seleziona **Crea**.

>[!NOTE]
>
> Per la configurazione di Cloud Service, assicurati che tutte le configurazioni siano testate in un ambiente non di produzione prima di implementarle in produzione. <br><br> Per ulteriori informazioni, consulta la [documentazione ufficiale sulla distribuzione ad AEM as a Cloud Service](https://experienceleague.adobe.com/it/docs/experience-manager-cloud-service/content/implementing/deploying/overview).
