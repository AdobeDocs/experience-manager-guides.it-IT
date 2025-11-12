---
title: Scarica e installa modelli AEM Sites per Cloud Services
description: Scopri come scaricare e installare i modelli di AEM Sites per i servizi cloud
feature: Installation
role: Admin
level: Experienced
exl-id: 67f7ff26-fbc7-426c-aa7d-9bf4debf05d8
source-git-commit: 4c564a0ffaa8f287bcaf012634d49dbf1e0682b4
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 1%

---

# Scaricare e installare modelli di AEM Sites (servizi cloud)

Questa guida fornisce istruzioni dettagliate per impostare e configurare il modello AEM Guides più recente per la generazione di pagine AEM Sites in un ambiente cloud. Segui questi passaggi per installare i pacchetti richiesti, creare e configurare i predefiniti e generare AEM Sites.

## Prerequisiti

Prima di procedere con la configurazione, verifica che siano soddisfatti i seguenti prerequisiti:

- **Adobe Experience Manager (AEM) Cloud**: istanza in esecuzione di **AEM as a Cloud Service** con **AEM Guides 2502 o versioni successive**.

- **Autorizzazioni richieste**: è necessario disporre delle seguenti autorizzazioni:

   - Accedi a **Cloud Manager** per distribuire i pacchetti.
   - Accesso a **Archivio Git** associato al tuo ambiente.
   - Autorizzazioni per creare e modificare i predefiniti in AEM Guides.

- **Scarica pacchetti**: scarica i seguenti pacchetti dal portale di distribuzione software:

   - Pacchetto componenti: guides-components.all-1.x.0.zip
   - Modello siti: aemg-docs-1.x.0.zip

## Installazione del pacchetto tramite distribuzione cloud

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

## Crea sito utilizzando i modelli installati

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

      ![Crea nuovo predefinito per sito AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-output-preset.png){width="350" align="left"}

   6. Seleziona **Aggiungi** per creare il predefinito.
2. **Configura predefinito per sito AEM:** Sono disponibili due opzioni per configurare il sito preconfigurato:

   **Opzione 1: utilizzare il menu a discesa Sito**

   1. Seleziona **Sito** come creato in precedenza (ad esempio, Sito documenti AEMG).
   2. Verificare che il percorso di pubblicazione **1&rbrace; e il modello di pagina** Argomento **siano impostati automaticamente su:**
      - Percorso di pubblicazione: `/content/AEMG-Docs-Site/en/docs/product`
      - Modello pagina argomento: pagina argomento

      ![Utilizza il menu a discesa del sito per configurare il sito AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown-cs.png){width="350" align="left"}

   **Opzione 2: utilizzare il percorso del sito**

   1. Imposta il **percorso sito** manualmente come `/content/AEMG-Docs-Site/en/docs/product`.
   2. Verificare che il modello **Pagina argomento** sia impostato automaticamente su Pagina argomento.

      ![Utilizzare il percorso del sito per configurare il sito AEM](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path-cs.png){width="650" align="left"}

3. **Salva il predefinito:** Salva le modifiche apportate al predefinito.

## Generare AEM Sites

1. **Genera sito:**
   1. Con il predefinito configurato, genera il sito AEM per la mappa DITA corrispondente.
   2. Il sito generato sarà disponibile nel percorso: `/content/AEMG-Docs-Site/en/docs/product`.
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
> Assicurati che tutte le configurazioni siano testate in un ambiente non di produzione prima di implementarle in produzione. <br><br> Per ulteriori informazioni, consulta la [documentazione ufficiale sulla distribuzione ad AEM as a Cloud Service](https://experienceleague.adobe.com/it/docs/experience-manager-cloud-service/content/implementing/deploying/overview).
