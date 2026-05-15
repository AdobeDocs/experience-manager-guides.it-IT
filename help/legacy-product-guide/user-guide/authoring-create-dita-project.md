---
title: Creare un progetto DITA
description: Creare un progetto DITA utilizzando un modello in AEM Guides. Scopri come utilizzare un progetto DITA per avviare le recensioni.
feature: Reviewing
role: User
hide: true
exl-id: 1b29c50a-04d0-4052-b893-44fb8bcc3c97
TQID: https://experienceleague.adobe.com/7MU9ThZrrkJ1owYxDxKztHnadVb27Jk5Hhvst2NiQl8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 472
ht-degree: 0%

---

# Creare un progetto DITA {#id1645HA00NM6}

AEM Guides fornisce un modello di progetto DITA che è possibile utilizzare per creare e gestire le attività di revisione.

È possibile creare un progetto DITA e utilizzarlo per avviare le revisioni. Un progetto consente di definire una scadenza e di controllare le attività e il tempo necessari per completare l&#39;attività di revisione per la quale è stato creato il progetto.

È possibile aggiungere membri del team a un progetto a cui assegnare vari ruoli: Autori, Revisori e Editori.

Dopo aver creato il progetto DITA, è possibile avviare la revisione dall&#39;Editor Web o dall&#39;interfaccia utente di Assets. Per ulteriori dettagli, vedere [Inviare argomenti per la revisione](review-send-topics-for-review.md#).

Analogamente, ogni volta che un autore avvia un flusso di lavoro di revisione, i membri selezionati del progetto ricevono una notifica e-mail. Per configurare le notifiche e-mail, vedi *Personalizzare i modelli e-mail* in Installare e configurare Adobe Experience Manager Guides as a Cloud Service.

Per creare un progetto DITA, effettuare le seguenti operazioni:

1. Apri la console Progetti.

   Puoi accedere alla console Progetti anche dal seguente URL:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Fai clic su **Crea** \> **Progetto** per avviare la procedura guidata Crea progetto.

   ![](images/project-console-63.png){width="650"}

1. Nella pagina Crea progetto selezionare il modello **Progetto DITA** e fare clic su **Avanti**.

1. Nella pagina Proprietà progetto, immetti i seguenti dettagli:

   Informazioni nella scheda **Base**:

   ![](images/create-project.png){width="650"}

   - Immetti **Titolo**, **Descrizione** e **Data di scadenza** del progetto.

   - È possibile scegliere una miniatura per il progetto.

   - Per impostazione predefinita, sei il proprietario del progetto. Per aggiungere altri utenti a questo progetto:

   1. Immettere o scegliere un utente dall&#39;elenco a discesa **Utente**.

   1. Scegli un tipo di utente: Autori, Revisori o Editori.

      >[!NOTE]
      >
      >In questo elenco a discesa vengono visualizzati altri tipi di utenti, ma per un progetto DITA è necessario scegliere solo il tipo di utente Autori, Revisori o Editori. Anche se si aggiunge un utente di un tipo diverso, tale utente non sarà in grado di accedere alle funzioni specifiche DITA disponibili in AEM Guides.

   1. Fai clic su **Aggiungi**.

      >[!NOTE]
      >
      >Se si utilizza AEM Guides versione 3.5 o precedente, viene visualizzata un&#39;opzione per selezionare un file di mappa DITA per risolvere i riferimenti chiave per i flussi di lavoro di modifica, anteprima e revisione degli argomenti. Nelle versioni 3.6 e successive è possibile impostare la mappa principale tramite l&#39;editor Web. Per ulteriori informazioni, vedere [Preferenze utente](web-editor-features.md#id2087G0P40SB) nell&#39;editor Web. Un altro modo per impostare la mappa principale è configurarla a livello globale o di cartella. Per ulteriori dettagli, vedere *Configurare profili globali o a livello di cartella* nella Guida all&#39;installazione e alla configurazione.

   Informazioni nella scheda **Avanzate**:

   - Immettere un nome per il progetto. Questo nome viene utilizzato per creare l’URL per questo progetto.

1. Fai clic su **Crea**.

   Viene visualizzata la finestra di dialogo Progetto creato.

1. Fai clic su **Apri** per aprire la pagina del progetto.


**Argomento padre:**&#x200B;[&#x200B; Rivedi argomenti o mappe](review.md)
