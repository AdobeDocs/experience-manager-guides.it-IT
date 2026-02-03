---
title: Esempi
description: Elenco di esempi di personalizzazione
exl-id: 40cdc703-7a78-4979-a7b5-1158558d4868
source-git-commit: 924c34a2ec6249b81cbdddf72392dac600e22e9f
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---

# Esempi

In questo pacchetto sono stati inoltre forniti alcuni esempi di personalizzazione (disponibili all&#39;indirizzo `guides_extension/src`). Segue una breve descrizione per ciascuno di essi.

1. [Menu di scelta rapida](./examples/file_options.ts)
In questo esempio è stato personalizzato il menu di scelta rapida `file_options` per rimuovere le opzioni `Delete` e `Edit` e sostituire l&#39;opzione `Duplicate` con l&#39;opzione `Download`.

2. [Pannello sinistro](./examples/left_panel_container.ts)
In questo esempio abbiamo personalizzato `left tab panel` per avere un altro`tab` denominato &quot;TEST EXTENSION&quot; e un `tab panel` corrispondente con etichetta: `Test Tab Panel`

3. [Pannello destro](./examples/right_panel_container.ts)
In questo esempio abbiamo personalizzato `right tab panel` per avere un altro `tab` denominato &quot;TEST EXTENSION&quot; e un `tab panel` corrispondente con etichetta: `New Tab Panel`

4. [Pannello archivio](./examples/repository_panel.ts)

5. [Barra degli strumenti](./examples/toolbar.ts)
In questo esempio sono stati sostituiti i pulsanti `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` con un singolo pulsante `More Insert Options` contenente tutti questi pulsanti.

6. [Pulsante Gestisci nel pannello Metadati](./examples/metadata_report_manage_button.ts)
In questo esempio, abbiamo personalizzato il pulsante **Gestisci** (che si trova nel pannello Metadati della pagina Rapporti) in modo che venga disabilitato quando i file selezionati sono in modalità di sola lettura. In questo modo è possibile evitare la modifica accidentale di metadati su file non destinati alla modifica.

[Verifica esempi app]

1. [Casella degli strumenti Annotazione](./examples/review_app_examples/annotation_extension.ts)
In questo esempio è stato aggiunto un altro pulsante alla casella degli strumenti di annotazione che apre l’argomento di revisione corrente in AEM.

2. [Commento revisione](./examples/review_app_examples/review_comment.ts)
In questo esempio abbiamo aggiunto la sostituzione del nome utente con le informazioni utente (che comprendono il nome completo e il titolo del commento), aggiunto un ID commento univoco, un’icona mailTo e aggiunto campi di input per indicare la gravità e la motivazione del commento.
È stato aggiunto anche un pulsante `accept with modification` ai commenti sul lato XMLEditor che apre una finestra di dialogo.

3. [Risposta commento](./examples/review_app_examples/comment_reply.ts)
In questo esempio abbiamo aggiunto che il nome utente è stato sostituito da informazioni utente (che comprendono il nome completo e il titolo del commento) e aggiunto un’icona mailTo nell’intestazione del commento.

4. [Pannello revisioni in linea](./examples/review_app_examples/inline_review_panel.ts)
In questo file, viene calcolato e assegnato l&#39;ID commento univoco, indicato negli esempi `Review Comment` e `Comment Reply`.
   - Il metodo `setCommentId` imposta l&#39;ID univoco di ogni commento in base al numero di commenti.

   - `setUserInfo` imposta il valore di userInfo, utilizzando il nome completo e il titolo per ogni commento.

   - `onNewCommentEvent` assicura che il metodo `setUserInfo` venga chiamato per ogni nuovo commento o risposta.

   - La funzione `updatedProcessComments` viene eseguita per ogni nuovo evento di commento e assicura che `setCommentId` venga chiamato se si riceve un nuovo evento di commento.

5. [Pannello recensioni argomenti](./examples/review_app_examples/topic_reviews.ts): questo file estende il [Pannello revisioni in linea](./examples/review_app_examples/inline_review_panel.ts) in modo che le personalizzazioni aggiunte funzionino anche sul lato app revisioni.

6. [Accetta con finestra di dialogo per modifica](./examples/review_app_examples/accept_with_modification_dialog.ts)
Questo è un esempio di aggiunta di nuovi widget all’app. È stata creata una nuova finestra di dialogo con due campi di testo di input: `Revised Text` e `Adjudicator Comment Rationale`

7. [Salva revisione](./examples/save_revision.ts)
Questo è un esempio di come aggiornare una finestra di dialogo esistente. Aggiungiamo un pulsante per la pubblicazione in questo. È consentita la modifica del contenuto della finestra di dialogo. Fai riferimento al relativo json qui: [`save_revision`](./jsons/dialogs/save_revision.json)

![Accetta con finestra di dialogo per modifica](./imgs/accept_with_modification_dialogue.png)

Ecco il pannello di revisione prima e dopo la personalizzazione:

![Pannello recensioni;](./imgs/review_panel.png)
![Accetta con finestra di dialogo per modifica](./imgs/customised_review_panel.png)
