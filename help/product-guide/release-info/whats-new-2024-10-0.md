---
title: Note sulla versione | Novità di Adobe Experience Manager Guides versione 2024.10.0
description: Scopri le funzioni nuove e migliorate della versione 2024.10.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: 545e51cbd970aa3df01a0fe2461a2e730c0db66a
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 1%

---

# Novità della versione 2024.10.0 (ottobre 2024)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2024.10.0 di Adobe Experience Manager Guides as a Cloud Service.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2024.10.0](fixed-issues-2024-10-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2024.10.0](../release-info/upgrade-instructions-2024-10-0.md).


## Miglioramenti alla pubblicazione

Nella versione 2024.10.0 sono stati apportati i seguenti miglioramenti per la pubblicazione dei contenuti:




### Miglioramenti nella pubblicazione dei frammenti di contenuto

Experience Manager Guides fornisce anche alcuni utili miglioramenti nei frammenti di contenuto:

- Experience Manager Guides consente di pubblicare un argomento o i relativi elementi in un frammento di contenuto.

- Puoi pubblicare e visualizzare i Frammenti di contenuto di un argomento dalla sezione **Output** nelle **Proprietà file**.


- Puoi creare facilmente varianti di frammento di contenuto filtrando il contenuto con condizioni durante la pubblicazione in un frammento di contenuto.

- Utilizza la nuova interfaccia di mappatura per selezionare e pubblicare facilmente gli elementi in un frammento di contenuto.

Adesso, la pubblicazione dei frammenti di contenuto sostituisce solo il contenuto mappato, anziché sovrascrivere l’intero frammento di contenuto. Questa funzione consente a un frammento di contenuto di contenere dati provenienti da più origini, ad esempio più argomenti o l’editor di frammenti di contenuto.

![Aggiungere il modello di frammento e i dettagli di mappatura nella finestra di dialogo Publish come frammento di contenuto](assets/content-fragment-mapping.png)

Per ulteriori dettagli, visualizzare [Frammenti di contenuto Publish](../user-guide/publish-content-fragment.md).


### Varianti dei frammenti esperienza Publish basate su filtri condizione

Experience Manager Guides consente di pubblicare un argomento o i relativi elementi in un frammento di esperienza. Ora puoi anche creare varianti di Frammento esperienza utilizzando i filtri condition o DITAVAL e riutilizzarle tra canali diversi o per tipi di pubblico diversi.

Ulteriori informazioni su come [Frammenti esperienza Publish](../user-guide/publish-experience-fragment.md).


### Predefinito AEM Sites riorganizzato per un facile utilizzo

Le impostazioni sono state riorganizzate per aiutarti a configurare rapidamente il predefinito di output e generare l’output di AEM Sites.
Puoi creare i predefiniti di AEM Sites esistenti selezionando l&#39;opzione **Usa mapping di componenti legacy** nella finestra di dialogo **Nuovo predefinito di output**.

Visualizza le schede **Generale**, **Contenuto** e **Riferimento incrociato** nei predefiniti di AEM Sites:
- **Generale**: contiene le configurazioni generali per generare l&#39;output. È possibile specificare il sito e il percorso di output, eliminare o sovrascrivere le pagine di output esistenti, eliminare le pagine generate in precedenza per gli argomenti rimossi, selezionare il modello di progettazione, conservare i file temporanei e specificare il flusso di lavoro di post-generazione.
- **Contenuto**: contiene le impostazioni applicabili al contenuto per la generazione dell&#39;output. È possibile selezionare i filtri, la baseline della mappa DITA e le proprietà dei metadati per la pubblicazione.
- **Riferimenti tra mappe**: questo elenco contiene argomenti contenenti riferimenti tra mappe con ambito =&quot;peer&quot;. È possibile specificare il contesto di pubblicazione per un elenco di riferimenti a mappe incrociate con ambito=&quot;peer&quot; per gli argomenti disponibili in altre mappe DITA. Questa scheda viene visualizzata se si utilizza la versione di Experience Manager Guides (UUID).



### Riferimenti di mappe incrociate da predefiniti di AEM Sites nell’editor web

