---
title: Configurazione predefinito SCORM
description: Scopri le varie configurazioni del predefinito SCORM in Formazione e apprendimento del prodotto
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
TQID: https://experienceleague.adobe.com/9WSwgksrX0fahrniOalbizWFXCqcW0QlGAHn707vm-k
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: f7c0b10f032c2584fb6e951da898faaeb4ca7aaf
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 0%

---

# Configura predefinito di output SCORM

Dopo aver creato il predefinito, configura le impostazioni del predefinito SCORM. Le opzioni di configurazione predefinite sono organizzate nelle schede Generali, Contenuto e Pubblica.

- **Generale:** Consente di specificare le impostazioni di output di base, ad esempio la versione supportata, il percorso di output, il nome del file ZIP, il modello di output e altre opzioni relative all&#39;esperienza dell&#39;Allievo.

  ![](assets/scorm-general-tab-v3.png){width="650"}

  **Esperienza dell&#39;Allievo**

   - **Gli Allievi devono avanzare nel contenuto in ordine sequenziale**: assicura agli Allievi di spostarsi nel quiz in una sequenza fissa e non possono saltare avanti o passare da una domanda all&#39;altra.
   - **Per procedere, gli Allievi devono tentare tutte le domande**: richiede agli Allievi di tentare tutte le domande prima di poter inviare il quiz, impedendo gli invii incompleti.
   - **Ordine delle domande casuale per ogni tentativo**: visualizza le domande del quiz in un ordine diverso per ogni tentativo, riducendo la prevedibilità.
   - **Scelte casuali delle risposte per ogni tentativo**: riproduce in modo casuale le opzioni di risposta per ogni domanda a ogni tentativo, riducendo la possibilità di indovinare in base alla posizione.
   - **Utilizza l&#39;ID domanda nel reporting dei quiz**: include l&#39;ID domanda univoco nei report dei quiz, semplificando il tracciamento, l&#39;analisi e la mappatura dei risultati in base a domande specifiche.
   - **Flusso di lavoro post-generazione**: quando si sceglie questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro post-generazione contenente tutti i flussi di lavoro configurati.

- **Contenuto:** utilizzare per specificare il filtro condizionale disponibile (utilizzando DITAVAL o un predefinito di condizione) e il set di variabili.

  ![](assets/scorm-content-tab.png){width="650"}


- **Pubblica in LMS:** Utilizza questa impostazione per pubblicare i contenuti direttamente in Adobe Learning Manager (ALM). Dal menu a discesa **Server di pubblicazione**, selezionare **Adobe Learning Manager**, quindi scegliere il **Profilo di pubblicazione** richiesto precedentemente configurato nelle impostazioni di Workspace. Il profilo selezionato viene utilizzato per stabilire la connessione e caricare il contenuto generato in ALM.

  >[!NOTE]
  >
  > Prima di pubblicare i contenuti in ALM, è necessario configurare un profilo di pubblicazione Adobe Learning Manager. Per ulteriori dettagli, visualizzare [Profili di pubblicazione](../lc-config-guide/lc-folder-profile.md).

  ![](assets/scorm-publish-lms.png){width="650"}

Una volta configurate tutte le modifiche, salva le modifiche per il predefinito SCORM utilizzando **Salva** nell&#39;angolo destro della barra degli strumenti della pagina del predefinito SCORM.
