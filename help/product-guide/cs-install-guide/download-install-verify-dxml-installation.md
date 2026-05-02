---
title: Verificare l’installazione di AEM Guides
description: Scopri come verificare l’installazione di AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

---

# Verificare l’installazione di AEM Guides {#id213BD030FBE}

Dopo aver installato AEM Guides, è necessario verificare se l’installazione è stata eseguita correttamente o meno. Per verificare l’installazione, effettua le seguenti operazioni:

1. Accedi al Developer Console del Cloud Service.

   Per informazioni dettagliate sull&#39;accesso a Developer Console, consulta [Accesso a Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) nella documentazione di AEM.

1. Accedi all’elenco dei bundle OSGi in AEM.

   Per informazioni dettagliate sull&#39;accesso ai bundle, vedi [Bundle](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) nella documentazione di AEM.

1. Cerca fmdita nell’elenco dei bundle e controllane lo stato.

   Lo stato deve mostrare *Attivo* per i bundle distribuiti correttamente. Se uno dei bundle non ha uno stato Attivo, controlla i registri di AEM per risolvere il problema di installazione.


**Argomento padre:**[ Scarica e installa](download-install.md)
