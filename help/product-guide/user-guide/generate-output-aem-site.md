---
title: Sito AEM
description: Crea e configura un predefinito per sito AEM nelle guide AEM. Utilizza il supporto del sito AEM per generare output basati su articoli, argomenti di collegamento dell’output, conferenze di pubblicazione e ricerche in una stringa all’interno del contenuto.
exl-id: 019d9fbf-2f23-4669-8022-d693be75c1c3
feature: Publishing
role: User
source-git-commit: b82f1f3b42f85cce8420d3962c69cd3bafc5728d
workflow-type: tm+mt
source-wordcount: '2621'
ht-degree: 0%

---

# Sito AEM {#id205BE3008SW}

Per l’output del sito AEM sono disponibili le seguenti opzioni:

Puoi creare il predefinito per sito AEM in due modi:

**Dall’editor web:** Nel pannello Repository, apri il file mappa DITA in Vista mappa, quindi nella scheda Output seleziona l’icona + per creare un predefinito di output e seleziona Sito AEM dal menu a discesa Tipo nella finestra di dialogo Aggiungi predefinito. Nell’editor web le configurazioni sono organizzate nelle schede Generali e Avanzate:

**Generale**

Il **Generale** La scheda contiene le seguenti configurazioni:

- Nome sito
- Percorso di output
- Pagine di output esistenti
- Elimina pagine del sito orfano
- Applica condizioni utilizzando \(se le condizioni sono definite per una mappa\)
- Usa baseline \(Se viene creata una baseline per una mappa\)
- Flusso di lavoro di post-generazione

**Avanzate**

La scheda Avanzate contiene le seguenti configurazioni:

- Scarica file temporanei
- Genera PDF separati per ogni argomento
- Usa proprietà mappa come predefinito

