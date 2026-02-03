---
title: Experience Manager Guides e Edge Delivery Services (Beta)
description: Scopri in che modo Edge Delivery Services (Beta) estende le possibilità di authoring e pubblicazione per Experience Manager Guides.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 7ca2eeb0356f3c82a8d970f291006fc6d19aca23
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 0%

---

# Experience Manager Guides e Edge Delivery Services (Beta)

Adobe Experience Manager Guides consente di pubblicare i contenuti DITA direttamente in Edge Delivery Services (EDS), attualmente disponibili in *Beta*, tramite un profilo di pubblicazione dedicato basato su GitHub. Questa funzionalità consente alle organizzazioni di fornire esperienze di documentazione reattiva e a elevate prestazioni, mantenendo al contempo i flussi di lavoro di authoring basati su DITA in Experience Manager Guides.

Per ulteriori dettagli sull&#39;utilizzo di EDS in Adobe Experience Manager, visualizzare [Panoramica di Edge Delivery Services](https://experienceleague.adobe.com/it/docs/experience-manager-cloud-service/content/edge-delivery/overview).

Per abilitare la pubblicazione da Experience Manager Guides a EDS (Beta), devi completare una serie di passaggi di configurazione in GitHub e Experience Manager Guides. Le sezioni seguenti descrivono ogni passaggio in sequenza e spiegano come interagiscono nel flusso di lavoro di pubblicazione complessivo.

