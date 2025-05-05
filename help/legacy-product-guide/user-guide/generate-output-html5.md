---
title: Usa HTML5
description: Scopri come creare un predefinito di HTML5 dall’editor web e dal dashboard delle mappe. Configura il predefinito di output di HTML5 in AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: e0ea38ac-84f1-4022-91e3-4827f123b26f
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 1%

---

# HTML5 {#id205BE700XO1}

L’output di HTML5 viene generato in una gerarchia di cartelle piatta. Ciò implica che la struttura di cartelle utilizzata dal contenuto nell’archivio non viene replicata nell’output di HTML5. L’intero contenuto viene pubblicato in formato di output HTML5 e salvato in un’unica cartella. I nomi dei file vengono sostituiti anche con gli UUID dei file nell’output generato. L&#39;unico file che non ha un nome di file basato su UUID è il file index.html.

Potete creare il predefinito HTML in due modi:

**Dall&#39;editor Web:** Nel pannello Archivio aprire il file di mappa DITA in visualizzazione mappa, quindi nella scheda Output selezionare l&#39;icona + per creare un predefinito di output e selezionare HTML5 dal menu a discesa Tipo nella finestra di dialogo Aggiungi predefinito.

>[!NOTE]
>
> È possibile scegliere il metodo per generare HTML5 utilizzando DITA-OT o FMPS \(se è stato configurato dall&#39;amministratore di sistema\).

Nell’editor web le configurazioni sono organizzate nelle schede Generali e Avanzate:

**Generale**

La scheda **Generale** contiene le seguenti configurazioni:

- Percorso di output
- Argomenti riga di comando DITA-OT
- Nome file
- Applica condizioni utilizzando \(se le condizioni sono definite per una mappa\)
- Usa baseline \(Se viene creata una baseline per una mappa\)
- Flusso di lavoro di post-generazione

**Avanzate**

La scheda Avanzate contiene le seguenti configurazioni:

- Nome trasformazione
- Mantieni file temporanei
- Proprietà file

Per ulteriori informazioni, vedere [Configurazione di HTML5](#id231KJA00REJ).

**Dal dashboard delle mappe**

Per aprire i predefiniti di output per PDF, fate clic su un file di mappa DITA dall&#39;interfaccia utente di Assets, quindi fate clic su Predefiniti di output e infine sull&#39;opzione HTML5. Nel dashboard Mappa, fai clic su **Modifica** in alto per aggiornare le varie configurazioni, quindi fai clic su **Salva**.

**Configurazione HTML5**

Per l&#39;output HTML5 sono disponibili le seguenti opzioni:

| Opzioni HTML5 | Descrizione |
| --- | --- |
| Tipo di output | Tipo di output che si desidera generare. Per generare l&#39;output di HTML5, scegliere l&#39;opzione HTML5. |
| Nome impostazione | Assegna un nome descrittivo alle impostazioni di output di HTML5 che stai creando. Ad esempio, puoi specificare _Output clienti interni_ o _Output utenti finali_. |
| Argomenti riga di comando DITA-OT | Specificare gli argomenti aggiuntivi che si desidera vengano elaborati da DITA-OT durante la generazione dell&#39;output. Per informazioni dettagliate sugli argomenti della riga di comando supportati in DITA-OT, vedere [Documentazione di DITA-OT](https://www.dita-ot.org/). |
| Genera reattivo tramite | Selezionate DITA-OT per generare l&#39;output di HTML5. |
| Applica condizioni utilizzando | Selezionare una delle opzioni seguenti:<br><br>* **Nessuna applicazione**: selezionare questa opzione se non si desidera applicare alcuna condizione all&#39;output pubblicato.<br>* **File DITAVal**: selezionare i file DITAVal per generare contenuto personalizzato. È possibile selezionare più file DITAVal utilizzando la finestra di dialogo Sfoglia o digitando il percorso del file. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVal vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. Se il file DITAVal viene spostato in un&#39;altra posizione o eliminato, non viene eliminato automaticamente dal dashboard delle mappe. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. Passa il cursore del mouse sul nome del file per visualizzare il percorso nell’archivio di AEM in cui è memorizzato il file. È possibile selezionare solo i file DITAVal e viene visualizzato un errore se è stato selezionato un altro tipo di file. FrameMaker Publishing Server non supporta più file DITAVAL.<br>* **Predefinito condizione**: seleziona un predefinito condizione dall&#39;elenco a discesa per applicare una condizione durante la pubblicazione dell&#39;output. L&#39;opzione è visibile se è stata aggiunta una condizione presente nella scheda Predefiniti condizione della console Mappa DITA. Per ulteriori informazioni sul predefinito di condizione, vedere [Utilizzare i predefiniti di condizione](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>È possibile selezionare più file DITAVAL utilizzando la finestra di dialogo Sfoglia o digitando il percorso del file. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVAL vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. Passa il cursore del mouse sul nome del file per visualizzare il percorso nell’archivio di AEM in cui è memorizzato il file. È possibile salvare solo file DITAVAL. Se hai selezionato un altro file, viene visualizzato un errore.<br><br>**Nota**: FrameMaker Publishing Server non supporta più file DITAVAL. |
| Nome trasformazione | Specifica il tipo di output da generare. Questa opzione è necessaria se si desidera generare l&#39;output utilizzando un plug-in personalizzato, integrato nel plug-in DITA-OT. Se ad esempio si desidera generare l&#39;output XHTML, specificare `xhtml`. Per un elenco delle trasformazioni disponibili in DITA-OT, vedere [Trasformazioni DITA-OT (formati di output)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) nella Guida utente OASIS DITA-OT. |
| Nome file | Specificare il nome del file con cui si desidera salvare l&#39;output di HTML5.<br><br>**Nota**: se non si specifica un nome di file, verrà utilizzato il titolo della mappa DITA per generare il nome finale del file di output di HTML5. Se la mappa non ha un titolo, viene utilizzato il nome del file della mappa DITA come output finale di HTML5. Il nome del file viene bonificato utilizzando le regole configurate nel sistema per gestire qualsiasi carattere non valido. |
| Esegui flusso di lavoro di post-generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in AEM. È necessario selezionare un flusso di lavoro da eseguire dopo il completamento del flusso di lavoro di generazione dell&#39;output.<br><br>**Nota**:per ulteriori informazioni sulla creazione di un flusso di lavoro di generazione post-output personalizzato, vedere _Personalizzare il flusso di lavoro di generazione post-output_ in Installare e configurare Adobe Experience Manager Guides as a Cloud Service. |
| Percorso di destinazione | Il percorso all’interno dell’archivio AEM in cui è memorizzato l’output di HTML5. |
| Mantieni file temporanei | Selezionare questa opzione per mantenere i file temporanei generati da DITA-OT. Se si verificano errori durante la generazione dell&#39;output tramite DITA-OT, selezionare questa opzione per mantenere i file temporanei. È quindi possibile utilizzare tali file per risolvere eventuali errori di generazione dell&#39;output.<br> <br> Dopo aver generato l&#39;output, selezionare l&#39;icona **Scarica file temporanei** ![Scarica file temporanei](images/download-temp-files-icon.png) per scaricare la cartella ZIP contenente i file temporanei. <br><br> **Nota**: se le proprietà del file vengono aggiunte durante la generazione, i file temporanei di output includono anche un file *metadata.xml* contenente tali proprietà. |
| Appiattisci gerarchia file | Selezionare l&#39;opzione per generare l&#39;output di HTML5 in una gerarchia di cartelle piatta. L’intero contenuto viene pubblicato in formato di output HTML5 in una gerarchia di file flat e salvato in un’unica cartella. <br> Se si deseleziona questa opzione, l&#39;output viene generato in una gerarchia di cartelle nidificate e l&#39;intera struttura di cartelle viene replicata. |
| Usa linea di base | Se è stata creata una baseline per la mappa DITA selezionata, selezionare questa opzione per specificare la versione da pubblicare.<br><br>Per ulteriori dettagli, vedere [Utilizzare la previsione](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF). |
| Proprietà file | Seleziona le proprietà da elaborare come metadati. Queste proprietà vengono impostate dalla pagina Proprietà del file mappa DITA o del file mappa segnalibro. Le proprietà selezionate dall&#39;elenco a discesa vengono visualizzate nel campo **Proprietà file**. Seleziona l’icona a forma di croce accanto alla proprietà per rimuoverla. <br><br>**Nota**: è inoltre possibile passare i metadati all&#39;output utilizzando la pubblicazione DITA-OT. Per ulteriori dettagli, vedere [Trasmettere i metadati all&#39;output utilizzando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Argomento padre:**&#x200B;[ Informazioni sui predefiniti di output](generate-output-understand-presets.md)
