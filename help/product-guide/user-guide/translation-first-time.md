---
title: Best practice per la traduzione dei contenuti
description: Scopri le best practice per la traduzione dei contenuti nelle Guide AEM. Scopri come configurare il servizio di traduzione, creare un nuovo progetto di traduzione e avviare il processo di traduzione.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 1%

---

# Best practice per la traduzione dei contenuti {#id1678G0S702F}

Considera il seguente punto per la traduzione del contenuto:

- I nomi delle cartelle e dei file devono essere conformi agli standard di denominazione dei file, ad esempio non devono essere presenti spazi, apostrofi, parentesi graffe, segni di uguale, caratteri speciali o non ASCII.

- Se traduci il contenuto in lingue diverse, devi creare cartelle corrispondenti a ciascuna lingua. Ognuna di queste cartelle della lingua conterrà il contenuto corrispondente a tale lingua. Ad esempio, puoi creare cartelle utilizzando il designatore della lingua come `de` per il tedesco, `fr` per il francese e così via. In alternativa, è possibile creare cartelle utilizzando la lingua e l’area geografica come `fr-FR` per il francese quale utilizzato in Francia o `fr-CA` per il francese utilizzato in Canada.
- Per la lingua di destinazione devono essere selezionate anche le lingue effettive in base alle cartelle delle lingue di destinazione nella rispettiva istanza.
- La configurazione cloud deve essere la stessa della cartella di origine e in una cartella deve essere presente una sola configurazione cloud. Puoi creare più cartelle in /conf, se desideri utilizzare più connettori di traduzione.
- Una cartella non può contenere più di 1000 file.
- Assicurati che l’utente che ha avviato il processo di traduzione disponga delle autorizzazioni di lettura, modifica, creazione ed eliminazione per le cartelle della lingua di origine e di destinazione.
- Poiché la traduzione dei contenuti richiede la creazione di un progetto di traduzione, l’utente deve avere accesso alla creazione di un progetto in AEM.
- Se desideri utilizzare i predefiniti condizionali con la mappa, devi crearli prima di avviare il processo di traduzione. Poiché i predefiniti condizionali sono inclusi anche nella versione tradotta della mappa, la creazione dei predefiniti prima di avviare il processo di traduzione si assicura che siano disponibili nella versione tradotta.
- Il processo di traduzione del contenuto deve essere avviato dalla console delle mappe DITA e non dall’interfaccia utente di AEM Assets.
- Il flusso di lavoro di traduzione DITA basato su componenti non deve essere utilizzato se si traducono contenuti tramite traduzione umana. Tuttavia, questa opzione deve essere utilizzata per la traduzione automatica.
- I contenuti e i supporti utilizzati a livello globale che non richiedono la localizzazione devono essere tenuti fuori dalle copie per lingua.
- Tutti i contenuti comuni che devono essere localizzati devono essere conservati in una cartella comune sotto la cartella della lingua.

La figura seguente mostra un esempio di struttura di cartelle in AEM quando si dispone di contenuto utilizzato a livello globale e tre copie per lingua.

![](images/aem-directory_structure.png){width="800" align="left"}

## Configurare il servizio di traduzione

Per configurare il servizio di traduzione umana o automatica da utilizzare, effettua le seguenti operazioni:

1. Nell’interfaccia utente Assets, seleziona la cartella della lingua di origine.

1. Apri le proprietà della cartella e vai a **Cloud Service** scheda.

1. In **Cloud Service** , configura il servizio di traduzione che desideri utilizzare.

   Puoi configurare la traduzione automatica o umana.

   Assicurati che in una cartella esista una sola configurazione per il connettore di traduzione. Se sono presenti più connettori di traduzione, è possibile creare più cartelle in /conf. Prima di avviare il processo di traduzione, la cartella della lingua di origine deve avere una configurazione cloud selezionata.

   >[!NOTE]
   >
   > Consulta [Configurazione del framework di integrazione della traduzione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) nella documentazione dell’AEM per informazioni dettagliate sull’integrazione con servizi di traduzione di terze parti.

1. Clic **Salva e chiudi** per salvare le proprietà della cartella aggiornate.


>[!TIP]
>
> Consulta la *Traduzione* sezione nella guida alle best practice per le best practice sulla traduzione dei contenuti.

## Crea un nuovo progetto di traduzione

Per creare un progetto di traduzione, effettua le seguenti operazioni:

