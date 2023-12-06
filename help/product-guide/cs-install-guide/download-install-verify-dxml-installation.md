---
title: Verificare l'installazione delle guide AEM
description: Scopri come verificare l’installazione delle guide AEM
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Verificare l&#39;installazione delle guide AEM {#id213BD030FBE}

Dopo aver installato le guide AEM, è necessario verificare se l&#39;installazione è stata eseguita correttamente o meno. Per verificare l’installazione, effettua le seguenti operazioni:

1. Accedi alla Console per sviluppatori del tuo Cloud Service.

   Per informazioni dettagliate sull’accesso a Console sviluppatori, consulta [Accesso a Console sviluppatori](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) nella documentazione AEM.

1. Accedi all’elenco dei bundle OSGi in AEM.

   Per informazioni dettagliate sull’accesso ai bundle, consulta [Bundle](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) nella documentazione AEM.

1. Cerca fmdita nell’elenco dei bundle e controllane lo stato.

   Lo stato dovrebbe mostrare *Attivo* per i bundle distribuiti correttamente. Se uno dei bundle non ha uno stato Attivo, controlla i registri AEM per risolvere il problema di installazione.


**Argomento padre:**[ Scarica e installa](download-install.md)
