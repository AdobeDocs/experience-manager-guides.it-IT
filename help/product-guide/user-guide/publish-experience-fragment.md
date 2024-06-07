---
title: Pubblicare un argomento in un frammento di esperienza
description: Pubblica un argomento o gli elementi di un argomento in un frammento di esperienza nelle guide AEM.  Scopri come visualizzare i frammenti di esperienza presenti in un argomento e ripubblicarli.
feature: Publishing
role: User
source-git-commit: 7c7e3dcddf733793a5d6db50205ba60d24702451
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 0%

---


# Pubblicare Frammenti Esperienza

I frammenti di esperienza sono parti di contenuto modulare in Adobe Experience Manager. Questi blocchi di contenuto sono basati su modelli e incapsulano sia il contenuto che il relativo layout. Questi contenuti riutilizzabili consentono ai creatori di contenuti di assemblare e fornire esperienze coerenti e scalabili su più canali supportati da Experience Manager. Questa funzione consente di creare facilmente esperienze di marketing coerenti in modo efficiente, come newsletter, banner promozionali e testimonianze di clienti.

Le guide di Experience Manager consentono di pubblicare un argomento o i relativi elementi in un frammento di esperienza. Puoi creare una mappatura basata su JSON tra un argomento e i relativi elementi in un frammento di esperienza. Quindi, utilizza la mappatura per pubblicare un argomento o i relativi elementi in un frammento di esperienza. Puoi quindi utilizzare i frammenti di esperienza in qualsiasi sito di Experienci Manager o estrarre i dettagli tramite API supportate da Frammenti di esperienza.




Per generare un frammento di esperienza, effettua le seguenti operazioni:


1. Crea una cartella nei Frammenti esperienza. Utilizza questa cartella per salvare i frammenti esperienza creati in base ai modelli di frammenti esperienza. Ad esempio: *sales-experience-fragments*.
1. Seleziona la cartella, quindi fai clic su **Proprietà** dall’alto.
1. Modifica le proprietà della cartella (ad esempio, *sales-experience-fragments*).


   * **Titolo**: visualizza o modifica il titolo della cartella.

   * **Modelli consentiti**: contiene l’elenco dei modelli che possono essere aggiunti come pagine figlie del frammento esperienza. Per aggiungere il modello consentito, specifica l’espressione regolare per recuperare i modelli richiesti in **Modelli consentiti** campo.
Ad esempio:
     `/libs/cq/experience-fragments/components/experiencefragment/template`

     Se non si definisce un modello consentito per una cartella, i modelli vengono selezionati dalla cartella principale o dalla cartella dei modelli per impostazione predefinita.
   * **Ordinabile**: consente di modificare l’ordine delle risorse all’interno di una cartella.
     ![aggiungi dettagli di configurazione cloud nelle proprietà della cartella](images/experience-fragment-folder-properties.png){width="650" align="left"}
     *Aggiungi la configurazione cloud nelle proprietà della cartella per collegarla ai modelli del frammento.*
1. Per generare un frammento di esperienza, seleziona **Nuovo output** ![icona nuovo output](./images/Add_icon.svg) dal **Uscite** sezione nella sezione **Proprietà file** di un argomento.
1. Seleziona **Frammento esperienza**.\
   ![scheda delle opzioni delle proprietà del file](./images/file-properties-outputs.png){width="300" align="left"}

   *Aggiungere un nuovo frammento di esperienza dalle proprietà file di un argomento*.

   >[!NOTE]
   >
   > Puoi anche pubblicare un frammento di esperienza dalla sezione **Vista archivio**. Seleziona l’argomento da pubblicare come frammento di esperienza. Quindi, dalla sezione **Opzioni** menu, seleziona **Pubblica come** > **Frammento esperienza**.