>[!NOTE]
>
> Prima di eseguire i passaggi descritti in questa procedura, accertati di aver creato le cartelle principali e di destinazione della lingua richieste come descritto in [Best practice per la traduzione dei contenuti](#id1678G0S702F).

1. Nell’interfaccia utente Assets, fai clic sul file di mappa DITA.

1. Fai clic su **Traduzione** scheda.

1. Dalla sezione **Lingue di destinazione** , seleziona la lingua in cui desideri tradurre il progetto e fai clic su **Fine**.

   Vengono visualizzati un riepilogo e i dettagli degli argomenti e delle risorse associate.

   >[!IMPORTANT]
   >
   > Il **Lingue di destinazione** mostra solo le lingue per le quali viene creata una cartella della lingua parallela alla lingua di origine. Non viene visualizzata neanche una cartella della lingua creata a qualsiasi altro livello, ad esempio a un livello inferiore rispetto alla cartella della lingua di origine. Assicurati di creare tutte le cartelle della lingua di destinazione allo stesso livello della cartella della lingua di origine.

1. Seleziona gli argomenti da inviare per la traduzione.

   Puoi anche utilizzare le seguenti opzioni di filtro per argomenti:

   >[!NOTE]
   >
   > Dopo aver applicato il filtro richiesto, fai clic su **Fine** nel pannello Filtro per filtrare gli argomenti in base alla selezione.

   - **Stato traduzione**: scegli di filtrare gli argomenti in base al loro stato di traduzione. Le opzioni disponibili sono: Non sincronizzato, Copia mancante, In corso e In sincronia.
   - **Ricerca**: immetti uno o più termini da cercare nei titoli degli argomenti.
   - **Tipo di origine**: consente di filtrare gli argomenti in base ai tipi di file. Le opzioni disponibili sono: Tutto, DITA, Mappa DITA, Risorsa.
   - **Versione di origine modificata dopo**: scegli di filtrare l’argomento in base alla data e all’ora di modifica. Tutti gli argomenti modificati dopo la data e l&#39;ora specificate vengono visualizzati nell&#39;elenco.
   - **Linea di base**: fare clic su Usa baseline e scegliere una baseline creata sulla mappa. Tutti i file che fanno parte della baseline selezionata vengono visualizzati nella pagina Traduzione. Potete scegliere i file desiderati dalla linea di base e procedere con il processo di traduzione. Una volta tradotti i contenuti, puoi esportare la linea di base tradotta. Per ulteriori dettagli sull&#39;esportazione della linea di base tradotta, vedi [Esporta previsione tradotta](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1. Clic **Crea/aggiorna copie per lingua** nella parte inferiore del pannello Filtro.

1. Dalla sezione **Progetto** elenco, seleziona **Crea un nuovo progetto di traduzione**.

   >[!NOTE]
   >
   > Se disponi già di un progetto di traduzione, puoi aggiungere argomenti a tale progetto. Seleziona **Aggiungi a progetto di traduzione esistente** opzione dalla **Progetto** e scegli un progetto da **Progetto di traduzione esistente** elenco.

1. Nel campo **Titolo progetto**, inserisci un titolo.

1. Seleziona la **Includi mappa DITA** opzione per inviare la mappa per la traduzione.
1. Clic **Inizio** per creare un nuovo progetto di traduzione.

   Viene creato un nuovo progetto di traduzione con la versione selezionata degli argomenti. In questo momento, viene visualizzato un messaggio pop-up che conferma la creazione del progetto di traduzione. Una volta che tutte le copie per lingua di destinazione sono disponibili nel progetto di traduzione, si riceve una notifica nella casella in entrata. Una volta che l’area di destinazione delle copie per lingua è disponibile nel progetto di traduzione, puoi procedere e avviare il processo di traduzione.

   ![](images/status-translation-uuid.png){width="800" align="left"}


La scheda Traduzione include le sezioni seguenti:

- **Riepilogo**: mostra il numero di argomenti a cui si fa riferimento, la lingua di origine e il relativo codice.
- **Dettagli**: mostra il titolo dell’argomento, il tipo di argomento, il codice della lingua dell’argomento, la lingua di origine, la versione dell’argomento di origine, l’etichetta aggiunta all’argomento e lo stato della traduzione.




## Avvia il processo di traduzione {#id225IK030OE8}

Per avviare il processo di traduzione, effettua le seguenti operazioni:

1. In **Progetti** , passa alla cartella del progetto creata per la localizzazione.

1. Fai clic sul progetto di localizzazione per aprire la pagina dei dettagli.

1. Fare clic sulla freccia **Lavoro di traduzione** affiancare e selezionare **Inizio** dall’elenco per avviare il flusso di lavoro di traduzione.

   >[!NOTE]
   >
   > Se utilizzi il servizio di traduzione umana, devi esportare il contenuto per la traduzione. Una volta che hai il contenuto tradotto, devi importarlo nuovamente nel progetto di traduzione.

1. Per visualizzare lo stato del processo di traduzione, fai clic sui puntini di sospensione nella parte inferiore della **Lavoro di traduzione** affiancare.


Al termine della traduzione, lo stato del processo di traduzione diventa *Pronto per la revisione*. Per completare il processo di traduzione, devi accettare la copia tradotta e i metadati della risorsa dalla sezione Processo di traduzione nella console Progetto.

>[!NOTE]
>
> Se rifiuti la traduzione per uno o più argomenti in un processo di traduzione, il **In corso** lo stato di traduzione di tutti gli argomenti rifiutati ritorna allo stato originale. Lo stato degli argomenti indicati viene controllato e ripristinato in base all’ultimo stato di traduzione. Inoltre, i file di traduzione creati nel progetto di destinazione non vengono eliminati anche se la traduzione viene rifiutata per essi.

**Argomento padre:**[ Traduci contenuto](translation.md)