Per ulteriori informazioni, consulta [Configurazione sito AEM](#id231KIM004X1).

**Dal dashboard delle mappe**

Per aprire i predefiniti di output per il sito AEM, fai clic su un file di mappa DITA dall’interfaccia utente Assets, quindi fai clic su Predefiniti di output e infine sull’opzione di output Sito AEM. Nel dashboard delle mappe, fai clic su **Modifica** nella parte superiore per aggiornare le varie configurazioni, quindi fai clic su **Salva**.

>[!TIP]
>
> Consulta la *Pubblicazione di siti AEM* sezione nella guida alle best practice per le best practice sulla creazione dell’output del sito AEM.

## Configurazione sito AEM {#id_aem_site_config}

Per l’output del sito AEM sono disponibili le seguenti opzioni:

| Opzioni sito AEM | Descrizione |
| --- | --- |
| Tipo di output | Tipo di output che si desidera generare. Per generare l&#39;output responsivo del sito AEM, scegliere l&#39;opzione Sito AEM. |
| Nome impostazione | Assegna un nome descrittivo alle impostazioni del sito AEM che stai creando. Ad esempio, puoi specificare *Output clienti interni* o *output degli utenti finali*. |
| Nome sito | Nome del sito in cui l’output viene archiviato nell’archivio AEM.<br><br>Viene creato un nodo nell’archivio AEM con il nome specificato qui. Se non si specifica il nome del sito, il nodo del sito viene creato con il nome del file mappa DITA.<br><br>Il Nome sito specificato viene utilizzato anche come titolo nella scheda del browser.<br><br>È inoltre possibile utilizzare le variabili durante l&#39;impostazione del nome del sito. Per ulteriori dettagli sull’utilizzo delle variabili, consulta [Utilizzare le variabili per impostare le opzioni Percorso di destinazione, Nome sito o Nome file](generate-output-use-variables.md#id18BUG70K05Z). |
| Design | Selezionare il modello struttura da utilizzare per generare l&#39;output.<br><br>Per informazioni dettagliate sull’utilizzo di modelli di progettazione personalizzati per generare l’output, contatta l’amministratore della pubblicazione. |
| Percorso di destinazione | Il percorso all’interno dell’archivio AEM in cui è memorizzato l’output. Durante la generazione dell’output finale, il Nome sito e il Percorso di destinazione vengono combinati. Ad esempio, se si specifica Nome sito come `user-guide` e il percorso di destinazione come `/content/output/aem-guides`, quindi l&#39;output finale viene generato sotto `/content/output/aem-guides/user-guide` nodo.<br><br>Puoi anche utilizzare le variabili durante l’impostazione del Percorso di destinazione. Per ulteriori dettagli sull’utilizzo delle variabili, consulta [Utilizzare le variabili per impostare le opzioni Percorso di destinazione, Nome sito o Nome file](generate-output-use-variables.md#id18BUG70K05Z). |
| Applica condizioni tramite | Selezionare una delle opzioni seguenti:<br><br>**Nessuna applicazione**: seleziona questa opzione se non desideri applicare alcuna condizione all’output pubblicato.<br>**File DITAVal**: seleziona i file DITAVal per generare contenuto condizionale. È possibile selezionare più file DITAVal utilizzando la finestra di dialogo Sfoglia o digitando il percorso del file. Utilizza l’icona a forma di croce accanto al nome del file per rimuoverlo. I file DITAVal vengono valutati nell&#39;ordine specificato, pertanto le condizioni specificate nel primo file hanno la precedenza rispetto a quelle specificate nei file successivi. È possibile mantenere l&#39;ordine dei file aggiungendo o eliminando file. Se il file DITAVal viene spostato in un&#39;altra posizione o eliminato, non viene eliminato automaticamente dal dashboard delle mappe. È necessario aggiornare il percorso nel caso in cui i file vengano spostati o eliminati. Passa il cursore del mouse sul nome del file per visualizzare il percorso nell’archivio AEM in cui è memorizzato il file. È possibile selezionare solo i file DITAVal e viene visualizzato un errore se si seleziona un altro tipo di file.<br>**Predefinito condizione**: seleziona un predefinito di condizione dal menu a discesa per applicare una condizione durante la pubblicazione dell’output. Questa opzione è visibile se è stata aggiunta una condizione per il file di mapping DITA. Le impostazioni condizionali sono disponibili nella scheda Predefiniti condizione della console delle mappe DITA. Per ulteriori informazioni sul predefinito di condizione, consulta [Utilizzare i predefiniti per le condizioni](generate-output-use-condition-presets.md#id1825FL004PN). |
| Pagine di output esistenti | Seleziona la **Sovrascrivi contenuto** per sovrascrivere il contenuto nelle pagine esistenti. Questa opzione sovrascrive solo il contenuto presente nei nodi content e head della pagina. Questa opzione consente la pubblicazione mista dei contenuti. Selezionando questa opzione è possibile selezionare l&#39;eliminazione di pagine orfane dall&#39;output pubblicato. Questo è anche il *predefinito* opzione per la creazione dell&#39;output del sito AEM.<br><br>Seleziona la **Elimina e crea** opzione per forzare l’eliminazione di tutte le pagine esistenti durante la pubblicazione. Questa opzione elimina il nodo della pagina insieme al relativo contenuto e a tutte le pagine figlie al suo interno. Utilizza questa opzione se hai modificato il modello di progettazione del predefinito di output o se desideri rimuovere eventuali pagine aggiuntive già presenti nella destinazione. |
| Elimina pagine del sito orfano | Selezione del **Sovrascrivi contenuto** nel **Pagine di output esistenti** questa opzione. Se selezioni questa opzione, tutte le pagine orfane vengono eliminate dal sito AEM pubblicato. Per eseguire correttamente questa funzione, è necessario pubblicare l&#39;intera mappa DITA e non utilizzare la pubblicazione incrementale.<br><br>Si supponga di aver pubblicato una mappa DITA contenente gli argomenti a.dita, b.dita e c.dita. Prima di pubblicare di nuovo la mappa, hai rimosso l’argomento b.dita dalla mappa. Ora, se hai selezionato questa opzione, tutto il contenuto relativo a b.dita viene rimosso dall’output del sito AEM e vengono pubblicati solo a.dita e c.dita.<br><br>Questa funzione non rimuove alcuna mappa secondaria pubblicata. Ad esempio, se la mappa padre contiene una mappa figlio e si rimuove l&#39;intera mappa figlio, il contenuto della mappa figlio non viene eliminato dall&#39;output pubblicato. Tuttavia, se rimuovi un argomento da una mappa figlio e lo ripubblichi, il contenuto dell&#39;argomento rimosso viene eliminato dall&#39;output del sito.<br><br>Inoltre, se è presente del contenuto di riferimento e tale contenuto viene rimosso prima di essere ripubblicato, i dati del contenuto di riferimento non vengono rimossi.<br><br>**Nota**: le informazioni sulle pagine orfane eliminate vengono acquisite anche nei registri di generazione dell’output. Per ulteriori informazioni sull&#39;accesso ai file di registro, vedere [Visualizza e controlla il file di registro](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). |
| Scarica file temporanei | Selezionare questa opzione per scaricare i file temporanei generati da DITA-OT. Il percorso in cui DITA-OT memorizza i file temporanei si trova nel registro di generazione dell&#39;output. Se si verificano errori durante la generazione dell&#39;output tramite DITA-OT, selezionare questa opzione per mantenere i file temporanei. Puoi quindi utilizzare questi file per risolvere eventuali errori di generazione dell’output.<br> <br>  Dopo aver generato l’output, seleziona la **Scarica file temporanei** ![icona scarica file temporanei](images/download-temp-files-icon.png) per scaricare la cartella ZIP contenente i file temporanei. <br><br> **Nota**: se selezioni alcune proprietà del file e poi scarichi i file temporanei, ottieni anche il *metadati.xml* nella cartella ZIP. |
| Genera PDF separati per ciascun argomento | Se questa opzione è selezionata, viene creato anche un PDF per ogni argomento della mappa DITA. Quando selezionate questa opzione, viene visualizzata una nuova opzione Dividi percorso PDF.<br><br>Nel campo Dividi percorso PDF specificare il percorso in cui memorizzare i PDF generati per ciascun argomento.<br><br>**Nota**: le guide AEM utilizzano il plug-in DITA-OT denominato pdfx per generare PDF per ciascun argomento. Questo plug-in è fornito in dotazione con il pacchetto DITA-OT fornito con il prodotto. Puoi personalizzare questo plug-in per generare PDF in base alle tue esigenze. Se si utilizza un plug-in DITA-OT personalizzato, assicurarsi di integrare il plug-in pdfx per disporre della funzionalità di generazione PDF a livello di argomento. |
| Esegui flusso di lavoro di post-generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in AEM. È necessario selezionare un flusso di lavoro da eseguire dopo il completamento del flusso di lavoro di generazione dell&#39;output. |
| Usa linea di base | Se è stata creata una baseline per la mappa DITA selezionata, selezionare questa opzione per specificare la versione da pubblicare.<br><br>**Importante**: quando generi un output incrementale per il sito AEM, l’output viene creato utilizzando la versione corrente dei file e non la baseline allegata.<br><br>Consulta [Utilizzare la previsione](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) per maggiori dettagli. |
| Proprietà file | Seleziona le proprietà da elaborare come metadati. Queste proprietà vengono impostate dalla pagina Proprietà del file mappa DITA o del file mappa segnalibro. Le proprietà selezionate dall&#39;elenco a discesa vengono visualizzate sotto **Proprietà file** campo. Seleziona l’icona a forma di croce accanto alla proprietà per rimuoverla. <br><br>**Nota**: le proprietà dei metadati fanno distinzione tra maiuscole e minuscole.<br><br>*Se è stata selezionata una baseline, i valori delle proprietà si basano sulla versione della baseline selezionata.<br>* Se non è stata selezionata una baseline, i valori delle proprietà si basano sulla versione più recente.<br><br>È inoltre possibile trasmettere i metadati all&#39;output utilizzando la pubblicazione DITA-OT. Per maggiori dettagli vedi, [Trasmettere i metadati all&#39;output utilizzando DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Nota**: se non hai definito i `cq:tags` nell’opzione Proprietà, i valori per `cq:tags` vengono prelevati dalla copia di lavoro corrente anche se è stata selezionata una baseline per la pubblicazione. |
| Usa Le Proprietà Della Mappa Se Mancano Nell’Argomento | Se questa opzione è selezionata, le proprietà definite per il file mappa vengono copiate anche negli argomenti in cui tali proprietà non sono definite. Quando utilizzate questa opzione, tenete presente quanto segue:<br><br>*Solo le proprietà String, Date o Long (singole e multivalore) possono essere trasmesse alle pagine del sito AEM.<br>* I valori dei metadati per una proprietà di tipo String non supportano caratteri speciali, ad esempio `@, #, " "`).<br>* Questa opzione deve essere utilizzata insieme al `Properties` opzione. |

