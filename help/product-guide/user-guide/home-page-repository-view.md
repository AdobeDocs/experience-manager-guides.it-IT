---
title: Archivio nella home page
description: Scopri l’archivio nella pagina Home. Scopri l’interfaccia e le funzioni dell’archivio in Adobe Experience Manager Guides nella pagina Home.
feature: Authoring
role: User
source-git-commit: e45343812a67c6755c76f1b31b68c7201cdd8772
workflow-type: tm+mt
source-wordcount: '1412'
ht-degree: 0%

---

# Conoscere l’interfaccia dell’archivio

L’archivio funge da spazio centralizzato per migliorare la reperibilità di cartelle e file. Offre una vista completa a elenco tabulare di cartelle e file con più colonne, offrendo dettagli contestuali per tutti i file e le risorse.

Questa interfaccia unificata semplifica diverse funzioni, tra cui la creazione di nuovi file o cartelle, la modifica di file, il caricamento di risorse e la ricerca di file con solide opzioni di filtro, garantendo in tal modo efficienza e facilità d’uso.

![](images/repository-view-home.png){align="left"}

L’interfaccia dell’archivio è suddivisa nelle sezioni seguenti:

- Barra di navigazione dell’archivio
- Vista tabulare dell’archivio

## Barra di navigazione dell’archivio

La barra di navigazione dell’archivio, che si trova nella parte superiore dell’interfaccia dell’archivio, consente di accedere rapidamente alle azioni essenziali elencate.

![](images/tab-bar-repository-view.png){align="left"}


- **Pannello di navigazione cartelle**: visualizza una struttura gerarchica delle cartelle all&#39;interno dell&#39;archivio, consentendo una navigazione fluida. Questo pannello mostra solo le informazioni a livello di cartella. Quando una cartella viene selezionata da qui, il suo contenuto, i file e le sottocartelle vengono visualizzati nella vista Archivio. Puoi mostrare o nascondere questo pannello utilizzando l’icona evidenziata di seguito.

  ![](images/folder-navigation-panel.png){align="left"}

- **Breadcrumb**: indica il percorso corrente all&#39;interno dell&#39;archivio, con la gerarchia delle cartelle che conducono alla cartella corrente. Puoi selezionarla per tornare a una cartella specifica all’interno della gerarchia.

  ![](images/breadcrumbs.png){width="650" align="left"}

- **Aggiorna**: aggiorna l&#39;archivio per riflettere le modifiche più recenti.
- **Carica Assets**: consente di caricare le risorse direttamente nella cartella corrente, come evidenziato nelle breadcrumb.
- **Nuovo**: consente la creazione di nuovi argomenti, mappe e cartelle all&#39;interno della cartella corrente, come evidenziato nelle breadcrumb.
- **Assistente AI**: uno strumento potente e basato sull&#39;intelligenza artificiale progettato per migliorare la produttività tramite le funzionalità di assistenza avanzata. La funzionalità [Assistente AI](./ai-assistant.md) è attualmente disponibile solo per Adobe Experience Manager as a Cloud Service.
- **Altre azioni**: consente di accedere a opzioni aggiuntive. Selezionando questo pulsante si apre un menu con le seguenti opzioni:
   - **Assets**: ti porta a una destinazione in base alla tua configurazione.
      - **Servizi cloud**: se utilizzi Servizi cloud, quando selezioni l&#39;opzione **Assets** vieni reindirizzato alla pagina di navigazione di AEM.
      - **Software on-premise**: se si utilizza Adobe Experience Manager Guides (4.2.1 e versioni successive), se si seleziona l&#39;opzione **Assets**, verrà visualizzato il percorso del file corrente nell&#39;interfaccia utente di Assets.
   - **Impostazioni Workspace**: consente di accedere alla finestra di dialogo **Impostazioni Workspace**. Per ulteriori dettagli, visualizzare [Configurazione impostazioni di Workspace](../cs-install-guide/workspace-settings.md).
- **Espandi visualizzazione**: consente di espandere la visualizzazione della pagina utilizzando l&#39;icona **Espandi**. In questa visualizzazione, la barra dell’intestazione è nascosta e lo spazio disponibile risulta quindi notevolmente ridotto. Per tornare alla vista standard, utilizzare l&#39;icona Esci dalla vista espansa.

## Vista tabulare dell’archivio

