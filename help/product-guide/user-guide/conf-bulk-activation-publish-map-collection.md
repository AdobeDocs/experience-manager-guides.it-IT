---
title: Attiva output
description: Attiva l'output delle mappe DITA in AEM Guides. Scopri come attivare i contenuti nell’istanza di pubblicazione.
exl-id: 4da644b9-8c5f-4976-a212-960085b693b8
feature: Publishing, Bulk Activation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 1%

---

# Attiva output {#id214GGF00V5U}

Dopo aver creato una raccolta di mappe per l’attivazione in blocco, il passaggio successivo consiste nell’attivare il contenuto nell’istanza di pubblicazione. Per attivare il contenuto, effettua le seguenti operazioni:

1. Seleziona il logo Adobe Experience Manager nella parte superiore e scegli **Strumenti**.

1. Nel pannello **Strumenti**, seleziona **Guide**.

1. Seleziona il riquadro **Dashboard di pubblicazione in blocco**.

   Viene visualizzato il dashboard Pubblicazione in blocco con un elenco di raccolte di mappe di attivazione in blocco. Puoi accedere a questa dashboard anche dal pannello a sinistra della [home page di Adobe Experience Manager Guides](intro-home-page.md).

1. Selezionare la raccolta che si desidera pubblicare e selezionare **Apri**.

   ![](images/bulk-activation-collection-open.png){align="left"}

1. \(*Facoltativo*\) Applica i filtri richiesti dalla barra a sinistra per filtrare la mappa in base alla lingua, al predefinito di output o alla lingua modificati.

   >[!NOTE]
   >
   >Genera l&#39;output per la mappa utilizzando il predefinito di output prima di attivarlo nella raccolta di mappe.


Visualizza i diversi modi per attivare la raccolta in base alla configurazione.

<details>
<summary> Servizi cloud </summary>

![pubblicazione di raccolte in blocco su cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

Puoi attivare l&#39;output nelle istanze **Anteprima** o **Pubblica**.

**Anteprima**

* Per attivare l&#39;output delle mappe selezionate, selezionare l&#39;output delle mappe pregenerato e selezionare **Pubblica in** > **Anteprima**.
* Per attivare l&#39;output di tutte le mappe DITA con i relativi predefiniti configurati, selezionare la casella di controllo accanto alla colonna **Mappa**, quindi selezionare **Pubblica in** > **Pubblica**.


**Pubblica**

* Per attivare l&#39;output delle mappe selezionate, selezionare l&#39;output delle mappe pregenerato e selezionare **Pubblica in** > **Pubblica**.

* Per attivare l&#39;output di tutte le mappe DITA con i relativi predefiniti configurati, selezionare la casella di controllo accanto alla mappa (colonna), quindi selezionare **Pubblica su** > **Pubblica**.


>[!NOTE]
> 
> La casella di controllo per un output mappa è abilitata solo se è stato generato l&#39;output per una mappa.

Quando l’output della mappa viene inserito nella coda per la pubblicazione, viene visualizzato un messaggio di operazione riuscita.

Una volta attivato l’output per i file di mappa selezionati, viene aggiornata la scheda della cronologia del controllo e viene visualizzato l’output attivato più recente. La colonna **Pubblicato** è stata aggiornata con la data e l&#39;ora di pubblicazione.

</details>

<details>    
<summary>  Software on-premise </summary>


Effettua una delle seguenti operazioni:

* Per attivare l&#39;output delle mappe selezionate, selezionare l&#39;output delle mappe pregenerato e selezionare **Pubblicazione rapida**.
* Per attivare l&#39;output di tutte le mappe DITA con i relativi predefiniti configurati, selezionare la casella di controllo accanto alla mappa (colonna), quindi selezionare **Pubblicazione rapida.**
  ![raccolta in blocco-pubblicazione](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >La casella di controllo per un output mappa è abilitata solo se è stato generato l&#39;output per una mappa.


Quando l’output della mappa viene inserito nella coda per la pubblicazione, viene visualizzato un messaggio di operazione riuscita.

Una volta attivato l’output per i file di mappa selezionati, viene aggiornata la scheda della cronologia del controllo e viene visualizzato l’output attivato più recente. La colonna **Pubblicato** è stata aggiornata con la data e l&#39;ora di pubblicazione.

**Argomento padre: **[Attivazione in blocco del contenuto pubblicato](conf-bulk-activation.md)