## Nota aggiuntiva sul sito AEM

### Genera output basato su articoli dall’editor web

È possibile generare l&#39;output del sito AEM per uno o più argomenti o per l&#39;intera mappa DITA dall&#39;editor Web. È necessario creare predefiniti di output per la mappa DITA e quindi generare facilmente l&#39;output del sito AEM per la mappa. Se sono stati aggiornati alcuni argomenti della mappa, è inoltre possibile generare l&#39;output del sito AEM solo per tali argomenti dall&#39;editor Web. Per ulteriori dettagli, consulta [Pubblicazione basata su articolo dall’editor web](web-editor-article-publishing.md#id218CK0U019I).

### Genera argomenti di collegamento di output da altre mappe

È uno scenario molto comune disporre di un set elevato di documenti distribuiti in più cartelle e mappe DITA. Diventa estremamente complesso pubblicare contenuti collegati da varie posizioni. Per impostazione predefinita, tutti i collegamenti `<xref>` vengono creati con `local` `@scope`. La pubblicazione di tali argomenti non comporta alcuna sfida, in quanto utilizza un collegamento diretto all’argomento. Se l&#39;argomento non è incluso nella mappa DITA corrente, il collegamento non visualizza il contenuto collegato.

Un altro modo di collegare il contenuto consiste nel creare un collegamento utilizzando `peer` `@scope`. Per tali contenuti, il collegamento viene risolto in fase di esecuzione scegliendo il titolo del file e il contesto configurato per l&#39;argomento collegato dal contesto di pubblicazione della mappa DITA. La schermata seguente mostra il pannello Proprietà per un collegamento che presenta `peer` `@scope`:

