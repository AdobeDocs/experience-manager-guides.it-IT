---
title: Altre funzioni nell’Editor mappa
description: Scopri alcune funzioni comuni nell’Editor mappa. Scopri come risolvere i riferimenti chiave nell’Editor mappa.
exl-id: f0e7a402-ac12-4c63-9d7f-92567ee29a39
feature: Authoring, Map Editor
role: User
TQID: https://experienceleague.adobe.com/Af2mFR-OG-QTbQU7HBQb-kfvuCcw5fd89CA4-mSroNE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: c3a30c22dd49ab8af898ecd2ff032101d2f9d93f
workflow-type: tm+mt
source-wordcount: 1285
ht-degree: 0%

---

# Funzioni aggiuntive nell’Editor mappa {#id1942D0T0HUI}

Alcune funzioni comuni nell’Editor mappa sono:

## Risolvi riferimenti chiave {#id176GD01H05Z}

Un riferimento a una chiave di contenuto DITA o `conkeyref` è un meccanismo per inserire una parte di contenuto da un argomento a un altro. Questo meccanismo utilizza la chiave per individuare il contenuto da riutilizzare, anziché il meccanismo di riferimento diretto ai contenuti. Per ulteriori informazioni sui riferimenti diretti e indiretti in DITA, visualizzare *Indirizzi DITA* in Specifiche lingua OASIS DITA.

Se all&#39;argomento DITA sono associati riferimenti chiave, è necessario risolverli prima di visualizzare in anteprima, modificare o rivedere un argomento.

I riferimenti chiave vengono risolti in base alla mappa principale impostata nel seguente ordine di priorità:

1. Preferenze utente
1. Pannello Vista mappa
1. Profilo cartella

La mappa principale selezionata in Preferenze utente ha la precedenza più alta per risolvere i riferimenti chiave, seguita dal pannello Vista mappa e dalla mappa principale Profilo cartella. Pertanto, se nelle Preferenze utente non è impostata alcuna mappa, viene utilizzata la mappa aperta nel pannello Vista mappa. Se nel pannello Vista mappa non è aperta alcuna mappa, per risolvere i riferimenti chiave viene utilizzata la mappa impostata nei Profili cartella.

I riferimenti chiave possono essere memorizzati all&#39;interno di un file mappa DITA o di un file DITA separato. In Experience Manager Guides, puoi specificare i riferimenti chiave a livello di progetto o di sessione. Se per la sessione utente è già definita una mappa radice, questa viene utilizzata per risolvere le chiavi. Altrimenti, viene utilizzata la mappa principale predefinita per quella cartella. Se non è configurata una mappa principale predefinita, all’utente vengono evidenziati i riferimenti chiave mancanti.

Esistono diversi modi per risolvere i riferimenti chiave in un argomento DITA definendo la mappa DITA da utilizzare nelle posizioni seguenti:

**Proprietà progetto** - È possibile definire una mappa radice per la risoluzione dei riferimenti chiave durante la creazione di un progetto nella sezione Proprietà progetto.

Questa mappa principale sarà applicabile a tutte le risorse (cartelle e sottocartelle) associate a quel progetto. Per il contenuto a cui si fa riferimento in più progetti, viene mantenuto un elenco alfabetico di progetti e viene utilizzata la mappa principale predefinita associata al primo progetto. È inoltre possibile scegliere la mappa DITA da utilizzare dall&#39;elenco per la risoluzione dei riferimenti chiave.

**Anteprima argomento** - Nella modalità di anteprima argomento, selezionare l&#39;icona Risoluzione chiave nella barra degli strumenti e selezionare il file DITA da utilizzare per i riferimenti chiave.

**Visualizzazione modifica argomento** - Selezionare l&#39;icona Risoluzione chiave durante la modifica di un argomento DITA e selezionare il file DITA da utilizzare per la risoluzione dei riferimenti chiave.

## Aggiungi riferimenti di navigazione

L&#39;elemento `navref` viene utilizzato all&#39;interno di una mappa DITA per includere i riferimenti di spostamento da un&#39;altra mappa DITA. Questo consente agli autori di riutilizzare la struttura di navigazione, ad esempio menu o collegamenti condivisi, senza unire nell’output il contenuto effettivo della mappa di riferimento.

>[!NOTE]
>
> L&#39;elemento `navref` è destinato esclusivamente alla navigazione all&#39;interno della struttura della mappa. Non contribuisce all&#39;output delle mappe DITA generato ed è escluso dall&#39;elaborazione e dalla visualizzazione in visualizzazione Mappa, Report, Linea di base, Traduzione e Anteprima.

Per aggiungere riferimenti di navigazione a una mappa, effettuare le seguenti operazioni:

1. Aprire il file di mapping DITA in cui si desidera aggiungere un riferimento di spostamento.

   Il file di mappa viene aperto nell&#39;Editor mappa.
1. Passare alla vista Autore e posizionare il cursore in una posizione valida per un riferimento di navigazione.
1. Selezionare l&#39;opzione **Elemento** nella barra degli strumenti.
1. Nella finestra di dialogo **Inserisci elemento**, seleziona **navref**.

   ![](./images/select-navref-element.png)
1. Viene visualizzata la finestra di dialogo **Seleziona percorso**. Seleziona un file di mappa da includere come riferimento di navigazione nella mappa e scegli **Seleziona**.

Nella posizione specificata viene aggiunto un riferimento di navigazione del file di mappa selezionato. Inoltre, il titolo della mappa a cui si fa riferimento viene visualizzato sia nella vista Creazione che nella vista Layout.

