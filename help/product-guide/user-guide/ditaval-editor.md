---
title: Usa editor DITAVAL
description: Scopri come creare e modificare i file DITAVAL utilizzando l’Editor DIVATAL in Adobe Experience Manager Guides. Scopri in che modo l’editor DITAVAL supporta i file DITAVAL nelle visualizzazioni di authoring e sorgente.
exl-id: f3901a4f-1925-42aa-b773-0d6f18175ce8
feature: Authoring, DITAVAL Editor
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 0%

---

# editor DITAVAL {#ditaval-editor}

I file DITAVAL vengono utilizzati per generare output condizionale. In un singolo argomento, puoi aggiungere condizioni utilizzando gli attributi dell’elemento per condizionare il contenuto. Quindi, create un file DITAVAL in cui specificate le condizioni che devono essere selezionate per generare il contenuto e quali condizioni devono essere escluse dall&#39;output finale.

Adobe Experience Manager Guides consente di creare e modificare facilmente i file DITAVAL mediante l&#39;editor DITAVAL. L&#39;editor DITAVAL recupera gli attributi \(o tag\) definiti nel sistema ed è possibile utilizzarli per creare o modificare file DITAVAL. Per ulteriori dettagli sulla creazione e la gestione dei tag in Adobe Experience Manager, visualizzare la sezione [Amministrazione dei tag](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=it) nella documentazione di Adobe Experience Manager.

Nelle sezioni seguenti vengono descritte le opzioni disponibili per un file DITAVAL in Experience Manager Guides.

