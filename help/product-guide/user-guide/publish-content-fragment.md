---
title: Pubblicare un argomento in un frammento di contenuto
description: Pubblicare un argomento o gli elementi di un argomento in un frammento di contenuto nelle guide AEM.  Scopri come visualizzare i frammenti di contenuto presenti in un argomento e ripubblicarli.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 0%

---

# Pubblicare in un frammento di contenuto

I frammenti di contenuto sono parti discrete di contenuto nell’AEM. Sono contenuti strutturati basati su un modello di contenuto. I frammenti di contenuto sono contenuti puri senza informazioni di progettazione o layout. Possono essere creati e gestiti indipendentemente dai canali supportati dall’AEM. I frammenti di contenuto sono modulari, dove il contenuto viene suddiviso in componenti più piccoli.

Le guide AEM consentono di pubblicare un argomento o gli elementi all’interno di un argomento in un frammento di contenuto. Puoi creare una mappatura basata su JSON tra un argomento e un modello per frammenti di contenuto. Utilizza questa mappatura per pubblicare un argomento o gli elementi all’interno di un argomento in un frammento di contenuto. Puoi quindi utilizzare i frammenti di contenuto in qualsiasi sito AEM o estrarre i dettagli tramite API supportate dai frammenti di contenuto.


Per creare un frammento di contenuto, effettua le seguenti operazioni:

1. Creare un [modello per frammenti di contenuto](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=it) in AEM Assets.
1. Crea una cartella in cui salvare i frammenti di contenuto creati in base al modello per frammenti di contenuto. Ad esempio, &quot;stock-content-fragments&quot;.
1. Modifica le proprietà della cartella (ad esempio, &quot;stock-content-fragments&quot;) e aggiungi il percorso della cartella, che contiene il modello per frammenti di contenuto nella configurazione cloud.
Ad esempio, aggiungi `/conf/we-retail` nella configurazione cloud. Questa configurazione collega tutti i modelli per frammenti di contenuto alla cartella.\
   ![aggiungi dettagli di configurazione cloud nelle proprietà della cartella](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Aggiungi la configurazione cloud nelle proprietà della cartella per collegarla ai modelli di frammenti.*
1. Seleziona l’argomento da pubblicare nel **Vista archivio**.
1. Dalla sezione **Opzioni** menu, seleziona **Pubblica come** > **Frammento di contenuto**.
1. In **Pubblica come frammento di contenuto** , compila i seguenti dettagli:
   ![Aggiungi il modello di frammento e i dettagli della mappatura nella finestra di dialogo Pubblica come frammento di contenuto](images/content-fragment-publish.png){width="500" align="left"}
   *Aggiungi il percorso, il modello e i dettagli di mappatura per pubblicare un argomento o i relativi elementi come frammento di contenuto. Puoi sovrascrivere un frammento di contenuto esistente.*

   * **Percorso**: sfoglia e seleziona il percorso della cartella in cui desideri pubblicare il frammento di contenuto. Puoi anche selezionare un frammento di contenuto esistente e pubblicarlo.
   * **Titolo**: immetti il titolo del frammento di contenuto.
   * **Nome**: immetti il nome del frammento di contenuto.
   * **Modello**: seleziona il modello per frammenti di contenuto da utilizzare per creare il frammento di contenuto. I modelli vengono selezionati dalla cartella configurata nei servizi cloud.
   * **Mappatura**: seleziona una mappatura dal menu a discesa. Seleziona le mappature da *contentFragmentMapping.json* file.



     In base alla configurazione, l’amministratore può aggiungere le mappature nel *contentFragmentMapping.json* file.

     <details>
        <summary>Servizi cloud</summary>

     Ulteriori informazioni su come [creare una mappatura tra un argomento e un frammento di contenuto](../cs-install-guide/conf-content-fragment-mapping-cs.md) nella Guida all&#39;installazione e alla configurazione dei Cloud Service.
     </details>

     <details>
        <summary> Software on-premise</summary>

     Ulteriori informazioni su come [creare una mappatura tra un argomento e un frammento di contenuto](../install-guide/conf-content-fragment-mapping.md) nella Guida all’installazione e alla configurazione on-premise.

     </details>
   * Seleziona la **Sovrascrivere** casella di controllo se il frammento di contenuto esiste già e desideri sovrascriverlo. Le guide AEM visualizzano un errore se non selezioni la casella di controllo e il frammento di contenuto esiste già.
1. Clic **Crea** per pubblicare il frammento di contenuto.
1. Puoi visualizzare i frammenti di contenuto di un argomento nella sezione **Frammenti** sezione nella sezione **Proprietà file**.

   ![Visualizzare i frammenti di contenuto per un argomento](images/topic-content-fragments.png){width="300" align="left"}

   *Visualizza i frammenti di contenuto presenti in un argomento e ripubblicali.*

È inoltre possibile ripubblicare il frammento di contenuto per aggiornare il frammento di contenuto con il contenuto più recente dell’argomento DITA.



Dopo aver pubblicato i frammenti di contenuto, puoi utilizzarli in qualsiasi sito AEM.