L’ultimo miglioramento apportato a Experience Manager Guides introduce i riferimenti delle mappe incrociate nei predefiniti di AEM Sites dell’editor web.
I riferimenti alle mappe incrociate in Experience Manager Guides consentono di migliorare la navigazione nei contenuti, di riutilizzare i contenuti e di migliorare l’esperienza utente.


È possibile specificare il contesto di pubblicazione per un elenco di riferimenti di mappe incrociate ad argomenti disponibili in altre mappe DITA con ambito=&quot;peer&quot;. Ad esempio, l&#39;argomento 1 nella Mappa A contiene un riferimento all&#39;argomento 2. L&#39;argomento 2 può essere presente in una o più mappe.  Per ogni collegamento puoi selezionare la mappa principale e un predefinito specifico oppure l’output pubblicato più di recente.

Se in un file si fa riferimento allo stesso argomento più di una volta, è possibile aggiungere un contesto di pubblicazione diverso per ogni istanza. Questo offre maggiore flessibilità e controllo sui contenuti. Ad esempio, l&#39;argomento 3 è presente sia nella Mappa B che nella Mappa C. L&#39;argomento 1 contiene due riferimenti all&#39;argomento 3. Potete scegliere Mappa B come mappa padre per il primo collegamento e Mappa C come mappa padre per il secondo collegamento.

![Predefinito legacy di AEM Sites](assets/aem-sites-legacy.png)

*Specificare il contesto di pubblicazione per gli argomenti collegati dalla scheda **Riferimenti tra mappe incrociate**del predefinito **AEM Sites**.*

Ulteriori informazioni su [Predefiniti AEM Sites](../user-guide/generate-output-aem-site.md).

### Opzione per scegliere una gerarchia di file piatta o nidificata per l&#39;output di HTML5

Ora Experience Manager Guides consente di mantenere la gerarchia di cartelle piatte per i file temporanei, in cui l’intero contenuto viene pubblicato in formato di output HTML5 e salvato in un’unica cartella.
Se non si sceglie di &quot;appiattire&quot; la gerarchia dei file, l&#39;output di HTML5 viene generato in una gerarchia di cartelle nidificate. Ciò implica che la struttura di cartelle originale del contenuto, con i file organizzati in sottocartelle, viene replicata nell’output. Questa gerarchia di cartelle nidificate consente un&#39;organizzazione e una categorizzazione dei file più complesse, semplificando la gestione e la navigazione di grandi volumi di dati.


Ulteriori informazioni su come [generare l&#39;output di HTML5](../user-guide/generate-output-html5.md).


## Miglioramenti dell’editor

I seguenti miglioramenti all’editor sono stati aggiunti nella versione 2024.10.0:

### Accesso in sola lettura alla modalità Autore e Source per i file bloccati

Se un file DITA o Markdown è bloccato o estratto da un altro utente, non è possibile modificarne o modificarne il contenuto. Oltre all’Anteprima, nella modalità Autore o Source è possibile visualizzarla come file di sola lettura.
In modalità di sola lettura, è possibile visualizzare il contenuto insieme ai tag e agli attributi nella modalità **Autore** o **Source** e modificare le proprietà del file.

È inoltre possibile accedere alla visualizzazione **Layout** per le mappe DITA di sola lettura.
>[!NOTE]
>
> Gli amministratori del profilo di cartella devono aggiornare *ui_config.json* in modo da poter accedere in modo armonioso ai file di sola lettura nelle modalità Autore, Source e Layout.

![editor file bloccato](./assets/locked-file-editor.png)
*Visualizza i file bloccati in modalità Autore e Source.*


Scopri come [aprire i file bloccati in modalità Autore e Source](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes).


### Condizioni raggruppate per un&#39;organizzazione avanzata dei contenuti

Experience Manager Guides ora consente di raggruppare le condizioni e di presentarle in una gerarchia nidificata, consentendo di aggiungere più condizioni a un singolo gruppo. Raggruppando le condizioni è possibile organizzarle e applicarle in modo migliore a tutto il contenuto.

![condizioni organizzate in una gerarchia nidificata](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Ulteriori informazioni sulla descrizione della funzionalità **Conditions** nella sezione [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS).




