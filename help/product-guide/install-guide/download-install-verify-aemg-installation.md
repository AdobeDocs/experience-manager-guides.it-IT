---
title: Verificare l'installazione delle guide AEM
description: Scopri come verificare l’installazione delle guide AEM
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Verificare l&#39;installazione delle guide AEM {#id213BD030FBE}

Dopo aver installato le guide AEM, è necessario verificare se l&#39;installazione è stata eseguita correttamente o meno. Per verificare il processo di installazione, effettuare le seguenti operazioni:

1. Accedi all’istanza dell’AEM e passa alla pagina dei bundle della console web AEM. L’URL predefinito per accedere alla pagina dei bundle è:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Viene visualizzato un elenco di bundle.

1. Filtrare l&#39;elenco dei bundle immettendo fmdita nella casella di testo di filtraggio e premendo **Invio**.

   L’elenco dei bundle viene filtrato in modo da mostrare i bundle installati dalle Guide AEM. Se l’installazione è andata a buon fine, tutti i bundle installati avranno **Stato** di **Attivo**.

   Se uno dei bundle non ha un **Attivo** stato, quindi controlla i registri AEM per risolvere il problema di installazione.


>[!IMPORTANT]
>
> È possibile prendere in considerazione una serie di raccomandazioni sull&#39;ottimizzazione delle prestazioni per migliorare le prestazioni del sistema. Consulta [Recommendations per l&#39;ottimizzazione delle prestazioni](download-install-recommend-perf-optimiz.md#) per i dettagli.

**Argomento padre:**[ Scarica e installa](download-install.md)
