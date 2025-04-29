---
title: Gestire le attività di revisione mediante il dashboard Revisione
description: Gestisci le attività di revisione dal dashboard di revisione in AEM Guides. Scopri le azioni da eseguire nella scheda attività, contenuto e revisori e controlla lo stato di un’attività di revisione.
exl-id: 4fef5653-1c73-4b68-adf2-b24145555142
feature: Reviewing
role: User
source-git-commit: 717d300c6e879bad573f67e3eb91dd266ab203c6
workflow-type: tm+mt
source-wordcount: '1312'
ht-degree: 0%

---

# Gestire le attività di revisione mediante il dashboard Revisione {#id2056B0Y70X4}

Il flusso di lavoro di gestione delle revisioni può includere diverse attività. Ad esempio, è possibile aggiungere revisori per un particolare argomento o estendere la scadenza per una revisione. È inoltre possibile contrassegnare l&#39;attività di revisione come completata se si ritiene che tutte le parti interessate abbiano fornito il proprio feedback. Queste attività possono essere gestite utilizzando il dashboard Revisione.

Per accedere e utilizzare il dashboard Revisione, effettuare le seguenti operazioni:

>[!NOTE]
>
> Puoi gestire le attività di revisione solo per i progetti per i quali sei l’Autore \(o l’Iniziatore\). Anche se sei un revisore o un editore \(utente\), non potrai accedere ad alcuna delle attività del progetto.

1. Nella console **Progetti**, seleziona il progetto di revisione che desideri gestire.

   Viene visualizzato un pannello Progetto con sezioni delle attività.

   ![](images/review-management.png){align="left"}

1. Seleziona i tre punti nella sezione **Recensioni**.

   Viene visualizzato il dashboard Revisione. Nel dashboard sono elencate tutte le attività di revisione create.

   ![](images/review-dashboard.png){align="left"}

   Nel dashboard Revisione vengono visualizzati i dettagli relativi all&#39;attività di revisione, ad esempio il nome dell&#39;attività, l&#39;autore che ha avviato la revisione, la data di inizio della revisione, la data di scadenza, lo stato, il numero di nuovi commenti non accettati o rifiutati dall&#39;autore e il nome dei revisori. Le attività sono elencate in ordine di nuove attività rispetto alle attività meno recenti.

   >[!NOTE]
   >
   > Se si seleziona il collegamento Attività di revisione, viene aperto l&#39;argomento o il file di mappa inviato per la revisione.

