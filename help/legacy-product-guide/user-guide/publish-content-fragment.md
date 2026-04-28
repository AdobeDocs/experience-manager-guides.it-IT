---
title: Pubblicare un argomento in un frammento di contenuto
description: Pubblica un argomento o gli elementi di un argomento in un frammento di contenuto in AEM Guides.  Scopri come visualizzare i Frammenti di contenuto presenti in un argomento e ripubblicarli.
feature: Publishing
role: User
hide: true
exl-id: f8a8dfd3-19de-49ff-b4d4-265b3ac09488
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 1%

---

# Pubblicare frammenti di contenuto

I frammenti di contenuto sono parti discrete di contenuto in Adobe Experience Manager. Sono contenuti strutturati basati su un modello di contenuto. I frammenti di contenuto sono contenuti puri senza informazioni di progettazione o layout. Possono essere creati e gestiti indipendentemente dai canali supportati da Adobe Experience Manager. I frammenti di contenuto sono modulari, dove il contenuto viene suddiviso in componenti più piccoli.

Experience Manager Guides consente di pubblicare un argomento o i relativi elementi in un frammento di contenuto.

>[!NOTE]
>
>Puoi scegliere solo gli elementi in un argomento per i quali è stato definito un attributo id.


Per creare un frammento di contenuto, effettua le seguenti operazioni:

