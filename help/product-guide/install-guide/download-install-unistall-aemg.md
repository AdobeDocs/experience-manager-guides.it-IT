---
title: Disinstallare AEM Guides
description: Scopri come disinstallare AEM Guides
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/W6cpFBqAnriNXNYqP6r-GZm7tJhPWnlSI53q33iduvE'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%
---
# Disinstallare AEM Guides {#id21BHG0C0SXA}

Puoi disinstallare AEM Guides utilizzando Gestione pacchetti di CRX. Durante la disinstallazione, il contenuto dell’archivio viene ripristinato allo snapshot creato immediatamente prima dell’installazione del pacchetto.

Per disinstallare AEM Guides, effettua le seguenti operazioni:

1. Accedi all’istanza di AEM e passa a Gestione pacchetti CRX. L’URL predefinito per accedere al gestore di pacchetti è:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Cercare il pacchetto com.adobe.fmdita.
1. Fai clic sul pacchetto per espanderlo.
1. Fai clic su **Altro** per aprire il menu a discesa.
1. Fare clic su **Disinstalla** e attendere il completamento della disinstallazione.
1. Se il pacchetto non è più necessario, fare clic su **Elimina** dopo aver disinstallato il pacchetto.

## Dopo la disinstallazione

Per pulire i file residui dopo la disinstallazione, effettuare le seguenti operazioni:

1. Pulisci la cache dello script utilizzando:

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. Puoi annullare la validità della cache utilizzando:

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Fare clic su **Annulla validità cache**.
1. Pulisci la cache del browser.

**Argomento padre:**&#x200B;[&#x200B; Scarica e installa](download-install.md)
