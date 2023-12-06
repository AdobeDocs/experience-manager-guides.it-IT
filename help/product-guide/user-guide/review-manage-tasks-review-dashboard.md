---
title: Gestire le attività di revisione mediante il dashboard Revisione
description: Gestisci le attività di revisione dal dashboard di revisione nelle guide AEM. Scopri le azioni da eseguire nella scheda attività, contenuto e revisori e controlla lo stato di un’attività di revisione.
exl-id: 4fef5653-1c73-4b68-adf2-b24145555142
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 0%

---

# Gestire le attività di revisione mediante il dashboard Revisione {#id2056B0Y70X4}

Il flusso di lavoro di gestione delle revisioni può includere diverse attività. Ad esempio, è possibile aggiungere revisori per un particolare argomento o estendere la scadenza per una revisione. È inoltre possibile contrassegnare l&#39;attività di revisione come completata se si ritiene che tutte le parti interessate abbiano fornito il proprio feedback. Queste attività possono essere gestite utilizzando il dashboard Revisione.

Per accedere e utilizzare il dashboard Revisione, effettuare le seguenti operazioni:

>[!NOTE]
>
> Puoi gestire le attività di revisione solo per i progetti per i quali sei l’Autore \(o l’Iniziatore\). Anche se sei un revisore o un editore \(utente\), non potrai accedere ad alcuna delle attività del progetto.

1. In **Progetti** fare clic sul progetto di revisione che si desidera gestire.

   Viene visualizzato un pannello Progetto con sezioni delle attività.

   ![](images/review-management.png){width="800" align="left"}

1. Fai clic sui tre punti in **Recensioni** affiancare.

   Viene visualizzato il dashboard Revisione. Nel dashboard sono elencate tutte le attività di revisione create.

   ![](images/review-dashboard.png){width="800" align="left"}

   Nel dashboard Revisione vengono visualizzati i dettagli relativi all&#39;attività di revisione, ad esempio il nome dell&#39;attività, l&#39;autore che ha avviato la revisione, la data di inizio della revisione, la data di scadenza, lo stato, il numero di nuovi commenti non accettati o rifiutati dall&#39;autore e il nome dei revisori. Le attività sono elencate in ordine di nuove attività rispetto alle attività meno recenti.

   >[!NOTE]
   >
   > Se si fa clic sul collegamento Attività di revisione, viene aperto l&#39;argomento o il file di mappa inviato per la revisione.

