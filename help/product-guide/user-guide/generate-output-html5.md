---
title: Usa HTML5
description: Scopri come creare un predefinito di HTML5 dall’editor web e dal dashboard delle mappe. Configura il predefinito di output HTML5 nelle guide AEM.
exl-id: b54bf3a0-7a13-41a0-ae72-cdf2caf8d974
feature: Publishing
role: User
source-git-commit: 6006cabdc11b80179833a21b4d99d2f6c3f968ee
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 1%

---

# HTML5 {#id205BE700XO1}

L’output di HTML5 viene generato in una gerarchia di cartelle piatta. Ciò implica che la struttura di cartelle utilizzata dal contenuto nell’archivio non viene replicata nell’output di HTML5. L’intero contenuto viene pubblicato in formato di output HTML5 e salvato in un’unica cartella. I nomi dei file vengono sostituiti anche con gli UUID dei file nell’output generato. L&#39;unico file che non ha un nome di file basato su UUID è il file index.html.

Il predefinito HTML può essere creato in due modi:

**Dall’editor web:** Nel pannello Repository, apri il file mappa DITA in Vista mappa, quindi nella scheda Output seleziona l’icona + per creare un predefinito di output e seleziona HTML5 dal menu a discesa Tipo nella finestra di dialogo Aggiungi predefinito.

