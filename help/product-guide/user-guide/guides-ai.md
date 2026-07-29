---
title: Guide AI per la funzionalità di assegnazione tag avanzati
description: Scopri come utilizzare le Guide AI per la funzionalità di assegnazione tag avanzati per argomenti e mappe in un’unica operazione.
source-git-commit: b866964c30a565eab0f6f9aec4b3fc9013f15f75
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 0%

---


# Guida introduttiva di AI Guides

>[!NOTE]
>
> L’intelligenza artificiale delle guide è disponibile in Experience Manager Guides as a Cloud Service a partire dalla versione 2026.08.0. Contatta il team di successo del cliente per abilitare questa funzione.

Le guide AI consentono di assegnare tag ai contenuti in modo più rapido, semplice e coerente. Utilizzando l’abilità di assegnazione tag avanzati agentica di Adobe CX Enterprise Collaborator, Guides AI analizza il contenuto e consiglia i tag pertinenti in base alla tassonomia dell’organizzazione, anziché leggere manualmente il contenuto per decidere quali tag applicare. Puoi mantenere il controllo rivedendo i tag suggeriti e scegliendo di applicarli o rifiutarli prima di confermare la selezione, riducendo in modo significativo lo sforzo manuale, migliorando la precisione dei tag e garantendo metadati coerenti all’interno della documentazione.

## Pannello IA per le guide

Il pannello IA per le guide fornisce tutti gli strumenti necessari per generare, esaminare e applicare i tag suggeriti dall’intelligenza artificiale.

![Guide pannello IA](images/guides-ai-panel.png){width="650"}

I seguenti componenti di Guides AI consentono di aggiungere file, configurare tag consigliati e gestire il flusso di lavoro di assegnazione tag avanzati:

- **(A)** Cronologia conversazioni: consente di visualizzare e riaprire le conversazioni precedenti per esaminare i suggerimenti e le azioni dei tag precedenti.

  ![Cronologia delle conversioni del pannello IA per le guide](images/chat-history.png){width="350"}

- **(B)** Nuova chat: avvia una nuova sessione di assegnazione tag per un argomento, una mappa o un set di file diverso.
- **(C)** Spazio dei nomi dei tag: seleziona gli spazi dei nomi della tassonomia da cui l&#39;IA delle guide deve generare i consigli sui tag. Vengono considerati solo i tag degli spazi dei nomi selezionati.

  ![Tassonomia del pannello IA delle guide](images/taxononmy.png){width="350"}

- **(D)** Spazio di risposta: rivedi i consigli sui tag generati dall&#39;intelligenza artificiale e scegli di accettarli, rifiutarli o modificarli prima di applicare i tag.
- **(E)** Spazio della richiesta: immettere una richiesta di richiesta per generare suggerimenti di tag per il contenuto selezionato.
- **(F)** Allega file o aggiungi contesto: aggiunge argomenti, mappe o file esterni dal sistema locale per fornire il contenuto che Guides AI deve analizzare per i consigli sui tag.
- Modello **(G)**: visualizza il modello di IA utilizzato per analizzare il contenuto e generare i consigli sui tag. Sono disponibili diversi modelli OpenAI e Anthropic Claude. Per impostazione predefinita, è selezionata l&#39;opzione **Usa predefinito manifesto**, che utilizza il modello configurato per l&#39;assistente selezionato.
- **(H)** Invia: invia la richiesta e il contenuto allegato per generare consigli sui tag basati su AI.

## Applicare tag a uno o più argomenti con l&#39;abilità di assegnazione tag avanzati

Per applicare i tag a uno o più argomenti con abilità di assegnazione tag avanzati, effettua le seguenti operazioni per utilizzare l’intelligenza artificiale delle guide:

