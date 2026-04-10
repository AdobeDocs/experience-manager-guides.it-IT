---
title: Installare Adobe Experience Manager
description: Scopri come installare Adobe Experience Manager
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Installare Adobe Experience Manager {#id213BCI020E8}

AEM Guides è un plug-in che viene installato su Adobe Experience Manager. L’installazione di AEM richiede la comprensione di alcuni concetti di base di AEM e scenari di distribuzione consigliati. Le seguenti risorse di collegamento ti aiuteranno a iniziare l’installazione di AEM:

- [Concetti di base di AEM](https://helpx.adobe.com/it/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

- [Distribuzioni consigliate di AEM](https://helpx.adobe.com/it/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)

>[!IMPORTANT]
>
> Se utilizzi Java 11 con AEM 6.5.x, potresti riscontrare un problema - *JDK 11 causa`NoClassDefFoundError`*. Per risolvere il problema, consulta l’articolo [JDK 11, NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html).

Dopo aver identificato la strategia di distribuzione più adatta all&#39;organizzazione, eseguire il processo di installazione come descritto nella sezione *[Guida introduttiva](https://helpx.adobe.com/it/experience-manager/6-5/sites/deploying/using/deploy.html#GettingStarted)* della documentazione di AEM.

Se prevedi di aggiornare l’istanza di AEM, devi seguire la sequenza indicata:

1. Disinstalla AEM Guides.
1. Aggiorna l’istanza di AEM.
1. Reinstalla AEM Guides.

>[!IMPORTANT]
>
> È possibile prendere in considerazione una serie di raccomandazioni sull&#39;ottimizzazione delle prestazioni per migliorare le prestazioni del sistema. Per ulteriori informazioni, vedere [Consigli per l&#39;ottimizzazione delle prestazioni](./perf-optimization-on-prem.md).
