---
title: Installare pacchetti per la pubblicazione basata su articoli
description: Scopri come installare pacchetti per la pubblicazione basata su articoli
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/ZX3-rirhXTcufDkFQOF12vj3uh28gSfIpxFwlOQF-Yk
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: afb45297-4313-4f67-818e-bc0b03abe086id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 374
ht-degree: 0%

---

# Installare pacchetti per la pubblicazione basata su articoli {#id21BNL02052Z}

AEM Guides fornisce una potente funzione di pubblicazione basata su articoli integrata con l’editor web. Questa funzione consente di pubblicare uno o più argomenti contemporaneamente. Dopo aver aperto una mappa nell’Editor mappa, puoi passare alla scheda Output per creare un predefinito e quindi scegliere uno o più argomenti per generare l’output. È possibile utilizzare la funzione di pubblicazione basata su articoli per generare in modo incrementale l&#39;output di uno o più argomenti o pubblicare il contenuto in una piattaforma della knowledge base in base a un singolo articolo. Per ulteriori dettagli vedi *Pubblicazione basata su articolo dalla sezione Editor Web* nella Guida utente.

Per creare un sito AEM per la pubblicazione dell’output basato su articoli, effettua le seguenti operazioni:

1. Scarica **il pacchetto di contenuti dei componenti XML Documentation per Cloud Service** dal [portale di distribuzione software Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Apri Gestione pacchetti di AEM. L&#39;URL predefinito per accedere al gestore di pacchetti è: `https://<hostname>/crx/packmgr/index.jsp`
1. Caricare il pacchetto di contenuti dei componenti di XML Documentation per Cloud Service, quindi installarlo.
1. Scarica il file `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` dal [portale di distribuzione software Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. In Navigazione globale, selezionare **Siti**.
1. Nell&#39;interfaccia utente di Sites, fai clic sul pulsante **Crea** in alto a destra.
1. Seleziona **Sito da modello** dal menu a discesa **Crea**.
1. Fai clic sul pulsante **Importa**, quindi seleziona `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` scaricato nel sistema. Una volta importato, il modello di sito viene elencato in basso.

   >[!NOTE]
   >
   > È necessario importare il file ZIP solo per la prima volta. Una volta importato, il modello di sito è disponibile nell’elenco.

   Seleziona **Modello della Knowledge Base per pubblicazione basata su articolo** per creare il sito AEM e fai clic su **Avanti** nell&#39;angolo in alto a destra.

1. Immetti il **Titolo sito** e il **Nome sito** e fai clic su **Crea** nell&#39;angolo in alto a destra. Un sito AEM viene creato utilizzando il modello di sito Tragopan. \(Sito di Tragopan è un esempio di sito AEM della knowledge base con modelli per pagine di categorie, sezioni e articoli.\)

   >[!NOTE]
   >
   > Puoi creare più siti AEM utilizzando lo stesso modello.


È possibile utilizzare il sito AEM per pubblicare l&#39;articolo utilizzando i predefiniti di output dell&#39;editor Web.

**Argomento padre:**[ Personalizza editor Web](conf-web-editor.md)