1. Accedi a Experience Manager Guides.
1. Nella home page, selezionare **Guide AI** dalla barra di spostamento. Assicurati che la funzione di intelligenza artificiale delle guide sia abilitata dall’amministratore.
1. Aggiungi l’argomento per il quale desideri generare consigli sui tag utilizzando uno dei seguenti metodi:

   - **Utilizzo di prompt suggeriti**: per la prima chat nell&#39;area Risposta, selezionare **Suggerisci tag per un prompt di file**. Il prompt viene aggiunto automaticamente allo spazio del prompt. Selezionare `[file]`, quindi scegliere l&#39;argomento dal repository o da una raccolta nella finestra di dialogo **Seleziona file**. È possibile selezionare un argomento dalla finestra di dialogo **Seleziona file**.

     ![Accedi al pannello IA delle guide utilizzando i prompt suggeriti](images/suggested-prompts.png){width="650"}

   - **Utilizzo del collegamento**: Digitare `/` nel campo Prompt, quindi scegliere **Aggiungi riferimento archivio** per scegliere un argomento dal repository (oppure **Aggiungi file dal dispositivo** per caricare un argomento dal computer) e immettere il prompt suggerito *Suggerisci tag per un file*.

   - **Trascina e rilascia**: trascina uno o più argomenti nello spazio dei prompt e digita i tag *Suggerisci per un file*.

     ![accedere al pannello IA delle guide trascinando un argomento o una mappa](images/dragging-prompts.png){width="650"}

   - **Specificare i percorsi degli argomenti**: digitare `@` seguito dai percorsi separati da virgole per più argomenti da mappe uguali o diverse, quindi immettere il prompt: *Suggerire tag per un file*.

     ![Aggiunta di argomenti in blocco al pannello IA delle guide](images/topics-path-add.png){width="650"}

1. Seleziona **Invia**.

