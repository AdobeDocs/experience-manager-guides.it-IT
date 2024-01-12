---
title: Creare una mappa
description: Crea una mappa con Map Editor nelle guide AEM. Trova i passaggi per creare un file di mappa basato su un modello di mappa.
exl-id: b9cda118-ab6f-4d6b-9616-a083180ba069
feature: Authoring, Map Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Creare una mappa {#id176FEN0D05Z}

AEM Guides fornisce due modelli di mappe preconfigurati: DITA map e Bookmap. Puoi anche creare modelli di mappa personalizzati e condividerli con gli autori per creare file di mappa.

Per creare un file di mappa, effettua le seguenti operazioni:

1. Nell’interfaccia utente Assets, individua il percorso in cui desideri creare il file di mappa.

1. Clic **Crea** \> **Mappa DITA**.

1. Nella pagina Blueprint, seleziona il tipo di modelli di mappa che desideri utilizzare e fai clic su **Successivo**.

   >[!NOTE]
   >
   > Il modo in cui gli argomenti vengono trattati in un file di mappa dipende dal modello di mappa. Ad esempio, se si seleziona il modello Mappa, l&#39;argomento fa riferimento a \(`topicref`\) vengono utilizzati per fare riferimento ad argomenti. Nel caso di una mappa di un argomento, i riferimenti ad argomento vengono creati utilizzando `chapter` elemento DITA.

   ![](images/map-template.png){width="650" align="left"}

1. Nella pagina Proprietà, specifica la mappa **Titolo**.

1. \(Facoltativo\) Specificare il file **Nome**.

   Se l’amministratore ha configurato il nome file automatico in base all’impostazione UUID, l’opzione per specificare il nome file non sarà visibile. Al file viene automaticamente assegnato un nome di file basato su UUID.

   Se è disponibile l’opzione di denominazione del file, anche il nome viene suggerito automaticamente in base al Titolo della mappa. Se desiderate specificare manualmente il nome del file mappa, accertatevi che il nome del file non contenga spazi, apostrofi o parentesi graffe e termini con `.ditamap`.

1. Fai clic su **Crea**.

   Viene visualizzato il messaggio Mappa creata.

   Ogni nuovo file di mappa creato dall’interfaccia utente Assets **Crea** \> **Mappa DITA** o all’editor web viene assegnato un ID mappa univoco. Inoltre, la nuova mappa viene salvata come copia di lavoro più recente in DAM. Fino a quando non salvi una revisione di una mappa appena creata, nella Cronologia versioni non viene visualizzato alcun numero di versione. Se apri la mappa per la modifica, le informazioni sulla versione vengono visualizzate nell’angolo superiore destro della scheda del file mappa:

   ![](images/first-version-map-none.png){width="650" align="left"}

   Le informazioni sulla versione di una mappa appena creata vengono visualizzate come *nessuno*. Quando salvi una nuova versione, ad essa viene assegnato il numero di versione 1.0. Per ulteriori informazioni sul salvataggio di una nuova versione, consulta [Salva come nuova versione](web-editor-features.md#save-as-new-version-id209ME400GXA).

   Puoi scegliere di aprire la mappa per la modifica nell’editor di mappe configurato oppure di salvare il file di mappa nell’archivio AEM.

   >[!NOTE]
   >
   > Per utilizzare l&#39;Editor mapping avanzato, accedere al file di mapping nell&#39;Editor Web. Se l&#39;amministratore ha configurato l&#39;Editor mapping avanzato come editor predefinito nei file di mapping, il file di mapping viene aperto direttamente nell&#39;Editor mapping avanzato per la modifica. Consulta *Imposta l&#39;Editor mappe avanzato come predefinito* sezione in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.


**Argomento padre:**[ Utilizzare l’Editor mappa](map-editor.md)
