---
title: Best practice per la traduzione dei contenuti
description: Conoscere le best practice per la traduzione dei contenuti in AEM Guides. Scopri come configurare il servizio di traduzione, creare un nuovo progetto di traduzione e avviare il processo di traduzione.
feature: Translation
role: User
hide: true
exl-id: 09e813fd-ec22-4d2e-9ee7-098d562ad44f
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 1%

---

# Best practice per la traduzione dei contenuti {#id1678G0S702F}

Considera il seguente punto per la traduzione del contenuto:

- I nomi delle cartelle e dei file devono essere conformi agli standard di denominazione dei file, ad esempio non devono essere presenti spazi, apostrofi, parentesi graffe, segni di uguale, caratteri speciali o non ASCII.

- Se traduci il contenuto in lingue diverse, devi creare cartelle corrispondenti a ciascuna lingua. Ognuna di queste cartelle della lingua conterrà il contenuto corrispondente a tale lingua. Ad esempio, è possibile creare cartelle utilizzando il designatore di lingua come `de` per il tedesco, `fr` per il francese e così via. In alternativa, è possibile creare cartelle utilizzando i designatori della lingua e dell&#39;area geografica come `fr-FR` per il francese utilizzato in Francia o `fr-CA` per il francese utilizzato in Canada.
- Per la lingua di destinazione devono essere selezionate anche le lingue effettive in base alle cartelle delle lingue di destinazione nella rispettiva istanza.
- La configurazione cloud deve essere la stessa della cartella di origine e in una cartella deve essere presente una sola configurazione cloud. Puoi creare più cartelle in /conf, se desideri utilizzare più connettori di traduzione.
- Una cartella non può contenere più di 1000 file.
- Assicurati che l’utente che ha avviato il processo di traduzione disponga delle autorizzazioni di lettura, modifica, creazione ed eliminazione per le cartelle della lingua di origine e di destinazione.
- Poiché la traduzione del contenuto richiede la creazione di un progetto di traduzione, l’utente deve avere accesso alla creazione di un progetto in AEM.
- Se desideri utilizzare i predefiniti condizionali con la mappa, devi crearli prima di avviare il processo di traduzione. Poiché i predefiniti condizionali sono inclusi anche nella versione tradotta della mappa, la creazione dei predefiniti prima di avviare il processo di traduzione si assicura che siano disponibili nella versione tradotta.
- Il processo di traduzione del contenuto deve essere avviato dalla console delle mappe DITA e non dall’interfaccia utente di AEM Assets.
- Il flusso di lavoro di traduzione DITA basato su componenti non deve essere utilizzato se si traducono contenuti tramite traduzione umana. Tuttavia, questa opzione deve essere utilizzata per la traduzione automatica.
- I contenuti e i supporti utilizzati a livello globale che non richiedono la localizzazione devono essere tenuti fuori dalle copie per lingua.
- Tutti i contenuti comuni che devono essere localizzati devono essere conservati in una cartella comune sotto la cartella della lingua.

L’illustrazione seguente mostra un esempio di struttura di cartelle in AEM in presenza di contenuto utilizzato a livello globale e tre copie per lingua.

![](images/aem-directory_structure.png){width="800" align="left"}

## Configurare il servizio di traduzione

Per configurare il servizio di traduzione umana o automatica da utilizzare, effettua le seguenti operazioni:

1. Nell’interfaccia utente di Assets, seleziona la cartella della lingua di origine.

1. Apri le proprietà della cartella e passa alla scheda **Servizi cloud**.

1. Nella scheda **Servizi cloud** configura il servizio di traduzione che desideri utilizzare.

   Puoi configurare la traduzione automatica o umana.

   Assicurati che in una cartella esista una sola configurazione per il connettore di traduzione. Se sono presenti più connettori di traduzione, è possibile creare più cartelle in /conf. Prima di avviare il processo di traduzione, la cartella della lingua di origine deve avere una configurazione cloud selezionata.

   >[!NOTE]
   >
   > Consulta [Configurazione del framework di integrazione della traduzione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) nella documentazione di AEM per informazioni dettagliate sull&#39;integrazione con servizi di traduzione di terze parti.

1. Fai clic su **Salva e chiudi** per salvare le proprietà della cartella aggiornate.


>[!TIP]
>
> Consulta la sezione *Traduzione* nella guida alle best practice per le best practice sulla traduzione dei contenuti.

## Crea un nuovo progetto di traduzione

Per creare un progetto di traduzione, effettua le seguenti operazioni:

