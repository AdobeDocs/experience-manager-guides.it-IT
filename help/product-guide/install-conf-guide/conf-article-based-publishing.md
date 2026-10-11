---
title: Installare pacchetti per la pubblicazione basata su articoli
description: Scopri come installare pacchetti per la pubblicazione basata su articoli
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 24e47af6-8d81-4994-8d97-474f5029392b
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 0%
---
# Installare pacchetti per la pubblicazione basata su articoli {#id21BNL02052Z}

AEM Guides fornisce una potente funzione di pubblicazione basata su articoli integrata nell’editor. Questa funzione consente di pubblicare uno o più argomenti contemporaneamente. Dopo aver aperto una mappa nell’Editor mappa, puoi passare alla scheda Output per creare un predefinito e quindi scegliere uno o più argomenti per generare l’output. È possibile utilizzare la funzione di pubblicazione basata su articoli per generare in modo incrementale l&#39;output di uno o più argomenti o pubblicare il contenuto in una piattaforma della knowledge base in base a un singolo articolo. Per ulteriori dettagli vedi *Pubblicazione basata su articolo dalla sezione Editor* nella Guida utente.

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


Puoi utilizzare il sito AEM per pubblicare l’articolo utilizzando i predefiniti di output dell’editor.

>[!TAB On-Premise]

Per abilitare la pubblicazione basata su articoli, scarica e installa i seguenti pacchetti dal portale di distribuzione software Adobe. Installali per creare un sito Tragopan. \(Sito di Tragopan è un sito di AEM della knowledge base di esempio con modelli per pagine di categorie, sezioni e articoli.\) Aggiornare il sito di Tragopan per generare l&#39;output del sito di AEM utilizzando i predefiniti di output dell&#39;editor.

- Modello della knowledge base per la pubblicazione basata su articoli
- Pacchetto di componenti per la pubblicazione basata su articoli

>[!ENDTABS]


**Argomento padre:**[ Personalizza editor](customize-overview.md)
