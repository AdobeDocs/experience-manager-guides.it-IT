---
title: Knowledge Base
description: Scopri come creare un predefinito della Knowledge Base dall’editor web e dal dashboard delle mappe. Configura il predefinito di output della Knowledge Base in AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 5fc81de9-9ae0-4cd4-a7ef-b52eed2479f7
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 2%

---

# Knowledge Base {#knowledge-base}

È possibile creare il predefinito **Knowledge Base** dall&#39;editor Web:

Nel pannello Repository, apri il file di mappa DITA in **Vista mappa**, quindi nella scheda **Output** seleziona l&#39;icona + per creare un predefinito di output, quindi seleziona **Knowledge Base** dal menu a discesa **Tipo** nella finestra di dialogo **Nuovo predefinito di output**. È possibile denominare il predefinito e scegliere la destinazione per generare l&#39;output utilizzando **Adobe Experience Manager**, **Salesforce** o **ServiceNow**.




## Configurazione della Knowledge Base{#knowledge-base-configuration}


Nell&#39;editor Web, le seguenti configurazioni sono state organizzate nelle schede **Generale** e **Articoli**. È inoltre possibile configurare le impostazioni per la **Knowledge Base** specifica selezionata come destinazione, **Adobe Experience Manager**, **Salesforce** o **ServiceNow**.


### Generale

| Opzioni della Knowledge Base | Descrizione |
| --- | --- |
| Applica condizioni utilizzando | Selezionare una delle opzioni seguenti:<br><br>* **Nessuna applicazione**: selezionare questa opzione se non si desidera applicare alcuna condizione all&#39;output pubblicato.<br>* **File DITAVAL**: selezionare i file DITAVAL per generare contenuto personalizzato. È possibile selezionare più file DITAVAL utilizzando la finestra di dialogo Sfoglia o digitando il percorso del file. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVAL vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. Se il file DITAVAL viene spostato in un&#39;altra posizione o eliminato, non viene eliminato automaticamente dal predefinito. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. Passa il cursore del mouse sul nome del file per visualizzare il percorso nell’archivio di Adobe Experience Manager in cui è memorizzato il file. È possibile selezionare solo i file DITAVAL e viene visualizzato un errore se si seleziona un altro tipo di file.<br>* **Predefinito condizione**: seleziona un predefinito condizione dal menu a discesa per applicare una condizione durante la pubblicazione dell&#39;output. L&#39;opzione è visibile se è stata aggiunta una condizione presente nella scheda Predefiniti condizione della console Mappa DITA. Per ulteriori informazioni sui predefiniti di condizione, visualizzare [Usa predefiniti di condizione](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usa linea di base | Se è stata creata una baseline per la mappa DITA selezionata, selezionare questa opzione per specificare la versione da pubblicare.<br><br>Visualizza [Utilizza la previsione](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) per ulteriori dettagli. |
| Flusso di lavoro di post-generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in Adobe Experience Manager. Dopo aver completato la generazione dell’output, devi selezionare un flusso di lavoro da eseguire.<br><br>**Nota**: ulteriori informazioni su come [personalizzare il flusso di lavoro di generazione post-output](/help/product-guide/cs-install-guide/customize-workflows.md#id17A6GI004Y4) nella Guida all&#39;installazione e alla configurazione per Cloud Services. |

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

È inoltre possibile visualizzare le seguenti opzioni nei predefiniti di Salesforce e ServiceNow:

| Opzioni | Descrizione |
| --- | --- |
| Rimuovi l&#39;intestazione dell&#39;argomento dal corpo dell&#39;articolo. | Selezionare questa opzione per rimuovere l&#39;intestazione dell&#39;argomento dall&#39;articolo nell&#39;output pubblicato. |
| Carica come bozza | Seleziona questa opzione per caricare l’argomento e condividerlo come bozza prima di renderlo disponibile agli utenti. |
| Carica immagini | Selezionare questa opzione se si desidera includere nell&#39;output pubblicato tutte le immagini contenute negli argomenti. |
| Carica documenti collegati | Selezionare questa opzione per includere nell&#39;output pubblicato i documenti collegati agli argomenti. |


### Adobe Experience Manager

>[!NOTE]
>
>È possibile utilizzare il predefinito della Knowledge Base di Adobe Experience Manager se è stato configurato dall&#39;amministratore. Per ulteriori dettagli, visualizzare [Pubblicazione basata su articolo dalla sezione Web Editor](/help/product-guide/install-guide/configure-article-based-publishing.md) nella Guida all&#39;installazione e alla configurazione.

| Opzioni Adobe Experience Manager | Descrizione |
| --- | --- |
| Usa percorso articolo | Selezionare questa opzione per visualizzare il **percorso articolo** della cartella contenente i modelli della Knowledge Base. |
| Percorso articolo | Questo campo viene visualizzato se si seleziona l&#39;opzione **Usa percorso articolo**. Selezionare il sito della Knowledge Base all&#39;interno dell&#39;archivio Adobe Experience Manager in cui è memorizzato l&#39;output. |
| Sito | Utilizzare questo campo per selezionare la Knowledge Base di Adobe Experience Manager richiesta. Puoi configurare le knowledge base nel sito Adobe Experience Manager per archiviare il contenuto in base alle autorizzazioni. Gli articoli di questa mappa DITA possono essere pubblicati in queste knowledge base. |
| Categoria | Seleziona una categoria dal menu a discesa per pubblicare gli argomenti del sommario in quella categoria sul sito di Adobe Experience Manager. |
| Modello sezione e modello articolo | Si tratta dei componenti strutturali utilizzati per organizzare il contenuto dell’output. Sono predefiniti nel modello Sito Adobe Experience Manager. |
| Flusso di lavoro di post-generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in Adobe Experience Manager. È necessario selezionare un flusso di lavoro da eseguire dopo il completamento del flusso di lavoro di generazione dell&#39;output.<br>Ulteriori informazioni su come [personalizzare il flusso di lavoro di generazione post-output](/help/product-guide/install-guide/customize-workflows.md#id17A6GI004Y4) nella Guida all&#39;installazione e alla configurazione. |

>[!TIP]
> 
>Selezionare **Aggiorna** ![icona di aggiornamento](images/navtitle-refresh-icon.svg) per compilare i rispettivi modelli nei campi in base al modello della Knowledge Base selezionato.

### Articoli

Questa scheda visualizza la struttura o la vista gerarchica della mappa. Scegliere gli argomenti da pubblicare in una knowledge base. Espandere un nodo del sommario e scegliere gli argomenti da pubblicare.

**Argomento padre:** [Informazioni sui predefiniti di output](generate-output-understand-presets.md)
