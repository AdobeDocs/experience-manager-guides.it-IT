---
title: Note sulla versione | Novità di Adobe Experience Manager Guides versione 4.4.0
description: Scopri le funzioni nuove e migliorate di Adobe Experience Manager Guides versione 4.4.0
role: Leader
source-git-commit: 57c3b39f0ab0fde5b18e4d4ae0e1501738997e68
workflow-type: tm+mt
source-wordcount: '3050'
ht-degree: 15%

---

# Novità della versione 4.6.0 (settembre 2024)

Questo articolo descrive le nuove funzioni introdotte con la versione 4.6.0 di Adobe Experience Manager Guides.

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 4.6.0](../release-info/fixed-issues-4-6-0.md).

Scopri le [istruzioni di aggiornamento per la versione 4.6.0](../release-info/upgrade-instructions-4-6-0.md).


## Miglioramenti alla pubblicazione

Nella versione 4.6.0 sono stati apportati i seguenti miglioramenti per la pubblicazione dei contenuti:



### Publish di un argomento o dei relativi elementi in un frammento di esperienza

Un frammento di esperienza è un’unità di contenuto modulare all’interno di Adobe Experience Manager che integra contenuto e layout. I frammenti di esperienza sono fondamentali per creare esperienze coerenti e coinvolgenti, che possono essere ulteriormente riutilizzate su più canali. Ad esempio, puoi creare frammenti di esperienza per intestazioni o piè di pagina con elementi di branding, banner promozionali, testimonianze di clienti e promozioni di eventi.

![scheda opzioni proprietà file](./assets/file-properties-outputs-4-6.png) {width="300" align="left"}

*Publish e visualizzare i frammenti di esperienza di un argomento dalla sezione **Output**nelle **Proprietà file**.*

Experience Manager Guides ora consente di pubblicare un argomento o i relativi elementi in un frammento di esperienza. Puoi creare una mappatura basata su JSON tra un argomento o i relativi elementi e un modello di Frammento di esperienza. Puoi anche creare varianti di Frammento esperienza utilizzando i filtri di condizione.

Ulteriori informazioni su come [Frammenti esperienza Publish](../user-guide/publish-experience-fragment.md).



### Miglioramenti nella pubblicazione dei frammenti di contenuto

Experience Manager Guides fornisce anche alcuni utili miglioramenti nei frammenti di contenuto:

- Experience Manager Guides consente di pubblicare un argomento o i relativi elementi in un frammento di contenuto.

- Puoi pubblicare e visualizzare i Frammenti di contenuto di un argomento dalla sezione **Output** nelle **Proprietà file**.


- Puoi creare facilmente varianti di frammento di contenuto filtrando il contenuto con condizioni durante la pubblicazione in un frammento di contenuto.

- Utilizza la nuova interfaccia di mappatura per selezionare e pubblicare facilmente gli elementi in un frammento di contenuto.

Adesso, la pubblicazione dei frammenti di contenuto sostituisce solo il contenuto mappato, anziché sovrascrivere l’intero frammento di contenuto. Questa funzione consente a un frammento di contenuto di contenere dati provenienti da più origini, ad esempio più argomenti o l’editor di frammenti di contenuto.

![Aggiungere il modello di frammento e i dettagli di mappatura nella finestra di dialogo Publish come frammento di contenuto](assets/content-fragment-mapping.png)

Per ulteriori dettagli, visualizzare [Frammenti di contenuto Publish](../user-guide/publish-content-fragment.md).

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






### Possibilità di passare metadati dalle proprietà del file argomento all&#39;output di PDF nativo

Ora Experience Manager Guides consente di aggiungere i metadati dalle proprietà del file di un argomento ai layout di pagina durante la generazione dell’output di Native PDF. Utilizza questa funzione per aggiungere ai layout di pagina metadati specifici per argomento, come il titolo, i tag e la descrizione. È inoltre possibile personalizzare il PDF pubblicato in base ai metadati dell&#39;argomento, ad esempio aggiungendo una filigrana allo sfondo dell&#39;argomento in base allo stato del documento dell&#39;argomento.

![aggiungi metadati pdf nativo](./assets/add-metadata-native-pdf.png) {width="300" align="left"}

