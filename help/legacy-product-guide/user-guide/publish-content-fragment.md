---
title: Publish di un argomento in un frammento di contenuto
description: Publish di un argomento o degli elementi all’interno di un argomento in un frammento di contenuto in AEM Guides.  Scopri come visualizzare i Frammenti di contenuto presenti in un argomento e ripubblicarli.
feature: Publishing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 0%

---

# Frammenti di contenuto Publish

I frammenti di contenuto sono parti discrete di contenuto in Adobe Experience Manager. Sono contenuti strutturati basati su un modello di contenuto. I frammenti di contenuto sono contenuti puri senza informazioni di progettazione o layout. Possono essere creati e gestiti indipendentemente dai canali supportati da Adobe Experience Manager. I frammenti di contenuto sono modulari, dove il contenuto viene suddiviso in componenti più piccoli.

Adobe Experience Manager Guides consente di pubblicare un argomento o gli elementi all’interno di un argomento in un frammento di contenuto. Puoi creare una mappatura basata su JSON tra un argomento e un modello per frammenti di contenuto. Utilizzare questa mappatura per pubblicare un argomento o gli elementi di un argomento in un frammento di contenuto. Puoi quindi utilizzare i frammenti di contenuto in qualsiasi sito Adobe Experience Manager o estrarre i dettagli tramite API supportate dai frammenti di contenuto.


Per creare un frammento di contenuto, effettua le seguenti operazioni:

