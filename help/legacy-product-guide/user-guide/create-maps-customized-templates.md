---
title: Creare mappe in base a modelli personalizzati
description: Scopri come creare un modello personalizzato, utilizzarlo per creare nuovi file di mappa e passare il titolo definito a una mappa DITA in AEM Guides.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 0f86ac98-7ba4-4e15-8a1f-83456afa7570
source-git-commit: 4801f0d327b4bd0641aa195d39ec2c4be2a2ce74
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 0%

---

# Creare mappe in base a modelli personalizzati {#id225VF0808MP}

È possibile creare modelli di mappa personalizzati e utilizzarli per creare mappe DITA insieme ai modelli di argomento e ai modelli di mappa a cui si fa riferimento nel modello di mappa

Puoi fare riferimento ad altri modelli di mappa e modelli di argomento dal modello di mappa personalizzato. I modelli di mappa indicati possono fare riferimento a vari modelli di mappa, modelli di argomento, argomenti, mappe, immagini, video e altre risorse. Il modello di mappa personalizzato può aiutarti a replicare molto facilmente i modelli di mappa e l’intera struttura di cartelle a cui si fa riferimento. Questi modelli personalizzati sono particolarmente utili per creare e ricreare più mappe che hanno strutture e riferimenti ricorsivi.

>[!NOTE]
>
> I modelli di argomento non vengono creati ricorsivamente. Vengono generati solo i modelli di argomento che si trovano direttamente all&#39;interno del modello di mappa e qualsiasi modello di argomento all&#39;interno di un modello di argomento viene semplicemente indicato direttamente nell&#39;elemento padre.

## Creare modelli personalizzati

AEM Guides consente di creare mappe e argomenti personalizzati dalla cartella modelli dita. Puoi utilizzare questi modelli personalizzati per creare la mappa e l’argomento. Puoi anche condividere questi modelli con gli autori, che possono utilizzarli per creare i loro file. Utilizzando questi modelli, puoi consentire agli autori di conservare copie separate di determinate risorse all’interno della cartella dei modelli.

>[!NOTE]
>
> Tutte le risorse a cui fare riferimento e che devono essere mantenute in devono essere mantenute all’esterno della cartella dei modelli.