![](./images/navref-added-author-view.png)

*Visualizzazione autore*

![](./images/navref-added-layout-view.png)

*Visualizzazione Layout*

## Esegui verifica stato su una mappa

L&#39;opzione Esegui verifica stato nel menu di scelta rapida consente di eseguire una verifica stato sulla mappa selezionata per rilevare problemi quali collegamenti interrotti, ID duplicati e errori di convalida di Schematron prima della pubblicazione.

>[!NOTE]
>
> Questa funzione è attivata per impostazione predefinita. Se preferisci non utilizzare questa funzione nel tuo ambiente, contatta il team Customer Success.

I controlli disponibili per l&#39;esecuzione sono definiti da un predefinito di controllo di integrità, creato e gestito da un amministratore a livello di profilo di cartella. Per ulteriori dettagli, visualizzare [Creare e gestire i predefiniti di verifica stato](../install-conf-guide/conf-health-check-preset.md).

Per eseguire un controllo di integrità su una mappa, effettuare le seguenti operazioni:

1. Apri una mappa nell’editor.
1. Nel menu Opzioni, selezionare l&#39;opzione **Esegui controllo integrità**.
   ![](./images/run-health-check-option.png)
1. Viene visualizzata la finestra di dialogo Esegui verifica stato. Selezionare un predefinito di verifica stato che si desidera eseguire. È possibile selezionare solo i predefiniti configurati per il profilo di cartella.

   Selezionando un predefinito, carica i controlli definiti nella finestra di dialogo.

   ![](./images/health-check-selected-checks.png)
1. *Facoltativo* Selezionare una baseline. Se non si desidera utilizzare una previsione, selezionare **Nessuno**.
1. Seleziona **Esegui**.

Puoi anche eseguire un controllo di integrità su una mappa dal pannello **Rapporto controllo di integrità**. Per questo, apri una mappa nella vista Mappa e seleziona l&#39;icona **Rapporto di verifica stato**.

![](./images/health-check-report-icon.png)

>[!NOTE]
>
>Questa opzione viene visualizzata solo per una mappa su cui non è stato ancora eseguito alcun controllo di integrità. Se sulla mappa è già stata eseguita una verifica di integrità, se si seleziona l&#39;icona **Rapporto di verifica di integrità** verrà aperto il rapporto esistente.

Nel pannello, seleziona **Esegui verifica stato**.

![](./images/run-health-check-report-panel.png)

Viene aperta la stessa finestra di dialogo **Esegui verifica stato** in cui è possibile selezionare un predefinito di verifica stato e una baseline per eseguire una verifica stato sulla mappa, come descritto nei passaggi precedenti.

## Utilizzo del rapporto di verifica stato nell’editor

Quando esegui una verifica stato per una mappa, il rapporto viene aperto nel pannello **Rapporto verifica stato** come illustrato di seguito:

![](./images/health-check-report-panel-editor.png)

### Opzioni del pannello dei rapporti di verifica stato

Nel pannello Rapporto Verifica stato sono disponibili le seguenti opzioni:

- **Nome mappa**: nome della mappa per cui è stato generato il report.
- **Icona Info**: selezionare questa opzione per visualizzare il nome del predefinito, la versione della mappa e la linea di base (se presente) utilizzata per generare il report.
- **Filtro**: limita il report a una regola specifica, ad esempio per visualizzare solo i risultati dei collegamenti interrotti. Il filtro elenca solo i tipi di regole che hanno prodotto risultati nel rapporto corrente.
- **Scarica report**: scarica il report.
- **Rigenera**: esegue di nuovo il controllo di integrità.

### Risultati verifica stato

Ogni risultato ottenuto dai controlli selezionati è elencato con i seguenti dettagli:
- **Gravità**: livello di gravità del risultato, ad esempio Errore, Avviso, Informazioni o Fatale.
- **Nome predefinito per verifica stato**: nome del predefinito utilizzato per generare il rapporto
- **Nome regola**: la regola che ha prodotto il risultato, ad esempio Collegamenti interrotti o ID duplicato.
- **Numero riga**: la riga nel file in cui si è verificato il problema.
- **Risorsa**: file in cui è stato trovato il problema.

Seleziona un risultato per aprire il file corrispondente alla riga esatta in cui persiste il problema.

![](./images/health-check-preset-report-selected.png)

>[!NOTE]
>
>I risultati del collegamento interrotto aprono il file in modalità Creazione. I risultati della convalida ID duplicato e Schematron aprono il file in modalità Source.

### Rigenerare il rapporto

Dopo aver risolto un problema, seleziona **Rigenera** nella barra degli strumenti per eseguire nuovamente il controllo dello stato e confermare che il problema è stato risolto. Nella finestra di dialogo **Rigenera** visualizzata, selezionare i controlli che si desidera includere nel report rigenerato.

![](./images/health-check-preset-report-regenerate.png)

>[!NOTE]
>
> I rapporti di verifica stato sono specifici dell’utente che li ha generati. Se più utenti generano un rapporto per la stessa mappa, ogni utente visualizza i propri risultati. Gli amministratori, tuttavia, hanno sempre accesso all’ultimo rapporto generato per la mappa.

### Scarica il rapporto

Seleziona **Scarica report** per scaricare il report in formato XLS, con informazioni dettagliate per ogni risultato.


**Argomento padre:**[ Introduzione all&#39;editor mappe](map-editor.md)