1. Selezionare un&#39;attività di revisione.

   Viene visualizzato Modifica proprietà e [Stato](#check-review-status-id199RF0A0UHS) nella barra degli strumenti.

1. Se si fa clic su **Modifica proprietà**, viene visualizzata la pagina Dettagli attività.

   Nella pagina Dettagli attività sono disponibili tre schede: Attività, Contenuto e Revisori. Nelle sezioni seguenti vengono illustrate le varie funzioni disponibili in ciascuna scheda.


## Scheda Attività

![](images/review-task-page.png){width="800" align="left"}

È possibile eseguire le azioni seguenti sotto **Attività** scheda:

- Modifica il titolo dell’attività in **Titolo** campo.
- Aggiungi assegnatari predefiniti nel **Assegna a** elenco a discesa. I revisori che aggiungi da qui potranno esaminare tutti gli argomenti che fanno parte di questa attività di revisione. Puoi scegliere di rimuovere o aggiungere selettivamente più revisori ad argomenti specifici da [Scheda Revisori](#reviewer-tab-id199RF0N0MUI).
- Aggiornare la descrizione dell&#39;attività in **Descrizione** campo.
- Modifica il **Data di scadenza**. Puoi posticipare o posticipare la scadenza per il completamento dell’attività.
- Selezionare l&#39;opzione per consentire agli utenti di esaminare solo gli argomenti ad essi assegnati.
- Clic **Aggiorna** per aggiornare i dettagli modificati.
- Clic **Completa** per contrassegnare l&#39;attività di revisione come completata prima della data di scadenza. Quando l&#39;attività di un singolo argomento viene contrassegnata come Completa, la revisione dell&#39;argomento selezionato viene chiusa. Tuttavia, nel caso di argomenti condivisi per la revisione tramite una mappa DITA, contrassegnando l&#39;attività Mappa DITA come Completa verrà chiusa la revisione di tutti gli argomenti della mappa condivisi per la revisione.
- Clic **Duplica** per creare una copia dell&#39;attività di revisione. Il processo di creazione di un&#39;attività di revisione duplicata è simile a quello di creazione di una nuova attività di revisione. Dopo aver avviato il flusso di lavoro dell&#39;attività duplicata, viene visualizzata la pagina Crea attività di revisione. È necessario fornire i dettagli della nuova attività come spiegato in [Invia argomenti per la revisione](review-send-topics-for-review.md#).

  Se è stata selezionata un&#39;attività di revisione creata da una mappa DITA, vengono visualizzati gli argomenti che costituiscono un pert della mappa. È quindi possibile scegliere gli argomenti che si desidera includere nella nuova attività di revisione.

  In caso di attività di revisione duplicata da uno o più argomenti di revisione, nell&#39;elenco delle attività di revisione vengono visualizzati solo tali argomenti. Puoi scegliere di condividere questi argomenti per la revisione con un diverso gruppo di revisori.

- Clic **Chiudi** per passare alla pagina Casella in entrata.

## Scheda Contenuto

![](images/review-content-page.png){width="800" align="left"}

È possibile eseguire le azioni seguenti sotto **Contenuto** scheda:

- Modifica la versione dell’argomento inviato per la revisione. È possibile scegliere la versione più recente dell&#39;argomento, la versione in data, la versione con etichetta specifica o la versione con una baseline specifica \(per una mappa DITA\).

- Clic **Aggiorna** per condividere la versione aggiornata dell&#39;argomento con i revisori. I revisori ricevono una notifica e-mail che indica che la versione più recente dell’argomento è stata inviata per la revisione. La volta successiva che un revisore apre l&#39;argomento, viene visualizzata la versione aggiornata dell&#39;argomento.

  >[!NOTE]
  >
  > In caso di versione aggiornata di un argomento, i vecchi commenti vengono mantenuti anche nella versione più recente. I revisori possono anche vedere le differenze tra le due versioni.

- Clic **Completa** per contrassegnare l&#39;attività di revisione come completata prima della data di scadenza. Quando l&#39;attività di un singolo argomento viene contrassegnata come Completa, la revisione dell&#39;argomento selezionato viene chiusa. Tuttavia, nel caso di argomenti condivisi per la revisione tramite una mappa DITA, contrassegnando l&#39;attività Mappa DITA come Completa verrà chiusa la revisione di tutti gli argomenti della mappa condivisi per la revisione.

- Clic **Duplica** per creare una nuova attività di revisione utilizzando come base l&#39;attività corrente.


## Scheda Revisori {#reviewer-tab-id199RF0N0MUI}

![](images/reviewers-tab.png){width="800" align="left"}

È possibile eseguire le azioni seguenti sotto **Revisori** scheda:

- **Seleziona tutto**: seleziona tutti gli argomenti nell&#39;elenco degli argomenti. È possibile eseguire facilmente un&#39;operazione batch dopo aver selezionato tutti gli argomenti.
- **Cancella selezione**: deseleziona gli argomenti selezionati nell&#39;elenco argomenti.

  >[!NOTE]
  >
  > È inoltre possibile selezionare o deselezionare singolarmente un argomento facendo clic sulla casella di spunta accanto all&#39;argomento.

- **Aggiungi**: visualizza la finestra di dialogo Aggiungi revisori. È possibile digitare il nome del ruolo di revisore o utente \(o gruppo\) che si desidera aggiungere come revisore agli argomenti selezionati.
- **Rimuovi**: visualizza la finestra di dialogo Rimuovi revisori. È possibile digitare il nome di un revisore o di un ruolo utente \(o gruppo\) che si desidera rimuovere come revisore dagli argomenti selezionati.
- **Riassegna**: visualizza la finestra di dialogo Riassegna revisori. È possibile digitare il nome di un revisore o di un ruolo utente \(o gruppo\) a cui si desidera assegnare l&#39;attività di revisione. In questo modo tutti i revisori esistenti verranno rimossi dagli argomenti selezionati e i revisori appena selezionati verranno assegnati a tali argomenti.
- **Esporta**: ti consente di esportare i dettagli dell’attività di revisione in un file CSV. Il file contiene dettagli quali il percorso e il titolo dell&#39;argomento, il nome del revisore e la versione degli argomenti inviati per la revisione.
- **Modifica revisori**: facendo clic su ![](images/edit_pencil_icon.svg)nell&#39;elenco degli argomenti viene visualizzata la finestra di dialogo Modifica revisori. Da questa finestra di dialogo è possibile aggiungere o rimuovere revisori per l&#39;argomento selezionato.

## Controllare lo stato di un&#39;attività di revisione {#check-review-status-id199RF0A0UHS}

Dalla pagina principale del dashboard Revisione, se si seleziona un task di revisione e si fa clic su **Stato**, viene visualizzato il rapporto sullo stato dell&#39;attività di revisione:

![](images/review-status-report.png){width="800" align="left"}

La relazione sullo stato dell&#39;attività di revisione contiene i dettagli riportati di seguito.

- Nome\(s\) del revisore a cui è assegnata l&#39;attività di revisione.
- La colonna Stato indica lo stato della revisione. Lo stato potrebbe essere uno dei seguenti:
   - **Non avviato**: il revisore non ha ancora aperto il collegamento per la revisione.
   - **In corso**: il revisore ha aperto il collegamento di revisione ed è in fase di revisione dell’argomento.
   - **Completa**: il revisore ha completato la revisione completando l’attività di revisione a lui assegnata. L&#39;attività di revisione è disponibile nella casella in entrata delle notifiche AEM per ogni revisore.
- Quando un revisore apre un collegamento di revisione e passa a un particolare argomento, tale argomento viene aggiunto all&#39;elenco Argomenti esaminati. In questo modo gli autori possono determinare se i revisori hanno aperto le rispettive sezioni o meno. Eventuali commenti sono riportati tra parentesi.
- Numero totale di commenti su tutti gli argomenti. In caso di più argomenti in revisione, il numero di commenti per ciascun argomento è indicato \(tra parentesi\) rispetto al nome dell’argomento.
- Data dell&#39;ultimo accesso a un argomento da parte del revisore.

**Argomento padre:**[ Rivedi argomenti o mappe](review.md)
