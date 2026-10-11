---
title: Configurare la funzione di traduzione nell’editor
description: Scopri come configurare la funzione di traduzione nell’editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 22d7e1c7-2059-43fb-b7aa-3ae4a6072678
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%
---
# Configurare la funzione di traduzione nell’editor per Cloud Service

L’editor fornisce una potente funzione di traduzione per tradurre il contenuto in più lingue.

Puoi utilizzare la scheda **Gestisci** nell&#39;editor per tradurre i contenuti. Questa scheda è disponibile per impostazione predefinita.

Per nascondere la scheda **Gestisci** nell&#39;editor, effettuare le seguenti operazioni:

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

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor](customize-overview.md)
