---
title: Disinstallare le guide AEM
description: Scopri come disinstallare le guide AEM
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Disinstallare le guide AEM {#id21BHG0C0SXA}

Puoi disinstallare le guide AEM utilizzando Gestione pacchetti CRX. Durante la disinstallazione, il contenuto dell’archivio viene ripristinato allo snapshot creato immediatamente prima dell’installazione del pacchetto.

Per disinstallare le guide AEM, effettua le seguenti operazioni:

1. Accedi all’istanza AEM e passa a Gestione pacchetti CRX. L’URL predefinito per accedere al gestore di pacchetti è:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Cercare il pacchetto com.adobe.fmdita.
1. Fai clic sul pacchetto per espanderlo.
1. Clic **Altro** per aprire il menu a discesa.
1. Clic **Disinstalla** e attendi il completamento della disinstallazione.
1. Se non è più necessario, fare clic su **Elimina** dopo la disinstallazione del pacchetto.

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

1. Clic **Annulla validità cache**.
1. Pulisci la cache del browser.

**Argomento padre:**[ Scarica e installa](download-install.md)
