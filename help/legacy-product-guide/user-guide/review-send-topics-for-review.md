---
title: Invia argomenti per la revisione
description: Scopri come creare un’attività di revisione e inviare argomenti per la revisione in AEM Guides. Inviare uno o più argomenti in una mappa DITA per la revisione.
feature: Reviewing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '2752'
ht-degree: 0%

---

# Invia argomenti per la revisione {#id199RD0S035Z}

Il flusso di lavoro di revisione crea un ambiente con più revisori in cui l&#39;iniziatore specifica un elenco di argomenti per la revisione, aggiunge più revisori e assegna una sequenza temporale all&#39;attività di revisione. AEM Guides consente agli utenti appartenenti ai gruppi Author e Publishers di avviare una revisione.

Poiché il flusso di lavoro di revisione è specifico per il progetto, l&#39;iniziatore della revisione deve far parte del team del progetto o disporre dei diritti per creare un progetto. Al momento della creazione di un progetto, puoi definire i membri del team per il progetto e assegnare loro vari ruoli o gruppi. Per ulteriori informazioni sui progetti, vedere [Creare un progetto DITA](authoring-create-dita-project.md#).

Puoi creare un’attività di revisione da:

- **Editor Web**: consente di inviare un singolo argomento o una mappa DITA per la revisione. Il flusso di lavoro per la creazione di un’attività di revisione è comune nell’editor web e nell’interfaccia utente di Assets. Solo il metodo di avvio del flusso di lavoro di revisione è diverso. Per informazioni sull&#39;avvio del flusso di lavoro di revisione dall&#39;editor Web, vedere la funzionalità [Crea attività di revisione](web-editor-features.md#id215OCJ00JXA) nell&#39;editor Web.

- **Interfaccia utente di Assets**: consente di inviare uno o più argomenti e mappa DITA per la revisione. La condivisione di documenti da rivedere dal flusso di lavoro dell’interfaccia utente di Assets è trattata in questo argomento.


Nell’interfaccia utente di Assets, un autore/editore può creare un’attività di revisione in due modi:

- Invia uno o più argomenti per la revisione
- Inviare più argomenti da una mappa DITA per la revisione

## Invia uno o più argomenti per la revisione {#id1721E600FY4}

>[!IMPORTANT]
>
> Prima di creare un&#39;attività di revisione, verificare di aver creato un progetto e di aver aggiunto i revisori al progetto.

Per creare un&#39;attività di revisione e inviare gli argomenti per la revisione, effettuare le seguenti operazioni:

>[!NOTE]
>
> È possibile creare un&#39;attività di revisione solo se si è un autore o un editore in un progetto DITA.

1. Passa alla cartella desiderata nell’interfaccia utente di Assets.

1. Fai clic sull’icona Seleziona nell’azione rapida e seleziona gli argomenti da inviare per la revisione.

   ![](images/select-asset-62.png){width="300" align="left"}

1. Nella barra degli strumenti, fai clic su **Crea attività di revisione**. Viene visualizzata la pagina di creazione dell’attività di revisione.

   >[!NOTE]
   >
   > È possibile creare un&#39;attività di revisione solo per gli argomenti con una revisione. Se l’argomento selezionato non ha una revisione, verrà visualizzato un messaggio di richiesta.

   ![](images/create-review-task-023.png){width="650" align="left"}

1. Immetti un **Titolo** per l&#39;attività e seleziona un **Progetto** DITA dall&#39;elenco a discesa.

