---
title: Configurare la funzione di traduzione nell’editor web
description: Scopri come configurare la funzione di traduzione nell’editor web
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/7-SFQ0FXQ6bGo3pjAOK-18sEsU4-zriruioG2nMx2o0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9baid: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 154
ht-degree: 0%

---

# Configurare la funzione di traduzione nell’editor web {#id21BONI0J0YR}

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

**Argomento padre:**[ Personalizza editor Web](conf-web-editor.md)
