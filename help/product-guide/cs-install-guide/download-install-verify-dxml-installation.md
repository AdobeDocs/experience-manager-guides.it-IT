---
title: Verificare l’installazione di AEM Guides
description: Scopri come verificare l’installazione di AEM Guides
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/WDiYcOCdCuaJCrGYCupOS0TEk5TV-1q6Zi5z-S7KWLA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 162
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