1. [Configurazione di GitHub per EDS (Beta)](#set-up-and-configure-github-for-eds-beta)
2. [Creare e configurare un profilo di pubblicazione per EDS (Beta) in Experience Manager Guides](#create-and-configure-a-publish-profile-for-eds-beta-in-experience-manager)
3. [Personalizzare l’output utilizzando i blocchi EDS](#customize-output-using-eds-blocks)

Per una procedura dettagliata e rapida, visualizza [Pubblicazione in AEM Guides](https://experienceleague.adobe.com/it/docs/experience-manager-guides/using/knowledge-base/expert-session/publishing-in-aem-guides-aug25).



## Configurazione di GitHub per EDS (Beta)

Questa sezione descrive come impostare e configurare GitHub per l’utilizzo con EDS (Beta). Include la creazione di un archivio utilizzando la piattaforma standard Adobe, la connessione di GitHub a Adobe Experience Manager tramite AEM Code Sync, la configurazione delle applicazioni GitHub e OAuth richieste e la definizione del punto di montaggio dell’archivio utilizzato per la pubblicazione dei contenuti.

### Creare un archivio GitHub per EDS (Beta)

EDS (Beta) richiede un archivio GitHub con una struttura predefinita. Adobe fornisce un archivio standard ufficiale appositamente progettato per gli utenti di Experience Manager Guides.

Per creare l’archivio, effettua le seguenti operazioni:

1. Aprire l&#39;archivio modelli standard di Experience Manager Guides [`aem-guides-boilerplate`](https://github.com/adobe/aem-guides-boilerplate).
   ![](assets/eds-boilerplate-template.png){align="left"}

2. Crea un nuovo archivio utilizzando questo modello. Scopri come [creare un archivio da un modello](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template). Verificare che la visibilità dell&#39;archivio sia impostata su *Pubblico* in modo che sia accessibile da EDS.

   ![](assets/eds-create-new-repo.png){align="left"}

L’archivio viene ora creato e allineato con la struttura del modello standard.

![](assets/eds-repo-created-github-view.png){align="left"}

### Collegare GitHub ad Adobe tramite AEM Code Sync

Adobe Experience Manager utilizza un&#39;applicazione GitHub denominata **AEM Code Sync** per inviare contenuti da Experience Manager Guides a GitHub.

Per installare e configurare l&#39;applicazione *AEM Code Sync*, effettuare le seguenti operazioni:

1. Passare alla pagina [Sincronizzazione codice AEM](https://github.com/apps/aem-code-sync) e selezionare **Installa**.
2. *AEM Code Sync* monitora le modifiche all&#39;archivio e assicura che gli aggiornamenti vengano inviati correttamente a GitHub.

   >[!NOTE]
   >
   > Durante l’installazione dell’applicazione, assicurati di utilizzare lo stesso account GitHub a cui appartiene l’archivio.

   ![](assets/eds-aem-code-sync-page.png){align="left"}
3. Nella pagina successiva, concedi l’accesso all’archivio creato. A questo scopo, seleziona l&#39;opzione **Seleziona solo archivi**, quindi seleziona il tuo archivio dal menu a discesa.

   ![](assets/eds-aem-code-sync-install-authorize.png){width="350" align="left"}
4. Selezionare **Installa e autorizza**.

Sei stato reindirizzato alla pagina di installazione di GitHub, a conferma della corretta registrazione dell&#39;applicazione *AEM Code Sync*. Puoi anche salvare gli URL di anteprima e live del sito web da questa pagina.

![](assets/eds-aem-code-sync-registered.png){align="left"}

### Creare una nuova app GitHub

1. Su GitHub, passa alla barra laterale a sinistra e seleziona **Impostazioni sviluppatore**.
2. Nella barra laterale sinistra, seleziona **App GitHub**.
3. Seleziona **Nuova app GitHub**.

   ![](assets/eds-new-github-app.png){width="650" align="left"}
4. Nella pagina **Registra nuova app GitHub**, fornisci i dettagli seguenti:
   - **Nome app GitHub**: immetti un nome per l&#39;app. Ad esempio, `USERNAME-eds-app` dove USERNAME è il tuo nome utente GitHub.
   - **URL home page**: immettere l&#39;URL dell&#39;istanza di Experience Manager Guides.

     URL di esempio (formato): `https://<aem-author-url>/libs/fmdita/clientlibs/xmleditor/page.html`

     URL di esempio: `https://author-p16602-e335172-cmstg.adobeaemcloud.com/libs/fmdita/clientlibs/xmleditor/page.html`
   - **URL callback**: uguale all&#39;URL della home page.
   - **URL webhook**: disabilita questa opzione.
   - **Autorizzazioni archivio**: impostare **Autorizzazioni di lettura e scrittura** per *Azioni, Amministrazione e Attestazione*.
5. Seleziona **Crea app GitHub**.

L&#39;app è ora pronta. Sei stato reindirizzato alla pagina **Impostazioni** dell&#39;app GitHub.

![](assets/eds-github-app-registered-page.png){align="left"}

### Crea una nuova app OAuth

È necessaria un’app OAuth per autenticare gli utenti durante la creazione di un profilo di pubblicazione EDS (Beta) in Experience Manager Guides. Abilita un flusso di accesso sicuro utilizzando un *ID client* e un *Segreto client*.

Per creare una nuova app OAuth, effettua le seguenti operazioni:

1. Su GitHub, passa alla barra laterale a sinistra e seleziona **Impostazioni sviluppatore**.
2. Nella barra laterale sinistra, seleziona **App OAuth**.
3. Seleziona **Nuova app OAuth**.

   ![](assets/eds-new-oauth-app.png){width="650" align="left"}
4. Registra l’applicazione fornendo i seguenti dettagli obbligatori:
   - **Nome applicazione**: immettere il nome dell&#39;archivio EDS
   - **URL home page**: immettere l&#39;URL dell&#39;istanza di Experience Manager Guides. Per il formato URL di esempio, fare riferimento al passaggio 4 della sezione [Creare una nuova app GitHub](#create-a-new-github-app).
   - **URL callback di autorizzazione**: uguale all&#39;URL della home page
5. Selezionare l&#39;opzione **Abilita flusso dispositivo**, quindi selezionare **Registra applicazione** per completare la registrazione.

   ![](assets/eds-new-github-app-register.png){width="650" align="left"}

L&#39;app è ora pronta. Annota l&#39;*ID client*. Puoi generare fino a cinque *segreti client* ora o in seguito durante la configurazione del profilo di pubblicazione in Experience Manager Guides.

![](assets/eds-new-oauth-app-page.png){align="left"}


### Configurare l’URL del punto di montaggio nell’archivio EDS (Beta)

EDS (Beta) legge il contenuto da un percorso di archivio GitHub definito come URL *mountpoint* nel file `fstab.yaml`.

Per configurare l&#39;URL del punto di attivazione nel file `fstab.yaml`:

1. Apri il file `fstab.yaml` nel tuo archivio e aggiorna quanto segue:
   - `your-user-name`
   - `your-repo-name`

   >[!NOTE]
   >
   > Nell&#39;URL del punto di attivazione, `main` indica il ramo in cui si desidera pubblicare il contenuto e `docs` indica la cartella principale dell&#39;archivio EDS (Beta) su cui si sta lavorando. Se preferisci modificare il nome del ramo in GitHub, devi aggiornare lo stesso nome di ramo nell&#39;URL *punto_att* (nel file `fstab.yaml`) e nel profilo di pubblicazione EDS corrispondente in Experience Manager Guides.

   ![](assets/eds-fstab-yaml-file.png){width="650" align="left"}
2. Seleziona **Commit changes**, immetti i dettagli del commit e conferma.
3. Torna a [Impostazioni sviluppatore](https://github.com/settings/apps), individua l&#39;app e seleziona **Modifica**.

   ![](assets/eds-edit-github-app.png){width="650" align="left"}
4. Passare alla pagina **Installa app** e selezionare **Installa**.

   ![](assets/eds-install-eds-app.png){width="650" align="left"}
5. Ripeti i passaggi 2 e 3 dalla sezione [Connetti GitHub ad Adobe tramite AEM Code Sync](#connect-github-to-adobe-via-aem-code-sync) per autorizzare l&#39;archivio.

## Creare e configurare un profilo di pubblicazione per EDS (Beta) in Experience Manager

Le sezioni seguenti descrivono ogni passaggio in sequenza e spiegano come impostare il profilo di pubblicazione EDS (Beta), configurare un predefinito di output e generare l’output utilizzando EDS (Beta) in Experience Manager Guides.

### Creare il profilo di pubblicazione EDS (Beta)

1. Vai a **[Impostazioni Workspace](/help/product-guide/cs-install-guide/workspace-settings.md)** **>** **Pubblica profili**.
2. Seleziona l&#39;icona **+** per creare un nuovo profilo di pubblicazione e fornisci i seguenti dettagli:
   - **Tipo di server**: seleziona **Edge Delivery Services GitHub (Beta)** dal menu a discesa.
   - **Nome**: immettere un nome per il profilo.
   - **Nome archivio**: utilizza il nome dell&#39;archivio GitHub creato dalla boilerplate.
   - **Nome utente**: immetti il nome utente GitHub.
   - **Ramo principale**: impostato su principale (impostazione predefinita).
   - **Cartella principale**: impostata su docs (impostazione predefinita).
   - **ID client e segreto client**: recuperali dall&#39;app GitHub. Per ulteriori informazioni, consulta [Creare una nuova app OAuth](#create-a-new-oauth-app).
3. Seleziona **Accesso** per eseguire l&#39;autenticazione.

   ![](assets/eds-publish-profile.png){width="650" align="left"}
4. Al completamento dell&#39;autenticazione, selezionare **Salva**.

Il profilo di pubblicazione EDS (Beta) è ora configurato.

### Creazione di un predefinito di output per EDS (Beta) e generazione di output

1. Apri la mappa nella console Mappa.
2. Nella scheda **Predefiniti di output**, selezionare **+** per creare un nuovo predefinito di output.
3. Nella finestra di dialogo **Nuovo predefinito di output**, fornisci i seguenti dettagli:
   - **Tipo**: Seleziona **Servizio Edge Delivery (Beta)**
   - **Nome**: specifica un nome per questo predefinito
4. Seleziona **Aggiungi**.

   ![](assets/eds-output-preset.png){width="650" align="left"}
5. Apri il predefinito di output EDS (Beta) appena creato e passa alla scheda **Config**.
   - Seleziona il profilo di pubblicazione creato nel passaggio precedente.
   - Abilita **Push to live**.

   Quando **Invia a live** è abilitato, l&#39;output generato viene confermato in GitHub e gli aggiornamenti corrispondenti vengono propagati immediatamente al sito Web live.

   ![](assets/eds-output-preset-config-tab.png){width="650" align="left"}

6. Selezionare **Salva**, quindi **Genera output**.

>[!NOTE]
>
> L&#39;output generato viene archiviato nella cartella **docs** dell&#39;archivio EDS (Beta).

Viene ora generato l’output EDS (Beta). Il contenuto viene presentato in un layout pulito e reattivo. Include elementi regolari come il titolo della pagina, le breadcrumb, il contenuto del corpo e tutti i blocchi utilizzati nell’argomento. Il sommario a sinistra (generato dalla mappa) consente di navigare tra gli argomenti, mentre un mini-sommario a destra evidenzia le sezioni all’interno della pagina corrente. L’intero output è completamente reattivo, garantendo un’esperienza di lettura ottimizzata e coerente tra i dispositivi.

![](assets/eds-site-output.png){align="left"}

## Personalizzare l’output utilizzando i blocchi EDS

EDS utilizza `blocks` per controllare lo stile e la visualizzazione delle diverse parti del contenuto. Puoi modificare i blocchi esistenti o crearne di personalizzati.

Gli esempi descritti di seguito descrivono come personalizzare un blocco esistente e crearne uno nuovo per applicare uno stile all&#39;output finale EDS (Beta) in Experience Manager Guides.

### Personalizzare un blocco di breadcrumb per aggiornarne il colore del testo

Le breadcrumb vengono utilizzate in più pagine per aiutare gli utenti a capire dove si trovano nella documentazione. Poiché questo blocco viene visualizzato in modo coerente in tutto il sito web, l’aggiornamento dello stile consente un aggiornamento unificato del design.

Per personalizzare un blocco di breadcrumb per aggiornarne il colore del testo, effettua le seguenti operazioni:

1. Vai all&#39;archivio GitHub e apri la cartella `blocks`.
2. Seleziona il blocco **breadcrumb**.

   ![](assets/eds-breadcrumbs.png){width="650" align="left"}
3. Aprire il file `css` e aggiornare il colore del testo.
4. Apporta le modifiche a GitHub.
5. Aggiorna il sito web live per visualizzare gli aggiornamenti.

### Aggiornare gli script EDS (Beta) per creare un elemento personalizzato nell’output pubblicato

In alcuni casi, potrebbe essere utile applicare uno stile solo a una parte specifica del contenuto. Per ottenere questo risultato, esegui i seguenti passaggi utilizzando un blocco personalizzato.

1. Aprire il file dell&#39;argomento e selezionare il testo all&#39;interno di un elemento tag.

   Nella schermata seguente, il contenuto all&#39;interno del tag `example` è selezionato.
   ![](assets/eds-example-tag-org-output.png){width="650" align="left"}
2. Per configurare il testo all&#39;interno del tag `example`:
   - Passa a **Proprietà contenuto**.
   - Aggiungi l&#39;attributo `outputclass`.
   - Imposta il relativo valore su `example eds-force-block`.
   - Seleziona **Aggiungi**.
     ![](assets/eds-example-tag.png){width="650" align="left"}
3. Salvate e rigenerate l&#39;output.
4. Creare una nuova cartella con lo stesso nome di `outputclass` nella directory `blocks`. Scopri come [aggiungere file a un repository](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository#adding-a-file-to-a-repository-using-the-command-line).

   ![](assets/eds-example-folder.png){width="650" align="left"}
5. Aggiungere i file richiesti `css` e facoltativi `js`.

   ![](assets/eds-example-folder-subfolders.png){width="650" align="left"}
6. Eseguire il commit delle modifiche e rigenerare l&#39;output.

Il contenuto selezionato ora visualizza lo stile personalizzato definito nel blocco.

![](assets/eds-example-output.png){width="650" align="left"}