>[!NOTE]
>
> Prima di eseguire i passaggi della procedura, accertati di aver creato le cartelle principali e di destinazione della lingua richieste come descritto in [Best practice per la traduzione del contenuto](#id1678G0S702F).

1. Nell’interfaccia utente di Assets, fai clic sul file di mappa DITA.

1. Fai clic sulla scheda **Traduzione**.

1. Dall&#39;elenco **Lingue di destinazione**, selezionare le impostazioni locali in cui tradurre il progetto e fare clic su **Fine**.

   Vengono visualizzati un riepilogo e i dettagli degli argomenti e delle risorse associate.

   >[!IMPORTANT]
   >
   > Le **lingue di destinazione** mostrano solo le lingue per le quali viene creata una cartella delle lingue parallela alla lingua di origine. Non viene visualizzata neanche una cartella della lingua creata a qualsiasi altro livello, ad esempio a un livello inferiore rispetto alla cartella della lingua di origine. Assicurati di creare tutte le cartelle della lingua di destinazione allo stesso livello della cartella della lingua di origine.

1. Seleziona gli argomenti da inviare per la traduzione.

   Puoi anche utilizzare le seguenti opzioni di filtro per argomenti:

   >[!NOTE]
   >
   > Dopo aver applicato il filtro richiesto, fai clic su **Fine** nel pannello Filtro per filtrare gli argomenti in base alla selezione.

   - **Stato traduzione**: scegliere di filtrare gli argomenti in base al relativo stato di traduzione. Le opzioni disponibili sono: Non sincronizzato, Copia mancante, In corso e In sincronia.
   - **Ricerca**: immetti uno o più termini da cercare nei titoli degli argomenti.
   - **Tipo Source**: scegliere di filtrare gli argomenti in base ai tipi di file. Le opzioni disponibili sono: Tutto, DITA, Mappa DITA, Risorsa.
   - **Versione di Source modificata dopo**: scegliere di filtrare l&#39;argomento in base alla data e all&#39;ora di modifica. Tutti gli argomenti modificati dopo la data e l&#39;ora specificate vengono visualizzati nell&#39;elenco.
   - **Previsione**: fare clic su Usa previsione e scegliere una previsione creata sulla mappa. Tutti i file che fanno parte della baseline selezionata vengono visualizzati nella pagina Traduzione. Potete scegliere i file desiderati dalla linea di base e procedere con il processo di traduzione. Una volta tradotti i contenuti, puoi esportare la linea di base tradotta. Per ulteriori dettagli sull&#39;esportazione della baseline tradotta, vedere [Esporta baseline tradotta](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1. Fai clic su **Crea/aggiorna copie per lingua** nella parte inferiore del pannello Filtro.

1. Dall&#39;elenco **Progetto**, selezionare **Crea nuovo progetto di traduzione**.

   >[!NOTE]
   >
   > Se disponi già di un progetto di traduzione, puoi aggiungere argomenti a tale progetto. Seleziona l&#39;opzione **Aggiungi al progetto di traduzione esistente** dall&#39;elenco **Progetto** e scegli un progetto dall&#39;elenco **Progetto di traduzione esistente**.

1. Nel campo **Titolo progetto**, inserisci un titolo.

1. Selezionare l&#39;opzione **Includi mappa DITA** per inviare la mappa per la traduzione.
1. Fai clic su **Inizio** per creare un nuovo progetto di traduzione.

   Viene creato un nuovo progetto di traduzione con la versione selezionata degli argomenti. In questo momento, viene visualizzato un messaggio pop-up che conferma la creazione del progetto di traduzione. Una volta che tutte le copie per lingua di destinazione sono disponibili nel progetto di traduzione, si riceve una notifica nella casella in entrata. Una volta che l’area di destinazione delle copie per lingua è disponibile nel progetto di traduzione, puoi procedere e avviare il processo di traduzione.

   ![](images/status-translation-uuid.png){width="800" align="left"}


La scheda Traduzione include le sezioni seguenti:

- **Riepilogo**: mostra il numero di argomenti a cui si fa riferimento e la lingua di origine insieme al relativo codice.
- **Dettagli**: mostra il titolo dell&#39;argomento, il tipo di argomento, il codice della lingua dell&#39;argomento, la lingua di origine, la versione dell&#39;argomento di origine, l&#39;etichetta aggiunta all&#39;argomento e lo stato della traduzione.




## Avvia il processo di traduzione {#id225IK030OE8}

Per avviare il processo di traduzione, effettua le seguenti operazioni:

1. Nella console **Progetti**, passa alla cartella dei progetti creata per la localizzazione.

1. Fai clic sul progetto di localizzazione per aprire la pagina dei dettagli.

1. Fai clic sulla freccia del riquadro **Processo di traduzione** e seleziona **Avvia** dall&#39;elenco per avviare il flusso di lavoro di traduzione.

   >[!NOTE]
   >
   > Se utilizzi il servizio di traduzione umana, devi esportare il contenuto per la traduzione. Una volta che hai il contenuto tradotto, devi importarlo nuovamente nel progetto di traduzione.

1. Per visualizzare lo stato del processo di traduzione, fai clic sui puntini di sospensione nella parte inferiore del riquadro **Processo di traduzione**.


Al termine della traduzione, lo stato del processo di traduzione diventa *Pronto per la revisione*. Per completare il processo di traduzione, devi accettare la copia tradotta e i metadati della risorsa dalla sezione Processo di traduzione nella console Progetto.

>[!NOTE]
>
> Se si rifiuta la traduzione di uno o più argomenti in un processo di traduzione, lo stato di traduzione **In corso** di tutti gli argomenti rifiutati viene ripristinato allo stato originale. Lo stato degli argomenti indicati viene controllato e ripristinato in base all’ultimo stato di traduzione. Inoltre, i file di traduzione creati nel progetto di destinazione non vengono eliminati anche se la traduzione viene rifiutata per essi.

**Argomento padre:**&#x200B;[ Traduci contenuto](translation.md)
