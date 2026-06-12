---
title: Configurare Adobe Workfront in Experience Manager Guides
description: Scopri come configurare Workfront in Experience Manager Guides
feature: Authoring
role: Admin
level: Experienced
exl-id: 1f72642c-e694-47cd-9182-f4f4aaf69655
TQID: https://experienceleague.adobe.com/Yua4Y6xsnec3O-hpTNhSmK4HvsCwaGYbLTxUxEeQAKY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: ae478996-b206-4712-9b0c-dc78a2644453
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 600
ht-degree: 2%

---

# Configurare Adobe Workfront

Adobe Workfront è una soluzione di gestione del lavoro basata su cloud che consente a team e organizzazioni di pianificare, monitorare e gestire il proprio lavoro in modo efficiente. L’integrazione tra Experience Manager Guides e Adobe Workfront consente di accedere a solide funzionalità di gestione dei progetti oltre alle funzionalità principali di Experience Manager Guides CCMS, che consentono di pianificare, allocare e tenere traccia delle attività in modo efficiente.

Ulteriori informazioni sull&#39;[integrazione Adobe Workfront](../user-guide/workfront-integration.md) in Experience Manager Guides.

## Prerequisiti

Prima di iniziare, assicurati che:

1. Hai accesso standard ad Adobe Workfront e accesso amministratore a Experience Manager Guides.
2. [crea un nuovo modulo personalizzato in Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) richiesto per Experience Manager Guides utilizzando in modo specifico i campi seguenti:

   | Tipo di campo | Etichetta | Nome | Scelte (Mostra valori abilitati) |
   |------------|------|------|-------------------------------|
   | Menu a discesa a selezione singola | Tipo di attività | task-type | Authoring (valore = AUTHOR), pubblicazione (valore = PUBLISH), traduzione (valore = TRANSLATION), revisione (valore = REVIEW) |
   | Menu a discesa a selezione singola | Stato attività | task-state | Authoring (valore = AUTHOR), pubblicazione (valore = PUBLISH), traduzione (valore = TRANSLATION), revisione (valore = REVIEW) |
   | Testo con formattazione | Elenco autori | author-list | - |
   | Testo con formattazione | Elenco revisori | reviewer-list | - |
   | Testo su riga singola | URL di revisione | review-url | - |
   | Testo su riga singola | URL attività | task-url | - |
   | Testo su riga singola | Oggetto e-mail | oggetto e-mail | - |

>[!NOTE]
>
> * Nella tabella precedente, le scelte rappresentano le opzioni disponibili nel campo **Tipo di attività**. Per ogni opzione è necessario specificare il **nome attività** e il **valore attività**. Il nome e i valori per ogni tipo di attività devono essere esattamente gli stessi indicati nella tabella precedente. Ad esempio, per il tipo di attività Autore, fornisci **Authoring** come nome e **AUTHOR** come valore corrispondente.
> * Quando lavori con i servizi locali, assicurati sempre che `localhost` sia sostituito con l&#39;indirizzo del server corretto nella configurazione **Day CQ Link Externalizer** per ricevere correttamente il collegamento dell&#39;attività risolto nelle notifiche e-mail.
> * Durante la creazione di un&#39;attività di revisione in Workfront, gli utenti (autori o revisori) devono far parte del gruppo **workflow-users**. Inoltre, come **Autore** devi far parte del gruppo **autori** e **autori**, mentre come **Revisore** devi far parte del gruppo **revisori**.


## Introduzione

Per configurare Adobe Workfront in Experience Manager Guides, effettua le seguenti operazioni.

1. Apri il **pannello Strumenti** e seleziona **Guide**.
2. Selezionare **Configura Workfront**.

   Viene visualizzata la pagina **Configurazione Workfront**.

   ![](assets/configure-workfront-page.png)

3. Nella pagina **Configurazione Workfront**, immetti l&#39;URL completo del dominio Workfront, dell&#39;ID client e della chiave del segreto client dell&#39;organizzazione.

   Per accedere alla chiave **ID client** e **Segreto client** configurate nella configurazione di Adobe Workfront, passa a `Setup >> Systems>> oAuth2 Applications`.

   Per ulteriori dettagli sulla configurazione del dominio Adobe Workfront, vedi la sezione Flusso del codice di autorizzazione in [Creare applicazioni OAuth2 per le integrazioni Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/configure-integrations/create-oauth-application#create-an-oauth2-application-using-user-credentials-authorization-code-flow).

4. Seleziona **Accesso e verifica**.

   Viene visualizzata nuovamente la pagina di accesso di Adobe Workfront.
5. Accedi con il tuo indirizzo e-mail Adobe Workfront, quindi seleziona **Consenti accesso** per consentire all&#39;applicazione Oauth2 di accedere al tuo account Adobe Workfront.

   Verrai automaticamente reindirizzato alla pagina di configurazione di Workfront in Experience Manager Guides.

6. Nell’elenco a discesa del modulo personalizzato, seleziona il modulo personalizzato Adobe Workfront creato per Experience Manager Guides. Visualizza [Prerequisiti](#prerequisites).
7. Seleziona **Salva e chiudi** per applicare e salvare le modifiche alla configurazione di Workfront.

Una volta configurati, [aggiungi gli utenti ad Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) utilizzando gli stessi indirizzi e-mail di Experience Manager Guides.