![](images/peer-link-scope-link.png){width="800" align="left"}

Per semplificare la pubblicazione di mappe complesse e argomenti collegati ad altri argomenti in altre mappe, le guide AEM consentono di impostare il contesto di pubblicazione per ogni predefinito di output.

Il contesto di pubblicazione consente di specificare l’argomento da utilizzare per la mappatura per la pubblicazione di un output specifico. Comprendiamo questo con l&#39;aiuto di un esempio — supponiamo che tu abbia quattro cartelle: campione a, campione b, campione c e campione d. Ogni cartella contiene una mappa DITA, ovvero mappa DITA A, mappa DITA B, mappa DITA C e mappa DITA D. Il collegamento tra mappe si verifica quando un argomento nella mappa DITA A si collega a un argomento nella mappa DITA B, C o D. Nella schermata seguente, un argomento di esempio contiene i collegamenti \(o riferimenti\) ai file che fanno parte di altre mappe DITA.

![](images/sample-concept-link-to-other.png){width="350" align="left"}

Ora, quando configuri le impostazioni di pubblicazione del sito AEM per il file di mappa che contiene questo argomento, puoi selezionare quale contesto di pubblicazione viene utilizzato per la pubblicazione del contenuto collegato. Un contesto di pubblicazione è una combinazione di mappa DITA e relativo predefinito di output. Il predefinito di output, a sua volta, contiene una versione specifica del contenuto e dei predefiniti condizionali. L&#39;intera combinazione della mappa DITA, del predefinito di output, della versione di \(files\) e delle condizioni definisce il contesto di pubblicazione di una mappa collegata.

Per specificare il contesto di pubblicazione per i file con collegamento incrociato, effettua le seguenti operazioni:

1. Apri **Predefiniti di output** della mappa DITA da pubblicare.

1. Seleziona la **Sito AEM** predefinito di output.

   Vengono visualizzate le schede Impostazioni predefinite AEM e Contesto di pubblicazione.

   ![](images/aem-site-publish-settings.png){width="800" align="left"}

