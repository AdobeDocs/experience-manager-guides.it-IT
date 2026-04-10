---
title: Configurare il titolo per le icone Check-In e Check-Out
description: Scopri come configurare il titolo per le icone di check-in e check-out
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Configurare il titolo per le icone Archivia ed Estrai per On-Premise

AEM Guides consente di configurare il titolo per le icone di Check-In e Check-Out nell&#39;editor Web. Per configurare il titolo per le icone di check-in e check-out, effettuare le seguenti operazioni:

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
