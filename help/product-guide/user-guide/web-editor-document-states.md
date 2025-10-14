---
title: Stato documento
description: Scopri i tipi di stati dei documenti in Adobe Experience Manager Guides. Scopri come modificare o visualizzare lo stato del documento e come utilizzarlo in DDLC.
exl-id: 3a68b2ed-b917-4f05-8b2b-d2722a740502
feature: Authoring, Features of Web Editor, Document State
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---

# Stato documento {#id1821HC00URO}

Per gestire la preparazione dei documenti, Adobe Experience Manager Guides fornisce la proprietà Stato documento per indicare lo stato corrente del documento. Gli stati dei documenti consentono di verificare rapidamente se un documento è nuovo, in revisione o completato.

## Tipi di stati dei documenti

Un documento può avere uno qualsiasi degli stati definiti nel profilo **Stato documento**. Ad esempio, un documento può avere uno dei seguenti stati:

- Bozza: indica che il documento viene creato e salvato con nuove modifiche.
- In revisione: indica che è stato avviato un flusso di lavoro di revisione per il documento.
- Rivisto: indica che il documento è stato rivisto dagli utenti a cui è destinato.

Questi stati vengono impostati manualmente o automaticamente in base alle impostazioni del profilo Stati documento. Ad esempio, se il profilo dello stato del documento è configurato con lo stato iniziale come Bozza e lo stato In revisione è definito per i documenti in revisione. Quindi, quando si crea un documento, lo stato del documento è impostato su *Bozza*. Se si avvia un&#39;attività di revisione, lo stato del documento viene modificato in In revisione.

È inoltre possibile modificare manualmente lo stato del documento per uno o più documenti. Tuttavia, se si sceglie di modificare lo stato del documento per più documenti, lo stato consentito è determinato dagli stati comuni consentiti per i documenti selezionati. Si supponga ad esempio di aver definito gli stati del documento come Bozza, In revisione, Rivisto e Pronto per la pubblicazione nello stesso ordine. Nel documento one.dita lo stato è impostato su *Bozza* e nel documento two.dita lo stato è impostato su Rivisto. Quando si selezionano sia one.dita che two.dita, lo stato del documento consentito sarà *Pronto per la pubblicazione*. Poiché two.dita è nello stato *Reviewed*, il successivo stato possibile per two.dita è solo *Ready to Publish*, che viene visualizzato quando entrambi i documenti sono selezionati.

>[!NOTE]
>
> Un documento può esistere in un solo stato alla volta.

## Modificare lo stato del documento dall&#39;editor

Per modificare lo stato di un documento, effettuare le seguenti operazioni:

1. Aprite il documento nell&#39;editor, quindi selezionate Proprietà file dal pannello Destra.
1. Nel pannello Proprietà file, seleziona il nuovo stato dal menu a discesa **Stato documento**. È possibile selezionare solo gli stati del documento consentiti nella sezione Transizione stato del profilo Stato documento.

   >[!NOTE]
   >
   >Gli amministratori possono visualizzare tutti gli stati dei documenti e modificare il documento in qualsiasi stato possibile.

1. Seleziona **Salva** nella richiesta di conferma.

## Modificare lo stato del documento dall’interfaccia utente di Assets

1. Nell’interfaccia utente di Assets, seleziona uno o più documenti per i quali desideri modificare lo stato del documento.
1. Nella barra degli strumenti principale, seleziona **Proprietà**.
1. Selezionare il nuovo stato dal menu a discesa **Stato documento**. È possibile selezionare solo gli stati del documento consentiti nella sezione Transizione stato del profilo Stato documento.

   >[!NOTE]
   >
   >Gli amministratori possono visualizzare tutti gli stati dei documenti e modificare il documento in qualsiasi stato possibile.

1. Seleziona **Salva e chiudi**.

### Visualizza stato documento

La vista a schede dell&#39;interfaccia utente di Assets mostra lo stato corrente insieme alla data e alle dimensioni di creazione del rispettivo argomento o mappa DITA.

![](images/document_state.png){align="left"}

## Utilizzare gli stati del documento in DDLC