1. Selezionare un&#39;attività di revisione.

   Nella barra degli strumenti sono visualizzate le opzioni Modifica proprietà e [Stato](#check-review-status-id199RF0A0UHS).

1. Se si seleziona **Modifica proprietà**, viene visualizzata la pagina Dettagli attività.

   Nella pagina Dettagli attività sono disponibili tre schede: Attività, Contenuto e Revisori. Nelle sezioni seguenti vengono illustrate le varie funzioni disponibili in ciascuna scheda.


## Scheda Attività

![](images/review-task-page.png){align="left"}

Nella scheda **Attività** è possibile eseguire le azioni seguenti:

- Modifica il titolo dell&#39;attività nel campo **Titolo**.
- Aggiungi gli assegnatari predefiniti nell&#39;elenco a discesa **Assegna a**. I revisori che aggiungi da qui potranno esaminare tutti gli argomenti che fanno parte di questa attività di revisione. Puoi scegliere di rimuovere o aggiungere selettivamente altri revisori ad argomenti specifici dalla [scheda Revisori](#reviewer-tab-id199RF0N0MUI).
- Aggiorna la descrizione dell&#39;attività nel campo **Descrizione**.
- Modifica la **data di scadenza**. Puoi posticipare o posticipare la scadenza per il completamento dell’attività.
- Selezionare l&#39;opzione per consentire agli utenti di esaminare solo gli argomenti ad essi assegnati.
- Seleziona **Aggiorna** per aggiornare i dettagli modificati.

  Viene visualizzato un messaggio per confermare se l’aggiornamento è riuscito o meno.
- Seleziona **Completa** per contrassegnare l&#39;attività di revisione come completata prima della data di scadenza. Quando l&#39;attività di un singolo argomento viene contrassegnata come Completa, la revisione dell&#39;argomento selezionato viene chiusa. Tuttavia, nel caso di argomenti condivisi per la revisione tramite una mappa DITA, contrassegnando l&#39;attività Mappa DITA come Completa verrà chiusa la revisione di tutti gli argomenti della mappa condivisi per la revisione.
- Seleziona **Duplica** per creare una copia dell&#39;attività di revisione. Il processo di creazione di un&#39;attività di revisione duplicata è simile a quello di creazione di una nuova attività di revisione. Dopo aver avviato il flusso di lavoro dell&#39;attività duplicata, viene visualizzata la pagina Crea attività di revisione. Devi fornire i dettagli della nuova attività come spiegato in [Invia argomenti per la revisione](review-send-topics-for-review.md#).

  Se è stata selezionata un&#39;attività di revisione creata da una mappa DITA, vengono visualizzati gli argomenti che costituiscono un pert della mappa. È quindi possibile scegliere gli argomenti che si desidera includere nella nuova attività di revisione.

  In caso di attività di revisione duplicata da uno o più argomenti di revisione, nell&#39;elenco delle attività di revisione vengono visualizzati solo tali argomenti. Puoi scegliere di condividere questi argomenti per la revisione con un diverso gruppo di revisori.

- Seleziona **Chiudi** per passare alla pagina Posta in arrivo.

## Scheda Contenuto

![](images/review-content-page.png){align="left"}

Puoi eseguire le azioni seguenti nella scheda **Contenuto**:

- Modifica la versione dell’argomento inviato per la revisione. È possibile scegliere la versione più recente dell&#39;argomento, la versione in data, la versione con etichetta specifica o la versione con una baseline specifica \(per una mappa DITA\).

- Selezionare **Aggiorna** per condividere la versione aggiornata dell&#39;argomento con i revisori. I revisori ricevono una notifica e-mail che indica che la versione più recente dell’argomento è stata inviata per la revisione. La volta successiva che un revisore apre l&#39;argomento, visualizza la versione aggiornata dell&#39;argomento.

  >[!NOTE]
  >
  > In caso di versione aggiornata di un argomento, i vecchi commenti vengono mantenuti anche nella versione più recente. I revisori possono anche visualizzare le differenze tra le due versioni.

- Seleziona **Completa** per contrassegnare l&#39;attività di revisione come completata prima della data di scadenza. Quando l&#39;attività di un singolo argomento viene contrassegnata come Completa, la revisione dell&#39;argomento selezionato viene chiusa. Tuttavia, nel caso di argomenti condivisi per la revisione tramite una mappa DITA, contrassegnando l&#39;attività Mappa DITA come Completa verrà chiusa la revisione di tutti gli argomenti della mappa condivisi per la revisione.

- Seleziona **Duplica** per creare una nuova attività di revisione utilizzando l&#39;attività corrente come base.


## Scheda Revisori {#reviewer-tab-id199RF0N0MUI}

![](images/reviewers-tab.png){align="left"}

Puoi eseguire le seguenti azioni nella scheda **Revisori**:

- **Seleziona tutto**: seleziona tutti gli argomenti nell&#39;elenco degli argomenti. È possibile eseguire facilmente un&#39;operazione batch dopo aver selezionato tutti gli argomenti.
- **Cancella selezione**: deseleziona gli argomenti selezionati nell&#39;elenco.

  >[!NOTE]
  >
  > È inoltre possibile selezionare o deselezionare singolarmente un argomento selezionando la casella di controllo accanto all&#39;argomento.

- **Aggiungi**: visualizza la finestra Aggiungi revisori. È possibile digitare il nome del ruolo di revisore o utente \(o gruppo\) che si desidera aggiungere come revisore agli argomenti selezionati.
- **Rimuovi**: visualizza la finestra di dialogo Rimuovi revisori. È possibile digitare il nome di un revisore o di un ruolo utente \(o gruppo\) che si desidera rimuovere come revisore dagli argomenti selezionati.
- **Riassegna**: visualizza la finestra di dialogo Riassegna revisori. È possibile digitare il nome di un revisore o di un ruolo utente \(o gruppo\) a cui si desidera assegnare l&#39;attività di revisione. In questo modo tutti i revisori esistenti verranno rimossi dagli argomenti selezionati e i revisori appena selezionati verranno assegnati a tali argomenti.
- **Esporta**: consente di esportare i dettagli dell&#39;attività di revisione in un file CSV. Il file contiene dettagli quali il percorso e il titolo dell&#39;argomento, il nome del revisore e la versione degli argomenti inviati per la revisione.
- **Modifica revisori**: se si seleziona l&#39;icona ![](images/edit_pencil_icon.svg) nell&#39;elenco degli argomenti, viene visualizzata la finestra di dialogo Modifica revisori. Da questa finestra di dialogo è possibile aggiungere o rimuovere revisori per l&#39;argomento selezionato.

## Controllare lo stato di un&#39;attività di revisione {#check-review-status-id199RF0A0UHS}

Dalla pagina principale del dashboard di revisione, se si seleziona un&#39;attività di revisione e si sceglie **Stato**, viene visualizzato il rapporto sullo stato dell&#39;attività di revisione.

![](images/review-status-report.png){align="left"}

La relazione sullo stato dell&#39;attività di revisione contiene i dettagli riportati di seguito.

- Nome\(s\) del revisore a cui è assegnata l&#39;attività di revisione.
- La colonna Stato indica lo stato della revisione. Lo stato potrebbe essere uno dei seguenti:
   - **Non avviato**: il revisore non ha ancora aperto il collegamento di revisione.
   - **In corso**: il revisore ha aperto il collegamento di revisione e sta esaminando l&#39;argomento.
   - **Completo**: il revisore ha completato la revisione completando l&#39;attività di revisione ad esso assegnata. L’attività di revisione si trova nella casella in entrata delle notifiche di AEM per ogni revisore.
- Quando un revisore apre un collegamento di revisione e passa a un particolare argomento, tale argomento viene aggiunto all&#39;elenco Argomenti esaminati. In questo modo gli autori possono determinare se i revisori hanno aperto le rispettive sezioni o meno. Eventuali commenti sono riportati tra parentesi.
- Numero totale di commenti su tutti gli argomenti. In caso di più argomenti in revisione, il numero di commenti per ciascun argomento è indicato \(tra parentesi\) rispetto al nome dell’argomento.
- Data dell&#39;ultimo accesso a un argomento da parte del revisore.

**Argomento padre:**[ Introduzione alla revisione](review.md)
