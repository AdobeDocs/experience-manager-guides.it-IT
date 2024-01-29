---
title: JSON
description: Scopri come creare un predefinito JSON dall’editor web e dal dashboard delle mappe. Configura il predefinito di output JSON nelle guide AEM.
exl-id: 9eb426fc-ca0a-4932-8a55-fea731281a0a
feature: Publishing
role: User
source-git-commit: 6006cabdc11b80179833a21b4d99d2f6c3f968ee
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 1%

---

# JSON {#id231KK0180T4}

Puoi creare il predefinito JSON dall’editor web:

Nel pannello Archivio, apri il file di mappa DITA in Vista mappa, quindi nella scheda Output seleziona l’icona + per creare un predefinito di output e seleziona JSON dal menu a discesa Tipo nella finestra di dialogo Aggiungi predefinito.

Nell’editor web, le seguenti configurazioni sono state organizzate in **Generale** scheda:

- Percorso di output
- File indice
- Applica condizioni utilizzando \(se le condizioni sono definite per una mappa\)
- Usa baseline \(Se viene creata una baseline per una mappa\)
- Proprietà da propagare nell’output
- Flusso di lavoro di post-generazione

Per ulteriori informazioni, consulta [Configurazione JSON](#id231KJA00REJ).


**Configurazione JSON**

Per il predefinito JSON sono disponibili le seguenti opzioni:

>[!NOTE]
>
> Puoi anche modificare il file JSON nell’editor web.

| Opzioni JSON | Descrizione |
| --- | --- |
| Percorso di output | Il percorso all’interno dell’archivio AEM in cui è memorizzato l’output JSON. |
| File indice | Puoi assegnare un nome al file di indice che stai creando per l’output JSON. Per impostazione predefinita, seleziona il nome del file della mappa DITA e aggiunge un suffisso (come `map_filename_index.json`).<br><br>È inoltre possibile utilizzare le variabili durante l&#39;impostazione del file di indice. Per ulteriori dettagli sull’utilizzo delle variabili, consulta [Utilizzare le variabili per impostare le opzioni Percorso di destinazione, Nome sito o Nome file](generate-output-use-variables.md#id18BUG70K05Z). |
| Applica condizioni utilizzando | Selezionare una delle opzioni seguenti:<br><br>* **Nessuna applicazione**: seleziona questa opzione se non desideri applicare alcuna condizione all’output pubblicato.<br>* **file DITAVAL**: seleziona i file DITAVAL per generare contenuti personalizzati. È possibile selezionare più file DITAVAL utilizzando la finestra di dialogo Sfoglia o digitando il percorso del file. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVAL vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. Se il file DITAVAL viene spostato in un&#39;altra posizione o eliminato, non viene eliminato automaticamente dal dashboard delle mappe. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. Passa il cursore del mouse sul nome del file per visualizzare il percorso nell’archivio AEM in cui è memorizzato il file. È possibile selezionare solo i file DITAVAL e viene visualizzato un errore se è stato selezionato un altro tipo di file.<br>* **Predefinito condizione**: seleziona un predefinito di condizione dal menu a discesa per applicare una condizione durante la pubblicazione dell’output. L&#39;opzione è visibile se è stata aggiunta una condizione presente nella scheda Predefiniti condizione della console Mappa DITA. Per ulteriori informazioni sul predefinito di condizione, consulta [Utilizzare i predefiniti per le condizioni](generate-output-use-condition-presets.md#id1825FL004PN). |
| Usa linea di base | Se è stata creata una baseline per la mappa DITA selezionata, selezionare questa opzione per specificare la versione da pubblicare.<br><br>Consulta [Utilizzare la previsione](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) per maggiori dettagli. |
| Proprietà da propagare nell’output | Seleziona le proprietà da elaborare come metadati. Queste proprietà vengono impostate dalla pagina Proprietà del file mappa DITA o del file mappa segnalibro. Le proprietà selezionate dall&#39;elenco a discesa sono elencate sotto il campo Proprietà.<br><br>**Nota**: puoi anche definire proprietà personalizzate e trasmettere i metadati all’output utilizzando la pubblicazione DITA-OT. Per maggiori dettagli vedi, [Utilizzare i metadati](metadata-dita.md#id21BJ00QD0XA). |
| Flusso di lavoro di post-generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in AEM. È necessario selezionare un flusso di lavoro da eseguire dopo il completamento del flusso di lavoro di generazione dell&#39;output.<br><br>**Nota**: per ulteriori informazioni sulla creazione di un flusso di lavoro personalizzato per la generazione post-output, consulta _Personalizzare il flusso di lavoro di generazione post-output_ nella guida Installare e configurare Adobe Experience Manager Guides as a Cloud Service. |

**Argomento padre:**[ Informazioni sui predefiniti di output](generate-output-understand-presets.md)