1. In **Genera frammento esperienza** , compilare i seguenti dettagli:
   ![Aggiungi il modello di frammento e i dettagli della mappatura nella finestra di dialogo Pubblica come frammento esperienza](images/experience-fragment-generate.png){width="500" align="left"}

   *Aggiungi il percorso, il modello e i dettagli di mappatura per pubblicare un argomento o i relativi elementi come frammento di esperienza. Puoi sovrascrivere un frammento di esperienza esistente.*

   * **Percorso**: sfoglia e seleziona il percorso della cartella in cui desideri pubblicare il frammento di esperienza. Puoi anche selezionare un frammento di esperienza esistente e ripubblicarlo.
   * **Titolo**: digita il titolo del frammento di esperienza. Per impostazione predefinita, il titolo viene compilato con il titolo dell’argomento. Puoi modificarlo. Questo titolo viene utilizzato per generare il nome del frammento di esperienza.
   * **Nome**: digita il nome del frammento di esperienza. Per impostazione predefinita, il nome viene compilato con il titolo dell&#39;argomento e gli spazi vengono sostituiti con &quot;_&quot;. Ad esempio: *sample_experience_fragment*. Puoi modificarlo. Questo nome viene utilizzato per generare l’URL per il frammento di esperienza.
   * **Modello**: seleziona il modello Frammento esperienza da utilizzare per creare il frammento esperienza. I modelli vengono selezionati dalla cartella configurata nelle proprietà.
   * **Mappatura**: seleziona la mappatura da *experienceFragmentMapping.json* e lo visualizza.



     L’amministratore può aggiungere le mappature nel *experienceFragmentMapping.json* file.  Ulteriori informazioni su come [creare una mappatura tra un argomento e un frammento di esperienza](../cs-install-guide/conf-experience-fragment-mapping-cs.md) nella Guida all&#39;installazione e alla configurazione.

   * Puoi anche selezionare condizioni diverse per pubblicare il contenuto.  Selezionare una delle opzioni seguenti:


      * **Nessuno**: seleziona questa opzione se non desideri applicare alcuna condizione all’output pubblicato.
      * **Utilizzo di DITAVAL**: seleziona il file DITAVAL per generare contenuti personalizzati. Potete selezionare il file DITAVAL utilizzando la finestra di dialogo Sfoglia (Browse) o digitando il percorso del file.
      * **Utilizzo degli attributi**: puoi definire gli attributi della condizione negli argomenti DITA. Quindi, seleziona l’attributo della condizione per pubblicare il contenuto pertinente.

     >[!NOTE]
     > 
     >Le condizioni sono abilitate solo se gli attributi della condizione sono definiti nell&#39;argomento.


   * Seleziona la **Sovrascrivi contenuto esistente** Se il frammento di esperienza esiste già e desideri sovrascriverlo, seleziona la casella di controllo. Experience Manager di Guide: se non selezioni la casella di controllo e il frammento di esperienza esiste già, viene visualizzato un errore.
1. Clic **Genera** per pubblicare il frammento di esperienza.
1. Puoi visualizzare i Frammenti di esperienza per un argomento nella sezione **Uscite** sezione nella sezione **Proprietà file**. I Frammenti esperienza vengono visualizzati in base alla data e all’ora di pubblicazione, il più recente dei quali è il primo.

   ![Visualizzare i frammenti esperienza per un argomento](images/experience-fragment-outputs.png){width=300 align=&quot;left&quot;}

   *Visualizza i Frammenti esperienza presenti in un argomento e ripubblicali.*




Dopo aver pubblicato i frammenti esperienza, puoi utilizzarli su qualsiasi sito Adobe Experience Manager.


## Menu Opzioni per un frammento esperienza

Per un frammento di esperienza puoi anche eseguire le seguenti azioni dalla sezione **Opzioni** menu:

* **Genera**: ripubblica il frammento di esperienza per aggiornarlo con il contenuto più recente dell’argomento DITA. Quando rigeneri l’output, non puoi modificare il percorso, il nome, il titolo e il modello del frammento di esperienza. Tuttavia, potete selezionare condizioni diverse durante la rigenerazione dell&#39;output.

* **Duplica**: duplica un frammento di esperienza. Puoi modificare il percorso, il nome, il titolo e il modello. Puoi anche selezionare condizioni diverse quando duplichi un frammento di esperienza.

* **Rimuovi**: rimuovi un frammento di esperienza dall’elenco degli output. Viene visualizzata una richiesta di conferma. Una volta confermata, il frammento di esperienza viene rimosso da **Uscite** elenco. Tuttavia, il frammento di esperienza non viene eliminato dalla cartella.

* **Visualizza**: visualizza l’editor del frammento di esperienza. Puoi anche apportare modifiche e salvarle.


