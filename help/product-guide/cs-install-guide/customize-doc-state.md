---
title: Configurare gli stati dei documenti
description: Scopri come configurare gli stati dei documenti
exl-id: ab155879-4472-464d-ab25-6075088d718b
feature: Document State
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# Configurare gli stati dei documenti {#id181GB0400UI}

Le guide AEM consentono di definire gli stati del documento per gli argomenti DITA in base ai requisiti dell&#39;organizzazione. È possibile definire diversi stati del documento dall&#39;inizio alla fine. Ad esempio, il primo stato può essere Bozza e può passare a Revisione, Approvato, Tradotto e infine Pubblicato.

Esistono due modi in cui un argomento può passare da uno stato all&#39;altro: manuale e automatico. Gli stati del documento definiti in un profilo possono essere utilizzati per modificare manualmente lo stato del documento. Questa operazione può essere eseguita dalla pagina Proprietà di un file di argomento. È inoltre possibile definire chi può spostare il documento da uno stato all&#39;altro. Ad esempio, un autore può creare un documento e lo stato predefinito del documento può essere Bozza. Quando l&#39;autore invia il documento per la revisione, può modificare lo stato del documento in In-Review. Il revisore può cambiare lo stato del documento in Approvato o in Bozza di nuovo in base al processo di revisione. Se il documento è Approvato, l&#39;editore può cambiare lo stato del documento in Tradotto o Pubblicato a seconda del flusso di lavoro.

>[!NOTE]
>
> Se un utente appartiene al *amministratori* , l&#39;utente può modificare lo stato di un documento da qualsiasi stato indipendentemente dalle transizioni di stato del documento definite nel sistema.

## Creare uno stato del documento

Le guide AEM vengono fornite con una serie di stati di documento predefiniti. Questi stati sono:

- Bozza
- Modifica
- In-Review
- Approvato
- Esaminato
- Fine

Questi stati predefiniti sono disponibili per tutti gli argomenti DITA creati in DAM. È possibile creare stati del documento personalizzati e assegnarli a una cartella specifica. Tutti i file DITA creati in tale cartella avranno quindi accesso ai nuovi stati del documento creati.

Per creare gli stati del documento utilizzando il Profilo cartella, effettuare le seguenti operazioni:

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti.
1. Fai clic sul riquadro Stati del documento.

   Viene visualizzata la pagina Stati risorse. Per impostazione predefinita, la pagina mostra un profilo predefinito.

1. Clic **Crea profilo** e immetti i seguenti dettagli:
   - Immetti il nome del profilo nel campo Profilo.
   - Specifica il percorso in cui desideri applicare il nuovo profilo.
   - Specificare gli stati del documento in **Stati consentiti** in **Stati**. Gli stati predefiniti del documento sono Bozza, Modifica (Edit), In-Review, Approvato (Approved) e Fatto (Done).

     Fai clic su **Aggiungi** per aggiungere uno stato del documento.

      - Fare clic sull&#39;icona Elimina per eliminare uno stato del documento.

     >[!NOTE]
     >
     > Non eliminare uno stato del documento se i documenti sono ancora in tale stato. Se si elimina uno stato del documento, non sarà possibile modificarne lo stato a meno che non si appartenga al *amministratore* gruppo di utenti.

   - Specificare lo stato iniziale del documento in **Stato iniziale**.
   - Specificare lo stato finale del documento in **Stato finale**.
   - Specificare la transizione di stato del documento in **Da** e **A** in **Transizione stato**.

      - Specificare gli utenti e i gruppi di utenti che possono modificare lo stato del documento in **Gruppi**.

      - Fai clic su **Aggiungi** per aggiungere una transizione di stato.

      - Fai clic sull’icona Elimina per eliminare una transizione di stato.

     >[!NOTE]
     >
     > Non eliminare una transizione di stato se i documenti sono ancora in `From` stato. Se si elimina una transizione di stato, non sarà possibile modificare lo stato del documento di tali documenti a meno che non si appartenga al *amministratore* gruppo di utenti.

1. Clic **Fine**.

## Creare una copia di un profilo di stato del documento

A seconda delle esigenze, è possibile creare una copia di un profilo di stato del documento esistente. È possibile utilizzare la copia come base per la creazione di un altro profilo di documento.

