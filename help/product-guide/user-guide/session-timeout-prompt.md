---
title: Informazioni sui timeout di sessione in Experience Manager Guides
description: Scopri i timeout delle sessioni in Experience Manager Guides.
feature: Authoring, Publishing
role: User
exl-id: f09b1215-4753-4dfd-89ef-1629257e5efe
TQID: 'https://experienceleague.adobe.com/nrxkVxSUooy2-08PaUp1pjiH8w2kBBNGC9efarvepbQ'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%
---
# Perché Experience Manager Guides mi disconnette dopo un determinato periodo di tempo?

Experience Manager Guides termina una sessione utente dopo un determinato periodo di inattività (timeout di inattività). Questa funzionalità di disconnessione automatica è configurata in Adobe Experience Manager. Alla scadenza della sessione, viene visualizzato un avviso popup per informare l’utente della sessione scaduta. Questo avviso impedisce all’utente di apportare ulteriori modifiche al contenuto.

**Come funziona il timeout della sessione?**

Experience Manager Guides invia una richiesta in background `token.json` ogni 30 secondi per convalidare la sessione. Se la sessione è ancora attiva, viene restituito un token valido. Se la sessione è scaduta per inattività, viene restituito un token vuoto e la sessione viene considerata inattiva.

**Cosa succede alla scadenza della sessione?**

Quando viene rilevata una sessione inattiva:

- Viene visualizzato un avviso popup per segnalare che l&#39;utente è stato disconnesso.

  ![](images/sign-out-prompt.png)

- L&#39;avviso disattiva tutte le interazioni con l&#39;applicazione.

- Selezionando **OK** si aggiorna il browser e si viene reindirizzati alla pagina di accesso.
- Dopo aver effettuato l’accesso, vieni reindirizzato all’ultima pagina aperta di Experience Manager Guides.

**Passaggi successivi**

L’avviso di scadenza della sessione aiuta a prevenire la perdita di dati limitando l’opportunità di apportare modifiche all’applicazione durante una sessione inattiva. Per evitare la perdita accidentale di contenuto, si consiglia di salvare il lavoro regolarmente nell’editor, in particolare prima di uscire dal sistema per un periodo prolungato.
