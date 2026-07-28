---
title: Predefiniti modello per la generazione di output
description: Scopri come creare e utilizzare i predefiniti di modello per la generazione di output in Adobe Experience Manager Guides.
source-git-commit: 0107a693c6d07c84f20dad7a9ffb53e8cb888d08
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 1%

---


# Configurare i predefiniti per modelli per la generazione di output

>[!NOTE]
>
> Il predefinito per modelli è disponibile in Experience Manager Guides as a Cloud Service a partire dalla versione 2026.08.0. Contatta il team di successo del cliente per abilitare questa funzione.

I predefiniti di modello consentono agli amministratori di standardizzare le configurazioni dei predefiniti di output su più mappe DITA. Invece di configurare singolarmente lo stesso predefinito di output per ogni mappa, puoi definire un predefinito come modello e applicarlo a tutte le mappe associate a un profilo di cartella.

Questa funzionalità consente di mantenere configurazioni di pubblicazione coerenti tra i progetti e riduce il lavoro di configurazione manuale.

## Vantaggi

L&#39;utilizzo dei predefiniti di modello offre i seguenti vantaggi:

- Assicura configurazioni di pubblicazione coerenti su più mappe.
- Riduce le operazioni manuali eliminando la configurazione ripetitiva dei predefiniti.
- Consente la gestione centralizzata delle impostazioni dei predefiniti di output.

## Tipi di output supportati

I predefiniti per modelli sono supportati per tutti i tipi di predefiniti di output, ad eccezione dei seguenti:

- Edge Delivery Services
- Knowledge Base
- SCORM

## Creare e gestire un predefinito per modelli

>[!NOTE]
>
> - I predefiniti modello possono essere creati e gestiti solo da **Amministratori** e **Amministratori profilo cartella**.
> - I predefiniti per modelli sono destinati alla gestione della configurazione e non vengono utilizzati direttamente per la generazione dell’output.

1. Configura il profilo di cartella da utilizzare per le cartelle.
2. Apri **Predefiniti di output** dalla console Mappa per la cartella associata.
3. Crea o seleziona il predefinito di output da utilizzare come modello.

   >[!NOTE]
   >
   > Quando crei o selezioni il predefinito di output da utilizzare come modello, accertati che sia aggiunto al profilo della cartella corrente.

4. Selezionare **Imposta come modello** dal menu **Opzioni** per il predefinito.

   ![](assets/template-preset.png){width="650"}

   Il predefinito di output selezionato viene convertito in un predefinito modello. I predefiniti modello sono identificati da un’icona modello, che li distingue dai normali predefiniti. Per rimuovere lo stato del modello, seleziona **Annulla impostazione come modello** dal menu **Opzioni** del predefinito del modello in qualsiasi momento.

   ![](assets/unset-as-template.png){width="650"}

5. Selezionare **Applica modifiche predefinito** dal menu **Opzioni** del predefinito del modello per applicare le impostazioni del predefinito aggiornato a tutte le mappe esistenti nel profilo di cartella selezionato.

   Viene visualizzata la finestra di dialogo **Applica modifiche predefinito**.

   ![](assets/apply-preset-change.png){width="350"}

6. Per sovrascrivere il predefinito esistente, selezionare la casella di controllo **Sovrascrivi predefinito esistente** e selezionare **OK**. La sovrascrittura aggiorna il predefinito ma non modifica le impostazioni Baseline, Predefinito condizione, DITAVAL, Elenco argomenti o Contesto di pubblicazione nel predefinito di destinazione. Queste impostazioni rimangono invariate.

   Viene visualizzata una finestra di dialogo **Conferma azione** che indica il numero di mappe a cui si applicano le modifiche del predefinito.

   ![](assets/confirm-preset-change.png){width="350"}

7. Selezionare **OK**.

Le modifiche vengono applicate a tutti i predefiniti in tutte le mappe all’interno delle cartelle associate.

>[!NOTE]
>
> Quando crei una nuova mappa nella cartella associata, la copia locale del predefinito di modello sarà disponibile anche per la nuova mappa creata.


## Comportamento generazione output

I predefiniti per modelli sono modelli di configurazione e non sono destinati alla pubblicazione diretta. Quando un predefinito è contrassegnato come modello:

- L’output di generazione non è disponibile.
- Impossibile utilizzare il predefinito modello per la pubblicazione.
- Gli output generati esistenti per il predefinito di modello rimangono accessibili se sono stati creati prima della conversione del predefinito in un modello.



