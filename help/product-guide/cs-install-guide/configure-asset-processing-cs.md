---
title: Configurare l’elaborazione delle risorse per Cloud Service
description: Scopri come configurare l’elaborazione delle risorse per Cloud Service
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 5b29b2b5f725b5d9a2029fb232e62f387a5338fd
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