>[!NOTE]
>
> È possibile scegliere il metodo per generare HTML5 utilizzando DITA-OT o FMPS \(se è stato configurato dall&#39;amministratore di sistema\).

Nell’editor web le configurazioni sono organizzate nelle schede Generali e Avanzate:

**Generale**

Il **Generale** La scheda contiene le seguenti configurazioni:

- Percorso di output
- Argomenti riga di comando DITA-OT
- Nome file
- Applica condizioni utilizzando \(se le condizioni sono definite per una mappa\)
- Usa baseline \(Se viene creata una baseline per una mappa\)
- Flusso di lavoro di post-generazione

**Avanzate**

La scheda Avanzate contiene le seguenti configurazioni:

- Nome trasformazione
- Pulisci file temporanei DITA-OT
- Proprietà file

Per ulteriori informazioni, consulta [Configurazione HTML5](#id231KJA00REJ).

**Dal dashboard delle mappe**

Per aprire i predefiniti di output per PDF, fai clic su un file di mappa DITA dall’interfaccia utente Assets, quindi fai clic su Predefiniti di output e infine sull’opzione HTML5. Nel dashboard Mappa, fai clic su **Modifica** nella parte superiore per aggiornare le varie configurazioni, quindi fai clic su **Salva**.

**Configurazione HTML5**

Per l’output di HTML5 sono disponibili le seguenti opzioni:

| Opzioni HTML5 | Descrizione |
| --- | --- |
| Tipo di output | Tipo di output che si desidera generare. Per generare l&#39;output di HTML5, scegliete l&#39;opzione HTML5. |
| Nome impostazione | Assegna un nome descrittivo alle impostazioni di output di HTML5 che stai creando. Ad esempio, puoi specificare _Output clienti interni_ o _output degli utenti finali_. |
| Argomenti riga di comando DITA-OT | Specificare gli argomenti aggiuntivi che si desidera vengano elaborati da DITA-OT durante la generazione dell&#39;output. Per informazioni dettagliate sugli argomenti della riga di comando supportati in DITA-OT, vedere [Documentazione DITA-OT](https://www.dita-ot.org/). |
| Genera reattivo tramite | Selezionate DITA-OT per generare l&#39;output di HTML5. |
| Applica condizioni utilizzando | Selezionare una delle opzioni seguenti:<br><br>* **Nessuna applicazione**: seleziona questa opzione se non desideri applicare alcuna condizione all’output pubblicato.<br>* **File DITAVal**: seleziona i file DITAVal per generare contenuto personalizzato. È possibile selezionare più file DITAVal utilizzando la finestra di dialogo Sfoglia o digitando il percorso del file. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVal vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. Se il file DITAVal viene spostato in un&#39;altra posizione o eliminato, non viene eliminato automaticamente dal dashboard delle mappe. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. Passa il cursore del mouse sul nome del file per visualizzare il percorso nell’archivio AEM in cui è memorizzato il file. È possibile selezionare solo i file DITAVal e viene visualizzato un errore se è stato selezionato un altro tipo di file. Il FrameMaker Publishing Server non supporta più file DITAVAL.<br>* **Predefinito condizione**: seleziona un predefinito di condizione dal menu a discesa per applicare una condizione durante la pubblicazione dell’output. L&#39;opzione è visibile se è stata aggiunta una condizione presente nella scheda Predefiniti condizione della console Mappa DITA. Per ulteriori informazioni sul predefinito di condizione, consulta [Utilizzare i predefiniti per le condizioni](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>È possibile selezionare più file DITAVAL utilizzando la finestra di dialogo Sfoglia o digitando il percorso del file. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVAL vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. Passa il cursore del mouse sul nome del file per visualizzare il percorso nell’archivio AEM in cui è memorizzato il file. È possibile salvare solo file DITAVAL. Se hai selezionato un altro file, viene visualizzato un errore.<br><br>**Nota**: il FrameMaker Publishing Server non supporta più file DITAVAL. |
| Nome trasformazione | Specifica il tipo di output da generare. Questa opzione è necessaria se si desidera generare l&#39;output utilizzando un plug-in personalizzato, integrato nel plug-in DITA-OT. Ad esempio, per generare l’output XHTML, specifica `xhtml`. Per un elenco delle trasformazioni disponibili in DITA-OT, vedere [Trasformazioni DITA-OT (formati di output)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) nella Guida utente di OASIS DITA-OT. |
| Nome file | Specificare il nome del file con cui si desidera salvare l&#39;output di HTML5.<br><br>**Nota**:Se non si specifica un nome di file, viene utilizzato il titolo della mappa DITA per generare il nome finale del file di output HTML5. Se la mappa non ha un titolo, viene utilizzato il nome del file della mappa DITA per denominare l&#39;output finale di HTML5. Il nome del file viene bonificato utilizzando le regole configurate nel sistema per gestire qualsiasi carattere non valido. |
| Esegui flusso di lavoro di post-generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in AEM. È necessario selezionare un flusso di lavoro da eseguire dopo il completamento del flusso di lavoro di generazione dell&#39;output.<br><br>**Nota**: per ulteriori informazioni sulla creazione di un flusso di lavoro personalizzato per la generazione post-output, consulta _Personalizzare il flusso di lavoro di generazione post-output_ in Installare e configurare Adobe Experience Manager Guides as a Cloud Service. |
| Percorso di destinazione | Il percorso all’interno dell’archivio AEM in cui è memorizzato l’output di HTML5. |
| Pulisci file temporanei DITA-OT | Selezionare questa opzione per pulire i file temporanei generati da DITA-OT. Il percorso in cui DITA-OT memorizza i file temporanei si trova nel registro di generazione dell&#39;output.<br><br>Se si verificano errori durante la generazione dell&#39;output tramite DITA-OT, è possibile deselezionare questa opzione per mantenere i file temporanei. Puoi quindi utilizzare questi file per risolvere eventuali errori di generazione dell’output. |
| Usa linea di base | Se è stata creata una baseline per la mappa DITA selezionata, selezionare questa opzione per specificare la versione da pubblicare.<br><br>Consulta [Utilizzare la previsione](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) per maggiori dettagli. |
| Proprietà file | Seleziona le proprietà da elaborare come metadati. Queste proprietà vengono impostate dalla pagina Proprietà del file mappa DITA o del file mappa segnalibro. Le proprietà selezionate dall&#39;elenco a discesa vengono visualizzate sotto **Proprietà file** campo. Seleziona l’icona a forma di croce accanto alla proprietà per rimuoverla. <br><br>**Nota**: puoi anche trasmettere i metadati all’output utilizzando la pubblicazione DITA-OT. Per maggiori dettagli vedi, [Trasmettere i metadati all&#39;output utilizzando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Argomento padre:**[ Informazioni sui predefiniti di output](generate-output-understand-presets.md)
