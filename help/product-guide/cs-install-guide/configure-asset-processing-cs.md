---
title: Configurare l’elaborazione delle risorse per Cloud Service
description: Scopri come configurare l’elaborazione delle risorse per Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 219a096f-4087-489f-9b3b-104864817198
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 3%

---

# Configurare la funzione di elaborazione delle risorse

Per configurare la funzione di elaborazione delle risorse, effettua le seguenti operazioni:

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](../cs-install-guide/download-install-additional-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Valore predefinito:** &quot;true&quot; |
