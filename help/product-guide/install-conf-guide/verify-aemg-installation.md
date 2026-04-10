---
title: Verificare l’installazione di AEM Guides
description: Scopri come verificare l’installazione di AEM Guides
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Verificare l’installazione di AEM Guides {#id213BD030FBE}

Dopo aver installato AEM Guides, è necessario verificare se l’installazione è stata eseguita correttamente o meno.

Le seguenti schede forniscono istruzioni per verificare l’installazione di AEM Guides in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Per verificare l’installazione, effettua le seguenti operazioni:

1. Accedi al Developer Console del Cloud Service.

   Per informazioni dettagliate sull&#39;accesso a Developer Console, consulta [Accesso a Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=it) nella documentazione di AEM.

1. Accedi all’elenco dei bundle OSGi in AEM.

   Per informazioni dettagliate sull&#39;accesso ai bundle, vedi [Bundle](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=it#bundles) nella documentazione di AEM.

1. Cerca fmdita nell’elenco dei bundle e controllane lo stato.

   Lo stato deve mostrare *Attivo* per i bundle distribuiti correttamente. Se uno dei bundle non ha uno stato Attivo, controlla i registri di AEM per risolvere il problema di installazione.

>[!TAB On-Premise]

Per verificare l’installazione, effettua le seguenti operazioni:

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
> È possibile prendere in considerazione una serie di raccomandazioni sull&#39;ottimizzazione delle prestazioni per migliorare le prestazioni del sistema. Per ulteriori informazioni, vedere [Consigli per l&#39;ottimizzazione delle prestazioni](perf-optimization-on-prem.md#).

>[!ENDTABS]


