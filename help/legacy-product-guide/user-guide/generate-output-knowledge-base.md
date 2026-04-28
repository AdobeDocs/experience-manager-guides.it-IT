---
title: Knowledge Base
description: Learn how to create Knowledge Base preset from the web editor and the map dashboard. Configure Knowledge Base output preset in AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 5fc81de9-9ae0-4cd4-a7ef-b52eed2479f7
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 2%

---

# Knowledge Base {#knowledge-base}

You can create the **Knowledge Base** preset from the Web Editor:

In the Repository panel, open the DITA map file in **Map View**, then in the **Output** tab, select the + icon to create an output preset, and then select **Knowledge Base** from the **Type** dropdown in the **New output preset** dialog. You can name the preset and choose the target to generate the output using the **Adobe Experience Manager**, **Salesforce**, or **ServiceNow**.




## Knowledge Base configuration{#knowledge-base-configuration}


In the Web editor, the following configurations have been organized under the **General** and **Articles** tabs. You can also configure the settings for the specific **Knowledge Base** you have selected as a target, **Adobe Experience Manager**, **Salesforce**, or **ServiceNow**.


### Generale

| Knowledge Base  options | Descrizione |
| --- | --- |
| Applica condizioni utilizzando | Select one of the following options:<br><br>* **None applied**: Select this option if you don&#39;t want to apply any condition on the published output.<br>* **DITAVAL file**: Select DITAVAL file(s) to generate personalized content. You can select multiple DITAVAL files using the browse dialog or by typing the file path. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVAL vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. If the DITAVAL file is moved to another location or deleted, it&#39;s not automatically deleted from the preset. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. You can hover over the file name to view the path in the Adobe Experience Manager repository where the file is stored. You can only select DITAVAL files, and an error is displayed if you select any other file type.<br>* **Condition preset**: Select a condition preset from the dropdown to apply a condition while publishing the output. L&#39;opzione è visibile se è stata aggiunta una condizione presente nella scheda Predefiniti condizione della console Mappa DITA. To know more about condition presets, view [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usa linea di base | Se è stata creata una baseline per la mappa DITA selezionata, selezionare questa opzione per specificare la versione da pubblicare.<br><br>View [Work with Baseline](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) for more details. |
| Flusso di lavoro di post-generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in Adobe Experience Manager. È necessario selezionare un flusso di lavoro da eseguire al termine della generazione dell&#39;output.<br><br>**Nota**: ulteriori informazioni su come [personalizzare il flusso di lavoro di generazione post-output](/help/product-guide/cs-install-guide/customize-workflows.md#id17A6GI004Y4) nella Guida all&#39;installazione e alla configurazione per Cloud Services. |

### ServiceNow

| Opzioni ServiceNow | Descrizione |
| --- | --- |
| Profilo di pubblicazione | Utilizza il menu a discesa per selezionare dai profili di connessione ServiceNow configurati dall’amministratore. Per ulteriori informazioni su come l&#39;amministratore può creare un profilo di pubblicazione, visualizzare la descrizione della funzione **Impostazioni editor** nella sezione [Pannello sinistro](./web-editor-features.md#id2051EA0M0HS). |
| Knowledge Base | Utilizzare questo campo per selezionare la Knowledge Base ServiceNow richiesta. È possibile configurare le knowledge base nel sito ServiceNow per archiviare il contenuto in base alle autorizzazioni. Gli articoli di questa mappa DITA possono essere pubblicati in queste knowledge base. |
| Categoria e sottocategoria | Le categorie sono simili agli alberi gerarchici utilizzati per trovare e classificare gli articoli della Knowledge Base di ServiceNow. Aggiungere una categoria e una sottocategoria per pubblicare gli argomenti e i sottoargomenti del sommario in tale categoria e sottocategoria sul sito ServiceNow. |

### Salesforce

| Opzioni Salesforce | Descrizione |
| --- | --- |
| Profilo di pubblicazione | Utilizza il menu a discesa per selezionare tra i profili di connessione Salesforce configurati dall’amministratore. Per ulteriori informazioni su come l&#39;amministratore può creare un profilo di pubblicazione, visualizzare la descrizione della funzione **Impostazioni editor** nella sezione [Pannello sinistro](./web-editor-features.md#id2051EA0M0HS). |
| Tipo di record | Utilizza il menu a discesa per selezionare tra i tipi di record impostati in Salesforce in base alle impostazioni di visibilità basate sul profilo utente. I tipi di record di Salesforce consentono di raggruppare più record di un tipo per l&#39;oggetto. Definiscono la modalità di organizzazione della pubblicazione. Ad esempio, puoi selezionare FAQ Tipo di record e pubblicare in base al layout e ai campi della pagina FAQ. |
| Campo contenuto articolo | È possibile avere campi diversi e un layout univoco per ogni modello di tipo di record. Utilizzare questi campi per immettere informazioni specifiche in base al tipo di articolo. Ad esempio, puoi visualizzare il titolo, la risposta e l’equazione di un articolo di domande frequenti. |
| Categorie | Seleziona una categoria dal menu a discesa per pubblicare gli argomenti del sommario in quella categoria sul sito Salesforce. |

You can also view the following options in the Salesforce and ServiceNow presets:

| Opzioni | Descrizione |
| --- | --- |
| Remove the topic heading from the article body. | Select this option to remove the topic heading from the article in the published output. |
| Upload as draft | Select this option to upload the topic to share it as a draft before making it available to the users. |
| Upload images | Select this option if you want any images in topics to be included in the published output. |
| Upload linked documents | Select this option to include the documents linked in topics in the published output. |

### Adobe Experience Manager

>[!NOTE]
>
>You can use Adobe Experience Manager Knowledge Base preset if your administrator has configured it. For more details, view [Article-based publishing from the Web Editor](/help/product-guide/install-guide/configure-article-based-publishing.md) section in the Installation and Configuration Guide.

| Adobe Experience Manager options | Descrizione |
| --- | --- |
| Use article path | Select this option to view the **Article path** of the folder that contains the Knowledge Base templates. |
| Article Path | This field appears if you select the option **Use article path**. Browse to select the  Knowledge Base Site within your Adobe Experience Manager repository where the output is stored. |
| Sito | Use this field to select the required Adobe Experience Manager Knowledge Base. You can configure knowledge bases in the Adobe Experience Manager site to store the content based on the permissions. Gli articoli di questa mappa DITA possono essere pubblicati in queste knowledge base. |
| Categoria | Select a category from the dropdown to publish the topics of the TOC  in that category on the Adobe Expereince Manager site. |
| Section Template and Article Template | These are the structural components used to organize the content of your output. These are predefined in the Adobe Experience Manager Site template. |
| Flusso di lavoro di post-generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in Adobe Experience Manager. È necessario selezionare un flusso di lavoro da eseguire dopo il completamento del flusso di lavoro di generazione dell&#39;output.<br>Ulteriori informazioni su come [personalizzare il flusso di lavoro di generazione post-output](/help/product-guide/install-guide/customize-workflows.md#id17A6GI004Y4) nella Guida all&#39;installazione e alla configurazione. |

>[!TIP]
> 
>Selezionare **Aggiorna** ![icona di aggiornamento](images/navtitle-refresh-icon.svg) per compilare i rispettivi modelli nei campi in base al modello della Knowledge Base selezionato.

### Articoli

Questa scheda visualizza la struttura o la vista gerarchica della mappa. Scegliere gli argomenti da pubblicare in una knowledge base. Espandere un nodo del sommario e scegliere gli argomenti da pubblicare.

**Argomento padre:** [Informazioni sui predefiniti di output](generate-output-understand-presets.md)
