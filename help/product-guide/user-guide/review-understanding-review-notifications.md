---
title: Informazioni sulle notifiche di revisione
description: Scopri i diversi tipi di notifiche di revisione e come vengono attivate durante le diverse fasi del flusso di lavoro di revisione in Experience Manager Guides.
feature: Reviewing
role: User
source-git-commit: b7648fe1d36de3c243ca5a55f42a41f7523056ce
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Informazioni sulle notifiche di revisione

>[!IMPORTANT]
>
> Le nuove funzioni descritte in questo articolo sono abilitate per impostazione predefinita con la versione 2508 di Experience Manager Guides as a Cloud Services. Le revisioni create prima della migrazione non sono interessate e continueranno a utilizzare il flusso di lavoro precedente. Se preferisci continuare a utilizzare le funzioni esistenti senza questi aggiornamenti, contatta il team Customer Success per disabilitare le nuove funzioni.

Experience Manager Guides semplifica la collaborazione tra autori e revisori attraverso un flusso di lavoro di revisione strutturato. Come parte di questo flusso di lavoro, le notifiche svolgono un ruolo chiave nel mantenere tutti i partecipanti di un’attività di revisione informati e reattivi ai cambiamenti.

Ogni volta che viene eseguita un’azione correlata alla revisione, ad esempio l’assegnazione di un’attività, il completamento o gli aggiornamenti di feedback, viene inviata automaticamente una notifica agli utenti coinvolti nell’attività di revisione per attirare la loro attenzione immediata. Le notifiche vengono inviate in due formati:

- **Notifiche di AEM**: visualizzate nell&#39;interfaccia di AEM.
- **Notifiche e-mail**: inviate direttamente alla casella in entrata dell&#39;utente.

La tabella seguente fornisce una panoramica dei diversi tipi di notifiche di revisione, delle azioni che le attivano e del modo in cui vengono visualizzate nei diversi formati:


## Rivedi formati di notifica con valori di esempio

| **Azione di revisione** | **Titolo notifica (AEM)** | **Testo notifica (AEM)** | **Oggetto e-mail** | **Testo notifica e-mail** | **Destinatario** |
|-----------------------------|--------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| Attività di revisione creata | Attività di revisione assegnata: **Revisione homepage** | Assegnato da **Autore** | Attività di revisione assegnata: **Revisione homepage** | **L&#39;autore** ha creato un&#39;attività di revisione **Revisione home page** nel progetto **Revisione WebDocs** con data di scadenza **15 agosto 2025**. Sei stato assegnato come revisore. | **Revisore** |
| Feedback inviato | Rivedi il feedback ricevuto per **la recensione della homepage** | Feedback di **Revisore** | Rivedi il feedback ricevuto per **la recensione della homepage** | **Il revisore** ha inviato feedback per l&#39;attività **Revisione homepage** nel progetto **Revisione WebDocs**. Rivedi e apporta gli aggiornamenti necessari con largo anticipo rispetto alla scadenza **15 agosto 2025**. | **Autore** o **Iniziatore dell&#39;attività** |
| Riesame richiesto | È stata richiesta una nuova revisione per la **revisione della home page** | Richiesto da **Autore** | Nuova revisione richiesta per **Revisione home page** da **Autore** | **L&#39;autore** ha aggiornato il documento per l&#39;attività **Revisione home page** in base al tuo feedback e richiede una nuova revisione. Rivedi con largo anticipo la data di scadenza **15 agosto 2025**. | **Revisore** |
| Revisione chiusa | Attività di revisione chiusa: **Revisione homepage** | Chiuso da **Autore** | Attività di revisione chiusa: **Revisione homepage** | L&#39;attività di revisione **Revisione homepage** nel progetto **WebDocs Revamp** è stata chiusa da **Author**. | **Autore** o **Iniziatore dell&#39;attività** , **Revisore** |
| Revisore non assegnato | Non più assegnato all&#39;attività di revisione **Revisione homepage** | Revoca assegnazione da **Autore** | Non più assegnato all&#39;attività di revisione **Revisione homepage** | Ti è stata revocata l&#39;assegnazione dell&#39;attività di revisione **Revisione homepage** nel progetto **Revisione WebDocs** da **Autore**. | **Revisore** |
| Menzione tag | Menzionato nel commento dell&#39;attività di revisione per **Revisione homepage** | Citato da **Autore** | Menzionato nel commento dell&#39;attività di revisione per **Revisione homepage** | Sei stato menzionato in un commento all&#39;attività **Revisione homepage** in **Revisione WebDocs** da **Autore**. **Estratto di commento:** *&quot;Aggiornare la struttura dell&#39;intestazione in base alle linee guida per l&#39;accessibilità.&quot;* | **Utente menzionato** |
| Contenuto aggiornato durante la revisione | Argomento aggiornato nell&#39;attività di revisione **Revisione della home page** | Aggiornato da **Autore** | Argomento aggiornato nell&#39;attività di revisione **Revisione della home page** | **L&#39;autore** ha aggiornato le versioni dell&#39;argomento per l&#39;attività di revisione **Homepage Review**. Rivedi con largo anticipo la data di scadenza **15 agosto 2025**. | **Revisore** |


Nella tabella precedente, il **testo in grassetto** rappresenta valori di esempio ed è guidato da variabili predefinite che possono essere utilizzate nelle notifiche.


Ad esempio:

- **Homepage Review** è un nome di attività di esempio.
- **Priya** (Autore) e **John** (Revisore) sono nomi utente di esempio.
- **WebDocs Revamp** è un nome di progetto di esempio.
- **15 agosto 2025** è una data di scadenza di esempio.

Inoltre, se un’attività contiene commenti, nella notifica e-mail viene incluso un estratto di commento (una parte del commento completo). L’estratto viene visualizzato nei seguenti casi:

- Quando si viene taggati in un commento, nella notifica e-mail viene visualizzato un estratto del commento taggato.
- Quando si aggiunge un commento a livello di attività a un&#39;attività di revisione di cui si fa parte, un estratto di tale commento viene visualizzato nella notifica e-mail.

Per un elenco completo delle variabili predefinite e per esaminare la personalizzazione delle notifiche, visualizzare [Configurare e personalizzare i flussi di lavoro](../cs-install-guide/customize-workflows.md#customize-email-and-aem-notification-templates).




**Argomento padre:**[ Introduzione alla revisione](review.md)
