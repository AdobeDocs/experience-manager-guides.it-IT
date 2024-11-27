---
title: Gestire le attività di pubblicazione tramite la dashboard di Publish
description: Gestisci le attività di pubblicazione utilizzando la dashboard di Publish in AEM Guides. Scopri come accedere al dashboard di pubblicazione e annullare un’attività di pubblicazione.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Gestire le attività di pubblicazione tramite la dashboard di Publish {#id205CC08305Z}

Quando nel sistema è in esecuzione un set elevato di attività di pubblicazione, diventa praticamente impossibile controllare singolarmente ogni mappa DITA per monitorare l&#39;attività di pubblicazione. AEM Guides offre agli amministratori e agli editori una vista unificata di tutte le attività di pubblicazione in esecuzione nel sistema. Nel dashboard di Publish è disponibile un elenco di tutte le attività di pubblicazione attive.

La dashboard di Publish offre una panoramica completa di tutte le attività di pubblicazione attualmente in esecuzione nel sistema.

![](images/publish-dashboard.png){width="800" align="left"}

La dashboard di Publish contiene i seguenti dettagli:

- **Titolo mappa**: titolo di un file di mappa attualmente pubblicato o presente nella coda di pubblicazione.

- **Nome file** - Nome file della mappa DITA.

- **Predefinito di output** - Nome del predefinito di output utilizzato per generare l&#39;output.

- **Avviato da** - Nome utente dell&#39;utente che ha avviato l&#39;attività di pubblicazione.

- **Avviato il** - Data e ora di inizio dell&#39;attività di pubblicazione.

- **Tempo trascorso** - Tempo trascorso dall&#39;esecuzione dell&#39;attività di pubblicazione nel sistema.

- **Icona Elimina** - Annulla o interrompi un&#39;attività di pubblicazione.

Il pannello a sinistra nel dashboard di Publish fornisce le seguenti opzioni di filtro:

- **Predefinito di output** - Selezionare uno o più predefiniti di output per i quali si desidera visualizzare le attività di pubblicazione attualmente attive. Nella schermata seguente, le attività di pubblicazione vengono filtrate per mostrare solo le attività che utilizzano il predefinito di output Sito AEM:

  ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Avviato da** - Selezionare un nome utente dall&#39;elenco per visualizzare le attività di pubblicazione avviate dall&#39;utente selezionato.

- **Mappa** - Seleziona un file di mappa dall&#39;elenco per visualizzare le attività di pubblicazione in esecuzione per la mappa selezionata.

## Accedere al dashboard di Publish {#id205CC100DY4}

Per accedere al dashboard di Publish, effettua le seguenti operazioni:

>[!NOTE]
>
> Solo un amministratore o un editore può accedere al dashboard di Publish.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Fai clic sul riquadro **Dashboard di Publish**.

   Viene visualizzato il dashboard di Publish con un elenco di tutte le attività di pubblicazione attive nel sistema.

   Se si fa clic sul collegamento Nome file, viene visualizzata la console delle mappe DITA della mappa selezionata.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> Mentre generate l&#39;output dal dashboard delle mappe, potete accedere al dashboard di Publish anche dalla scheda Output. Per ulteriori dettagli, vedere [Visualizzare lo stato dell&#39;attività di generazione output](generate-output-for-a-dita-map.md#viewing_output_history).

## Annullare un’attività di pubblicazione

Per annullare un’attività di generazione output dal dashboard di Publish, effettua le seguenti operazioni:

1. [Accedi al dashboard di Publish](#id205CC100DY4).

1. Nell&#39;elenco delle attività di pubblicazione attive fare clic sull&#39;icona Elimina di un&#39;attività che si desidera annullare.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Fare clic su **Sì** al prompt del messaggio Conferma annullamento.

   Il comando di annullamento viene accettato e l&#39;annullamento viene tentato finché l&#39;attività rimane attiva. Una volta terminata, l&#39;attività viene rimossa dall&#39;elenco delle attività attualmente attivo. Lo stato dell&#39;attività viene aggiornato anche nella console delle mappe DITA come Annullato. Nella schermata seguente, l&#39;attività *HTML5* è stata annullata da Publish Dashboard e il suo stato è stato modificato anche nella console delle mappe DITA.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Argomento padre:**[ Generazione output](generate-output.md)
