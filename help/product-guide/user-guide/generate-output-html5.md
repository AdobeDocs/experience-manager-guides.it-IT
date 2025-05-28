---
title: Usa HTML5
description: Scopri come creare un predefinito HTML5 dalla console delle mappe e dal dashboard delle mappe. Configura il predefinito di output di HTML5 in AEM Guides.
exl-id: b54bf3a0-7a13-41a0-ae72-cdf2caf8d974
feature: Publishing
role: User
source-git-commit: 9ae2690c52ab5408a9d17e9a40a89fe1f902042f
workflow-type: tm+mt
source-wordcount: '1528'
ht-degree: 0%

---

# HTML5 {#id205BE700XO1}

È possibile creare il predefinito di output di HTML5 per pubblicare l&#39;output utilizzando DITA-OT e FMPS (se configurato dall&#39;amministratore).

È possibile creare il predefinito HTML5 in due modi:

- [Creare un predefinito di output HTML5 dalla console Mappa](#create-html5-output-preset-from-the-map-console)
- [Creare un predefinito di output HTML5 dal dashboard Mappa](#create-html5-output-preset-from-the-map-dashboard)

## Creare un predefinito di output HTML5 dalla console Mappa

Per creare il predefinito HTML5 dalla console Mappa, effettua le seguenti operazioni:

1. [Aprire un file mappa DITA nella console Mappa](./open-files-map-console.md).

   Puoi anche accedere al file mappa dal widget **File recenti** nella [sezione Panoramica](./intro-home-page.md#overview). Il file di mappa selezionato viene aperto nella console Mappa.
1. Nella scheda **Predefiniti di output**, seleziona l&#39;icona + per creare un predefinito di output.
1. Selezionare **HTML5** dal menu a discesa Tipo nella finestra di dialogo **Nuovo predefinito di output**.
1. Nel campo **Name**, specifica un nome per questo predefinito.
1. Nel campo **Genera HTML utilizzando**, selezionare DITA-OT.
1. Selezionare l&#39;opzione **Aggiungi al profilo cartella corrente** per creare un predefinito di output nel profilo cartella corrente. L&#39;icona ![profilo cartella](images/global-preset-icon.svg) indica un predefinito a livello di profilo della cartella.

   Ulteriori informazioni su [Gestire i predefiniti di output per profili globali e cartelle](./web-editor-manage-output-presets.md).

1. Seleziona **Aggiungi**.

   Viene creato il predefinito per HTML5.

   ![](images/html5-preset-dialog-new.png){width="300" align="left"}

Nella console Mappa, le opzioni di configurazione del predefinito sono organizzate nelle schede **Generale** e **Avanzate**.

La scheda **Generale** contiene le seguenti opzioni di configurazione:

- Percorso di output
- Argomenti riga di comando DITA-OT
- Nome file
- Filtro condizionale \(Se le condizioni sono definite per una mappa\)
- Usa baseline \(Se viene creata una baseline per una mappa\)
- Flusso di lavoro di post generazione

**Avanzate**

La scheda Avanzate contiene le seguenti opzioni di configurazione:

- Nome della trasformazione
- Mantieni file temporanei
- Appiattisci gerarchia file
- Proprietà file

Per informazioni dettagliate sulle opzioni di configurazione del predefinito, consulta la sezione [Configurazione del predefinito HTML5](#html5-preset-configuration).

## Creare un predefinito di output HTML5 dal dashboard Mappa

Per creare il predefinito HTML5 dal dashboard Mappa, effettua le seguenti operazioni:

1. Nell&#39;interfaccia utente di Assets, accedi alla mappa DITA e selezionala per aprirla nel dashboard Mappa.
1. Verificare che la scheda **Predefiniti di output** sia selezionata.
1. Seleziona **Crea** nella barra degli strumenti.

   Viene visualizzato un nuovo modulo per la creazione di predefiniti di output.

1. Immettere i dettagli di configurazione richiesti per il predefinito HTML5.
1. Seleziona **Fine** per salvare le impostazioni del predefinito.

Per informazioni dettagliate sulle opzioni di configurazione del predefinito, consulta la sezione [Configurazione del predefinito HTML5](#html5-preset-configuration).

## Configurazione predefinita HTML5

Le opzioni di configurazione variano leggermente a seconda che il predefinito sia configurato dalla console Mappa o dal dashboard Mappa. Alcune opzioni sono valide solo per il dashboard Mappa, mentre altre sono valide per entrambe.

Nei casi in cui la stessa configurazione abbia due etichette di campo diverse, un **/** le separa nella tabella seguente. Il primo rappresenta l’etichetta nella console Mappa e il secondo rappresenta l’etichetta nel dashboard Mappa.

Ad esempio, **Percorso di output/Percorso di destinazione** - In questo caso, **Percorso di output** è l&#39;etichetta utilizzata nella console Mappa, mentre **Percorso di destinazione** è l&#39;etichetta utilizzata nel dashboard Mappa per la stessa configurazione.

| Opzioni HTML5 | Descrizione |
| --- | --- |
| Tipo di output (*Applicabile solo per dashboard mappe*) | Tipo di output che si desidera generare. Per generare l&#39;output di HTML5, scegliere l&#39;opzione HTML5. |
| Nome impostazione (*Applicabile solo per dashboard mappa*) | Assegna un nome descrittivo alle impostazioni di output di HTML5 che stai creando. Ad esempio, puoi specificare _Output clienti interni_ o _Output utenti finali_. |
| Genera responsive utilizzando (*Applicabile solo per dashboard mappe*) | Selezionare **DITA-OT** per generare l&#39;output di HTML5. Seleziona **FrameMaker Publishing Server** se l&#39;amministratore ha configurato questa opzione. Alcune delle opzioni di configurazione variano quando si seleziona FMPS. |
| Percorso di output/Percorso di destinazione | Il percorso all’interno dell’archivio AEM in cui è memorizzato l’output di HTML5. |
| Argomenti riga di comando DITA-OT | Specificare gli argomenti aggiuntivi che si desidera vengano elaborati da DITA-OT durante la generazione dell&#39;output. <br><br> NOTA: a partire dalla versione 2502 di Experience Manager Guides, il parametro `generate.copy.outer` non viene più gestito internamente. Ciò significa che se il contenuto di HTML5 si trova all&#39;esterno della directory delle mappe, è necessario impostare esplicitamente il parametro `-Dgenerate.copy.outer=3` nel campo **Argomenti riga di comando DITA-OT**. In questo modo il contenuto viene elaborato e incluso correttamente nell’output. Per ulteriori dettagli sulla gestione del contenuto all&#39;esterno della directory delle mappe, visualizzare [la documentazione DITA-OT](https://www.dita-ot.org/dev/parameters/generate-copy-outer#:~:text=The%20generate.,located%20outside%20the%20map%20directory/). |
| Nome file | Specificare il nome del file con cui si desidera salvare l&#39;output di HTML5.<br><br>**Nota**: se non si specifica un nome di file, verrà utilizzato il titolo della mappa DITA per generare il nome finale del file di output di HTML5. Se la mappa non ha un titolo, viene utilizzato il nome del file della mappa DITA come output finale di HTML5. Il nome del file viene bonificato utilizzando le regole configurate nel sistema per gestire qualsiasi carattere non valido. |
| Condizionamento, filtraggio/applicazione delle condizioni tramite | Selezionare una delle opzioni seguenti:<br><br>* **Nessuna applicazione**: selezionare questa opzione se non si desidera applicare alcuna condizione all&#39;output pubblicato.<br>* **File DITAVal**: selezionare i file DITAVal per generare contenuto personalizzato. È possibile selezionare più file DITAVal utilizzando la finestra di dialogo Sfoglia o digitando il percorso del file. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVal vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. Se il file DITAVal viene spostato in un&#39;altra posizione o eliminato, non viene eliminato automaticamente dal dashboard delle mappe. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. Passa il cursore del mouse sul nome del file per visualizzare il percorso nell’archivio AEM in cui è memorizzato il file. È possibile selezionare solo i file DITAVal e viene visualizzato un errore se è stato selezionato un altro tipo di file. FrameMaker Publishing Server non supporta più file DITAVAL.<br>* **Predefinito condizione**: seleziona un predefinito condizione dall&#39;elenco a discesa per applicare una condizione durante la pubblicazione dell&#39;output. L&#39;opzione è visibile se è stata aggiunta una condizione presente nella scheda Predefiniti condizione della console Mappa DITA. Per ulteriori informazioni sul predefinito di condizione, visualizzare [Usa predefiniti di condizione](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>È possibile selezionare più file DITAVAL utilizzando la finestra di dialogo Sfoglia o digitando il percorso del file. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVAL vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. Passa il cursore del mouse sul nome del file per visualizzare il percorso nell’archivio AEM in cui è memorizzato il file. È possibile salvare solo file DITAVAL. Se hai selezionato un altro file, viene visualizzato un errore.<br><br>**Nota**: FrameMaker Publishing Server non supporta più file DITAVAL. |
| Flusso di lavoro di post generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in AEM. È necessario selezionare un flusso di lavoro da eseguire dopo il completamento del flusso di lavoro di generazione dell&#39;output.<br><br>**Nota**:per ulteriori informazioni sulla creazione di un flusso di lavoro di generazione post-output personalizzato, vedere _Personalizzare il flusso di lavoro di generazione post-output_ in Installare e configurare Adobe Experience Manager Guides as a Cloud Service. |
| Nome della trasformazione | Specifica il tipo di output da generare. Questa opzione è necessaria se si desidera generare l&#39;output utilizzando un plug-in personalizzato, integrato nel plug-in DITA-OT. Se ad esempio si desidera generare l&#39;output XHTML, specificare `xhtml`. Per un elenco delle trasformazioni disponibili in DITA-OT, visualizzare [Trasformazioni DITA-OT (formati di output)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) nella Guida utente OASIS DITA-OT. |
| Mantieni file temporanei | Selezionare questa opzione per mantenere i file temporanei generati da DITA-OT. Se si verificano errori durante la generazione dell&#39;output tramite DITA-OT, selezionare questa opzione per mantenere i file temporanei. È quindi possibile utilizzare tali file per risolvere eventuali errori di generazione dell&#39;output.<br> <br> Dopo aver generato l&#39;output, selezionare l&#39;icona **Scarica file temporanei** ![Scarica file temporanei](images/download-temp-files-icon.svg) per scaricare la cartella ZIP contenente i file temporanei. I file scaricati includerebbero anche `system_config.json` file che fornisce informazioni sull&#39;URL dell&#39;autore, sull&#39;URL locale e sull&#39;URL di pubblicazione. <br><br> **Nota**: se le proprietà del file vengono aggiunte durante la generazione, i file temporanei di output includono anche un file *metadata.xml* contenente tali proprietà. |
| Usa linea di base | Se è stata creata una baseline per la mappa DITA selezionata, selezionare questa opzione per specificare la versione da pubblicare.<br><br>Visualizza [Utilizza la previsione](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) per ulteriori dettagli. |
| Appiattisci gerarchia file | Selezionare l&#39;opzione per generare l&#39;output di HTML5 in una gerarchia di cartelle piatta. L’intero contenuto viene pubblicato in formato di output HTML5 in una gerarchia di file flat e salvato in un’unica cartella. <br> Se si deseleziona questa opzione, l&#39;output viene generato in una gerarchia di cartelle nidificate e l&#39;intera struttura di cartelle viene replicata. |
| Proprietà file | Seleziona le proprietà da elaborare come metadati. Queste proprietà vengono impostate dalla pagina Proprietà del file mappa DITA o del file mappa segnalibro. Le proprietà selezionate dall&#39;elenco a discesa vengono visualizzate nel campo **Proprietà file**. Seleziona l’icona a forma di croce accanto alla proprietà per rimuoverla. <br><br>**Nota**: è inoltre possibile passare i metadati all&#39;output utilizzando la pubblicazione DITA-OT. Per ulteriori dettagli, [Trasmettere i metadati all&#39;output utilizzando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |







**Argomento padre:**[ Informazioni sui predefiniti di output](generate-output-understand-presets.md)
