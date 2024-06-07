---
title: Pubblicare un argomento in un frammento di contenuto
description: Pubblicare un argomento o gli elementi all’interno di un argomento in un frammento di contenuto nelle guide AEM.  Scopri come visualizzare i Frammenti di contenuto presenti in un argomento e ripubblicarli.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
feature: Publishing
role: User
source-git-commit: 7c7e3dcddf733793a5d6db50205ba60d24702451
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 0%

---

# Pubblicare frammenti di contenuto

I frammenti di contenuto sono parti discrete di contenuto in Adobe Experience Manager. Sono contenuti strutturati basati su un modello di contenuto. I frammenti di contenuto sono contenuti puri senza informazioni di progettazione o layout. Possono essere creati e gestiti indipendentemente dai canali supportati da Adobe Experience Manager. I frammenti di contenuto sono modulari, dove il contenuto viene suddiviso in componenti più piccoli.

Le guide di Adobe Experience Manager consentono di pubblicare un argomento o gli elementi all’interno di un argomento in un frammento di contenuto. Puoi creare una mappatura basata su JSON tra un argomento e un modello per frammenti di contenuto. Utilizzare questa mappatura per pubblicare un argomento o gli elementi di un argomento in un frammento di contenuto. Puoi quindi utilizzare i frammenti di contenuto in qualsiasi sito Adobe Experience Manager o estrarre i dettagli tramite API supportate dai frammenti di contenuto.


Per creare un frammento di contenuto, effettua le seguenti operazioni:

