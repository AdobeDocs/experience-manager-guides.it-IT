---
title: Installare pacchetti per la pubblicazione basata su articoli
description: Scopri come installare pacchetti per la pubblicazione basata su articoli
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Installare pacchetti per la pubblicazione basata su articoli {#id21BNL02052Z}

AEM Guides fornisce una potente funzione di pubblicazione basata su articoli integrata con l’editor web. Questa funzione consente di pubblicare uno o più argomenti contemporaneamente. Dopo aver aperto una mappa nell’Editor mappa, puoi passare alla scheda Output per creare un predefinito e quindi scegliere uno o più argomenti per generare l’output. È possibile utilizzare la funzione di pubblicazione basata su articoli per generare in modo incrementale l&#39;output di uno o più argomenti o pubblicare il contenuto in una piattaforma della knowledge base in base a un singolo articolo. Per ulteriori dettagli vedi *Pubblicazione basata su articolo dalla sezione Editor Web* nella Guida utente.

Le schede seguenti forniscono istruzioni per creare un sito AEM per la pubblicazione di output basati su articoli in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

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

>[!TAB On-Premise]

Per abilitare la pubblicazione basata su articoli, scarica e installa i seguenti pacchetti dal portale di distribuzione software Adobe. Installali per creare un sito Tragopan. \(sito di Tragopan è un esempio di sito AEM della knowledge base con modelli per pagine di categorie, sezioni e articoli.\) Aggiorna il sito Tragopan per generare l’output del sito AEM utilizzando i predefiniti di output dell’editor web.

- Modello della knowledge base per la pubblicazione basata su articoli
- Pacchetto di componenti per la pubblicazione basata su articoli

>[!ENDTABS]


**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](customize-overview.md)
