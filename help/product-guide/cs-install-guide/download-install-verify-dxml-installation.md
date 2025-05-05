---
title: Verificare l’installazione di AEM Guides
description: Scopri come verificare l’installazione di AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Verificare l’installazione di AEM Guides {#id213BD030FBE}

Dopo aver installato AEM Guides, è necessario verificare se l’installazione è stata eseguita correttamente o meno. Per verificare l’installazione, effettua le seguenti operazioni:

1. Accedi al Developer Console del tuo Cloud Service.

   Per informazioni dettagliate sull&#39;accesso a Developer Console, vedere [Accesso a Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=it) nella documentazione AEM.

1. Accedi all’elenco dei bundle OSGi in AEM.

   Per informazioni dettagliate sull&#39;accesso ai bundle, vedi [Bundle](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=it#bundles) nella documentazione AEM.

1. Cerca fmdita nell’elenco dei bundle e controllane lo stato.

   Lo stato deve mostrare *Attivo* per i bundle distribuiti correttamente. Se uno dei bundle non ha uno stato Attivo, controlla i registri AEM per risolvere il problema di installazione.


**Argomento padre:**&#x200B;[ Scarica e installa](download-install.md)
