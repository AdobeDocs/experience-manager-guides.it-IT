---
title: Installare Adobe Experience Manager
description: Scopri come installare Adobe Experience Manager
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: d72b007c-9f0a-41be-bca2-2d6b54c30de1
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%
---
# Installare Adobe Experience Manager {#id213BCI020E8}

AEM Guides è un plug-in che viene installato su Adobe Experience Manager. L’installazione di AEM richiede la comprensione di alcuni concetti di base di AEM e scenari di distribuzione consigliati. Le seguenti risorse di collegamento ti aiuteranno a iniziare l’installazione di AEM:

- [Concetti di base di AEM](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

- [Distribuzioni consigliate di AEM](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)

>[!IMPORTANT]
>
> Se utilizzi Java 11 con AEM 6.5.x, potresti riscontrare un problema - *JDK 11 causa`NoClassDefFoundError`*. Per risolvere il problema, consulta l’articolo [JDK 11, NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html).

Dopo aver identificato la strategia di distribuzione più adatta all&#39;organizzazione, eseguire il processo di installazione come descritto nella sezione *[Guida introduttiva](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#GettingStarted)* della documentazione di AEM.

Se prevedi di aggiornare l’istanza di AEM, devi seguire la sequenza indicata:

1. Disinstalla AEM Guides.
1. Aggiorna l’istanza di AEM.
1. Reinstalla AEM Guides.

>[!IMPORTANT]
>
> È possibile prendere in considerazione una serie di raccomandazioni sull&#39;ottimizzazione delle prestazioni per migliorare le prestazioni del sistema. Per ulteriori informazioni, vedere [Consigli per l&#39;ottimizzazione delle prestazioni](./perf-optimization-on-prem.md).
