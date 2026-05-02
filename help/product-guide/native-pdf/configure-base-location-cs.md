---
title: PDF nativo | Configurare la posizione di output di base per la pubblicazione di PDF per i servizi cloud
description: Configurare la posizione di output di base per la pubblicazione di PDF for Cloud Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: d79085d6-938a-4e80-84a2-03562e6b76e0
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 2%

---

# Configurare la posizione di output di base per l’output di pubblicazione per i servizi cloud

Per configurare la posizione di output di base, effettuare le seguenti operazioni:

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](../cs-install-guide/download-install-additional-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare il percorso di output di base:

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Valore predefinito:** &quot;/content/dam/fmdita-outputs&quot; |
