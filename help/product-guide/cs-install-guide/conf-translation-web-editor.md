---
title: Configurare la funzione di traduzione nell’editor web
description: Scopri come configurare la funzione di traduzione nell’editor web
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Configurare la funzione di traduzione nell’editor web {#id21BONI0J0YR}

L’editor web fornisce una potente funzione di traduzione per tradurre il contenuto in più lingue.

È possibile utilizzare **Gestisci** nell’Editor web per tradurre i contenuti. Questa scheda è disponibile per impostazione predefinita.

Per nascondere **Gestisci** nell&#39;Editor Web, effettuare le seguenti operazioni:

1. Accedi a **Adobe Experience Manager** come amministratore.
1. Fai clic sul pulsante **Adobe Experience Manager** collegamento in alto e scelta **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul pulsante **Profilo globale** affiancare.
1. Fai clic su **Configurazione editor XML**.
1. Fai clic su **Modifica** nella parte superiore.
1. Scarica il file `ui\_config.json` file.Rimuovere il seguente frammento di codice dal file scaricato:

   ```json
   {
       "component":"tab",
       "id":"workflow",
       "title":"Manage",
       "on-click":"APP_MODE_CHANGE",
       "items":
       [
           {
               "component":"label",
               "label":"Manage"
           }
       ]
   },
   ```

1. Carica il file ui\_config.json aggiornato.

Tieni presente che **Gestisci** Il filtro non è più disponibile.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
