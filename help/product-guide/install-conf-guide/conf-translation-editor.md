---
title: Configurare la funzione di traduzione nell’editor web
description: Scopri come configurare la funzione di traduzione nell’editor web
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# Configurare la funzione di traduzione nell’editor web per Cloud Service

L’editor web fornisce una potente funzione di traduzione per tradurre il contenuto in più lingue.

Puoi utilizzare la scheda **Gestisci** nell&#39;editor Web per tradurre i contenuti. Questa scheda è disponibile per impostazione predefinita.

Per nascondere la scheda **Gestisci** nell&#39;editor Web, effettuare le seguenti operazioni:

1. Accedi a **Adobe Experience Manager** come amministratore.
1. Fai clic sul collegamento **Adobe Experience Manager** in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Fare clic su **Configurazione editor XML**.
1. Fai clic sull&#39;icona **Modifica** in alto.
1. Scarica il file `ui\_config.json`.Rimuovi il seguente frammento di codice dal file scaricato:

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

Il filtro **Gestisci** non è più disponibile.

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](customize-overview.md)
