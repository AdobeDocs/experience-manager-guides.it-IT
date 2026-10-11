---
title: Configurare il titolo per le icone Check-In e Check-Out
description: Scopri come configurare il titolo per le icone di check-in e check-out
exl-id: a8888a17-e819-4fa2-bb6f-cafe1002803a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/NytwQkk18-M0MpxxBP3OWg3WFJf6Oy3N5dBaiKlc6Gg'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%
---
# Configurare il titolo per le icone Archivia ed Estrai

AEM Guides consente di configurare il titolo per le icone Archivia ed Estrai nell’editor. Per configurare il titolo per le icone di check-in e check-out, effettuare le seguenti operazioni:

1. Scarica il file di configurazione dell’interfaccia utente accedendo a Adobe Experience Manager come amministratore.
1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto.
1. Nella sezione **Configurazione dell&#39;interfaccia utente dell&#39;editor XML**, fare clic sull&#39;icona **Scarica** per scaricare il file `ui_config.json` nel sistema locale.
1. Nel file `ui_config.json`, modificare il titolo nella sezione &quot;topbar&quot;. È possibile modificare i seguenti valori:

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Salva il file e caricalo.
