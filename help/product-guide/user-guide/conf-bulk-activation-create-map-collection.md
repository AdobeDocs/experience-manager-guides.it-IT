---
title: Creare una raccolta di mappe di attivazione in blocco
description: Scopri come creare una raccolta di mappe di attivazione in blocco nelle guide AEM.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: 1be8cddcbf58696a53bfccf887a04e5807f2198e
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Creare una raccolta di mappe di attivazione in blocco {#id214GG0E90EV}

Per creare una raccolta di mappe di attivazione in blocco, effettuare le seguenti operazioni:

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Seleziona il collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Seleziona la **Dashboard pubblicazione in blocco** affiancare.

   Per la prima volta, viene visualizzata una pagina di raccolte vuota. Se in precedenza hai creato raccolte per l&#39;attivazione in blocco, queste vengono visualizzate in questa pagina.

1. Fai clic su **Crea**.

1. Immetti un titolo per la raccolta mappe di attivazione in blocco e fai clic su **Crea**.

   Viene visualizzato un messaggio di operazione riuscita al momento della creazione della raccolta di mappe di attivazione in blocco.

1. Clic **Apri** sul messaggio di successo.

1. Seleziona **Modifica** e quindi seleziona **Aggiungi mappe**.

1. Individuare e aggiungere le mappe DITA che si desidera aggiungere alla raccolta di mappe di attivazione in blocco.

   Per impostazione predefinita, tutti i predefiniti e le impostazioni internazionali associati alla mappa vengono aggiunti automaticamente.

1. Selezionare l&#39;output desiderato attivando o disattivando il pulsante scorrevole.

   È possibile scegliere più predefiniti di output tra le diverse lingue disponibili.

1. Clic **Fine**.

I file di mappa DITA vengono aggiunti alla raccolta di mappe per l&#39;attivazione in blocco.

![ raccolta attivazione in blocco creata](images/bulk-activation-collection-created.png){width="800" align="left"}

## Scheda Mappe e predefiniti

Il **Mappe e predefiniti** Questa scheda presenta le informazioni nelle colonne seguenti:

- **Mappa**: mostra il titolo del file di mappa DITA.
- **Percorso mappa**: mostra il percorso completo del file di mappa DITA.

- **UUID**: mostra l’identificatore univoco associato al file.

- **Lingua**: mostra il codice della lingua della mappa DITA.
- **Predefinito**: mostra il titolo del predefinito di output configurato nel file di mappa. Inoltre, visualizza l’icona in base al tipo di predefinito di output.

  >[!NOTE]
  >
  > Il piccolo ![](images/global-preset-icon.svg) icona indica un predefinito a livello di profilo della cartella.

- **Modificato**: indica se la mappa DITA viene aggiornata dopo l&#39;ultima pubblicazione. In base a queste informazioni, è possibile decidere se attivare o meno l&#39;output per questa mappa DITA.
- **Generato**: mostra la data e l’ora dell’ultimo output generato.
- **Pubblicato**: mostra la data e l’ora dell’ultimo output pubblicato (o attivato). Se selezioni il collegamento, il **Risultati attivazione** viene visualizzata la pagina, che contiene i registri con informazioni sul percorso della directory principale in cui viene attivato il contenuto.

## Scheda Cronologia controlli

Il **Cronologia dei controlli** Questa scheda presenta le informazioni sugli output delle mappe attivate nelle colonne seguenti:
- **Mappa**: mostra il titolo del file di mappa DITA.
- **Percorso mappa**: mostra il percorso completo del file di mappa DITA.
- **UUID** : mostra l’identificatore univoco associato al file.
- **Lingua**: mostra il codice della lingua della mappa DITA.
- **Predefinito**: mostra il titolo del predefinito di output configurato nel file di mappa. Inoltre, visualizza l’icona in base al tipo di predefinito di output.
- **Stato**: mostra lo stato di attivazione come riuscita o non riuscita.
- **Destinazione**: se generi l’output in Guide di Experience Manager as a Cloud Service, puoi visualizzarne la destinazione come Pubblica o Anteprima.

  >[!NOTE]
  >
  > Il piccolo ![](images/global-preset-icon.svg) icona indica un predefinito a livello di profilo della cartella.

- **Modificato**: indica se la mappa DITA è stata aggiornata dopo l&#39;ultima pubblicazione. In base a queste informazioni, è possibile decidere se attivare l&#39;output per questa mappa DITA.
- **Pubblicato**: mostra la data e l’ora dell’ultimo output pubblicato (o attivato). Se selezioni il collegamento, viene visualizzata la pagina Risultati attivazione, che contiene i registri con informazioni sul percorso della directory principale in cui viene attivato il contenuto.
  ![ scheda cronologia audit raccolta attivazione in blocco creata](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Visualizzare le informazioni sugli output mappa attivati in **Cronologia dei controlli**scheda.*


  >[!NOTE]
  >
  > Le uscite nel **Cronologia dei controlli** sono ordinati in base al **Pubblicato** colonna.



## Pannello sinistro

Nel pannello a sinistra sono disponibili le seguenti opzioni di filtro:

- **Modificato**: puoi selezionare Sì o No. Se si seleziona sì, vengono visualizzate solo le mappe DITA modificate. Una mappa modificata è una mappa che è stata generata dall&#39;ultima pubblicazione.
- **Predefinito**: seleziona un predefinito per il quale vuoi filtrare i file di mappa. Questa colonna mostra il titolo del predefinito di output configurato nel file di mappa. Ad esempio, se scegli *Sito AEM* predefinito, vengono visualizzate solo le mappe che presentano *Sito AEM* predefinito di output configurato su di essi.
- **Lingua**: puoi selezionare uno qualsiasi dei codici della lingua disponibili e visualizzare solo la lingua selezionata nella scheda Mappe e predefiniti.

I filtri vengono aggiornati quando si passa da **Mappe e predefiniti** scheda a **Cronologia dei controlli** e viceversa.

**Argomento principale: **[Attivazione in blocco di contenuti pubblicati](conf-bulk-activation.md)