1. Apri **Contesto di pubblicazione** scheda.

   Viene visualizzato un elenco di argomenti dipendenti. Questi sono gli argomenti collegati da alcuni argomenti della mappa corrente, ma sono disponibili in altre mappe DITA.

   >[!NOTE]
   >
   > La scheda Contesto di pubblicazione mostra gli argomenti collegati tramite `peer` `@scope` solo. Per i collegamenti con `local` `@scope`, non è necessario specificare il contesto di pubblicazione.

   Per impostazione predefinita, per tutti gli argomenti collegati sono selezionati il predefinito di output e la mappa più recente.

   ![](images/default-publish-context.png){width="800" align="left"}

1. Per modificare la selezione predefinita della mappa DITA e del predefinito, fare clic su **Modifica** \(nella barra degli strumenti principale\).

1. Se desideri utilizzare l’output pubblicato più di recente di ciascun file dipendente nella mappa, seleziona **Usa il contesto di pubblicazione generato più di recente per tutti gli argomenti dipendenti**.

1. In **Mappa padre** dall&#39;elenco a discesa, selezionare il file di mapping con cui si desidera collegare l&#39;output della mappa corrente.

   Quando selezioni un file di mappa, l’UUID della mappa viene visualizzato nella colonna UUID mappa principale. I predefiniti di output associati alla mappa selezionata sono elencati nell&#39;elenco Predefiniti mappa padre.

1. In **Predefinito mappa principale** dall&#39;elenco a discesa, selezionare il predefinito di output con cui si desidera collegare l&#39;output della mappa corrente.

1. Selezionare la mappa desiderata e il relativo predefinito di output per tutti gli argomenti dipendenti e fare clic su **Fine**.

   È ora impostato il contesto per gli argomenti dipendenti. Potete generare l&#39;output per la mappa corrente. Per ulteriori informazioni sulla generazione dell’output, consulta [Genera output per una mappa DITA dalla console delle mappe](generate-output-for-a-dita-map.md#).

### Pubblicazione mista

Le guide AEM supportano la pubblicazione di contenuto DITA all&#39;interno del sito AEM esistente. Se ad esempio si dispone di un sito esistente, è possibile utilizzare l&#39;output Sito AEM per pubblicare solo il contenuto DITA del sito. In questo processo, il contenuto non DITA esistente non viene modificato dal processo di pubblicazione. Per ulteriori informazioni sulla configurazione del sito per la pubblicazione di solo contenuti DITA, contattare l&#39;amministratore della pubblicazione.

### Pubblicazione `conref`

Se sta usando `conref` nel contenuto, viene pubblicato come contenuto normale o incorporato insieme al contenuto nell’argomento sorgente \(o riferimento\). Il `conref` viene eseguito il rendering del contenuto insieme al contenuto principale e non viene creata alcuna pagina del sito separata per lo stesso. Quando cerchi il contenuto a cui si fa riferimento nel `conref`, quindi solo l&#39;argomento o la pagina principale contenente `conref` Il contenuto viene visualizzato nei risultati della ricerca.

>[!NOTE]
>
>Se hai generato pagine separate per il `conref` contenuti che utilizzano le guide dell’AEM versione 3.5 o precedente, quindi si consiglia di pulire/eliminare tali pagine utilizzando [Elimina pagine del sito orfano](#delete-orphan-page-aem-site) opzione.


### Cercare una stringa all’interno del contenuto

Puoi cercare una stringa nell’output del sito AEM. Per impostazione predefinita, è possibile cercare la stringa solo nei titoli. Per cercare la stringa nel contenuto o nel corpo dell&#39;output del sito AEM, contattare l&#39;amministratore di sistema per abilitare la proprietà flattening.enabled.

![Ricerca output sito AEM](images/aem-output-search.png){width="650" align="left"}

Per ulteriori dettagli vedi *Configurare l’appiattimento della struttura dei nodi del sito AEM* nella guida Installare e configurare Adobe Experience Manager Guides.

**Argomento padre:**[ Informazioni sui predefiniti di output](generate-output-understand-presets.md)
