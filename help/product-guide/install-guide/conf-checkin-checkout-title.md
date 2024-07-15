---
title: Configurare il titolo per le icone Check-In e Check-Out
description: Scopri come configurare il titolo per le icone di check-in e check-out
exl-id: a8888a17-e819-4fa2-bb6f-cafe1002803a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Configurare il titolo per le icone Archivia ed Estrai

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
