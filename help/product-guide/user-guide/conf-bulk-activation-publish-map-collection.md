---
title: Attiva output
description: Attiva l'output delle mappe DITA nelle guide AEM. Scopri come attivare i contenuti nell’istanza di pubblicazione.
exl-id: 4da644b9-8c5f-4976-a212-960085b693b8
feature: Publishing, Bulk Activation
role: User
source-git-commit: 66d22560d40012a7475026ed44cec7bf301c1a97
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 1%

---

# Attiva output {#id214GGF00V5U}

Dopo aver creato una raccolta di mappe per l’attivazione in blocco, il passaggio successivo consiste nell’attivare il contenuto nell’istanza di pubblicazione. Per attivare il contenuto, effettua le seguenti operazioni:

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Fai clic sul pulsante **Dashboard pubblicazione in blocco** affiancare.

   Viene visualizzato un elenco delle raccolte di mappe di attivazione in blocco.

1. Seleziona la raccolta da pubblicare e fai clic su **Apri**.

   ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1. \(*Facoltativo*\) Applica i filtri richiesti dalla barra a sinistra per filtrare la mappa in base alla lingua, al predefinito di output o alla versione modificata di \(stato\).

   >[!NOTE]
   >
   >Genera l&#39;output per la mappa utilizzando il predefinito di output prima di attivarlo nella raccolta di mappe.


Visualizza i diversi modi per attivare la raccolta in base alla configurazione.

<details>
<summary> Servizi cloud </summary>

![bulk-collection-publish su cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

Puoi attivare l’output in **Anteprima** o **Pubblica** istanze.

**Anteprima**

* Per attivare l&#39;output delle mappe selezionate, selezionate l&#39;output delle mappe pregenerato e selezionate **Pubblica in** > **Anteprima**.
* Per attivare l&#39;output di tutte le mappe DITA con i relativi predefiniti configurati, selezionare la casella di controllo accanto a **Mappa** e quindi selezionare **Pubblica in** > **Pubblica**.


**Pubblica**

* Per attivare l&#39;output delle mappe selezionate, selezionate l&#39;output delle mappe pregenerato e selezionate **Pubblica in** > **Pubblica**.

* Per attivare l&#39;output di tutte le mappe DITA con i relativi predefiniti configurati, selezionare la casella di controllo accanto a Mappa (colonna), quindi selezionare **Pubblica in** > **Pubblica**.


>[!NOTE]
> 
> La casella di controllo per un output mappa è abilitata solo se è stato generato l&#39;output per una mappa.

Quando l’output della mappa viene inserito nella coda per la pubblicazione, viene visualizzato un messaggio di operazione riuscita.

Una volta attivato l’output per i file di mappa selezionati, viene aggiornata la scheda della cronologia del controllo e viene visualizzato l’output attivato più recente. Il **Pubblicato** viene aggiornata con la data e l’ora di pubblicazione.

</details>

<details>    
<summary>  Software on-premise </summary>


Effettua una delle operazioni seguenti:

* Per attivare l&#39;output delle mappe selezionate, selezionate l&#39;output delle mappe pregenerato e selezionate **Pubblicazione rapida**.
* Per attivare l&#39;output di tutte le mappe DITA con i relativi predefiniti configurati, selezionare la casella di controllo accanto a Mappa (colonna), quindi selezionare **Pubblicazione rapida.**
  ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >La casella di controllo per un output mappa è abilitata solo se è stato generato l&#39;output per una mappa.


Quando l’output della mappa viene inserito nella coda per la pubblicazione, viene visualizzato un messaggio di operazione riuscita.

Una volta attivato l’output per i file di mappa selezionati, viene aggiornata la scheda della cronologia del controllo e viene visualizzato l’output attivato più recente. Il **Pubblicato** viene aggiornata con la data e l’ora di pubblicazione.

**Argomento principale: **[Attivazione in blocco di contenuti pubblicati](conf-bulk-activation.md)