Per creare una copia di un profilo di stato del documento, effettuare le seguenti operazioni:

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti.
1. Fai clic sul riquadro Stati del documento.

   Viene visualizzata la pagina Stati risorse.

1. Selezionare il profilo dello stato del documento da duplicare e fare clic su **Duplica profilo**.
1. Apporta le modifiche necessarie e fai clic su **Fine**.

## Eliminare una transizione di stato o stato di un documento

>[!NOTE]
>
> Non eliminare uno stato del documento o una transizione di stato se i documenti sono ancora nello stato o nella transizione di stato. Se si elimina una transizione di stato o stato, non sarà possibile modificare lo stato del documento di tali documenti a meno che non si appartenga al *amministratore* gruppo di utenti.

Per eliminare uno stato di documento o una transizione di stato da un profilo di stato di documento, effettuare le seguenti operazioni:

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti.
1. Fai clic sul riquadro Stati del documento.

   Viene visualizzata la pagina Stati risorse.

1. Selezionare il profilo dello stato del documento da cui si desidera eliminare lo stato del documento e fare clic su **Modifica profilo**.
1. Eliminare lo stato del documento o la transizione di stato e fare clic su **Fine**.

## Eliminare un profilo di stato del documento

Per eliminare un profilo di stato del documento, effettuare le seguenti operazioni:

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti.
1. Fai clic sul pulsante **Stati documento** affiancare.

   Viene visualizzata la pagina Stati risorse.

1. Selezionare il profilo dello stato del documento che si desidera eliminare e fare clic su **Elimina profilo**.

## Automatizzare la modifica dello stato del documento

Se non si desidera modificare manualmente gli stati del documento, è possibile creare un workflow e automatizzare la modifica dello stato del documento.

>[!NOTE]
>
> I flussi di lavoro automatizzati devono essere conformi agli stati del documento e alle transizioni definite nella configurazione. Il sistema non esegue alcun controllo per le modifiche dello stato effettuate tramite flussi di lavoro automatizzati.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Flusso di lavoro** dall&#39;elenco degli strumenti.

1. Fai clic sul pulsante **Modelli** affiancare.

1. Seleziona il flusso di lavoro appropriato, ad esempio Argomenti revisione.

1. Clic **Modifica**.

   Il flusso di lavoro si apre in una nuova scheda.

1. Clic **Modifica** \(alto a destra\).

1. Apri **Passaggi** browser; utilizzo **Attiva/Disattiva pannello laterale**, all’estrema sinistra della barra degli strumenti superiore

1. Trascina il passo appropriato\(s\) nella posizione desiderata nel modello.

1. Fai clic sul nuovo passaggio aggiunto nel modello di flusso di lavoro e seleziona **Configura** dalla barra degli strumenti del componente

1. Apri **Processo** scheda.

1. In **Processo** elenco a discesa, seleziona **Imposta lo stato del documento per qualsiasi risorsa DAM**.

1. Seleziona la **Avanzamento gestore** opzione.

   ![](assets/update-workflow-doc-state_cs.png)

1. In **Argomenti** , immettere lo stato del documento a cui si desidera passare dal flusso di lavoro selezionato.

   >[!NOTE]
   >
   > Assicurarsi di immettere lo stato corretto del documento nella casella di testo Argomenti. Se si immette un valore errato, il documento verrà impostato su uno stato errato.

1. Conferma la modifica con **Salva e chiudi**.


## Abilita flusso di lavoro di approvazione

Le guide AEM forniscono un flusso di lavoro di approvazione dei documenti che consente di controllare il ciclo di vita del processo di sviluppo dei documenti. Per abilitare il flusso di lavoro di approvazione, effettua le seguenti operazioni:

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul pulsante **Profilo globale** affiancare.
1. Seleziona la **Configurazione editor XML** e fai clic su **Modifica** icona in alto
1. Fai clic su **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.
1. In `ui_config.json` , abilitare la funzione del flusso di lavoro di approvazione modificando *funzioni* come mostrato di seguito:

   ```
   "features":  
   { 
      "approvalWorkflow":  true 
   }
   ```

1. Salva il file e caricalo.
