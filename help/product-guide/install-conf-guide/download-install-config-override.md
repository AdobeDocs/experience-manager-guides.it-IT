---
title: Sostituzioni di configurazione per Cloud Service
description: Scopri come eseguire le sostituzioni della configurazione
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---

# Sostituzioni di configurazione per Cloud Service {#id216IFC003XA}

Per apportare qualsiasi aggiornamento alla configurazione in Experience Manager Guides as a Cloud Service, è necessario utilizzare il seguente approccio generico:

1. Accedi all’archivio Git di Cloud Manager.

1. Crea un nuovo file JSON nella posizione seguente:

   `src/main/content/jcr\_root/apps/fmditaCustom/config/`

1. Denomina il file nel formato seguente:

   `$\{PID\}.cfg.json`

   In questo caso, il PID è l’ID processo della configurazione.

1. Aggiungi le proprietà nel file JSON utilizzando il seguente formato:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Apporta le modifiche ed esegui la pipeline Cloud Manager per distribuire la configurazione aggiornata.