Gli stati dei documenti svolgono un ruolo importante nella gestione del ciclo di vita dei documenti in DDLC. Se la tua organizzazione segue rigorosamente il DDLC, diventa essenziale disporre di un meccanismo per controllare la modifica dei documenti in base al loro stato. Ad esempio, puoi consentire la modifica di documenti in stato *Bozza* o *In revisione*. Tuttavia, una volta che un documento è rivisto ed è pronto per la pubblicazione, dovrebbe esserci un modo per impedire ulteriori modifiche ai documenti.

Experience Manager Guides fornisce un flusso di lavoro di approvazione dei documenti che consente di controllare il ciclo di vita del processo di sviluppo dei documenti. Quando un documento è pronto per la pubblicazione o ha raggiunto il penultimo stato, è possibile contrassegnarlo come approvato. Dopo l&#39;approvazione di un documento, Experience Manager Guides crea una nuova versione del documento e lo rende di sola lettura. È quindi possibile spostare il documento per la pubblicazione o creare una baseline per l&#39;ulteriore elaborazione.

Per avviare una nuova versione dai documenti contrassegnati come approvati, un autore deve avviare una nuova versione. Quando si avvia una nuova versione, lo stato del documento viene nuovamente modificato in *Bozza*. Modificando lo stato del documento in *Bozza*, il documento sarà nuovamente modificabile e sarà possibile continuare a lavorare alla versione successiva.

Per utilizzare la funzione di approvazione del documento, effettuare le seguenti operazioni:

>[!NOTE]
>
> La funzione di approvazione del flusso di lavoro deve essere abilitata dall’amministratore. Per ulteriori dettagli, visualizza la sezione *Abilita flusso di lavoro di approvazione* nell&#39;installazione e configurazione di Adobe Experience Manager Guides as a Cloud Service.

1. Nell&#39;editor aprire il documento che si desidera contrassegnare per l&#39;approvazione.

1. Seleziona l&#39;icona **Contrassegna come approvato**![](images/mark_approve_icon.svg).

1. Se il documento è in stato di approvazione, viene visualizzata la seguente finestra di dialogo:

   ![](images/mark-approved-correct-state.png){width="300" align="left"}

   Se il documento non può essere contrassegnato come approvato, viene visualizzato il seguente messaggio:

   ![](images/mark-approved-incorrect-state.png){width="300" align="left"}

1. Se il documento è pronto per essere contrassegnato come approvato, selezionare un&#39;etichetta dall&#39;elenco a discesa e selezionare **Approva**.

   >[!NOTE]
   >
   > Se l&#39;amministratore non ha configurato un elenco predefinito di etichette, viene visualizzato un campo di testo in formato libero per immettere un&#39;etichetta.

1. Una volta che il documento è stato contrassegnato come approvato, viene visualizzata una **Anteprima** del documento in modalità di sola lettura. Tutte le opzioni di modifica vengono rimosse da tutte e tre le modalità Autore, Source e Anteprima. Tuttavia, puoi comunque accedere al menu a discesa **Menu** che presenta le opzioni **Cronologia versioni** e **Tag**.

   ![](images/approved-doc-read-only.png){width="650" align="left"}

   >[!NOTE]
   >
   > In modalità Anteprima, il menu a discesa con le opzioni Cronologia versioni e Tag viene rimosso dalla barra degli strumenti.


Una volta contrassegnato come approvato, il documento non è più disponibile per la modifica. Se desideri utilizzare il documento per la prossima versione, devi riportarlo allo stato *Bozza*. Per ripristinare la modalità *Bozza* dello stato di un documento approvato, effettuare le seguenti operazioni:

1. In un documento approvato, selezionare l&#39;icona ![](images/approved-restart-draft-mode-icon.svg) **Avvia una nuova versione**.

   Viene visualizzato il messaggio Avvia nuova versione.

1. Seleziona **Conferma**.

   Lo stato del documento viene modificato in Bozza e il documento viene aperto nell&#39;Editor in modalità di modifica.


**Argomento padre:**&#x200B;[&#x200B; Introduzione all&#39;editor](web-editor.md)
