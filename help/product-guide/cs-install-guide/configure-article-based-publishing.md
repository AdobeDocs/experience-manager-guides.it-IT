---
title: Installare pacchetti per la pubblicazione basata su articoli
description: Scopri come installare pacchetti per la pubblicazione basata su articoli
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Installare pacchetti per la pubblicazione basata su articoli {#id21BNL02052Z}

Le guide AEM forniscono una potente funzione di pubblicazione basata su articoli integrata con l’editor web. Questa funzione consente di pubblicare uno o più argomenti contemporaneamente. Dopo aver aperto una mappa nell’Editor mappa, puoi passare alla scheda Output per creare un predefinito e quindi scegliere uno o più argomenti per generare l’output. È possibile utilizzare la funzione di pubblicazione basata su articoli per generare in modo incrementale l&#39;output di uno o più argomenti o pubblicare il contenuto in una piattaforma della knowledge base in base a un singolo articolo. Per maggiori dettagli vedi, *Pubblicazione basata su articolo dalla sezione Editor Web* nella Guida utente.

Per creare un sito AEM per la pubblicazione dell’output basato su articoli, effettua le seguenti operazioni:

1. Scarica **Pacchetto di contenuti per componenti XML Documentation per Cloud Service** dal tuo [Portale di distribuzione software Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Apri Gestione pacchetti AEM. L’URL predefinito per accedere al gestore di pacchetti è: `https://<hostname>/crx/packmgr/index.jsp`
1. Caricare il pacchetto di contenuti dei componenti di XML Documentation per il Cloud Service, quindi installarlo.
1. Scarica il file `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` file dal tuo [Portale di distribuzione software Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Dalla navigazione globale, seleziona **Sites**.
1. Nell’interfaccia utente di Sites, fai clic su **Crea** nell&#39;angolo superiore destro.
1. Seleziona **Sito da modello** dal **Crea** a discesa.
1. Fai clic su **Importa** e quindi selezionare il `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` scaricato sul sistema. Una volta importato, il modello di sito viene elencato in basso.

   >[!NOTE]
   >
   > È necessario importare il file ZIP solo per la prima volta. Una volta importato, il modello di sito è disponibile nell’elenco.

   Seleziona **Modello della knowledge base per la pubblicazione basata su articoli** per creare il sito AEM e fare clic su **Successivo** in alto a destra.

1. Inserisci il **Titolo sito** e **Nome sito** e fai clic su **Crea** in alto a destra. Un sito AEM viene creato utilizzando il modello di sito Tragopan. \(Il sito di Tragopan è un esempio di sito AEM della knowledge base con modelli per pagine di categorie, sezioni e articoli.\)

   >[!NOTE]
   >
   > Puoi creare più siti AEM utilizzando lo stesso modello.


Puoi utilizzare il sito AEM per pubblicare l’articolo utilizzando i predefiniti di output dell’editor web.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
