---
title: Utilizzare i predefiniti per le condizioni
description: Conoscere l’utilizzo dei predefiniti per le condizioni in AEM Guides. Scopri come creare, modificare, copiare ed eliminare i predefiniti per le condizioni in AEM.
feature: Publishing
role: User
hide: true
exl-id: 991179c7-186e-4b23-b918-248f596644ec
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 2%

---

# Utilizzare i predefiniti per le condizioni {#id1825FL004PN}

È possibile definire gli attributi negli argomenti DITA e utilizzare il predefinito di condizione per specificare cosa accade con l&#39;attributo nell&#39;output finale. Ad esempio, puoi aggiungere nel contenuto attributi come versione 1.0 e versione 2.0 e utilizzare un predefinito di condizione per includere la versione 1.0 per la versione 1.0 ed escludere la versione 2.0. Allo stesso modo, è possibile aggiungere al contenuto attributi come OS Windows e OS Linux e quindi includere o escludere il contenuto rilevante per l&#39;output finale in base al sistema operativo.

Puoi creare i predefiniti per le condizioni in due modi:

* Dall&#39;editor Web: consente di creare e gestire i predefiniti di condizione per una mappa DITA dall&#39;editor Web.
* Dal dashboard delle mappe: consente di creare e gestire i predefiniti per le condizioni di una mappa DITA dal dashboard delle mappe.


## Predefiniti di condizione dall’editor web

Experience Manager Guides consente di gestire i predefiniti per le condizioni dall’editor web e di utilizzarli all’interno dei predefiniti di output per generare l’output finale.
È possibile creare e visualizzare i predefiniti per le condizioni, visualizzare gli attributi e gestire le azioni per la mappa corrente dalla visualizzazione **Predefiniti per le condizioni** nell&#39;editor Web.

<img src="images//manage-condtions-presets.png" alt= "Predefiniti condizione nell’editor web" width="800" border="1px">



### Creare un predefinito di condizione

La visualizzazione **Predefiniti condizione** fornisce informazioni dettagliate sui predefiniti condizione, ad esempio gli attributi, i valori e le azioni.
Per creare un predefinito per le condizioni degli argomenti, effettua le seguenti operazioni:

1. Nel pannello **Archivio**, apri il file mappa DITA in Vista mappa.
1. Selezionare la scheda **Gestisci**.
1. Selezionare **Predefiniti condizione** a sinistra. Viene visualizzato l&#39;elenco dei predefiniti di condizioni definiti per la mappa DITA.
1. Seleziona l&#39;icona + accanto a **Predefiniti condizione** per aprire la finestra di dialogo **Nuovo predefinito condizione**.
1. Immettete un nome univoco per il predefinito.

   >[!NOTE]
   >
   > Viene visualizzato un errore se il campo del nome è vuoto o se si immette un carattere non valido o un nome uguale a un predefinito di condizione esistente. È possibile utilizzare un trattino &quot;-&quot; o il carattere di sottolineatura &quot;_&quot; come separatore.

1. Seleziona **Crea**.
Il nuovo predefinito di condizione viene aggiunto all’elenco.
1. Fai doppio clic su un predefinito di condizione per visualizzare gli attributi e le azioni.
Il pannello **Attributi** mostra tutti gli attributi aggiunti a qualsiasi riferimento presente nella mappa. Il pannello a destra mostra solo le condizioni aggiunte ai predefiniti condizione.
1. Per aggiungere gli attributi, effettuate una delle seguenti operazioni:
   * Seleziona uno o più attributi per aggiungere tutti i valori al relativo predefinito di condizione. Ad esempio, è possibile selezionare l&#39;attributo `platform` per aggiungerne tutti i valori.
   * Seleziona uno o più valori di attributo per aggiungerli al predefinito di condizione. Ad esempio, puoi selezionare i valori `Unix` e `Win` dell&#39;attributo platform
   * Selezionate una coppia di attributi e valori e trascinatela nel pannello centrale. Ad esempio, è possibile selezionare il valore `Unix` dell&#39;attributo platform e trascinarlo.
   * **Seleziona tutto** per aggiungere tutti gli attributi e i relativi valori al predefinito di condizione.
Per impostazione predefinita, l&#39;azione per un attributo è `Include`.