L’archivio funge da spazio centrale e fornisce un elenco tabulare di tutte le cartelle e dei file. Offre le seguenti caratteristiche:

- **Personalizza**: è possibile modificare le colonne visualizzate utilizzando l&#39;opzione **Personalizza** situata nell&#39;angolo superiore destro della visualizzazione Archivio. Questa opzione consente di mostrare o nascondere qualsiasi colonna e di ridisporre le colonne in base alle esigenze. Le colonne **Name** o **Title** sono obbligatorie e non possono essere disabilitate insieme. Altri campi, ad esempio **Tipo file**, **UUID**, **Stato documento**, **Bloccato da**, **Creato il** e **Modificato il**, possono essere attivati o disattivati in base alle esigenze. Puoi riorganizzarle semplicemente trascinandole e rilasciandole.

  ![](images/customize-repo-view.png){width="350" align="left"}

- **Ridimensionamento colonne**: è possibile ridimensionare le colonne selezionando le opzioni dal menu a discesa delle colonne.

- **Ordinamento**: le colonne Nome, Titolo, Creato il e Ultima modifica supportano l&#39;ordinamento crescente o decrescente, accessibile tramite il menu a discesa delle colonne.

- **Modifica del file**:

   - È possibile selezionare uno o più file dall&#39;elenco per la modifica.
   - Dopo aver selezionato i file desiderati utilizzando la casella di controllo, l&#39;opzione **Modifica** diventa disponibile nell&#39;angolo in alto a destra della visualizzazione Archivio.
   - Selezionando **Modifica** i file selezionati verranno aperti nell&#39;interfaccia dell&#39;editor, dove sarà possibile iniziare a modificarli.

     ![](images/edit-repo-view.png){align="left"}

- **Menu Opzioni per le cartelle**: è possibile eseguire le azioni seguenti utilizzando il menu **Opzioni** disponibile per una cartella:

  ![](images/options-folder-repo.png){width="350" align="left"}

   - **Nuovo**: creare un nuovo argomento DITA, una mappa DITA o una cartella.
   - **Carica Assets**: carica un file dal sistema locale alla cartella selezionata nell&#39;archivio.
   - **Aggiungi a raccolte**: aggiunge la cartella selezionata ai preferiti. Puoi scegliere di aggiungerlo a una raccolta esistente o nuova.
   - **Rielabora risorse**: attiva l&#39;elaborazione di tutte le risorse nella cartella.