1. Nel campo a discesa **Assegna a**, selezionare i revisori a cui si desidera inviare gli argomenti per la revisione.

   È possibile assegnare un&#39;attività di revisione a singoli utenti del progetto o a gruppi di utenti. Si noti che è possibile assegnare un&#39;attività di revisione a singoli utenti solo quando si fa parte del gruppo di amministratori del progetto, altrimenti i gruppi di utenti verranno visualizzati solo nel campo Assegna a.

   >[!NOTE]
   >
   > Il flusso di lavoro di revisione è specifico per il progetto. Quando si creano dei progetti, si aggiungono al progetto i membri del team e li si assegnano ai gruppi. Quindi quando selezioni il progetto qui, puoi scegliere i membri che fanno parte di quel progetto. Per ulteriori informazioni sui progetti, vedere [Creare un progetto DITA](authoring-create-dita-project.md#).

1. Immetti una **Descrizione** per l&#39;attività.

   Questa descrizione viene utilizzata come corpo dell’e-mail di notifica inviata ai revisori.

1. Seleziona **Data di scadenza** e l&#39;ora per contrassegnare la scadenza per la revisione.

   >[!NOTE]
   >
   > Una volta raggiunta la scadenza, viene inviata un’e-mail all’iniziatore per informare che l’attività di revisione è stata completata. L&#39;iniziatore può estendere la scadenza dell&#39;attività di revisione dal [dashboard di revisione](review-manage-tasks-review-dashboard.md#).

1. Selezionare la mappa radice dal **percorso rootmap**. Questa rootmap viene utilizzata per risolvere tutti i riferimenti chiave e i termini del glossario utilizzati nel contenuto della revisione. Se non si seleziona la rootmap, i riferimenti chiave o i termini del glossario associati all&#39;argomento DITA non vengono risolti prima di inviare l&#39;argomento per la revisione.

   Se si sta creando la revisione per una mappa DITA, per impostazione predefinita **Percorso rootmap** è impostato sul percorso della mappa. Se si sta creando la revisione per uno o più argomenti, per impostazione predefinita il percorso **Rootmap** viene impostato sulla mappa definita nelle Preferenze utente.

   >[!NOTE]
   >
   > La mappa principale selezionata ha la precedenza più alta per risolvere i riferimenti chiave. Per ulteriori dettagli, vedere [Risolvere i riferimenti chiave](map-editor-other-features.md#id176GD01H05Z).

1. Poiché è possibile assegnare revisori diversi ad argomenti diversi, l&#39;opzione **Consenti agli assegnatari di esaminare qualsiasi argomento** controlla se i revisori possono esaminare tutti gli argomenti di un&#39;attività di revisione o solo quelli che sono stati assegnati a esaminare.

   Se si desidera consentire a tutti i revisori di esaminare qualsiasi argomento nell&#39;attività di revisione, selezionare **Consenti agli assegnatari di rivedere qualsiasi argomento**.

   Se non si seleziona questa opzione, i revisori aggiunti nel campo **Assegna a** potranno esaminare solo gli argomenti ad essi assegnati.

1. Fai clic su **Avanti**.

   Viene visualizzata la pagina Contenuto.

   ![](images/content_page_review.png){width="800" align="left"}

1. Nella pagina Contenuto selezionare una versione dell&#39;argomento che si desidera condividere per la revisione.

   Per selezionare una versione è possibile utilizzare uno dei metodi seguenti:

   - *\(Predefinito\)* Scegli l&#39;opzione **Versione più recente** per selezionare l&#39;ultima revisione salvata degli argomenti.
   - Scegli l&#39;opzione **Versione il** e specifica la data e l&#39;ora per selezionare una versione in base alla data e all&#39;ora specificate. Se non è disponibile alcuna versione dell&#39;argomento alla data specificata, viene selezionata una versione disponibile immediatamente dopo la data e l&#39;ora specificate.
   - Scegliere l&#39;opzione **Seleziona etichetta** e selezionare un&#39;etichetta dall&#39;elenco a discesa.
1. Dopo aver selezionato una versione, fare clic su **Applica**.

   Per gli argomenti viene scelta la versione basata sull&#39;opzione selezionata.

   >[!NOTE]
   >
   > Puoi anche selezionare manualmente la versione desiderata dall&#39;elenco a discesa **Versione** di ciascun argomento.

1. Fai clic su **Avanti**.

   Viene visualizzata la pagina Revisori in cui è possibile aggiungere o rimuovere revisori. Per impostazione predefinita, i revisori aggiunti nel campo Assegna a vengono aggiunti automaticamente a ogni argomento selezionato per la revisione.

   ![](images/add-reviewers-topics.png){width="650" align="left"}

1. Nella pagina Revisori è possibile aggiungere o rimuovere revisori. Nella pagina Revisori sono disponibili le operazioni riportate di seguito.

   - **Seleziona tutto**: seleziona tutti gli argomenti nell&#39;elenco degli argomenti. È possibile eseguire facilmente un&#39;operazione batch dopo aver selezionato tutti gli argomenti.
   - **Cancella selezione**: deseleziona gli argomenti selezionati nell&#39;elenco.

     >[!NOTE]
     >
     > È inoltre possibile selezionare o deselezionare singolarmente un argomento facendo clic sulla casella di spunta accanto all&#39;argomento.

   - **Aggiungi**: visualizza la finestra Aggiungi revisori. È possibile digitare il nome del ruolo di revisore o utente \(o gruppo\) che si desidera aggiungere come revisore agli argomenti selezionati.
   - **Rimuovi**: visualizza la finestra di dialogo Rimuovi revisori. È possibile digitare il nome di un revisore o di un ruolo utente \(o gruppo\) che si desidera rimuovere come revisore dagli argomenti selezionati.

     >[!NOTE]
     >
     > È inoltre possibile rimuovere una revisione da un argomento facendo clic sul segno incrociato nella casella del revisore.

   - **Riassegna**: visualizza la finestra di dialogo Riassegna revisori. È possibile digitare il nome di un revisore o di un ruolo utente \(o gruppo\) a cui si desidera assegnare l&#39;attività di revisione. In questo modo tutti i revisori esistenti verranno rimossi dagli argomenti selezionati e i revisori appena selezionati verranno assegnati a tali argomenti.
   - **Esporta**: consente di esportare i dettagli dell&#39;attività di revisione in un file CSV. Il file contiene dettagli quali il percorso e il titolo dell&#39;argomento, il nome del revisore e la versione degli argomenti inviati per la revisione.
   - **Modifica revisori**: facendo clic sull&#39;icona ![](images/edit_pencil_icon.svg) nell&#39;elenco degli argomenti viene visualizzata la finestra di dialogo Modifica revisori. Da questa finestra di dialogo è possibile aggiungere o rimuovere revisori per l&#39;argomento selezionato.
1. Fai clic su **Crea** per creare l&#39;attività di revisione.

   Quando l&#39;attività di revisione viene creata correttamente, viene visualizzato un messaggio di conferma. Il [stato documento](web-editor-document-states.md#) per gli argomenti inviati per la revisione è impostato su In revisione.

   >[!NOTE]
   >
   > Puoi anche fare clic sul campanello Notifiche in alto a destra dello schermo e verificare che l’attività di revisione sia stata creata correttamente. Nel pannello Notifiche troverai una notifica per ogni revisore che faceva parte dell’attività di revisione e una per l’iniziatore della revisione.


A tutti i revisori viene inviata un&#39;e-mail con la notifica dell&#39;assegnazione di uno o più argomenti da rivedere. L’e-mail contiene un collegamento diretto su cui è possibile fare clic per accedere all’argomento in una finestra del browser.

Se vengono assegnati più argomenti, i revisori possono visualizzarli e selezionarli in un elenco a discesa di argomenti nel browser Web.

## Invio di più argomenti per la revisione da una mappa DITA

Una mappa DITA è un&#39;organizzazione logica di argomenti all&#39;interno di un libro. Quando si invia un singolo argomento per la revisione, il revisore non riceve alcuna informazione sulla posizione dell&#39;argomento nel libro. Se un revisore dispone di informazioni sulla posizione esatta dell&#39;argomento in fase di revisione, il revisore ottiene un contesto migliore dell&#39;argomento in fase di revisione.

AEM Guides consente di inviare contemporaneamente uno o più argomenti in una mappa DITA per la revisione. Il revisore può visualizzare il file di mappa completo insieme agli argomenti condivisi per la revisione. In questo modo, il revisore può ottenere più facilmente un contesto dell&#39;argomento nel file di mappa o libro.

È possibile condividere la stessa mappa DITA in per la revisione in più attività di revisione. Ad esempio, se in una mappa DITA sono presenti gli argomenti A, B, C, D ed E. In un&#39;attività di revisione è possibile condividere A, B e C per la revisione e in un&#39;altra attività di revisione è possibile inviare gli argomenti C, D ed E per la revisione. Il processo di revisione consente di condividere lo stesso argomento e mappare il file in più attività di revisione. Per l&#39;argomento comune in più attività di revisione, i commenti forniti in un&#39;attività di revisione non vengono sovrascritti o uniti ai commenti delle altre attività di revisione.

>[!IMPORTANT]
>
> Se un argomento di un file mappa è stato condiviso in più attività di revisione, il relativo stato viene visualizzato In revisione fino al completamento di tutte le attività di revisione.

Per inviare uno o più argomenti insieme al file mappa per la revisione, effettuare le seguenti operazioni:

>[!IMPORTANT]
>
> Dopo aver avviato una revisione tramite un file di mappa, non è necessario modificare la struttura del file aggiungendo nuovi argomenti o rimuovendo argomenti esistenti.

1. Passa alla cartella desiderata nell’interfaccia utente di Assets.

   >[!NOTE]
   >
   > Assicurati che la visualizzazione della console sia impostata sulla vista a schede o su quella a elenco.

1. Selezionare la mappa da cui si desidera inviare gli argomenti per la revisione.

1. Nella barra degli strumenti, fai clic su **Crea attività di revisione**. Viene visualizzata la pagina di creazione dell’attività di revisione.

1. Immetti un **Titolo** per l&#39;attività e seleziona un **Progetto** DITA dall&#39;elenco a discesa.

   >[!NOTE]
   >
   > È possibile creare un&#39;attività di revisione solo per gli argomenti con una revisione. Se la mappa contiene argomenti che non hanno una revisione, viene visualizzato un messaggio con un elenco di tali file. I file senza una revisione sono esclusi dall’attività di revisione.

1. Nel campo a discesa **Assegna a**, selezionare i revisori a cui si desidera inviare gli argomenti per la revisione.

   È possibile assegnare un&#39;attività di revisione a singoli utenti del progetto o a gruppi di utenti. Si noti che è possibile assegnare un&#39;attività di revisione a singoli utenti solo quando si fa parte del gruppo di amministratori del progetto, altrimenti i gruppi di utenti verranno visualizzati solo nel campo Assegna a.

   >[!NOTE]
   >
   > Il flusso di lavoro di revisione è specifico per il progetto. Quando si creano dei progetti, si aggiungono al progetto i membri del team e li si assegnano ai gruppi. Quindi quando selezioni il progetto qui, puoi scegliere i membri che fanno parte di quel progetto. Per ulteriori informazioni sui progetti, vedere [Creare un progetto DITA](authoring-create-dita-project.md#).

1. Immetti una **Descrizione** per l&#39;attività.

   Questa descrizione viene utilizzata come corpo dell’e-mail di notifica inviata ai revisori.

1. Seleziona **Data di scadenza** e l&#39;ora per contrassegnare la scadenza per la revisione.

   >[!NOTE]
   >
   > Una volta raggiunta la scadenza, viene inviata un’e-mail all’iniziatore per informare che l’attività di revisione è stata completata. L&#39;iniziatore può estendere la scadenza dell&#39;attività di revisione dal [dashboard di revisione](review-manage-tasks-review-dashboard.md#).

1. Poiché è possibile assegnare revisori diversi ad argomenti diversi, l&#39;opzione **Consenti agli assegnatari di esaminare qualsiasi argomento** controlla se i revisori possono esaminare tutti gli argomenti di un&#39;attività di revisione o solo quelli che sono stati assegnati a esaminare.

   Se si desidera consentire a tutti i revisori di esaminare qualsiasi argomento nell&#39;attività di revisione, selezionare **Consenti agli assegnatari di rivedere qualsiasi argomento**.

   Se non si seleziona questa opzione, i revisori aggiunti nel campo **Assegna a** potranno esaminare solo gli argomenti ad essi assegnati.

1. Fai clic su **Avanti**.

   Viene visualizzata la pagina Contenuto con tutti gli argomenti a cui si fa riferimento dal file di mappa. Se la mappa DITA contiene mappe nidificate, vengono elencati anche gli argomenti delle mappe nidificate.

   ![](images/content-page-map-review.png){width="800" align="left"}

1. Nella pagina Contenuto selezionare una versione dell&#39;argomento che si desidera condividere per la revisione.

   Per selezionare una versione è possibile utilizzare uno dei metodi seguenti:

   - *\(Predefinito\)* Scegli l&#39;opzione **Versione più recente** per selezionare l&#39;ultima revisione salvata degli argomenti.
   - Scegli l&#39;opzione **Versione il** e specifica la data e l&#39;ora per selezionare una versione in base alla data e all&#39;ora. Se non è disponibile alcuna versione dell&#39;argomento alla data specificata, viene selezionata una versione disponibile immediatamente dopo la data e l&#39;ora specificate.
   - Scegliere l&#39;opzione **Seleziona etichetta** e selezionare un&#39;etichetta dall&#39;elenco a discesa. Tutti gli argomenti contenenti l&#39;etichetta selezionata sono selezionati nell&#39;elenco a discesa **Versione**.
   - Scegliere l&#39;opzione **Seleziona una previsione** e selezionare una previsione dall&#39;elenco a discesa. Tutte le versioni dell&#39;argomento che fanno parte della baseline selezionata sono selezionate nell&#39;elenco a discesa **Versione**.
1. Dopo aver selezionato una versione, fare clic su **Applica**.

   Per gli argomenti viene scelta la versione basata sull&#39;opzione selezionata.

   >[!NOTE]
   >
   > Puoi anche selezionare manualmente la versione desiderata dall&#39;elenco a discesa **Versione** di ciascun argomento.

1. Fai clic su **Avanti**.

   Viene visualizzata la pagina Revisori in cui è possibile aggiungere o rimuovere revisori. Per impostazione predefinita, i revisori aggiunti nel campo Assegna a vengono aggiunti automaticamente a ogni argomento selezionato per la revisione.

1. Nella pagina Revisori è possibile aggiungere o rimuovere revisori. Nella pagina Revisori sono disponibili le operazioni riportate di seguito.

   - **Seleziona tutto**: seleziona tutti gli argomenti nell&#39;elenco degli argomenti. È possibile eseguire facilmente un&#39;operazione batch dopo aver selezionato tutti gli argomenti.
   - **Cancella selezione**: deseleziona gli argomenti selezionati nell&#39;elenco.

     >[!NOTE]
     >
     > È inoltre possibile selezionare o deselezionare singolarmente un argomento facendo clic sulla casella di spunta accanto all&#39;argomento.

   - **Aggiungi**: visualizza la finestra Aggiungi revisori. È possibile digitare il nome del ruolo di revisore o utente \(o gruppo\) che si desidera aggiungere come revisore agli argomenti selezionati.
   - **Rimuovi**: visualizza la finestra di dialogo Rimuovi revisori. È possibile digitare il nome di un revisore o di un ruolo utente \(o gruppo\) che si desidera rimuovere come revisore dagli argomenti selezionati.
   - **Riassegna**: visualizza la finestra di dialogo Riassegna revisori. È possibile digitare il nome di un revisore o di un ruolo utente \(o gruppo\) a cui si desidera assegnare l&#39;attività di revisione. In questo modo tutti i revisori esistenti verranno rimossi dagli argomenti selezionati e i revisori appena selezionati verranno assegnati a tali argomenti.
   - **Esporta**: consente di esportare i dettagli dell&#39;attività di revisione in un file CSV. Il file contiene dettagli quali il percorso e il titolo dell&#39;argomento, il nome del revisore e la versione degli argomenti inviati per la revisione.
   - **Modifica revisori**: facendo clic sull&#39;icona ![](images/edit_pencil_icon.svg) nell&#39;elenco degli argomenti viene visualizzata la finestra di dialogo Modifica revisori. Da questa finestra di dialogo è possibile aggiungere o rimuovere revisori per l&#39;argomento selezionato.
   >[!IMPORTANT]
   >
   > È necessario assegnare almeno un revisore per creare l&#39;attività di revisione.

1. Fai clic su **Crea** per creare l&#39;attività di revisione.

   Quando l&#39;attività di revisione viene creata correttamente, viene visualizzato un messaggio di conferma. Il [stato documento](web-editor-document-states.md#) per gli argomenti inviati per la revisione è impostato su In revisione.

   >[!NOTE]
   >
   > Puoi anche fare clic sul pannello Notifiche in alto a destra nell’interfaccia e verificare che l’attività sia stata creata correttamente. Nel pannello Notifiche troverai una notifica per ciascuna revisione che faceva parte dell’attività di revisione e una notifica per l’iniziatore della revisione.

   >[!IMPORTANT]
   >
   > Dopo aver avviato una revisione, non è necessario spostare o eliminare la mappa DITA o gli argomenti in una posizione diversa. In questo modo il processo di revisione si interromperà.


A tutti i revisori viene inviata un’e-mail con la notifica dell’assegnazione degli argomenti da rivedere. L’e-mail contiene un collegamento diretto su cui è possibile fare clic per accedere all’argomento in una finestra del browser. Gli argomenti insieme alla mappa DITA vengono aperti in modalità di revisione.

**Argomento padre:**[ Rivedi argomenti o mappe](review.md)