1. Seleziona **Aggiungi**. Puoi ripetere questo passaggio per aggiungere altri attributi. Gli attributi aggiunti vengono spostati dal pannello centrale a quello di destra.
1. Seleziona Rimuovi nella barra delle azioni in alto per rimuovere gli attributi selezionati nel pannello di destra.
1. (Facoltativo) Se necessario, puoi sovrascrivere l’azione applicata agli attributi.
Effettua una delle seguenti operazioni:
   * Per qualsiasi attributo, seleziona una delle azioni seguenti dal menu a discesa Azione.
      * Includi
      * Escludi
      * Passthrough
      * Flag
   * Seleziona più righe di attributi dal pannello di destra e scegli un’azione dalla barra delle azioni in alto. Ad esempio, puoi selezionare Escludi azione per gli attributi selezionati.
1. Seleziona **Salva** per salvare il predefinito di condizione.

   >[!NOTE]
   >
   > Se selezionate un altro predefinito o chiudete il predefinito senza salvarlo, viene visualizzato un avviso.

Dopo aver creato un predefinito di condizione, questo viene visualizzato nel menu a discesa **Predefiniti di condizione** dei predefiniti di output. Ulteriori informazioni su come [pubblicare l&#39;output di PDF](/help/product-guide/web-editor/native-pdf-web-editor.md).

### Rename a condition preset

Perform the following steps to rename a condition preset:

1. Hover over a condition preset from the **Condition Presets** panel.
1. Select **Rename** from the Options menu to open the **Rename condition preset** dialog.
1. Edit the name of the condition preset.
1. Fai clic su **Rinomina**.

### Duplicate a condition preset

Perform the following steps to duplicate a condition preset:

1. Hover over  a condition preset from the **Condition Presets** panel.
1. Select **Duplicate** from the Options menu to open the **Duplicate condition preset** dialog.
   >[!NOTE]
   >
   > The default name of the preset is `<selected condition preset name>_1`. Puoi modificare il nome in base alle tue esigenze.

1. Fai clic su **Duplica**.

### Delete condition preset

Perform the following steps to delete condition presets:

1. Hover over  a condition preset from the **Condition Presets** panel.
1. Select **Delete** from the Options menu to open the **Delete condition preset** dialog.
1. Fai clic su **Elimina**.



## Condition presets from the map dashboard


### Creare un predefinito di condizione

Perform the following steps to create a condition preset:

1. Select **Condition Presets** tab in the DITA map console.
1. Click **Create** button.
1. Enter a name for the preset in **Name Condition**.
1. Select one of the following default actions from **Set default action to** drop-down:

   * Includi
   * Escludi
   * Passthrough
   * Flag
The action is set as default action for all the attributes whether they are added to the condition preset or not.

   For example, you have 15 condition attributes in your document and you have included four of them in the condition preset. If you select **exclude** as default action, it is applied to all 15 attributes.

1. Per aggiungere gli attributi, effettuate una delle seguenti operazioni:
   * Click **Add** to one attribute to the condition preset. Puoi ripetere questo passaggio per aggiungere altri attributi.
   * Click **Add all** to add all the attributes to the condition preset.
1. \(Optional\) If required, you can override the default action applied to the attributes in Step 4. Effettua una delle seguenti operazioni:
   * Select multiple attributes, choose an action from **Set the action for selected conditions to**, and click **Apply**.
   * Select an action for an attribute from the **Action** drop-down.
1. Fai clic su **Salva**.

### Edit a condition preset

You can make changes in an existing condition preset to change the actions applied to the attributes in the condition preset. Perform the following steps to edit a condition preset:

1. Select **Condition Presets** tab in the DITA map console.
1. Click **Edit** button.
1. Make required changes for all the attributes in the condition preset.
1. Fai clic su **Salva**.

### Create a copy of a condition preset

You can create a copy of a condition preset and then modify it according to your requirement. Perform the following steps to create a copy of a condition preset:

1. Select **Condition Presets** tab in the DITA map console.
1. Click **Duplicate** button.

   >[!NOTE]
   >
   > The default name of the preset is `<selected condition preset name>_Duplicate`

   You can change the name according to your requirement.

1. \(Optional\) Make required changes for all the attributes in the condition preset.
1. Fai clic su **Salva**.

### Delete condition preset

You can delete one or more condition presets from the **Condition Preset** tab of the DITA map console. Per eliminare i predefiniti di condizione, effettua le seguenti operazioni:

1. Selezionare la scheda **Predefiniti condizione** nella console delle mappe DITA.
1. Seleziona il predefinito di condizione\(s\) da eliminare.
1. Fare clic sul pulsante **Rimuovi**.
1. Fai clic su **Rimuovi** per confermare l&#39;azione.

**Argomento padre:**&#x200B;[&#x200B; Generazione output](generate-output.md)
