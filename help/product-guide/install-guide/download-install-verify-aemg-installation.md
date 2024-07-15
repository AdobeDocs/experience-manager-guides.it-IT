---
title: Verificare l’installazione di AEM Guides
description: Scopri come verificare l’installazione di AEM Guides
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Verificare l’installazione di AEM Guides {#id213BD030FBE}

Dopo aver installato AEM Guides, è necessario verificare se l’installazione è stata eseguita correttamente o meno. Per verificare il processo di installazione, effettuare le seguenti operazioni:

1. Accedi all’istanza dell’AEM e passa alla pagina dei bundle della console web AEM. L’URL predefinito per accedere alla pagina dei bundle è:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Viene visualizzato un elenco di bundle.

1. Filtrare l&#39;elenco dei bundle immettendo fmdita nella casella di testo di filtro e premere **Invio**.

   L’elenco dei bundle viene filtrato in modo da mostrare i bundle installati da AEM Guides. Se l&#39;installazione è riuscita, tutti i bundle installati avranno un **Status** di **Active**.

   Se uno dei bundle non ha uno stato **Attivo**, controlla i registri AEM per risolvere il problema di installazione.


>[!IMPORTANT]
>
> È possibile prendere in considerazione una serie di raccomandazioni sull&#39;ottimizzazione delle prestazioni per migliorare le prestazioni del sistema. Per ulteriori informazioni, vedere [Recommendations per l&#39;ottimizzazione delle prestazioni](download-install-recommend-perf-optimiz.md#).

**Argomento padre:**[ Scarica e installa](download-install.md)
