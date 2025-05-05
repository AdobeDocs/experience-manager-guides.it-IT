---
title: Best practice per la traduzione dei contenuti
description: Conoscere le best practice per la traduzione dei contenuti in AEM Guides. Scopri come configurare il servizio di traduzione, creare un nuovo progetto di traduzione e avviare il processo di traduzione.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
feature: Translation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 0%

---

# Best practice per la traduzione dei contenuti {#id1678G0S702F}

Considera il seguente punto per la traduzione del contenuto:

- I nomi delle cartelle e dei file devono essere conformi agli standard di denominazione dei file, ad esempio non devono essere presenti spazi, apostrofi, parentesi graffe, segni di uguale, caratteri speciali o non ASCII.

- Se traduci il contenuto in lingue diverse, devi creare cartelle corrispondenti a ciascuna lingua. Ognuna di queste cartelle della lingua conterrà il contenuto corrispondente a tale lingua. Ad esempio, è possibile creare cartelle utilizzando il designatore di lingua come `de` per il tedesco, `fr` per il francese e così via. In alternativa, è possibile creare cartelle utilizzando i designatori della lingua e dell&#39;area geografica come `fr-FR` per il francese utilizzato in Francia o `fr-CA` per il francese utilizzato in Canada.
- Per la lingua di destinazione devono essere selezionate anche le lingue effettive in base alle cartelle delle lingue di destinazione nella rispettiva istanza.
- La configurazione cloud deve essere la stessa della cartella di origine e in una cartella deve essere presente una sola configurazione cloud. Puoi creare più cartelle in /conf, se desideri utilizzare più connettori di traduzione.
- Una cartella non può contenere più di 1000 file.
- Assicurati che l’utente che ha avviato il processo di traduzione disponga delle autorizzazioni di lettura, modifica, creazione ed eliminazione per le cartelle della lingua di origine e di destinazione.
- Poiché la traduzione del contenuto richiede la creazione di un progetto di traduzione, l’utente deve avere accesso alla creazione del progetto in Adobe Experience Manager.
- Se desideri utilizzare i predefiniti condizionali con la mappa, devi crearli prima di avviare il processo di traduzione. Poiché i predefiniti condizionali sono inclusi anche nella versione tradotta della mappa, la creazione dei predefiniti prima di avviare il processo di traduzione si assicura che siano disponibili nella versione tradotta.
- Il processo di traduzione del contenuto deve essere avviato dalla console delle mappe DITA e non dall’interfaccia utente di Adobe Experience Manager Assets.
- Il flusso di lavoro di traduzione DITA basato su componenti non deve essere utilizzato se si traducono contenuti tramite traduzione umana. Tuttavia, questa opzione deve essere utilizzata per la traduzione automatica.
- I contenuti e i supporti utilizzati a livello globale che non richiedono la localizzazione devono essere tenuti fuori dalle copie per lingua.
- Tutti i contenuti comuni che devono essere localizzati devono essere conservati in una cartella comune sotto la cartella della lingua.

L’illustrazione seguente mostra un esempio di struttura di cartelle in Adobe Experience Manager in presenza di contenuto utilizzato a livello globale e tre copie per lingua.

![](images/aem-directory_structure.png){align="left"}

## Configurare il servizio di traduzione

Per configurare il servizio di traduzione umana o automatica da utilizzare, effettua le seguenti operazioni:

1. Nell’interfaccia utente di Assets, seleziona la cartella della lingua di origine.

1. Apri le proprietà della cartella e passa alla scheda **Servizi cloud**.

1. Nella scheda **Servizi cloud** configura il servizio di traduzione che desideri utilizzare.

   Puoi configurare la traduzione automatica o umana.

   Assicurati che in una cartella esista una sola configurazione per il connettore di traduzione. Se sono presenti più connettori di traduzione, è possibile creare più cartelle in /conf. Prima di avviare il processo di traduzione, la cartella della lingua di origine deve avere una configurazione cloud selezionata.

   >[!NOTE]
   >
   > Visualizza [Configurazione del framework di integrazione della traduzione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) nella documentazione di Adobe Experience Manager per informazioni dettagliate sull&#39;integrazione con servizi di traduzione di terze parti.

1. Seleziona **Salva e chiudi** per salvare le proprietà della cartella aggiornate.


## Avvia il processo di traduzione {#id225IK030OE8}

Per avviare il processo di traduzione, effettua le seguenti operazioni:

1. Nella console **Progetti**, passa alla cartella dei progetti creata per la localizzazione.

1. Seleziona il progetto di localizzazione per aprire la pagina dei dettagli.

1. Seleziona la freccia nella sezione **Processo di traduzione** e seleziona **Avvia** dall&#39;elenco per avviare il flusso di lavoro di traduzione.

   >[!NOTE]
   >
   > Se utilizzi il servizio di traduzione umana, devi esportare il contenuto per la traduzione. Una volta che hai il contenuto tradotto, devi importarlo nuovamente nel progetto di traduzione.

1. Per visualizzare lo stato del processo di traduzione, seleziona i puntini di sospensione nella parte inferiore del riquadro **Processo di traduzione**.


Al termine della traduzione, lo stato del processo di traduzione diventa *Pronto per la revisione*. Per completare il processo di traduzione, devi accettare la copia tradotta e i metadati della risorsa dalla sezione Processo di traduzione nella console Progetto. Se desideri avviare un nuovo progetto di traduzione, visualizza [Crea un progetto di traduzione](translate-documents-web-editor.md#create-a-translation-project).

>[!NOTE]
>
>- Se si rifiuta la traduzione di uno o più argomenti in un processo di traduzione, lo stato di traduzione **In corso** di tutti gli argomenti rifiutati viene ripristinato allo stato originale. Lo stato degli argomenti indicati viene controllato e ripristinato in base all’ultimo stato di traduzione. Inoltre, i file di traduzione creati nella cartella della lingua di destinazione non vengono eliminati anche se la traduzione viene rifiutata per essi.
>- Se si rifiuta, elimina o annulla il processo di traduzione per un argomento presente in più progetti (per uno qualsiasi dei progetti), lo stato di traduzione **In corso** dell&#39;argomento non viene ripristinato, ma il progetto viene rimosso dall&#39;elenco di progetti **In corso** per la risorsa specificata.
>- Inoltre, se si annulla o si elimina il processo di traduzione o si elimina l&#39;intero progetto, lo stato di traduzione **In corso** viene ripristinato allo stato originale.

**Argomento padre:**&#x200B;[ Panoramica sulla traduzione dei contenuti](translation.md)
