---
title: Verificare l’installazione di AEM Guides
description: Scopri come verificare l’installazione di AEM Guides
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/sniTYknUIyJH0D1moIL3olj3AeBT08kLH52Gba27sqs
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 0%

---

# Verificare l’installazione di AEM Guides {#id213BD030FBE}

Dopo aver installato AEM Guides, è necessario verificare se l’installazione è stata eseguita correttamente o meno. Per verificare il processo di installazione, effettuare le seguenti operazioni:

1. Accedi all’istanza di AEM e passa alla pagina Bundle della console web AEM. L’URL predefinito per accedere alla pagina dei bundle è:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Viene visualizzato un elenco di bundle.

1. Filtrare l&#39;elenco dei bundle immettendo fmdita nella casella di testo di filtro e premere **Invio**.

   L’elenco dei bundle viene filtrato in modo da mostrare i bundle installati da AEM Guides. Se l&#39;installazione è riuscita, tutti i bundle installati avranno un **Status** di **Active**.

   Se uno dei bundle non ha uno stato **Attivo**, controlla i registri di AEM per risolvere il problema di installazione.


>[!IMPORTANT]
>
> È possibile prendere in considerazione una serie di raccomandazioni sull&#39;ottimizzazione delle prestazioni per migliorare le prestazioni del sistema. Per ulteriori informazioni, vedere [Consigli per l&#39;ottimizzazione delle prestazioni](download-install-recommend-perf-optimiz.md#).

**Argomento padre:**[ Scarica e installa](download-install.md)
