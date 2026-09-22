---
title: Assistente AI agente per la funzionalità di assegnazione tag avanzati
description: Scopri come utilizzare l’Assistente all’intelligenza artificiale di Agentic per la funzionalità di assegnazione tag avanzati per argomenti e mappe in un’unica operazione.
source-git-commit: cea0720e6482361a87b0e1dcff82760e3105436c
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 0%
---

# Utilizzare l’Assistente IA in modalità Agentic

>[!NOTE]
>
> L’Assistente IA in modalità Agentic è disponibile in Experience Manager Guides as a Cloud Service a partire dalla versione 2026.09.0. Richiede l’onboarding della tua organizzazione in CX Enterprise Coworker; una volta effettuato l’onboarding, contatta il team di successo del cliente per abilitare la funzione. Per informazioni dettagliate sulla configurazione, visualizzare [Configurare l&#39;Assistente di IA in modalità agente](../install-conf-guide/configure-ai-assistant-agentic-mode-cs.md).

L’Assistente AI in modalità Agentic rende l’assegnazione tag ai contenuti più veloce, semplice e coerente. Utilizzando l’abilità di assegnazione tag avanzati di Adobe CX Enterprise Coworker, l’Assistente AI analizza il contenuto e consiglia i tag rilevanti in base alla tassonomia della tua organizzazione, anziché leggere manualmente il contenuto per decidere quali tag applicare. Puoi mantenere il controllo rivedendo i tag suggeriti e scegliendo di applicarli o rifiutarli prima di confermare la selezione, riducendo lo sforzo manuale, migliorando la precisione dei tag e garantendo metadati coerenti all’interno della documentazione.

## Pannello Assistente AI

Il pannello Assistente AI offre tutti gli strumenti necessari per generare, rivedere e applicare i tag suggeriti da AI.

![Pannello dell&#39;Assistente di IA per l&#39;agente](images/guides-ai-panel.png){width="650"}

I seguenti componenti di IA Assistant in modalità Agentic consentono di aggiungere file, configurare tag recommendations e gestire il flusso di lavoro di assegnazione tag avanzati:

- **(A)** Cronologia conversazioni: consente di visualizzare e riaprire le conversazioni precedenti per esaminare i suggerimenti e le azioni dei tag precedenti.

  ![Cronologia delle conversioni del pannello Agentic AI Assistant](images/chat-history.png){width="350"}

- **(B)** Nuova chat: avvia una nuova sessione di assegnazione tag per un argomento, una mappa o un set di file diverso.
- **(C)** Spazio dei nomi dei tag: seleziona gli spazi dei nomi della tassonomia da cui l&#39;Assistente AI genera i consigli sui tag. Vengono considerati solo i tag degli spazi dei nomi selezionati.

  ![Tassonomia del pannello Agentic AI Assistant](images/taxononmy.png){width="350"}

- **(D)** Spazio di risposta: rivedi i consigli sui tag generati dall&#39;intelligenza artificiale e scegli di accettarli, rifiutarli o modificarli prima di applicare i tag.
- **(E)** Spazio della richiesta: immettere una richiesta di richiesta per generare suggerimenti di tag per il contenuto selezionato.
- **(F)** Allega file o aggiungi contesto: aggiunge argomenti, mappe o file esterni dal sistema locale per fornire il contenuto analizzato dall&#39;Assistente IA per i consigli sui tag.
- Modello **(G)**: visualizza il modello di IA utilizzato per analizzare il contenuto e generare i consigli sui tag. Sono disponibili diversi modelli OpenAI e Anthropic Claude. Per impostazione predefinita, è selezionata l&#39;opzione **Usa predefinito manifesto**, che utilizza il modello configurato per l&#39;assistente selezionato.
- **(H)** Invia: invia la richiesta e il contenuto allegato per generare consigli sui tag basati su AI.

## Applicare tag a uno o più argomenti con l&#39;abilità di assegnazione tag avanzati

Per applicare tag a uno o più argomenti con abilità di assegnazione tag avanzati, effettua le seguenti operazioni per utilizzare l’Assistente IA:

1. Accedi a Experience Manager Guides.
1. Nella home page, selezionare **Assistente AI** dalla barra di spostamento. Assicurati che l’Assistente AI in modalità Agentic sia abilitato dall’amministratore.
1. Aggiungi l’argomento per il quale desideri generare consigli sui tag utilizzando uno dei seguenti metodi:

   - **Utilizzo di prompt suggeriti**: per la prima chat nell&#39;area Risposta, selezionare **Suggerisci tag per un prompt di file**. Il prompt viene aggiunto automaticamente allo spazio del prompt. Selezionare `[file]`, quindi scegliere l&#39;argomento dal repository o da una raccolta nella finestra di dialogo **Seleziona file**. È possibile selezionare un argomento dalla finestra di dialogo **Seleziona file**.

     ![Accedere al pannello Agentic AI Assistant utilizzando i prompt suggeriti](images/suggested-prompts.png){width="650"}

   - **Utilizzo del collegamento**: Digitare `/` nel campo Prompt, quindi scegliere **Aggiungi riferimento archivio** per scegliere un argomento dal repository (oppure **Aggiungi file dal dispositivo** per caricare un argomento dal computer) e immettere un prompt come *Suggerisci tag per un file*.

   - **Trascina**: trascina uno o più argomenti nello spazio dei prompt e immetti un prompt come *Suggerisci tag per un file*.

     ![accedere al pannello dell&#39;Assistente di IA per l&#39;analisi dinamica trascinando un argomento o una mappa](images/dragging-prompts.png){width="650"}

   - **Specificare i percorsi degli argomenti**: digitare `@` seguito dai percorsi separati da virgole per più argomenti della stessa mappa o di mappe diverse e immettere un prompt come *Suggerisci tag per un file*.

     ![Aggiunta argomento in blocco pannello Assistente IA agente](images/topics-path-add.png){width="650"}

1. Seleziona **Invia**.

1. L’Assistente AI analizza il contenuto dell’argomento e genera consigli sui tag.

   ![Interfaccia del pannello Agentic AI Assistant durante l&#39;analisi e il pensiero](images/guides-ai-analysis.png){width="650"}

1. Rivedi i tag suggeriti come segue:

   >[!NOTE]
   >
   > Per gli argomenti che contengono già tag, l&#39;Assistente IA visualizza i tag esistenti. Questi tag sono di sola lettura e non possono essere modificati o rimossi.

   - Per un singolo argomento, puoi **Accettare** i consigli per applicarli o **Rifiutarli** se non sono necessari.

     ![Risposta del pannello Agentic AI Assistant dopo l&#39;analisi del contenuto](images/guides-ai-tags-review.png){width="650"}

   - Per più argomenti:
     1. Seleziona **Anteprima** per rivedere i consigli sui tag generati da IA.

        ![Anteprima dell&#39;analisi in blocco del pannello Agentic AI Assistant](images/topics-tag-preview.png){width="650"}

     1. Rivedi i tag suggeriti per ogni argomento, quindi scegli una delle azioni seguenti:
        - **Accetta tutti** per applicare tutti i tag suggeriti per tutti gli argomenti.
        - **Rifiuta tutti** per ignorare tutti i tag suggeriti per tutti gli argomenti.
        - **Cancella tutti i suggerimenti** per rimuovere tutti i tag suggeriti per un argomento specifico.
        - Seleziona l&#39;icona **X** accanto a un tag per rimuovere un singolo suggerimento di tag.

          ![Finestra di dialogo di anteprima dell&#39;analisi in blocco del pannello Agentic AI Assistant](images/topics-tag-preview-dialog.png){width="650"}

1. Quando accetti i tag suggeriti, l’abilità di assegnazione tag avanzati aggiunge i tag generati dall’intelligenza artificiale ai tag già applicati al contenuto.

Dopo aver completato la revisione, l’Assistente AI visualizza un riepilogo dei tag applicati all’argomento ed eventuali consigli di tag rifiutati.

![Riepilogo risposte pannello Assistente di IA per l&#39;analisi dei problemi](images/topic-tag-summary.png){width="650"}

## Applicare tag a più argomenti di una mappa utilizzando l’abilità di assegnazione tag avanzati

Per applicare tag a più argomenti di una mappa con abilità di assegnazione tag avanzati, effettua le seguenti operazioni per utilizzare l’Assistente IA:

1. Accedi a Experience Manager Guides.
1. Nella home page, selezionare **Assistente AI** dalla barra di spostamento. Assicurati che l’Assistente AI in modalità Agentic sia abilitato dall’amministratore.
1. Aggiungi la mappa per la quale desideri generare consigli sui tag utilizzando uno dei seguenti metodi, come descritto per gli argomenti:

   - **Utilizzo di prompt suggeriti**: per la prima chat nell&#39;area Risposta, selezionare **Suggerisci tag per un prompt di file**. Il prompt viene aggiunto automaticamente allo spazio del prompt. Selezionare `[file]`, quindi scegliere la mappa dall&#39;archivio o da una raccolta nella finestra di dialogo **Seleziona file**.

   - **Trascina e rilascia**: trascina una mappa nello spazio dei prompt e immetti un prompt come *Suggerisci tag per un file*.

   - **Utilizzo del collegamento**: Digitare `/` nel campo Prompt, quindi scegliere **Aggiungi riferimento archivio** per scegliere una mappa dal repository (oppure **Aggiungi file dal dispositivo** per caricare una mappa dal computer) e immettere un prompt come *Suggerisci tag per un file*.

     ![Assegnazione di tag in blocco dell&#39;Assistente di IA per l&#39;agente](images/ai-map-selection.png){width="650"}

1. Seleziona **Invia**.
Un messaggio indica che la mappa selezionata contiene più argomenti. Seleziona **Seleziona argomenti** per scegliere gli argomenti per i quali desideri assegnare tag ai consigli.

   ![Assegnazione di tag in blocco dell&#39;Assistente di IA per l&#39;agente durante la selezione degli argomenti](images/ai-select-topics.png){width="650"}

1. Nella finestra di dialogo **Seleziona argomenti**, seleziona gli argomenti per i quali desideri assegnare tag ai consigli.\
   La finestra di dialogo **Seleziona argomenti** fornisce quanto segue:

   - **Elenco argomenti:** visualizza tutti gli argomenti nella mappa selezionata. Seleziona gli argomenti per i quali desideri generare i consigli sui tag.
   - **Riquadro di anteprima:** Visualizza un&#39;anteprima dell&#39;argomento selezionato insieme ai tag esistenti.
   - **Filtro:** Filtra gli argomenti per visualizzare solo quelli con **Tag aggiunti** o **Nessun tag aggiunto**.

     ![Finestra di dialogo Selezione argomenti durante l&#39;applicazione dei tag](images/select-dialog.png){width="650"}

1. Seleziona **Conferma**. L’Assistente AI analizza gli argomenti selezionati e visualizza il numero di consigli sui tag generati per ogni argomento.
1. Seleziona **Anteprima** per rivedere i consigli sui tag generati da IA.
1. Rivedi i tag suggeriti per ogni argomento, quindi scegli una delle azioni seguenti:
   - **Accetta tutti** per applicare tutti i tag suggeriti per tutti gli argomenti.
   - **Rifiuta tutti** per ignorare tutti i tag suggeriti per tutti gli argomenti.
   - **Cancella tutti i suggerimenti** per rimuovere tutti i tag suggeriti per un argomento specifico.
   - Seleziona l&#39;icona **X** accanto a un tag per rimuovere un singolo suggerimento di tag.

     >[!NOTE]
     >
     > Per gli argomenti che contengono già tag, l&#39;Assistente IA visualizza i tag esistenti. Questi tag sono di sola lettura e non possono essere modificati o rimossi.

   ![Finestra di dialogo di anteprima per l&#39;assegnazione di tag in blocco dell&#39;Assistente IA agente](images/preview-dialog.png){width="650"}

1. Quando accetti i tag suggeriti, l’abilità di assegnazione tag avanzati aggiunge i tag generati dall’intelligenza artificiale ai tag già applicati al contenuto.

Dopo aver completato la revisione, l’Assistente AI visualizza un riepilogo dei tag applicati a ciascun argomento ed eventuali consigli di tag rifiutati.