*Aggiungi metadati ai campi nei layout di pagina.*

Scopri come [aggiungere campi e metadati](../native-pdf/design-page-layout.md#add-fields-metadata) in un layout di pagina.





### Supporto per i documenti Markdown nella pubblicazione di PDF nativi

Experience Manager Guides supporta anche i documenti Markdown nella pubblicazione Native PDF. Questa funzione è utile e consente di generare PDF per i file Markdown nella mappa DITA.

Per ulteriori dettagli, visualizzare il [supporto per i documenti Markdown](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


### Scarica il file temporaneo durante la generazione dell&#39;output tramite DITA-OT

È inoltre possibile scaricare i file temporanei generati quando si pubblica l&#39;output AEM Sites, HTML, Custom, JSON o PDF tramite DITA-OT. Questa funzione consente di analizzare eventuali problemi che potrebbero verificarsi durante il processo di generazione dell’output e di risolvere efficacemente i problemi.  
È inoltre possibile scaricare il file metadata.xml se sono state selezionate proprietà di metadati passate all&#39;output generato mediante DITA-OT. 

Per ulteriori dettagli sui predefiniti, visualizzare [Informazioni sui predefiniti di output](../user-guide/generate-output-understand-presets.md).


### Opzione per scegliere una gerarchia di file piatta o nidificata per l&#39;output di HTML5

Ora Experience Manager Guides consente di mantenere la gerarchia di cartelle piatte per i file temporanei, in cui l’intero contenuto viene pubblicato in formato di output HTML5 e salvato in un’unica cartella.
Se non si sceglie di &quot;appiattire&quot; la gerarchia dei file, l&#39;output di HTML5 viene generato in una gerarchia di cartelle nidificate. Ciò implica che la struttura di cartelle originale del contenuto, con i file organizzati in sottocartelle, viene replicata nell’output. Questa gerarchia di cartelle nidificate consente un&#39;organizzazione e una categorizzazione dei file più complesse, semplificando la gestione e la navigazione di grandi volumi di dati.


Ulteriori informazioni su come [generare l&#39;output di HTML5](../user-guide/generate-output-html5.md)


## Miglioramenti dell’editor

Nella versione 4.6.0 sono stati aggiunti i seguenti miglioramenti per l’editor:

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



### Seleziona il contenuto parziale tra gli elementi per le operazioni

Experience Manager Guides migliora l’esperienza di selezione dei contenuti tra gli elementi nell’editor web. Puoi selezionare facilmente il contenuto tra diversi elementi ed eseguire operazioni come renderlo in grassetto, corsivo e sottolineato.

Questa funzione consente di applicare o rimuovere facilmente la formattazione per il contenuto parzialmente selezionato. Puoi anche eliminare rapidamente il contenuto selezionato tra gli elementi. Una volta eliminato il contenuto, se necessario, il contenuto rimanente viene unito automaticamente in un singolo elemento valido. È inoltre possibile selezionare contenuto parziale tra gli elementi e quindi racchiudere il contenuto in un elemento DITA valido.

Nel complesso, questi miglioramenti offrono un’esperienza migliore e consentono di migliorare l’efficienza durante la modifica dei documenti.
Per ulteriori dettagli, visualizzare [Selezione parziale del contenuto nell&#39;elemento](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).



### Elenco separato per visualizzare e inserire elementi validi in base alla loro posizione

Durante la modifica di un documento nell&#39;Editor Web, è ora possibile visualizzare un elenco separato di elementi validi nella posizione corrente e al di fuori di essa. In base alle tue esigenze, scegli un elemento tra le seguenti opzioni:

- **Elementi validi nella posizione corrente** che è possibile inserire direttamente nella posizione corrente del cursore.
- **Elementi validi al di fuori del percorso corrente** che è possibile inserire dopo uno qualsiasi dei padri per l&#39;elemento corrente all&#39;interno della gerarchia degli elementi.

![Finestra di dialogo Inserisci elemento](assets/insert-element-dialog.png){width="300" align="left"}

*Visualizzare gli elenchi segregati di elementi validi per inserire un elemento nella posizione corrente.*


Questo elenco suddiviso di elementi validi consente di mantenere la struttura del contenuto e di seguire gli standard DITA.

Ulteriori informazioni sulla funzionalità **Inserisci elemento** nella sezione [Barra degli strumenti secondaria](../user-guide/web-editor-features.md#2051ea0j0y4).


### Esperienza rinnovata per cercare e filtrare i file nella vista archivio

Ora disponi di un’esperienza avanzata per filtrare i file. La funzionalità rinnovata di filtro dei file consente di cercare e navigare tra i file in modo più semplice.


![cerca i file nella vista archivio](assets/repository-filter-search-2404.png){width="300" align="left"}

*Cerca i file contenenti il testo`general purpose.`*

Sfrutta vantaggi quali un accesso più rapido ai file rilevanti e un’interfaccia utente più intuitiva, che rende l’esperienza di ricerca più fluida ed efficiente.

![filtro di ricerca rapida ](assets/repository-filter-search-quick.png) {width="300" align="left"}

*Utilizza i filtri rapidi per cercare file DITA e non DITA.*


>[!NOTE]
>
> Gli amministratori del profilo di cartella devono aggiornare *ui_config.json* in modo da poter accedere a questa funzione in modo armonioso.

Ulteriori informazioni sulla funzionalità **Ricerca con filtro** nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).

### Condizioni raggruppate per un&#39;organizzazione avanzata dei contenuti

Experience Manager Guides ora consente di raggruppare le condizioni e di presentarle in una gerarchia nidificata, consentendo di aggiungere più condizioni a un singolo gruppo. Raggruppando le condizioni è possibile organizzarle e applicarle in modo migliore a tutto il contenuto.

![condizioni organizzate in una gerarchia nidificata](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Ulteriori informazioni sulla descrizione della funzionalità **Conditions** nella sezione [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS).

### Personalizzare l’esperienza dell’editor web con una nuova interfaccia utente con le preferenze dell’utente

La finestra di dialogo **Preferenze utente** nell&#39;editor Web ora include una nuova scheda **Aspetto**. Questa nuova scheda consente di configurare in modo pratico le preferenze di aspetto più comuni nell’interfaccia dell’editor web.

È possibile configurare per visualizzare i file in base al titolo o al nome file e modificare il tema dell&#39;applicazione e la vista origine. Consente inoltre di configurare le impostazioni per individuare un file aperto nella vista archivio e gestire gli spazi unificatori.

![scheda aspetto delle preferenze utente](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Personalizza l&#39;aspetto in base alle tue preferenze.*

Ulteriori informazioni sulla descrizione della funzione **Preferenze utente** nella sezione [Pannello sinistro](../user-guide/web-editor-features.md#id2051EA0M0HS).


### Individuare un file aperto nella visualizzazione repository dell&#39;editor Web

Seleziona l&#39;opzione **Individua sempre i file nel repository** nelle **Preferenze utente** per spostarti rapidamente e individuare il file nella visualizzazione del repository. Non è necessario cercarla manualmente.

Durante la modifica, questa funzione consente inoltre di visualizzare facilmente la posizione del file all’interno della gerarchia dell’archivio.

Per ulteriori dettagli, visualizzare [individuare un file aperto nella visualizzazione del repository](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).

### Gestione migliorata degli spazi unificatori nell&#39;editor Web

Experience Manager Guides consente di visualizzare un indicatore di spazio unificatore durante la modifica di documenti nell&#39;editor Web. Inoltre, migliora la gestione degli spazi unificatori.
Converte più spazi vuoti consecutivi in un unico spazio per mantenere la visualizzazione WYSIWYG del documento nell&#39;editor Web. Questa funzione consente inoltre di migliorare l&#39;aspetto generale e la professionalità del documento.


Per ulteriori dettagli, visualizzare le [altre funzionalità dell&#39;editor Web](../user-guide/web-editor-other-features.md).


### Possibilità di visualizzare le proprietà di qualsiasi elemento dalla gerarchia degli elementi

Ora le proprietà del contenuto **Tipo** vengono visualizzate come menu a discesa. Puoi visualizzare e selezionare i tag della gerarchia completa per il tag corrente dal menu a discesa.

Questo menu a discesa consente di accedere rapidamente alle proprietà del contenuto per il tag selezionato.


Menu a discesa ![type nelle proprietà del contenuto](assets/content-properties-type.png){width="300" align="left"}

*Selezionare un tag dalla gerarchia per il tag corrente.*

Ulteriori informazioni sulla funzionalità **Proprietà contenuto** nella sezione [Pannello destro](../user-guide/web-editor-features.md#id2051eb003yk).



### Sono state migliorate le prestazioni durante l’archiviazione in blocco di file dall’Editor mappa

Experience Manager Guides migliora le prestazioni e l&#39;esperienza della funzione di archiviazione in blocco dei file dall&#39;Editor mappe. Questo miglioramento consente di archiviare i file in blocco in modo più rapido.
È inoltre possibile visualizzare l&#39;avanzamento dell&#39;operazione di archiviazione per i file dalla finestra di dialogo **Salva come nuova versione e sblocca**. Al termine dell&#39;operazione viene infine visualizzato il messaggio di operazione riuscita e tutti i file estratti selezionati vengono archiviati.

![Salva come nuova versione e sblocca la finestra di dialogo](./assets/save-version-lock.png){width="300" align="left"}

*Visualizzare l&#39;elenco e lo stato dei file archiviati in blocco dall&#39;Editor mappe.*

Scopri come [utilizzare l&#39;Editor mappe avanzato](../user-guide/map-editor-advanced-map-editor.md)





## Miglioramenti alla gestione del ciclo di vita dei contenuti

La gestione del ciclo di vita dei contenuti è stata migliorata nei seguenti modi:

### Possibilità di tradurre il contenuto in più lingue utilizzando gruppi di lingue preconfigurati

Experience Manager Guides ora consente di creare gruppi di lingue e tradurre facilmente il contenuto in più lingue. Questa funzione consente di organizzare e gestire le traduzioni in base alle esigenze della tua organizzazione.

Ad esempio, se devi tradurre il contenuto per alcuni paesi in Europa, puoi creare un gruppo contenente le lingue europee come inglese (EN), francese (FR), tedesco (DE), spagnolo (ES) e italiano (IT).



![pannello di traduzione](assets/translation-languages-2404.png){width="300" align="left"}

*Selezionare i gruppi di lingue o le lingue in cui tradurre i documenti.*

>[!NOTE]
>
>Se manca la cartella di destinazione di una lingua o la lingua di destinazione è la stessa della lingua di origine, la cartella di destinazione è disattivata e mostra un segnale di avviso.

In qualità di amministratore, puoi creare gruppi di lingue e configurarli in più profili di cartelle. In qualità di autore, puoi visualizzare i gruppi di lingue configurati nel tuo profilo di cartella.


Nel complesso, la creazione di gruppi linguistici migliora l’efficienza e la produttività dei progetti di traduzione, migliorando in ultima analisi il processo di localizzazione in più lingue.


Scopri come [tradurre i documenti dall&#39;editor Web](../user-guide/translate-documents-web-editor.md).


### Prestazioni e scalabilità migliorate per progetti di traduzione di grandi dimensioni

La funzione di traduzione è più veloce e scalabile che mai. Viene fornita con una nuova architettura che offre prestazioni migliorate. Il tempo di creazione del progetto è ora più veloce di prima e i conflitti durante il processo sono quasi inesistenti. Queste prestazioni migliorate consentono di eseguire traduzioni più veloci, garantendo un funzionamento ottimale anche per progetti di traduzione di grandi dimensioni.

Questo miglioramento è molto utile in quanto migliora la produttività e l’esperienza complessiva.

Ulteriori informazioni su come [tradurre i documenti dall&#39;editor Web](../user-guide/translate-documents-web-editor.md).

### Elimina o disattiva automaticamente il progetto di traduzione dopo la traduzione

Ora, in qualità di amministratore, puoi configurare i progetti di traduzione in modo che vengano disabilitati o eliminati automaticamente dopo aver completato la traduzione. Questa funzione consente di utilizzare in modo efficiente le risorse e gestire i file dopo aver completato la traduzione.

Se si elimina un progetto, vengono rimossi in modo permanente tutti i file e le cartelle presenti nel progetto. L’eliminazione dei progetti di traduzione consente inoltre di liberare spazio su disco occupato.

Puoi disattivare i progetti di traduzione se desideri utilizzarli in un secondo momento.

![](assets/editor-setting-translation.png){width="550" align="left"}


*Configura i gruppi di lingue e le impostazioni di pulizia per i progetti di traduzione.*


Ulteriori informazioni su come [eliminare o disabilitare automaticamente il progetto di traduzione](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


### Disattiva la postelaborazione per le cartelle selettive su Adobe Experience Manager Assets


In qualità di amministratore, ora puoi disabilitare la post-elaborazione e la generazione di UUID per le cartelle selettive su Experience Manager Assets. Questa configurazione potrebbe essere utile, soprattutto quando si tratta di più risorse o di strutture di cartelle complesse. Consente inoltre a più utenti di caricare rapidamente e simultaneamente le risorse senza interferire tra loro.  

La disattivazione della postelaborazione per una cartella influisce anche su tutte le relative cartelle secondarie. Tuttavia, Experience Manager Guides ora offre la possibilità di abilitare in modo selettivo la postelaborazione per singole cartelle secondarie all’interno della cartella ignorata.

Scopri come [disabilitare la postelaborazione per una cartella](../cs-install-guide/conf-folder-post-processing.md).


## Miglioramenti nei connettori delle origini dati

I seguenti miglioramenti sono stati apportati ai connettori delle origini dati per la versione 2024.4.0:

### Connettersi alle origini dati delle schede ADO (Microsoft Azure DevOps Board) di Salsify, Akeneo

Oltre ai connettori predefiniti esistenti, Experience Manager Guides fornisce anche connettori per origini dati Salsify, Akeneo e bacheche DevOps di Microsoft Azure (ADO). In qualità di amministratore, puoi scaricare e installare questi connettori. Quindi, configura i connettori installati.

### Copiare e incollare la query di esempio per creare un frammento di contenuto o un argomento

Puoi copiare e incollare facilmente una query di dati di esempio nel generatore per creare uno snippet di contenuto o un argomento. Con questa funzione, non è necessario ricordare la sintassi o creare una query manualmente. Invece di digitare manualmente la query, puoi copiare e incollare una query di esempio, modificarla e utilizzarla per recuperare i dati in base alle tue esigenze.

![finestra di dialogo inserisci frammento di contenuto](assets/insert-content-snippet.png){width="800" align="left"}

*Copia e modifica una query di esempio per creare lo snippet di contenuto.*

### Connettersi a file di dati JSON utilizzando un connettore per file


Ora, in qualità di amministratore, puoi configurare un connettore per file JSON per utilizzare i file di dati JSON come origine di dati. Utilizza il connettore per importare i file JSON dal computer o da Adobe Experience Manager Assets. In qualità di autore, puoi quindi creare snippet di contenuti o argomenti utilizzando i generatori.

Questa funzione consente di utilizzare i dati memorizzati nei file JSON e di riutilizzarli in vari snippet. Il contenuto viene inoltre aggiornato dinamicamente ogni volta che si aggiornano i file JSON.

### Configurare più URL di risorse per un connettore per creare snippet di contenuto o argomenti

In qualità di amministratore, puoi configurare più URL di risorse per alcuni connettori come Generic REST Client, Salsify, Akeneo e Microsoft Azure DevOps Boards (ADO).

Quindi, in qualità di autore, puoi connetterti alle origini dati per creare snippet o argomenti utilizzando i generatori. Questa funzione è utile in quanto non è necessario creare un’origine dati per ogni URL. Consente di recuperare rapidamente i dati da una qualsiasi delle risorse per una particolare origine dati in un singolo frammento di contenuto o argomento.

Visualizzare ulteriori dettagli sui connettori di origini dati e su come [configurare un connettore di origine dati dall&#39;interfaccia utente](../cs-install-guide/conf-data-source-connector-tools.md).

Scopri come [utilizzare dati dall’origine dati](../user-guide/web-editor-content-snippet.md).