1. Crea un [modello per frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=it) in Adobe Experience Manager Assets.
1. Crea una cartella in cui salvare i frammenti di contenuto creati in base al modello Frammento di contenuto. Ad esempio, &quot;stock-content-fragments&quot;.
1. Modifica le proprietà della cartella (ad esempio, &quot;stock-content-fragments&quot;) e aggiungi il percorso della cartella, che contiene il modello Frammento di contenuto nella configurazione cloud.
Aggiungere ad esempio `/conf/we-retail` nella configurazione cloud. Questa configurazione collega tutti i modelli per frammenti di contenuto alla cartella.\
   ![aggiungi dettagli configurazione cloud nelle proprietà della cartella](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Aggiungi la configurazione cloud nelle proprietà della cartella per collegarla ai modelli di frammenti.*

1. Per generare un frammento di contenuto, selezionare **Nuovo output** ![nuova icona output](./images/Add_icon.svg) dalla sezione **Output** nelle **Proprietà file** di un argomento.
1. Seleziona **Frammento di contenuto**.\
   ![scheda opzioni proprietà file](./images/file-properties-outputs-tab.png) {width="300" align="left"}

   *Aggiungere un nuovo frammento di contenuto dalle proprietà del file di un argomento*.

1. Nella finestra di dialogo **Genera frammento di contenuto**, compila i seguenti dettagli nelle schede **Generale** e **Mappatura**.

   Scheda **Generale**
   ![Aggiungere il modello di frammento e i dettagli di mappatura nella finestra di dialogo Pubblica come frammento di contenuto](images/generate-content-fragment.png)
   *Aggiungi il percorso, il nome, il titolo e il filtro delle condizioni per pubblicare un argomento o i relativi elementi come frammento di contenuto.*


   * **Percorso**: sfoglia e seleziona il percorso della cartella in cui desideri pubblicare il frammento di contenuto. Se selezioni un frammento di contenuto esistente, questo sovrascrive il contenuto dei campi mappati.
   * **Titolo**: digita il titolo del frammento di contenuto. Per impostazione predefinita, il titolo viene compilato con il titolo dell’argomento. Puoi modificarlo. Questo titolo viene utilizzato per generare il nome del frammento di contenuto.
   * **Nome**: digitare il nome del frammento di contenuto. Per impostazione predefinita, il nome viene compilato con il titolo dell&#39;argomento e gli spazi vengono sostituiti con &quot;_&quot;. Ad esempio, *sample_content_fragment*. Puoi modificarlo.  Questo nome viene utilizzato per generare l’URL per il frammento di contenuto.

   * Puoi selezionare condizioni diverse per creare varianti di frammenti di contenuto. Seleziona una delle opzioni seguenti:
     >[!NOTE]
     > 
     > Le condizioni sono abilitate solo se gli attributi della condizione sono definiti nell&#39;argomento.

      * **Nessuno**: selezionare questa opzione se non si desidera applicare alcuna condizione all&#39;output pubblicato.
      * **Utilizzo di DITAVAL**: selezionare il file DITAVAL per includere o escludere contenuto specifico nell&#39;output generato. Potete selezionare il file DITAVAL utilizzando la finestra di dialogo Sfoglia (Browse) o digitando il percorso del file.
      * **Utilizzo di attributi**: è possibile definire attributi di condizione negli argomenti DITA. Quindi, seleziona l’attributo della condizione per pubblicare il contenuto pertinente.






   Scheda **Mappatura**

   ![Aggiungere il modello di frammento e i dettagli di mappatura nella finestra di dialogo Pubblica come frammento di contenuto](images/content-fragment-mapping.png)

   *Selezionare il modello per frammenti di contenuto e aggiungere i dettagli di mappatura per pubblicare un argomento o i relativi elementi come frammento di contenuto.*

   * **Modello**: seleziona il modello per frammenti di contenuto da utilizzare per creare il frammento di contenuto. The models are picked from the folder, which you have configured on Experience Manager Guides server.
   * **Mapping**: You can view the topic elements that have an id attribute applied to them. Drag the topic elements to the fields present in the content fragment model.
The right side is populated with the published Content Fragment contents in case of an existing Content Fragment. These can be overwritten with the topic contents if necessary. You can also select **Undo** to revert the mapping changes.


     >[!NOTE]
     >
     > If you are using 4.4 or earlier versions, select a mapping from the drop-down. It picks the mappings from the *contentFragmentMapping.json* file.  Your administrator can add the mappings in the *contentFragmentMapping.json* file. Learn more about how to [create a mapping between a topic and a Content Fragment](/help/product-guide/cs-install-guide/conf-content-fragment-mapping-cs.md) in the Installation and Configuration Guide.

1. Click **Generate** to publish the Content Fragment.

1. You can view the Content Fragments for a topic under the **Outputs** section in the **File Properties**.

   ![View the Content Fragments for a topic](images/outputs-options-menu.png){width="300" align="left"}

   *View the Content Fragments present for a topic and republish them.*


Once you&#39;ve published the Content Fragments, you can also use them in any Adobe Experience Manager Site.




## Options menu for a Content Fragment

You can also perform the following actions for a Content Fragment from the **Options** menu:

* **Generate**: Republish the Content Fragment to update it with the latest content from the DITA topic. When you regenerate the output, you can change the path, name, title, model, and mapping of the Content Fragment. You can also select different conditions while regenerating the output.

* **Duplicate**: Duplicate a Content Fragment. You can change the path, name, title, model, and the mapping. You can also select different conditions when you duplicate a Content Fragment to create a Content Fragment variant.

* **Remove**: Remove a Content Fragment from the outputs list. Viene visualizzata una richiesta di conferma. Dopo la conferma, il frammento di contenuto viene rimosso dall&#39;elenco **Output**.

  >[!NOTE]
  >
  > Con questa azione nessun contenuto viene eliminato dal frammento di contenuto.

* **Visualizza**: visualizza l&#39;editor frammenti di contenuto. Puoi anche apportare modifiche e salvarle.

## Miglioramento della migrazione da non-UUID a contenuti UUID

Il nuovo script di migrazione dei contenuti UUID è stato ottimizzato in modo significativo, rendendo la migrazione dei contenuti da Non-UUID a UUID 30 volte più veloce dello script precedente. Include funzioni quali la ripresa dai punti di controllo, informazioni live, tempo di completamento stimato e reporting dettagliato, garantendo un processo di migrazione armonioso. In particolare, il processo di migrazione mantiene i metadati delle risorse senza alcuna modifica. Lo script è stato testato e verificato su un ampio set di dati di 3 milioni di risorse, a conferma della sua efficienza e affidabilità per le migrazioni su larga scala.

Ulteriori informazioni sulla [migrazione di contenuti da non-UUID a UUID](/help/product-guide/install-guide/migrate-non-uuid-4-3.md).