- **Menu Opzioni per i file**: è possibile eseguire le azioni seguenti utilizzando il menu **Opzioni** per un file:

  ![](images/options-file-repo-new.png){width="350" align="left"}

   - **Modifica**: apri il file per la modifica.
   - **Modifica in ossigeno**: selezionare questa opzione per modificare il file selezionato nel plug-in del connettore di ossigeno.

     >[!NOTE]
     >
     >Contatta il team di successo del cliente per abilitare questa funzione nell’ambiente. Questa funzione non è abilitata come parte del supporto predefinito. Per ulteriori dettagli, vedere la sezione [Configurare l&#39;opzione da modificare in Ossigeno](../cs-install-guide/conf-edit-in-oxygen.md) nella Guida all&#39;installazione e alla configurazione.

   - **Apri nella console delle mappe**: se il file selezionato è una mappa DITA, questa opzione apre la console delle mappe.
   - **Apri nel dashboard delle mappe**: se il file selezionato è una mappa DITA, questa opzione apre il dashboard delle mappe.
   - **Blocco**: ottieni un blocco sul file selezionato per la modifica.
   - **Anteprima**: consente di ottenere un&#39;anteprima rapida del file (.dita, .xml, audio, video o immagine) senza aprirlo.
   - **Duplicato**: utilizzare questa opzione per creare un duplicato o una copia del file selezionato.
   - **Sposta in**: utilizzare questa opzione per spostare il file selezionato in un&#39;altra cartella.
   - **Rinomina**: utilizzare questa opzione per rinominare il file selezionato.
   - **Elimina**: utilizzare questa opzione per eliminare il file selezionato.
   - **Aggiungi a**: scegliere di aggiungere alle raccolte o al contenuto riutilizzabile.
   - **Copia**: copia l&#39;UUID o il percorso completo del file.
   - **Rielabora risorsa**: attiva l&#39;elaborazione per la risorsa selezionata.
   - **Proprietà**: utilizzare questa proprietà per aprire la pagina Proprietà del file selezionato.
   - **Scarica come PDF**: utilizza l&#39;opzione per generare l&#39;output di PDF e scaricarlo.

### Esperienza di ricerca e filtro

L&#39;opzione **Cerca** consente di cercare i file richiesti dall&#39;archivio principalmente in base al **Titolo file**, **Nome file** e **Contenuto**. Puoi utilizzare uno, due o tutti e tre i criteri per la ricerca. Se non viene selezionato nessuno dei criteri, i risultati includeranno elementi comuni a tutti e tre i criteri.

![](images/search-in-repository.png){align="left"}

Seleziona l&#39;icona **Ricerca filtro** \(![Icona filtro di ricerca](images/filter-search-icon.svg)\) per aprire il pannello Filtro a destra.

![](images/Search-filters-repo.png){align="left"}

Per filtrare i file e restringere la ricerca, sono disponibili le seguenti opzioni:

- **Cerca in**: selezionare il percorso in cui si desidera eseguire la ricerca nei file presenti nel repository.

- **Tipo di file**: filtra la ricerca in base a un tipo di file specifico. Le opzioni disponibili sono: **Argomento**, **Mappa**, **DITAVAL**, **Immagine**, **Multimedia**, **Documento** e **Altri**.

- **Stato documento**: è possibile filtrare la ricerca in base allo stato corrente dei file. I valori di filtro disponibili sono definiti nel campo `repositoryFilters` di `ui_config.json file` e sono associati al profilo di cartella attualmente in uso.

  Ciò significa che:

   - Se utilizzi il Profilo globale, vengono applicati i valori dei filtri configurati nel Profilo globale.
   - Se selezioni un profilo di cartella specifico, vengono recuperati i valori dei filtri definiti in tale profilo.

  I valori di filtro predefiniti disponibili per lo stato del documento sono: Bozza, Modifica, In revisione, Approvato, Rivisto e Fine. Per informazioni dettagliate sulla personalizzazione dei valori di filtro per gli stati dei documenti, visualizzare [Configurare i filtri per lo stato dei documenti](../cs-install-guide/config-doc-state-filters.md).

- **Bloccato da**: visualizza un elenco di utenti. L’elenco viene impaginato e caricato in modo asincrono, mostrando un set limitato di utenti alla volta e recuperandone altri durante lo scorrimento o la navigazione. Ciò migliora la velocità di caricamento e le prestazioni complessive, soprattutto quando si lavora con un numero elevato di utenti.

- **Ultima modifica**: filtra il contenuto in base alla data di modifica. Seleziona un intervallo di date dal calendario o scegli una delle seguenti opzioni per l’intervallo di tempo:
   - Nell&#39;ultima settimana
   - Nell&#39;ultimo mese
   - Nell&#39;ultimo anno

- **Tag**: filtra il contenuto in base ai tag.

- **Elementi DITA**: consente di filtrare il contenuto in base a vari elementi DITA.

Dopo aver applicato tutti i filtri richiesti, seleziona **Applica** dall&#39;angolo inferiore destro del pannello Filtri.

I risultati della ricerca personalizzati in base al filtro selezionato vengono visualizzati come **elenco tabulare di soli file** (le cartelle non vengono visualizzate). È possibile rimuovere un filtro singolarmente o più filtri contemporaneamente e i risultati vengono aggiornati per riflettere la selezione aggiornata.

![](images/search-results-with-filters.png){align="left"}

Una volta visualizzati i risultati della ricerca, è possibile selezionare più file e aprirli nell&#39;editor utilizzando l&#39;icona **Modifica** oppure utilizzare tutti i risultati inviando i risultati della ricerca all&#39;editor tramite l&#39;opzione **Mostra nel pannello di ricerca**.

![](images/post-search-operation.png){align="left"}

**Mostra nel pannello di ricerca**

L&#39;opzione **Mostra nel pannello di ricerca** diventa disponibile dopo aver eseguito una ricerca nell&#39;archivio. Questa funzione ti consente di visualizzare tutti i risultati della ricerca nel **pannello Ricerca** nell&#39;Editor. Per ulteriori dettagli, visualizzare [Pannello di ricerca](./search-panel-explorer.md).

![](images/search-panel-repo.png){align="left"}

