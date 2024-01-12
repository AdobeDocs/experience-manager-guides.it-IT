---
title: Sostituzioni configurazione
description: Scopri come eseguire le sostituzioni della configurazione
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 0%

---

# Sostituzioni configurazione {#id216IFC003XA}

Per apportare qualsiasi aggiornamento alla configurazione, si deve utilizzare il seguente approccio generico:

1. Accedi all’archivio Git di Cloud Manager.

1. Crea un nuovo file JSON nella posizione seguente:

   src/main/content/jcr\_root/apps/fmditaCustom/config/

1. Denomina il file nel formato seguente:

   $\{PID\}.cfg.json

   In questo caso, il PID è l’ID processo della configurazione.

1. Aggiungi le proprietà nel file JSON utilizzando il seguente formato:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Apporta le modifiche ed esegui la pipeline di Cloud Manager per distribuire la configurazione aggiornata.


**Argomento padre:**[ Scarica e installa](download-install.md)
