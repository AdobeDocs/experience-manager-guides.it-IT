---
title: PDF nativo | Configurare la posizione di output di base per la pubblicazione di PDF for Cloud Services
description: Configurare la posizione di output di base per la pubblicazione di PDF for Cloud Services
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: ab6f1f09de2ef758d7f05ba0a49194ac9f387dea
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Configurare la posizione di output di base per l’output di pubblicazione per i servizi cloud

Per configurare la posizione di output di base, effettuare le seguenti operazioni:

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](../cs-install-guide/download-install-additional-config-override.md) per creare il file di configurazione.

1. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare il percorso di output di base:

   | PID | Chiave proprietà | Valore proprietà |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Valore predefinito:** &quot;/content/dam/fmdita-outputs&quot; |
