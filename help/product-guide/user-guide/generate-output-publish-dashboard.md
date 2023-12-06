---
title: Gestire le attività di pubblicazione tramite il dashboard di pubblicazione
description: Gestisci le attività di pubblicazione utilizzando il dashboard di pubblicazione nelle guide AEM. Scopri come accedere al dashboard di pubblicazione e annullare un’attività di pubblicazione.
exl-id: d9e25e52-ba9d-4088-ac95-8df76b69f5d3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Gestire le attività di pubblicazione tramite il dashboard di pubblicazione {#id205CC08305Z}

Quando nel sistema è in esecuzione un set elevato di attività di pubblicazione, diventa praticamente impossibile controllare singolarmente ogni mappa DITA per monitorare l&#39;attività di pubblicazione. Le guide AEM forniscono agli amministratori e agli editori una vista unificata di tutte le attività di pubblicazione in esecuzione nel sistema. Nel dashboard di pubblicazione è disponibile un elenco di tutte le attività di pubblicazione attive.

Il dashboard di pubblicazione offre una panoramica completa di tutte le attività di pubblicazione attualmente in esecuzione nel sistema.

![](images/publish-dashboard.png){width="800" align="left"}

Il dashboard di pubblicazione contiene i seguenti dettagli:

- **Titolo mappa** : titolo di un file mappa attualmente in fase di pubblicazione o presente nella coda di pubblicazione.

- **Nome file** - Nome del file della mappa DITA.

- **Predefinito di output** - Nome del predefinito di output utilizzato per generare l&#39;output.

- **Avviato da** : nome utente dell’utente che ha avviato l’attività di pubblicazione.

- **Iniziato il** - Data e ora di inizio dell&#39;attività di pubblicazione.

- **Tempo trascorso** - Tempo trascorso da quando l’attività di pubblicazione è in esecuzione nel sistema.

- **Icona Elimina** - Annullare o terminare un&#39;attività di pubblicazione.

Il pannello a sinistra nel dashboard di pubblicazione fornisce le seguenti opzioni di filtro:

- **Predefinito di output** - Selezionare uno o più predefiniti di output per i quali si desidera visualizzare le attività di pubblicazione attualmente attive. Nella schermata seguente, le attività di pubblicazione vengono filtrate per mostrare solo le attività che utilizzano il predefinito di output Sito AEM:

  ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Avviato da** - Selezionare un nome utente dall&#39;elenco per visualizzare le attività di pubblicazione avviate dall&#39;utente selezionato.

- **Mappa** - Selezionare un file di mapping dall&#39;elenco per visualizzare le attività di pubblicazione in esecuzione per la mappa selezionata.

## Accedere al dashboard di pubblicazione {#id205CC100DY4}

Per accedere al dashboard di pubblicazione, effettua le seguenti operazioni:

>[!NOTE]
>
> Solo un amministratore o un editore può accedere al dashboard di pubblicazione.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Fai clic sul pulsante **Pubblica dashboard** affiancare.

   Viene visualizzato il dashboard di pubblicazione con un elenco di tutte le attività di pubblicazione attive nel sistema.

   Se si fa clic sul collegamento Nome file, viene visualizzata la console delle mappe DITA della mappa selezionata.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> Mentre generate l&#39;output dal dashboard mappa, potete accedere al dashboard Pubblica (Publish) anche dalla scheda Output (Output). Per ulteriori dettagli, consulta [Visualizza lo stato dell&#39;attività di generazione output](generate-output-for-a-dita-map.md#viewing_output_history).

## Annullare un’attività di pubblicazione

Per annullare un’attività di generazione output dal dashboard di pubblicazione, effettua le seguenti operazioni:

1. [Accedere al dashboard di pubblicazione](#id205CC100DY4).

1. Nell&#39;elenco delle attività di pubblicazione attive fare clic sull&#39;icona Elimina di un&#39;attività che si desidera annullare.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Clic **Sì** al prompt dei messaggi Conferma annullamento.

   Il comando di annullamento viene accettato e l&#39;annullamento viene tentato finché l&#39;attività rimane attiva. Una volta terminata, l&#39;attività viene rimossa dall&#39;elenco delle attività attualmente attivo. Lo stato dell&#39;attività viene aggiornato anche nella console delle mappe DITA come Annullato. Nella schermata seguente, *HTML5* l&#39;attività viene annullata da Publish Dashboard e il suo stato viene modificato anche nella console delle mappe DITA.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Argomento padre:**[ Generazione di output](generate-output.md)
