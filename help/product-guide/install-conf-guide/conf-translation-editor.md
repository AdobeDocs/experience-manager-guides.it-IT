---
title: Configurare la funzione di traduzione nell’editor
description: Scopri come configurare la funzione di traduzione nell’editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 22d7e1c7-2059-43fb-b7aa-3ae4a6072678
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
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

**Argomento padre:**[ Personalizza editor](customize-overview.md)
