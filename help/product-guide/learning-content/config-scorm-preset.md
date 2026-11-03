---
title: Configurazione predefinito SCORM
description: Scopri le varie configurazioni del predefinito SCORM in Formazione e apprendimento del prodotto
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
TQID: https://experienceleague.adobe.com/9WSwgksrX0fahrniOalbizWFXCqcW0QlGAHn707vm-k
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 6b1f5e5a0264c340240a52e59c1d0e5c093fed50
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 0%
---
# Configura predefinito di output SCORM

Dopo aver creato il predefinito, configura le impostazioni del predefinito SCORM. Le opzioni di configurazione predefinite sono organizzate nelle schede Generale, Contenuto, Esperienza Allievo e Pubblica.

- **Generale:** utilizzato per specificare le impostazioni di output di base, ad esempio la versione supportata, il percorso di output, il nome file SCORM (zip), il modello di output e il flusso di lavoro di post-generazione per un nuovo elenco a discesa del flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati.

  ![](assets/scorm-general-tab-v3.png){width="650"}


- **Contenuto:** utilizzare per specificare il filtro condizionale disponibile (utilizzando DITAVAL o un predefinito di condizione) e il set di variabili.

  ![](assets/scorm-content-tab.png){width="650"}

- **Esperienza Allievo:** La scheda **Esperienza Allievo** consente di configurare il modo in cui gli Allievi interagiscono con l&#39;output SCORM e navigano all&#39;interno di esso. Le impostazioni sono organizzate in **Generale**, **Navigazione** e **Quiz** e consentono di controllare l&#39;accessibilità dei contenuti, il flusso di navigazione e il comportamento dei quiz per un&#39;esperienza di apprendimento personalizzata.

  ![](assets/learner-experience.png){width="650"}

  - **Generale:** configura le opzioni a livello di output, ad esempio l&#39;abilitazione dei download di PDF per gli Allievi.

    - **Consenti agli Allievi di scaricare il corso PDF**: se abilitata, questa opzione aggiunge un&#39;icona PDF all&#39;output SCORM. Facendo clic su questa icona, l’Allievo può scaricare una versione PDF del contenuto del corso direttamente dall’output pubblicato.

      **Prerequisiti:** Prima di abilitare questa opzione, verifica quanto segue:

      - Il **modello di output** deve essere configurato con l&#39;icona **Incorpora PDF** nella posizione desiderata e lo stesso modello deve essere selezionato nell&#39;opzione **Modello di output** nella scheda **Generale** durante la configurazione di un predefinito SCORM.

        ![](assets/embed-pdf.png){width="650"}

      - Il predefinito per PDF **nativo** associato deve essere stato generato almeno una volta. Se si seleziona un predefinito di PDF non generato, viene visualizzato un messaggio di errore in cui si chiede all’utente di pubblicare il predefinito.

    Una volta generato l’output SCORM con le impostazioni precedenti, l’output risultante include un’icona PDF, come mostrato di seguito, che consente agli Allievi di scaricare il PDF del corso.

    ![](assets/pdf-icon.png){width="650"}

  - **Navigazione:** Definisci il modo in cui gli Allievi si spostano nel corso, inclusa la progressione sequenziale, le condizioni di completamento obbligatorie e le regole per sbloccare il pulsante **Successivo**.

    - **Gli Allievi devono avanzare nel contenuto in ordine sequenziale**: assicura agli Allievi di spostarsi nel corso in una sequenza fissa e non possono saltare avanti o passare da un componente all&#39;altro del corso.
    - **Disattiva il pulsante Avanti se l&#39;Allievo non supera il quiz**: impedisce all&#39;Allievo di passare alla sezione/pagina successiva fino a quando non supera il quiz.
    - **Per procedere, gli Allievi devono tentare tutte le domande**: richiede agli Allievi di tentare tutte le domande prima di poter inviare il quiz, impedendo gli invii incompleti.
    - **Blocca avanzamento fino a completamento**: impedisce la navigazione attraverso il corso finché tutte le condizioni secondarie configurate di seguito non sono soddisfatte disabilitando il pulsante **Avanti** nel corso.
      - **Tutti gli elementi interattivi aperti**: richiede all&#39;Allievo di aprire ogni elemento interattivo della pagina.
      - **Tutti i file multimediali guardati**: richiede all&#39;Allievo di guardare tutti i file multimediali video/audio sulla pagina.
      - **Tutti i controlli della conoscenza sono stati tentati**: richiede all&#39;Allievo di tentare ogni domanda di controllo della conoscenza sulla pagina.
      - **Tempo minimo trascorso sulla pagina**: richiede che l&#39;Allievo rimanga sulla pagina per almeno la durata specificata prima che il pulsante Avanti sia abilitato. Una volta attivato, è necessario immettere il tempo richiesto come indicato di seguito.
        - **Tempo richiesto (secondi)**: il numero minimo di secondi (ad esempio `30`) in cui un Allievo deve rimanere nella pagina per soddisfare questa condizione.

  - **Quiz:** Configura il comportamento correlato al quiz, ad esempio la randomizzazione delle scelte relative all&#39;ordine delle domande e alle risposte, per ridurre la prevedibilità tra i tentativi.

    - **Ordine delle domande casuale per ogni tentativo**: visualizza le domande del quiz in un ordine diverso per ogni tentativo, riducendo la prevedibilità.
    - **Scelte casuali delle risposte per ogni tentativo**: riproduce in modo casuale le opzioni di risposta per ogni domanda a ogni tentativo, riducendo la possibilità di indovinare.

  - **Generazione rapporti**: utilizzare queste impostazioni per controllare quando vengono pubblicati in Adobe Learning Manager (ALM) lo stato di completamento e di esito positivo/negativo del corso.

    ![Impostazioni report](assets/reporting-scorm.png)

    - **Completamento corso**: definisce quando il corso viene contrassegnato come completato e pubblicato in ALM.

      - **Contrassegna il corso come completato al lancio**: contrassegna il corso come completato per l&#39;Allievo non appena viene avviato. Non è necessario che l’Allievo interagisca con alcun contenuto. Questa opzione è raramente necessaria, ma è disponibile se il flusso di lavoro lo richiede.
      - **In base agli argomenti completati**: contrassegna il corso come completato quando l&#39;Allievo raggiunge una **percentuale** o un **numero** specificato di argomenti completati. Scegliere l&#39;unità di misura, la percentuale o il numero, in base al modo in cui si desidera definire la soglia di completamento.
      - **In base al quiz con punteggio**: contrassegna il corso come completato in base allo stato del quiz dell&#39;Allievo, selezionato dal menu a discesa:

        - **Tentativo di quiz con valutazione**
        - **Quiz con punteggio superato**
        - **Quiz con punteggio superato o limite di tentativi raggiunto**

      Quando sono abilitati sia **In base agli argomenti completati** che **In base al quiz con punteggio**, utilizza il selettore **AND**/**OR** per definire la modalità di combinazione delle due condizioni:

      - **AND**: entrambe le condizioni devono essere vere.
      - **OR**: una delle due condizioni è sufficiente.

    - **Passaggio o errore corso**: definisce quando viene pubblicato in ALM uno stato di superamento o errore. La segnalazione dello stato di superamento o di errore è facoltativa.

      - **Segnala uno stato di esito positivo o negativo a LMS**: disattivalo se non desideri pubblicare lo stato di esito positivo o negativo in ALM. Se l&#39;opzione è disattivata, le altre opzioni di questo gruppo sono nascoste.
      - **Contrassegna il corso passato al lancio**: contrassegna il corso passato per l&#39;Allievo non appena viene avviato.
      - **In base agli argomenti completati**: contrassegna il corso come completato quando l&#39;Allievo raggiunge una **percentuale** o un **numero** specificato di argomenti completati. Scegliere l&#39;unità di misura, la percentuale o il numero, in base al modo in cui si desidera definire la soglia di completamento.
      - **In base al quiz con punteggio**: contrassegna il completamento o il fallimento del corso in base allo stato del quiz dell&#39;Allievo, selezionato dal menu a discesa

        - Tentativo di quiz con valutazione
        - Quiz con punteggio superato

      Quando sono abilitati sia **In base agli argomenti completati** che **In base al quiz con valutazione**, utilizzare il selettore **AND**/**OR** per combinarli, come descritto in precedenza.

    >[!NOTE]
    >
    >Per impostazione predefinita, queste impostazioni corrispondono al comportamento precedente: completamento al 100% degli argomenti completati e superamento in base sia al quiz con punteggio superato che agli argomenti completati al 100%. Questo vale sia per i predefiniti SCORM nuovi che per quelli esistenti, quindi nulla cambia per i corsi esistenti a meno che non si riconfigurino queste impostazioni.

- **Pubblica in LMS:** Utilizza questa impostazione per pubblicare i contenuti direttamente in Adobe Learning Manager (ALM). Dal menu a discesa **Server di pubblicazione**, selezionare **Adobe Learning Manager**, quindi scegliere il **Profilo di pubblicazione** richiesto precedentemente configurato nelle impostazioni di Workspace. Il profilo selezionato viene utilizzato per stabilire la connessione e caricare il contenuto generato in ALM.

  >[!NOTE]
  >
  > Prima di pubblicare i contenuti in ALM, è necessario configurare un profilo di pubblicazione Adobe Learning Manager. Per ulteriori dettagli, visualizzare [Profili di pubblicazione](../lc-config-guide/lc-folder-profile.md).

  ![](assets/scorm-publish-lms.png){width="650"}

Una volta configurate tutte le modifiche, salva le modifiche per il predefinito SCORM utilizzando **Salva** nell&#39;angolo destro della barra degli strumenti della pagina del predefinito SCORM.
