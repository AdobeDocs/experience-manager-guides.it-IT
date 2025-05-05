---
title: Disinstallare AEM Guides
description: Scopri come disinstallare AEM Guides
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Disinstallare AEM Guides {#id21BHG0C0SXA}

Puoi disinstallare AEM Guides utilizzando Gestione pacchetti di CRX. Durante la disinstallazione, il contenuto dell’archivio viene ripristinato allo snapshot creato immediatamente prima dell’installazione del pacchetto.

Per disinstallare AEM Guides, effettua le seguenti operazioni:

1. Accedi all’istanza dell’AEM e passa a Gestione pacchetti CRX. L’URL predefinito per accedere al gestore di pacchetti è:

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

**Argomento padre:**&#x200B;[ Scarica e installa](download-install.md)