1. L’intelligenza artificiale delle guide analizza il contenuto dell’argomento e genera consigli sui tag.

   ![Interfaccia del pannello IA delle guide durante l&#39;analisi e il pensiero](images/guides-ai-analysis.png){width="650"}

1. Rivedi i tag suggeriti come segue:

   >[!NOTE]
   >
   > Per gli argomenti che contengono già dei tag, in Guide AI vengono visualizzati i tag esistenti. Questi tag sono di sola lettura e non possono essere modificati o rimossi.

   - Per un singolo argomento, puoi semplicemente **Accettare** i consigli per applicarli o **Rifiutarli** se non sono necessari.

     ![Guida la risposta del pannello AI dopo l&#39;analisi del contenuto](images/guides-ai-tags-review.png){width="650"}

   - Per più argomenti:
     1. Seleziona **Anteprima** per rivedere i consigli sui tag generati da IA.

        ![Anteprima dell&#39;analisi in blocco del pannello IA delle guide](images/topics-tag-preview.png){width="650"}

     1. Rivedi i tag suggeriti per ogni argomento, quindi scegli una delle azioni seguenti:
        - **Accetta tutti** per applicare tutti i tag suggeriti per tutti gli argomenti.
        - **Rifiuta tutti** per ignorare tutti i tag suggeriti per tutti gli argomenti.
        - **Cancella tutti i suggerimenti** per rimuovere tutti i tag suggeriti per un argomento specifico.
        - Seleziona l&#39;icona **X** accanto a un tag per rimuovere un singolo suggerimento di tag.

          ![Guida la finestra di dialogo di anteprima dell&#39;analisi in blocco del pannello AI](images/topics-tag-preview-dialog.png){width="650"}

1. Quando accetti i tag suggeriti, l’abilità di assegnazione tag avanzati aggiunge i tag generati dall’intelligenza artificiale ai tag già applicati al contenuto.

Dopo aver completato la revisione, in Guide AI viene visualizzato un riepilogo dei tag applicati all’argomento ed eventuali consigli di tag rifiutati.

![Riepilogo risposte pannello IA guide](images/topic-tag-summary.png){width="650"}

## Applicare tag a più argomenti di una mappa utilizzando l’abilità di assegnazione tag avanzati

Per applicare tag a più argomenti di una mappa con abilità di assegnazione tag avanzati, effettua le seguenti operazioni per utilizzare l’intelligenza artificiale delle guide:

1. Accedi a Experience Manager Guides.
1. Nella home page, selezionare **Guide AI** dalla barra di spostamento. Assicurati che la funzione di intelligenza artificiale delle guide sia abilitata dall’amministratore.
1. Aggiungi la mappa per la quale desideri generare consigli sui tag utilizzando uno dei seguenti metodi, come descritto per gli argomenti:

   - **Utilizzo di prompt suggeriti**: per la prima chat nell&#39;area Risposta, selezionare **Suggerisci tag per un prompt di file**. Il prompt viene aggiunto automaticamente allo spazio del prompt. Selezionare `[file]`, quindi scegliere la mappa dall&#39;archivio o da una raccolta nella finestra di dialogo **Seleziona file**.

   - **Trascina e rilascia**: trascina una mappa nello spazio dei prompt e digita i tag *Suggerisci per un file*.

   - **Utilizzo del collegamento**: Digitare `/` nel campo Prompt, quindi scegliere **Aggiungi riferimento archivio** per scegliere una mappa dal repository (oppure **Aggiungi file dal dispositivo** per caricare una mappa dal computer) e immettere il prompt suggerito *Suggerisci tag per un file*.

     ![Guide all&#39;assegnazione di tag in blocco AI](images/ai-map-selection.png){width="650"}

1. Seleziona **Invia**.
Un messaggio indica che la mappa selezionata contiene più argomenti. Seleziona **Seleziona argomenti** per scegliere gli argomenti per i quali desideri assegnare tag ai consigli.

   ![Guida l&#39;assegnazione di tag in blocco AI durante la selezione degli argomenti](images/ai-select-topics.png){width="650"}

1. Nella finestra di dialogo **Seleziona argomenti**, seleziona gli argomenti per i quali desideri assegnare tag ai consigli.\
   La finestra di dialogo **Seleziona argomenti** fornisce quanto segue:

   - **Elenco argomenti:** visualizza tutti gli argomenti nella mappa selezionata. Seleziona gli argomenti per i quali desideri generare i consigli sui tag.
   - **Riquadro di anteprima:** Visualizza un&#39;anteprima dell&#39;argomento selezionato insieme ai tag esistenti.
   - **Filtro:** Filtra gli argomenti per visualizzare solo quelli con **Tag aggiunti** o **Nessun tag aggiunto**.

     ![Finestra di dialogo Selezione argomenti durante l&#39;applicazione dei tag](images/select-dialog.png){width="650"}

1. Seleziona **Conferma**. Guide IA analizza gli argomenti selezionati e visualizza il numero di consigli sui tag generati per ciascun argomento.
1. Seleziona **Anteprima** per rivedere i consigli sui tag generati da IA.
1. Rivedi i tag suggeriti per ogni argomento, quindi scegli una delle azioni seguenti:
   - **Accetta tutti** per applicare tutti i tag suggeriti per tutti gli argomenti.
   - **Rifiuta tutti** per ignorare tutti i tag suggeriti per tutti gli argomenti.
   - **Cancella tutti i suggerimenti** per rimuovere tutti i tag suggeriti per un argomento specifico.
   - Seleziona l&#39;icona **X** accanto a un tag per rimuovere un singolo suggerimento di tag.

     >[!NOTE]
     >
     > Per gli argomenti che contengono già dei tag, in Guide AI vengono visualizzati i tag esistenti. Questi tag sono di sola lettura e non possono essere modificati o rimossi.

   ![Guida la finestra di anteprima dell&#39;assegnazione tag in blocco AI](images/preview-dialog.png){width="650"}

1. Quando accetti i tag suggeriti, l’abilità di assegnazione tag avanzati aggiunge i tag generati dall’intelligenza artificiale ai tag già applicati al contenuto.

Dopo aver completato la revisione, in Guide AI viene visualizzato un riepilogo dei tag applicati a ciascun argomento ed eventuali consigli di tag rifiutati.