- [Crea file DITAVAL](#create-ditaval-file)
- [Modifica file DITAVAL](#edit-ditaval-file)
- [Visualizzazioni editor file DITAVAl](#ditaval-editor-views)
- [Utilizzo del file DITAVAL nell’interfaccia utente di Assets](#working-with-ditaval-files-in-the-assets-ui)

## Crea file DITAVAL

Per creare un file DITAVAL, effettuate le seguenti operazioni:

1. Nel pannello Archivio, seleziona l&#39;icona **Nuovo file**, quindi seleziona **Argomento** dal menu a discesa.

   ![](images/new-file-option.png){align="left"}

   È inoltre possibile accedere a questa opzione dalla [home page di Experience Manager Guides](./intro-home-page.md) e dal menu delle opzioni di una cartella nella visualizzazione Archivio.

2. Viene visualizzata la finestra di dialogo **Nuovo argomento**.

3. Nella finestra di dialogo **Nuovo argomento**, fornisci i seguenti dettagli:
   - Titolo per l&#39;argomento.
   - \(Facoltativo\)* Nome file dell&#39;argomento. Il nome del file viene suggerito automaticamente in base al Titolo dell’argomento. Se l’amministratore ha abilitato i nomi di file automatici in base all’impostazione UUID, il campo Nome non verrà visualizzato.
   - Modello su cui verrà basato l&#39;argomento. Per un file DITAVAL, selezionare **Ditaval** dall&#39;elenco a discesa.
   - Percorso in cui salvare il file dell&#39;argomento. Per impostazione predefinita, il percorso della cartella attualmente selezionata nell’archivio viene visualizzato nel campo Percorso.

   ![](images/new-topic-dialog-ditaval.png){width="300" align="left"}


4. Seleziona **Crea**.

L&#39;argomento viene creato nel percorso specificato. Inoltre, l’argomento viene aperto nell’Editor per la modifica.

![](images/ditaval-file-editor.png){align="left"}

## Modifica file DITAVAL

Quando si crea un argomento DITAVAL, questo viene aperto nell&#39;Editor per la modifica. Per modificare un argomento DITAVAL esistente, passare alla cartella o alla mappa in cui si trova l&#39;argomento DITAVAL, quindi selezionare **Modifica** dal menu **Opzioni**.

L&#39;editor DITAVAL consente di eseguire le seguenti operazioni:

- Attiva/Disattiva pannello sinistro

  Attiva/disattiva la visualizzazione del pannello sinistro. Se avete aperto il file DITAVAL tramite mappa DITA, la mappa e l&#39;archivio vengono visualizzati in questo pannello. Per ulteriori informazioni sull&#39;apertura di un file tramite mappa DITA, visualizzare [Modifica argomenti tramite mappa DITA](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

- Salva

  Salva le modifiche apportate nel file. Tutte le modifiche vengono salvate nella versione corrente del file.

- Aggiungi proprietà

  Aggiungi una singola proprietà nel file DITAVAL.

  ![](images/ditaval-editor-props-new.png)

  Nel primo elenco a discesa sono elencati gli attributi DITA consentiti che è possibile utilizzare nel file DITAVAL. Sono supportati cinque attributi: `audience`, `platform`, `product`, `props` e `otherprops`.

  Il secondo elenco a discesa mostra i valori configurati per l’attributo selezionato. Nell&#39;elenco a discesa successivo vengono quindi visualizzate le azioni che è possibile configurare per l&#39;attributo selezionato. I valori consentiti nel menu a discesa delle azioni sono - `include`, `exclude`, `passthrough` e `flag`. Per ulteriori informazioni su questi valori, vedere la definizione dell&#39;elemento [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) nella documentazione OASIS DITA

- Aggiungi tutte le proprietà

  Se desiderate aggiungere tutte le proprietà condizionali o gli attributi definiti nel sistema con un solo clic, utilizzate la funzione Aggiungi tutte le proprietà.

  >[!NOTE]
  >
  > Se tutte le proprietà condizionali definite esistono già nel file DITAVAL, non è possibile aggiungere altre proprietà. Viene visualizzato un messaggio di errore in questo scenario.

  ![](images/ditaval-all-props-new.png)

Dopo aver modificato il file DITAVAL, selezionare **Salva**.

>[!NOTE]
>
> Se si chiude il file senza salvare, le modifiche andranno perse. Se non desideri eseguire il commit delle modifiche nell&#39;archivio di Adobe Experience Manager, seleziona **Chiudi**, quindi seleziona **Chiudi senza salvare** nella finestra di dialogo **Modifiche non salvate**.

## Visualizzazioni dell’editor DITAVAL

L’editor DITAVAL di Adobe Experience Manager Guides supporta la visualizzazione dei file DITAVAL in due diverse modalità o visualizzazioni:

**Autore**:   Questa è una tipica visualizzazione di What You See is What You Get \(WYSISYG\) dell&#39;editor DITAVAL. Puoi aggiungere o rimuovere proprietà utilizzando la semplice interfaccia utente, che presenta le proprietà, i relativi valori e le azioni nell’elenco a discesa. Nella vista Autore sono disponibili le opzioni per inserire una singola proprietà e tutte le proprietà con un solo clic.

Per trovare la versione del file DITAVAL su cui si sta attualmente lavorando, posizionare il puntatore del mouse sul nome del file.

**Source**:   Nella vista Source viene visualizzato il codice XML sottostante che costituisce il file DITAVAL. Oltre a eseguire modifiche regolari del testo in questa visualizzazione, un autore può anche aggiungere o modificare proprietà utilizzando Smart Catalog.

Per richiamare lo Smart Catalog, posizionare il cursore alla fine di qualsiasi definizione di proprietà e immettere &quot;&lt;&quot;. Nell&#39;editor verrà visualizzato un elenco di tutti gli elementi XML validi che è possibile inserire in tale posizione.

![](images/ditaval-source-view-new.png)


## Utilizzo dei file DITAVAL nell’interfaccia utente di Assets

Puoi anche creare un file DITAVAL dall’interfaccia utente di Assets. I passaggi per creare un nuovo argomento DITAVAL sono i seguenti:

1. Nell’interfaccia utente di Assets, individua il percorso in cui desideri creare il file DITAVAL.

1. Selezionare **Crea** \> **Argomento DITA**.

1. Nella pagina Blueprint, seleziona il modello di file DITAVAL e seleziona **Avanti**.

1. Nella pagina Proprietà, specifica **Titolo** e **Nome** per il file DITAVAL.

   >[!NOTE]
   >
   > Il nome viene suggerito automaticamente in base al Titolo del file. Se si desidera specificare manualmente il nome del file, assicurarsi che il nome non contenga spazi, apostrofi o parentesi graffe e che termini con .ditaval.

1. Seleziona **Crea**.

   Viene visualizzato il messaggio Topic Created (Creazione argomento).

Potete scegliere di aprire il file DITAVAL per la modifica nell&#39;editor DITAVAL o salvare il file dell&#39;argomento nel repository di Adobe Experience Manager.

Per modificare un file DITAVAL esistente, effettuate le seguenti operazioni:

1. Nell’interfaccia utente di Assets, individua il file DITAVAL da modificare.

1. Per ottenere un blocco esclusivo sul file, selezionare il file e selezionare **Estrai**.

1. Selezionare il file e selezionare **Modifica** per aprire il file nell&#39;editor DITAVAL di Adobe Experience Manager Guides.



