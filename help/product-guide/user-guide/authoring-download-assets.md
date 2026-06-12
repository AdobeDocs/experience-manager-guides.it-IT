---
title: Scarica file
description: Scopri come scaricare file dalla console delle mappe DITA in AEM Guides ed esportare un file di mappe DITA nell’archivio AEM.
exl-id: ae9eb355-d3ac-446a-958b-5f2da43f5533
feature: Content Management
role: User
TQID: https://experienceleague.adobe.com/xwz0wuugvwPsmIX78kuwv5te2NGcNTik-qoJvijRzzg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41id: ad602516-aca3-4247-9ae8-f393d958efa9id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 864
ht-degree: 0%

---

# Scarica file {#id216MC0H0BE8}

È possibile scaricare risorse, inclusi file DITA e non DITA. Esistono diversi modi per scaricare le risorse, alcuni metodi sono nativi per Adobe Experience Manager e altri sono supportati da Adobe Experience Manager Guides. Per informazioni sul download di risorse Adobe Experience Manager native, visualizza [Scarica risorse da Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) nella documentazione di Adobe Experience Manager. La sezione seguente spiega il meccanismo di download dei file in Experience Manager Guides.

## Scaricare un file di mappa DITA dall&#39;editor

Per scaricare un file di mappa DITA dall&#39;editor, effettuare le seguenti operazioni:

1. Passare alla mappa DITA da scaricare.
1. Selezionare la mappa DITA per aprirla nell&#39;editor.

1. Nella vista Mappa, seleziona l&#39;icona **Opzioni** e scegli **Scarica mappa** dall&#39;elenco.

   ![](images/download-map-option-editor.png)

   Viene visualizzata la finestra di dialogo **Scarica mappa**.

   ![](images/download-map-dialog-new.png){width="300"}

1. Nella finestra di dialogo Scarica mappa puoi scegliere le seguenti opzioni:

   - **Usa baseline**: selezionare questa opzione per ottenere un elenco di baseline create per la mappa DITA. Per scaricare il file mappa e il relativo contenuto in base a una baseline specifica, selezionare la baseline dall&#39;elenco a discesa. Per ulteriori dettagli sull&#39;utilizzo delle baseline, visualizzare [Utilizzo delle baseline](generate-output-use-baseline-for-publishing.md#).

   - **Opzioni per la gerarchia dei file**: è inoltre possibile utilizzare il menu a discesa della gerarchia dei file per scegliere la modalità di gestione della struttura delle cartelle per i file di mappa scaricati. Opzioni disponibili:

      - **Mantieni gerarchia file**: selezionare questa opzione dal menu a discesa per mantenere la struttura di cartelle esistente per i file scaricati.
      - **Flatten file hierarchy**: seleziona questa opzione dal menu a discesa per scaricare tutti gli argomenti e i file multimediali a cui si fa riferimento in un&#39;unica cartella.

     Per ogni opzione, è possibile specificare ulteriormente la modalità di gestione dei nomi dei file per i file scaricati. Sono disponibili le seguenti opzioni di nome file:

      - **Usa nome file GUID**: scarica il file di mapping con GUID come nome file.
      - **Usa nome file effettivo**: scarica il file mappa con il nome file originale. Quando questa opzione viene utilizzata con la gerarchia dei file Flatten, tutti i nomi di file duplicati nella mappa vengono risolti automaticamente aggiungendo suffissi numerici (_2, _3 e così via) per garantire nomi di file univoci.

   >[!NOTE]
   >
   > È inoltre possibile scaricare il file mappa senza selezionare alcuna opzione. In tal caso, viene scaricata l&#39;ultima versione persistente degli argomenti e dei file multimediali di riferimento.


1. Seleziona **Scarica**.

   La richiesta di download della mappa è in coda.

   ![](images/download-map-notification.png)

   Riceverai la seguente notifica quando la mappa sarà pronta per il download.

   ![](images/download-map-success-message.png){width="550"}

1. Seleziona **Scarica** per scaricare il file mappa in formato `.zip`. In alternativa, scaricalo in un secondo momento dalla casella in entrata di AEM.

   >[!NOTE]
   >
   > Per impostazione predefinita, le mappe scaricate rimangono per cinque giorni nella casella in entrata delle notifiche Adobe Experience Manager.

Una volta scaricata la mappa, puoi selezionarla e utilizzare l’icona Apri nella parte superiore per aprire il contenuto scaricato. Per visualizzare i metadati associati alla mappa scaricata, aprire il file `metdata.json` incluso nel contenuto scaricato. Questo file è disponibile per entrambe le opzioni *Gerarchia file*: Flatten file hierarchy e Retain file hierarchy.

## Scaricare un file di mappa DITA dal dashboard Mappa

Dopo aver inserito il file mappa DITA nell&#39;archivio di Adobe Experience Manager, è possibile scaricare il file mappa insieme ai relativi dipendenti. Questo offre la flessibilità di condividere l&#39;intero file di mappa per la modifica, la convalida, la revisione o semplicemente la creazione di un backup.

Per scaricare un file mappa DITA insieme ai relativi file dipendenti, effettuare le seguenti operazioni:

1. Nell&#39;interfaccia utente di Assets, passare alla mappa DITA che si desidera scaricare.

1. Selezionare la mappa DITA per aprirla nella console delle mappe DITA.

1. Selezionare la scheda **Argomenti** per visualizzare l&#39;elenco degli argomenti disponibili nella mappa DITA.

1. Nella barra degli strumenti principale, seleziona **Scarica mappa**.

   Viene visualizzata la finestra di dialogo Scarica mappa.

   ![](images/download-map.png){width="300"}

1. Seleziona **Scarica**. Nella finestra di dialogo Scarica mappa puoi scegliere le seguenti opzioni:

   - **Usa baseline**: selezionare questa opzione per ottenere un elenco delle baseline create per la mappa DITA. Per scaricare il file mappa e il relativo contenuto in base a una baseline specifica, selezionare la baseline dall&#39;elenco a discesa. Per ulteriori dettagli sull&#39;utilizzo delle baseline, visualizzare [Utilizzo delle baseline](generate-output-use-baseline-for-publishing.md#).

   - **Flatten File Hierarchy**: selezionare questa opzione per salvare tutti gli argomenti e i file multimediali di riferimento in un&#39;unica cartella.


   >[!NOTE]
   >
   > È inoltre possibile scaricare il file mappa senza selezionare alcuna opzione. In tal caso, viene scaricata l&#39;ultima versione persistente degli argomenti e dei file multimediali di riferimento.

1. Dopo aver selezionato il pulsante **Scarica**, la richiesta di download della mappa è in coda. Riceverai la seguente notifica quando la mappa sarà pronta per il download.

   ![](images/download-map-prompt.png){width="550"}

   - Seleziona **Scarica** per scaricare il file mappa in formato.zip.

   - Seleziona **Scarica più tardi** per scaricare il file mappa in un secondo momento. Il collegamento per il download è accessibile dalla casella in entrata delle notifiche Adobe Experience Manager. Seleziona la notifica della mappa generata nella casella in entrata per scaricare la mappa in formato .zip.

   >[!NOTE]
   >
   > Per impostazione predefinita, le mappe scaricate rimangono per cinque giorni nella casella in entrata delle notifiche Adobe Experience Manager.

![](images/download-map-inbox.png){width="300"}

Una volta scaricata la mappa, puoi selezionarla e utilizzare l’icona Apri nella parte superiore per aprire il contenuto scaricato.

**Argomento padre:**[ Gestisci contenuto](authoring.md)
