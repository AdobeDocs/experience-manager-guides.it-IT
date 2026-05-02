---
title: Configurare Replica DITA Assets per Cloud Service
description: Scopri come configurare la replica delle risorse dita per Cloud Service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 1eafc6b2-2b85-486a-bb2c-0038fae1fef9
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 3%

---

# Configurare la replica delle risorse DITA

Per configurare la funzione di elaborazione delle risorse, effettua le seguenti operazioni:

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](../cs-install-guide/download-install-additional-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Valore predefinito:** &quot;true&quot; |
