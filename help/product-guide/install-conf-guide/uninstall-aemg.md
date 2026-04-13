---
title: Disinstallare AEM Guides
description: Scopri come disinstallare AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 84b248da-af7b-4811-a184-4ab17838faaa
source-git-commit: 2749c0df3bd5640c9491dce3ab6c96f707625969
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Disinstallare AEM Guides per on-premise{#id21BHG0C0SXA}

È possibile disinstallare AEM Guides for On-Premise utilizzando Gestione pacchetti di CRX. Durante la disinstallazione, il contenuto dell’archivio viene ripristinato allo snapshot creato immediatamente prima dell’installazione del pacchetto.

Per disinstallare AEM Guides for On-Premise, effettua le seguenti operazioni:

1. Accedi all’istanza di AEM e passa a Gestione pacchetti CRX. L’URL predefinito per accedere al gestore di pacchetti è:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Cerca il pacchetto `com.adobe.fmdita`.
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