1. Crea un [modello per frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=it) in Adobe Experience Manager Assets.
1. Crea una cartella in cui salvare i frammenti di contenuto creati in base al modello Frammento di contenuto. Ad esempio, &quot;stock-content-fragments&quot;.
1. Modifica le proprietà della cartella (ad esempio, &quot;stock-content-fragments&quot;) e aggiungi il percorso della cartella, che contiene il modello Frammento di contenuto nella configurazione cloud.
Aggiungere ad esempio `/conf/we-retail` nella configurazione cloud. Questa configurazione collega tutti i modelli per frammenti di contenuto alla cartella.\
   ![aggiungi dettagli configurazione cloud nelle proprietà della cartella](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Aggiungi la configurazione cloud nelle proprietà della cartella per collegarla ai modelli di frammenti.*

1. Per generare un frammento di contenuto, selezionare **Nuovo output** ![nuova icona output](./images/Add_icon.svg) dalla sezione **Output** nelle **Proprietà file** di un argomento.
1. Seleziona **Frammento di contenuto**.\
   ![scheda opzioni proprietà file](./images/file-properties-outputs-tab.png){width="300" align="left"}

   *Aggiungere un nuovo frammento di contenuto dalle proprietà del file di un argomento*.

1. Nella finestra di dialogo **Genera frammento di contenuto**, compila i seguenti dettagli:
   ![Aggiungere il modello di frammento e i dettagli di mappatura nella finestra di dialogo Publish come frammento di contenuto](images/content-fragment-publish.png){width="500" align="left"}
   *Aggiungere il percorso, il modello e i dettagli di mappatura per pubblicare un argomento o i relativi elementi come frammento di contenuto. È possibile sovrascrivere un frammento di contenuto esistente.*

   >[!NOTE]
   >
   >È inoltre possibile pubblicare un frammento di contenuto dalla **vista archivio**. Seleziona l’argomento da pubblicare come Frammento di contenuto. Dal menu **Opzioni**, selezionare **Publish As** > **Frammento di contenuto**.

   * **Percorso**: sfoglia e seleziona il percorso della cartella in cui desideri pubblicare il frammento di contenuto. Se selezioni un frammento di contenuto esistente, questo sovrascrive il contenuto dei campi mappati.
   * **Titolo**: digita il titolo del frammento di contenuto. Per impostazione predefinita, il titolo viene compilato con il titolo dell’argomento. Puoi modificarlo. Questo titolo viene utilizzato per generare il nome del frammento di contenuto.
   * **Nome**: digitare il nome del frammento di contenuto. Per impostazione predefinita, il nome viene compilato con il titolo dell&#39;argomento e gli spazi vengono sostituiti con &quot;_&quot;. Ad esempio, *sample_content_fragment*. Puoi modificarlo.  Questo nome viene utilizzato per generare l’URL per il frammento di contenuto.
   * **Modello**: seleziona il modello per frammenti di contenuto da utilizzare per creare il frammento di contenuto. I modelli vengono prelevati dalla cartella, che hai configurato nei servizi cloud.
   * **Mapping**: seleziona un mapping dal menu a discesa. Seleziona le mappature dal file *contentFragmentMapping.json*.



     L&#39;amministratore può aggiungere le mappature nel file *contentFragmentMapping.json*. Ulteriori informazioni su come [creare una mappatura tra un argomento e un frammento di contenuto](/help/product-guide/cs-install-guide/conf-content-fragment-mapping-cs.md) nella Guida all&#39;installazione e alla configurazione.

   * Puoi anche selezionare condizioni diverse per pubblicare il contenuto.  Selezionare una delle opzioni seguenti:


      * **Nessuno**: seleziona questa opzione se non desideri applicare alcuna condizione all&#39;output pubblicato.
      * **Utilizzo di DITAVAL**: selezionare il file DITAVAL per generare l&#39;output, che include contenuto specifico. Potete selezionare il file DITAVAL utilizzando la finestra di dialogo Sfoglia (Browse) o digitando il percorso del file.
      * **Utilizzo di attributi**: è possibile definire attributi di condizione negli argomenti DITA. Quindi, seleziona l’attributo della condizione per pubblicare il contenuto pertinente.
     >[!NOTE]
     > 
     >Le condizioni sono abilitate solo se gli attributi della condizione sono definiti nell&#39;argomento.



   * Selezionare **Sovrascrivi contenuto esistente** se il frammento di contenuto esiste già e si desidera sovrascriverlo. Se non selezioni la casella di controllo e il frammento di contenuto esiste già, Experience Manager Guides visualizza un errore.
1. Fai clic su **Genera** per pubblicare il frammento di contenuto.

1. Puoi visualizzare i Frammenti di contenuto per un argomento nella sezione **Output** delle **Proprietà file**.

   ![Visualizza i frammenti di contenuto per un argomento](images/outputs-options-menu.png){width="300" align="left"}

   *Visualizza i frammenti di contenuto presenti in un argomento e ripubblicali.*


Dopo aver pubblicato i frammenti di contenuto, puoi utilizzarli in qualsiasi sito Adobe Experience Manager.




## Menu Opzioni per un frammento di contenuto

Per un frammento di contenuto è inoltre possibile eseguire le azioni seguenti dal menu **Opzioni**:

* **Genera**: ripubblica il frammento di contenuto per aggiornarlo con il contenuto più recente dell&#39;argomento DITA. Quando rigeneri l’output, non puoi modificare il percorso, il nome, il titolo, il modello e la mappatura del frammento di contenuto. Tuttavia, potete selezionare condizioni diverse durante la rigenerazione dell&#39;output.

* **Duplicato**: duplicare un frammento di contenuto. È possibile modificare il percorso, il nome, il titolo, il modello e la mappatura. Puoi anche selezionare condizioni diverse quando duplichi un frammento di contenuto.

* **Rimuovi**: rimuovi un frammento di contenuto dall&#39;elenco degli output. Viene visualizzata una richiesta di conferma. Dopo la conferma, il frammento di contenuto viene rimosso dall&#39;elenco **Output**.

  >[!NOTE]
  >
  > Con questa azione nessun contenuto viene eliminato dal frammento di contenuto.

* **Visualizza**: visualizza l&#39;editor frammenti di contenuto. Puoi anche apportare modifiche e salvarle.