È possibile creare modelli di mappe e argomenti nei modi seguenti:
1. Riquadro Modelli del [pannello sinistro](./web-editor-features.md#left-panel-id2051ea0m0hs)
1. [Modelli nell’interfaccia utente di Assets](#templates-assets-ui)
1. [Menu Opzioni](#templates-in-assets-ui)

### Modelli nell’interfaccia utente di Assets {#templates-assets-ui}

**Modello argomento**

Per creare un modello di argomento, effettuare le seguenti operazioni:

1. Nell&#39;**interfaccia utente di Assets**, passare alla cartella dei modelli dita.

   ![](images/dita-templates.png){width="800" align="left"}

1. Fare clic sulla cartella **topic** per aprirla.Fare clic su **Crea \> Modello DITA**.
1. Nella pagina Blueprint, seleziona **Argomento**, quindi fai clic su **Avanti.**
1. Nella pagina Proprietà, specifica il modello di argomento **Titolo**.
1. Specifica il file **Name**

   >[!NOTE]
   >
   > Il nome del file deve avere l&#39;estensione .dita.

1. \(Facoltativo\) Aggiungere una descrizione.
1. Fai clic su **Crea**. Viene visualizzato il messaggio di creazione del modello di argomento. È quindi possibile aprire il modello di argomento e modificarlo.

**Modello mappa**

Per creare un modello di mappa, effettua le seguenti operazioni:

1. Nell&#39;**interfaccia utente di Assets**, passare alla cartella dei modelli dita.
1. Fai clic sulla cartella **map** per aprirla.
1. Fare clic su **Crea \> Modello DITA.**

   ![](images/create-dita-template.png){width="300" align="left"}

1. Nella pagina Blueprint, seleziona **Mappa** e fai clic su **Successivo**.
1. Nella pagina Proprietà, specifica il modello di mappa **Titolo**.
1. Specificare il file **Name**.

   >[!NOTE]
   >
   > Il nome del file deve avere l&#39;estensione .ditamap.

1. (Facoltativo\) Aggiungi una descrizione. Fai clic su **Crea**. Viene visualizzato il messaggio di creazione del modello di mappa. È quindi possibile aprire il modello di mappa e modificarlo. Puoi aggiungere i riferimenti per i modelli di argomento, i modelli di mappa e anche altre risorse nel modello di mappa.

### Menu Opzioni {#options-menu}

Per creare una mappa o un modello di argomento, effettuare le seguenti operazioni:

1. Selezionare la cartella **Mappa** o **Argomento** nella cartella dei modelli corrente. Ad esempio, la cartella `dita-templates`.
1. Dal menu **Opzioni**, selezionare **Crea modello mappa** o **Crea modello argomento**.

   Viene visualizzata la finestra di dialogo **Crea nuovo modello mappa** o **Crea nuovo modello argomento**.
1. Immetti il titolo e il nome del nuovo modello.
1. Scegliere il tipo di modello da creare dall&#39;elenco a discesa **Modello**.

Viene visualizzato il messaggio di creazione del modello di mappa. Puoi aggiungere il modello al tuo profilo globale o a livello di cartella. Il nuovo modello viene quindi visualizzato nel processo di creazione di argomenti o mappe e può essere utilizzato per creare mappe o argomenti.


L’amministratore può anche creare una cartella e configurarla come la cartella in cui puoi creare e salvare i modelli.

In base alla configurazione, scopri come configurare il percorso della cartella del modello DITA personalizzato:
<details>
    <summary> Servizi cloud </summary>

Scopri come [configurare il percorso della cartella dei modelli DITA personalizzati](/help/product-guide/install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) nella Guida all&#39;installazione e alla configurazione di Cloud Services.
</details>

<details>
    <summary> Software on-premise</summary>

Scopri come [configurare il percorso della cartella del modello DITA personalizzato](/help/product-guide/cs-install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) nella Guida all&#39;installazione e alla configurazione on-premise.
</details>

## Trasmettere il titolo definito nei modelli

Se si desidera passare il titolo dell&#39;argomento o della mappa utilizzata all&#39;interno del modello alle mappe DITA create utilizzando tale modello, utilizzare parentesi graffe intorno al titolo.

Esempio

```XML
<pubtitle>
   <mainpubtitle outputclass="booktitle">
   {title}
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>

The resultant DITA map with title "Rootmap1" will look like as follows:
<pubtitle>
   <mainpubtitle outputclass="booktitle">Rootmap1
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>
```

>[!NOTE]
> Solo la prima occorrenza della parentesi graffa verrà sostituita con il titolo.

Se non si utilizzano parentesi graffe attorno al titolo, la mappa DITA risultante verrà selezionata solo per il primo elemento e la nidificazione del titolo non verrà selezionata dal modello e avrà il seguente aspetto:

```XML
<pubtitle> Rootmap1 </pubtitle>
```

>[!NOTE]
> È inoltre possibile utilizzare le parentesi graffe intorno al testo per passare la struttura nidificata dai modelli personalizzati alle mappe DITA.

Esempio

```XML
<title>    
    <sub>        
        <b>{title}</b>    
    </sub>
</title>
```




## Utilizza il modello di mappa per creare nuove mappe

>[!NOTE]
>
> Il modello di mappa deve essere configurato dall’amministratore e reso disponibile per l’authoring. Per ulteriori dettagli, vedi *Configurare i modelli di authoring* nella sezione Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

Per creare una mappa utilizzando il modello di mappa personalizzato, effettua le seguenti operazioni:

1. Nell&#39;interfaccia utente di **Assets,** passa alla cartella in cui desideri creare la mappa.
1. Fare clic su **Crea \> Mappa DITA**.
1. Nella pagina Blueprint, seleziona il modello di mappa che desideri utilizzare e fai clic su **Avanti**. Ad esempio, se hai creato un modello di mappa &quot;test-template&quot;, selezionalo.
1. Nella pagina Proprietà, specifica la mappa **Titolo**.
1. Specificare il file **Name**.

   >[!NOTE]
   >
   > Il nome del file deve avere l&#39;estensione .ditamap.

1. Fai clic su **Crea**. Viene visualizzato il messaggio Mappa creata.


La mappa genera tutte le risorse a cui si fa riferimento all’interno della cartella dei modelli. Alcuni tipi di risorse a cui si fa riferimento in una mappa possono essere i seguenti:

- Se la mappa contiene il riferimento a un modello di argomento, ne viene creata una copia all&#39;interno della cartella, nella stessa gerarchia della cartella topic nella cartella `dita-templates`.
- Se la mappa contiene il riferimento a un modello di mappa, ne viene creata una copia all&#39;interno della cartella, nella stessa gerarchia della cartella delle mappe nella cartella `dita-templates`.
- Se la mappa contiene il riferimento generico a un argomento o a una mappa all&#39;esterno della cartella `dita-templates/topics` o `dita-templates/maps`, viene fatto riferimento allo stesso solo e non viene creata alcuna copia.

  >[!NOTE]
  >
  > `dita-templates/topics` e `dita-templates/maps` sono i percorsi predefiniti nelle Guide e sono configurabili.


  Se all’interno del modello mappa è presente una definizione di chiave del modello argomento, viene creata una nuova chiave \(quindi nuovo argomento\) a cui viene fatto riferimento nella mappa.

- Se nella cartella viene creato un altro argomento o mappa allo stesso livello, i nomi delle nuove risorse vengono aggiunti 0, 1, 2 e così via. È possibile scegliere di aprire la mappa per la modifica o salvare il file di mappa nel repository.

**Argomento padre:**&#x200B;[ Utilizzare l&#39;editor mappe](map-editor.md)
