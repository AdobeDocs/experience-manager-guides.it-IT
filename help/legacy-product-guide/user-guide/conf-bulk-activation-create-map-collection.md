---
title: Creare una raccolta di mappe di attivazione in blocco
description: Scopri come creare una raccolta di mappe di attivazione in blocco nelle guide di AEM.
feature: Publishing, Bulk Activation
role: User
hide: true
exl-id: a242efde-2b29-4d2b-8a50-fd4ae7e8f239
TQID: https://experienceleague.adobe.com/ADaV0D2fpnxIo3tKN9zw-oUKyN6wWgALOMmgt3yJfgw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 735
ht-degree: 0%

---

# Creare una raccolta di mappe di attivazione in blocco {#id214GG0E90EV}

Per creare una raccolta di mappe di attivazione in blocco, effettuare le seguenti operazioni:

1. Selezionare **Guide** dall&#39;elenco degli strumenti.

1. Seleziona il collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Seleziona il riquadro **Dashboard di pubblicazione in blocco**.

   Per la prima volta, viene visualizzata una pagina di raccolte vuota. Se in precedenza hai creato raccolte per l&#39;attivazione in blocco, queste vengono visualizzate in questa pagina.

1. Fai clic su **Crea**.

1. Immetti un titolo per la raccolta di mappe di attivazione in blocco e fai clic su **Crea**.

   Viene visualizzato un messaggio di operazione riuscita al momento della creazione della raccolta di mappe di attivazione in blocco.

1. Fai clic su **Apri** nel messaggio di operazione riuscita.

1. Seleziona **Modifica**, quindi seleziona **Aggiungi mappe**.

1. Individuare e aggiungere le mappe DITA che si desidera aggiungere alla raccolta di mappe di attivazione in blocco.

   Per impostazione predefinita, tutti i predefiniti e le impostazioni internazionali associati alla mappa vengono aggiunti automaticamente.

1. Selezionare l&#39;output desiderato attivando o disattivando il pulsante scorrevole.

   È possibile scegliere più predefiniti di output tra le diverse lingue disponibili.

1. Fai clic su **Fine**.

I file di mappa DITA vengono aggiunti alla raccolta di mappe per l&#39;attivazione in blocco.

![ ha creato la raccolta di attivazione in blocco](images/bulk-activation-collection-created.png){width="800"}

## Scheda Mappe e predefiniti

La scheda **Mappe e predefiniti** presenta le informazioni nelle colonne seguenti:

- **Mappa**: mostra il titolo del file di mappa DITA.
- **Percorso mappa**: mostra il percorso completo del file di mappa DITA.

- **UUID**: mostra l&#39;identificatore univoco associato al file.

- **Lingua**: mostra il codice della lingua della mappa DITA.
- **Predefinito**: mostra il titolo del predefinito di output configurato nel file di mappa. Inoltre, visualizza l’icona in base al tipo di predefinito di output.

  >[!NOTE]
  >
  > La piccola icona ![](images/global-preset-icon.svg) indica un predefinito a livello di profilo della cartella.

- **Modificato**: indica se la mappa DITA è stata aggiornata dopo l&#39;ultima pubblicazione. In base a queste informazioni, è possibile decidere se attivare o meno l&#39;output per questa mappa DITA.
- **Generato**: mostra la data e l&#39;ora dell&#39;ultimo output generato.
- **Pubblicato**: mostra la data e l&#39;ora dell&#39;ultimo output pubblicato (o attivato). Se selezioni il collegamento, viene visualizzata la pagina **Risultati attivazione**, che contiene i registri con informazioni sul percorso della directory principale in cui viene attivato il contenuto.

## Scheda Cronologia controlli

La scheda **Cronologia controlli** presenta informazioni sugli output delle mappe attivati nelle colonne seguenti:
- **Mappa**: mostra il titolo del file di mappa DITA.
- **Percorso mappa**: mostra il percorso completo del file di mappa DITA.
- **UUID**: mostra l&#39;identificatore univoco associato al file.
- **Lingua**: mostra il codice della lingua della mappa DITA.
- **Predefinito**: mostra il titolo del predefinito di output configurato nel file di mappa. Inoltre, visualizza l’icona in base al tipo di predefinito di output.
- **Stato**: mostra lo stato dell&#39;attivazione come completata o non riuscita.
- **Destinazione**: se generi l&#39;output in Experience Manager Guides as a Cloud Service, puoi visualizzarne la destinazione come Pubblica o Anteprima.

  >[!NOTE]
  >
  > La piccola icona ![](images/global-preset-icon.svg) indica un predefinito a livello di profilo della cartella.

- **Modificata**: indica se la mappa DITA è stata aggiornata dopo l&#39;ultima pubblicazione. In base a queste informazioni, è possibile decidere se attivare l&#39;output per questa mappa DITA.
- **Pubblicato**: mostra la data e l&#39;ora dell&#39;ultimo output pubblicato (o attivato). Se selezioni il collegamento, viene visualizzata la pagina Risultati attivazione, che contiene i registri con informazioni sul percorso della directory principale in cui viene attivato il contenuto.
  ![ ha creato la scheda della cronologia di controllo della raccolta di attivazione in blocco](images/bulk-collection-audit-history.png){width="800"}

  *Visualizza le informazioni sugli output delle mappe attivate nella scheda **Cronologia controllo**.*


  >[!NOTE]
  >
  > Gli output nella scheda **Cronologia controlli** sono ordinati in base alla colonna **Pubblicato**.



## Pannello sinistro

Nel pannello a sinistra sono disponibili le seguenti opzioni di filtro:

- **Modificato**: è possibile selezionare Sì o No. Se si seleziona sì, vengono visualizzate solo le mappe DITA modificate. Una mappa modificata è una mappa che è stata generata dall&#39;ultima pubblicazione.
- **Predefinito**: selezionare un predefinito per il quale si desidera filtrare i file di mappa. Questa colonna mostra il titolo del predefinito di output configurato nel file di mappa. Se ad esempio si sceglie il predefinito *Sito AEM*, verranno visualizzate solo le mappe con il predefinito di output *Sito AEM* configurato.
- **Lingua**: è possibile selezionare qualsiasi codice lingua disponibile e visualizzare solo la lingua selezionata nella scheda Mappe e predefiniti.

I filtri vengono aggiornati quando si passa dalla scheda **Mappe e predefiniti** alla scheda **Cronologia controlli** e viceversa.

**Argomento padre: **[Attivazione in blocco del contenuto pubblicato](conf-bulk-activation.md)
