---
title: Gestire le attività di pubblicazione tramite il dashboard di pubblicazione
description: Gestisci le attività di pubblicazione utilizzando il dashboard di pubblicazione in AEM Guides. Scopri come accedere al dashboard di pubblicazione e annullare un’attività di pubblicazione.
exl-id: d9e25e52-ba9d-4088-ac95-8df76b69f5d3
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# Gestire le attività di pubblicazione tramite il dashboard di pubblicazione {#id205CC08305Z}

Quando nel sistema è in esecuzione un set elevato di attività di pubblicazione, diventa praticamente impossibile controllare singolarmente ogni mappa DITA per monitorare l&#39;attività di pubblicazione. Adobe Experience Manager Guides offre agli amministratori e agli editori una vista unificata di tutte le attività di pubblicazione in esecuzione nel sistema. Nel dashboard di pubblicazione è disponibile un elenco di tutte le attività di pubblicazione attive.

Il dashboard di pubblicazione offre una panoramica completa di tutte le attività di pubblicazione attualmente in esecuzione nel sistema.

![](images/publish-dashboard.png){align="left"}

Il dashboard di pubblicazione contiene i seguenti dettagli:

- **Titolo mappa**: titolo di un file di mappa attualmente pubblicato o presente nella coda di pubblicazione.

- **Nome file** - Nome file della mappa DITA.

- **Predefinito di output** - Nome del predefinito di output utilizzato per generare l&#39;output.

- **Avviato da** - Nome utente dell&#39;utente che ha avviato l&#39;attività di pubblicazione.

- **Avviato il** - Data e ora di inizio dell&#39;attività di pubblicazione.

- **Tempo trascorso** - Tempo trascorso dall&#39;esecuzione dell&#39;attività di pubblicazione nel sistema.

- **Icona Elimina** - Annulla o interrompi un&#39;attività di pubblicazione.

Il pannello a sinistra nel dashboard di pubblicazione fornisce le seguenti opzioni di filtro:

- **Predefinito di output** - Selezionare uno o più predefiniti di output per i quali si desidera visualizzare le attività di pubblicazione attualmente attive. Nella schermata seguente, le attività di pubblicazione vengono filtrate in modo da mostrare solo le attività che utilizzano il predefinito di output Sito di AEM:

  ![](images/publish-dashboard-preset-filter.png){align="left"}

- **Avviato da** - Selezionare un nome utente dall&#39;elenco per visualizzare le attività di pubblicazione avviate dall&#39;utente selezionato.

- **Mappa** - Seleziona un file di mappa dall&#39;elenco per visualizzare le attività di pubblicazione in esecuzione per la mappa selezionata.

## Accedere al dashboard di pubblicazione

Puoi accedere a **Publish Dashboard** direttamente dalla [home page di Experience Manager Guides](./intro-home-page.md). Apri la home page e seleziona l&#39;opzione **Pubblica coda** nel pannello a sinistra.

>[!NOTE]
>
> Solo un amministratore o un editore può accedere al dashboard di pubblicazione.

Puoi anche accedere a **Publish Dashboard** dalla pagina **Strumenti** di Adobe Experience Manager. Per utilizzare questo metodo, effettuare le seguenti operazioni:

1. Seleziona il logo Adobe Experience Manager nella parte superiore, quindi seleziona **Strumenti**.

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Selezionare il riquadro **Pubblica dashboard**.

   Viene visualizzato il dashboard di pubblicazione con un elenco di tutte le attività di pubblicazione attive nel sistema.

   Se si seleziona il collegamento Nome file, viene visualizzato il dashboard delle mappe DITA della mappa selezionata.

   ![](images/publish-dashboard-click-filename-link.png){align="left"}


>[!NOTE]
>
> Puoi anche accedere alla dashboard di pubblicazione dalla scheda **Output** durante la generazione dell&#39;output dalla dashboard delle mappe. Per ulteriori dettagli, consultare [Visualizzare lo stato dell&#39;attività di generazione output](generate-output-for-a-dita-map.md#viewing_output_history).

## Annullare un’attività di pubblicazione

Per annullare un’attività di generazione output dal dashboard di pubblicazione, effettua le seguenti operazioni:

1. [Accedi al dashboard di pubblicazione](#access-the-publish-dashboard).

1. Dall&#39;elenco delle attività di pubblicazione attive, selezionare l&#39;icona Elimina di un&#39;attività che si desidera annullare.

   ![](images/publish-dashboard-cancel-task.png){align="left"}

1. Selezionare **Sì** al prompt dei messaggi **Conferma annullamento**.

   Il comando di annullamento viene accettato e l&#39;annullamento viene tentato finché l&#39;attività rimane attiva. Una volta terminata, l&#39;attività viene rimossa dall&#39;elenco delle attività attualmente attivo. Lo stato dell&#39;attività viene aggiornato anche nel dashboard delle mappe DITA come Annullato. Nella schermata seguente, l&#39;attività *HTML5* è stata annullata dal dashboard di pubblicazione e il suo stato è stato modificato anche nel dashboard delle mappe DITA.

   ![](images/cancelled-output-task.png){align="left"}


**Argomento padre:**&#x200B;[&#x200B; Generazione output](generate-output.md)
