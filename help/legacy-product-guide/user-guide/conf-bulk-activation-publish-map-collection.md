---
title: Attiva output
description: Attiva l'output delle mappe DITA in AEM Guides. Scopri come attivare i contenuti nell’istanza di pubblicazione.
feature: Publishing, Bulk Activation
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 1%

---

# Attiva output {#id214GGF00V5U}

Dopo aver creato una raccolta di mappe per l’attivazione in blocco, il passaggio successivo consiste nell’attivare il contenuto nell’istanza di pubblicazione. Per attivare il contenuto, effettua le seguenti operazioni:

1. Selezionare **Guide** dall&#39;elenco degli strumenti.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Fai clic sul riquadro **Bulk Publish Dashboard**.

   Viene visualizzato un elenco delle raccolte di mappe di attivazione in blocco.

1. Selezionare la raccolta da pubblicare e fare clic su **Apri**.

   ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1. \(*Facoltativo*\) Applica i filtri richiesti dalla barra a sinistra per filtrare la mappa in base alla lingua, al predefinito di output o alla lingua modificati.

   >[!NOTE]
   >
   >Genera l&#39;output per la mappa utilizzando il predefinito di output prima di attivarlo nella raccolta di mappe.


Visualizza i diversi modi per attivare la raccolta in base alla configurazione.

<details>
<summary> Servizi cloud </summary>

![pubblicazione di raccolte in blocco su cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

È possibile attivare l&#39;output nelle istanze **Anteprima** o **Publish**.

**Anteprima**

* Per attivare l&#39;output delle mappe selezionate, selezionare l&#39;output delle mappe pregenerato e selezionare **Publish in** > **Anteprima**.
* Per attivare l&#39;output di tutte le mappe DITA con i relativi predefiniti configurati, selezionare la casella di controllo accanto alla colonna **Mappa**, quindi selezionare **Publish a** > **Publish**.


**Publish**

* Per attivare l&#39;output delle mappe selezionate, selezionare l&#39;output delle mappe pregenerato e selezionare **Publish in** > **Publish**.

* Per attivare l&#39;output di tutte le mappe DITA con i relativi predefiniti configurati, selezionare la casella di controllo accanto alla mappa (colonna), quindi selezionare **Publish to** > **Publish**.


>[!NOTE]
> 
> La casella di controllo per un output mappa è abilitata solo se è stato generato l&#39;output per una mappa.

Quando l’output della mappa viene inserito nella coda per la pubblicazione, viene visualizzato un messaggio di operazione riuscita.

Una volta attivato l’output per i file di mappa selezionati, viene aggiornata la scheda della cronologia del controllo e viene visualizzato l’output attivato più recente. La colonna **Pubblicato** è stata aggiornata con la data e l&#39;ora di pubblicazione.

</details>

<details>    
<summary>  Software on-premise </summary>


Effettua una delle seguenti operazioni:

* Per attivare l&#39;output delle mappe selezionate, selezionare l&#39;output delle mappe pregenerato e selezionare **Publish rapido**.
* Per attivare l&#39;output di tutte le mappe DITA con i relativi predefiniti configurati, selezionare la casella di controllo accanto alla mappa (colonna), quindi selezionare **Publish rapido.**
  ![raccolta in blocco-pubblicazione](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >La casella di controllo per un output mappa è abilitata solo se è stato generato l&#39;output per una mappa.


Quando l’output della mappa viene inserito nella coda per la pubblicazione, viene visualizzato un messaggio di operazione riuscita.

Una volta attivato l’output per i file di mappa selezionati, viene aggiornata la scheda della cronologia del controllo e viene visualizzato l’output attivato più recente. La colonna **Pubblicato** è stata aggiornata con la data e l&#39;ora di pubblicazione.

**Argomento padre: **[Attivazione in blocco del contenuto pubblicato](conf-bulk-activation.md)