1. Creare un [Modello per frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=it) in Adobe Experience Manager Assets.
1. Crea una cartella in cui salvare i frammenti di contenuto creati in base al modello Frammento di contenuto. Ad esempio, &quot;stock-content-fragments&quot;.
1. Modifica le proprietà della cartella (ad esempio, &quot;stock-content-fragments&quot;) e aggiungi il percorso della cartella, che contiene il modello Frammento di contenuto nella configurazione cloud.
Ad esempio, aggiungi `/conf/we-retail` nella configurazione cloud. Questa configurazione collega tutti i modelli per frammenti di contenuto alla cartella.\
   ![aggiungi dettagli di configurazione cloud nelle proprietà della cartella](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Aggiungi la configurazione cloud nelle proprietà della cartella per collegarla ai modelli di frammenti.*

1. Per generare un frammento di contenuto, seleziona **Nuovo output** ![icona nuovo output](./images/Add_icon.svg) dal **Uscite** sezione nella sezione **Proprietà file** di un argomento.
1. Seleziona **Frammento di contenuto**.\
   ![scheda delle opzioni delle proprietà del file](./images/file-properties-outputs-tab.png){width="300" align="left"}

   *Aggiungere un nuovo frammento di contenuto dalle proprietà file di un argomento*.

1. In **Genera frammento di contenuto** , compilare i seguenti dettagli:
   ![Aggiungi il modello di frammento e i dettagli della mappatura nella finestra di dialogo Pubblica come frammento di contenuto](images/content-fragment-publish.png){width="500" align="left"}
   *Aggiungi i dettagli di percorso, modello e mappatura per pubblicare un argomento o i relativi elementi come frammento di contenuto. Puoi sovrascrivere un frammento di contenuto esistente.*

   >[!NOTE]
   >
   >Puoi anche pubblicare un Frammento di contenuto dalla sezione **Vista archivio**. Seleziona l’argomento da pubblicare come Frammento di contenuto. Quindi, dalla sezione **Opzioni** menu, seleziona **Pubblica come** > **Frammento di contenuto**.

   * **Percorso**: sfoglia e seleziona il percorso della cartella in cui desideri pubblicare il frammento di contenuto. Se selezioni un frammento di contenuto esistente, questo sovrascrive il contenuto dei campi mappati.
   * **Titolo**: digita il titolo del frammento di contenuto. Per impostazione predefinita, il titolo viene compilato con il titolo dell’argomento. Puoi modificarlo. Questo titolo viene utilizzato per generare il nome del frammento di contenuto.
   * **Nome**: digita il nome del frammento di contenuto. Per impostazione predefinita, il nome viene compilato con il titolo dell&#39;argomento e gli spazi vengono sostituiti con &quot;_&quot;. Ad esempio: *sample_content_fragment*. Puoi modificarlo.  Questo nome viene utilizzato per generare l’URL per il frammento di contenuto.
   * **Modello**: seleziona il modello per frammenti di contenuto da utilizzare per creare il frammento di contenuto. I modelli vengono prelevati dalla cartella, che hai configurato nei servizi cloud.
   * **Mappatura**: seleziona una mappatura dal menu a discesa. Seleziona le mappature da *contentFragmentMapping.json* file.



     L’amministratore può aggiungere le mappature nel *contentFragmentMapping.json* file. Ulteriori informazioni su come [creare una mappatura tra un argomento e un frammento di contenuto](../cs-install-guide/conf-content-fragment-mapping-cs.md) nella Guida all&#39;installazione e alla configurazione.

   * Puoi anche selezionare condizioni diverse per pubblicare il contenuto.  Selezionare una delle opzioni seguenti:


      * **Nessuno**: seleziona questa opzione se non desideri applicare alcuna condizione all’output pubblicato.
      * **Utilizzo di DITAVAL**: seleziona il file DITAVAL per generare l’output, che include contenuto specifico. Potete selezionare il file DITAVAL utilizzando la finestra di dialogo Sfoglia (Browse) o digitando il percorso del file.
      * **Utilizzo degli attributi**: puoi definire gli attributi della condizione negli argomenti DITA. Quindi, seleziona l’attributo della condizione per pubblicare il contenuto pertinente.
     >[!NOTE]
     > 
     >Le condizioni sono abilitate solo se gli attributi della condizione sono definiti nell&#39;argomento.



   * Seleziona **Sovrascrivi contenuto esistente** se il frammento di contenuto esiste già e desideri sovrascriverlo. Experience Manager di Guide: se non selezioni la casella di controllo e il frammento di contenuto esiste già, viene visualizzato un errore.
1. Clic **Genera** per pubblicare il frammento di contenuto.

1. Puoi visualizzare i Frammenti di contenuto di un argomento nella sezione **Uscite** sezione nella sezione **Proprietà file**.

   ![Visualizzare i frammenti di contenuto per un argomento](images/outputs-options-menu.png){width="300" align="left"}

   *Visualizza i Frammenti di contenuto presenti in un argomento e ripubblicali.*


Dopo aver pubblicato i frammenti di contenuto, puoi utilizzarli in qualsiasi sito Adobe Experience Manager.




## Menu Opzioni per un frammento di contenuto

Per un frammento di contenuto, puoi anche eseguire le seguenti azioni dalla sezione **Opzioni** menu:

* **Genera**: ripubblica il frammento di contenuto per aggiornarlo con il contenuto più recente dell’argomento DITA. Quando rigeneri l’output, non puoi modificare il percorso, il nome, il titolo, il modello e la mappatura del frammento di contenuto. Tuttavia, potete selezionare condizioni diverse durante la rigenerazione dell&#39;output.

* **Duplica**: duplica un frammento di contenuto. È possibile modificare il percorso, il nome, il titolo, il modello e la mappatura. Puoi anche selezionare condizioni diverse quando duplichi un frammento di contenuto.

* **Rimuovi**: rimuovi un frammento di contenuto dall’elenco degli output. Viene visualizzata una richiesta di conferma. Una volta confermata, il frammento di contenuto viene rimosso da **Uscite** elenco.

  >[!NOTE]
  >
  > Con questa azione nessun contenuto viene eliminato dal frammento di contenuto.

* **Visualizza**: visualizza l’editor dei frammenti di contenuto. Puoi anche apportare modifiche e salvarle.


