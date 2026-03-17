---
title: Gestire la replica delle risorse di origine DITA
description: Scopri come eseguire la replica delle risorse di origine DITA
feature: Publishing
role: User
source-git-commit: 52921a33d30817434424772ff32b1b31d4878497
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Gestire la replica delle risorse di origine DITA

Quando l&#39;output generato dal contenuto DITA viene pubblicato utilizzando **Pubblicazione rapida** o **Gestisci pubblicazione** in alcuni ambienti di pubblicazione, AEM tenta anche di pubblicare le risorse di origine DITA associate, ad esempio le mappe DITA e, in alcuni casi, gli argomenti DITA. Ciò si verifica perché AEM tratta le risorse DITA come dipendenze delle pagine Sites generate.

![](images/quick-publish-site-instance.png){width="350" align="left"}

Per evitare la replica involontaria del contenuto DITA nell&#39;ambiente di pubblicazione e problemi di prestazioni, gli amministratori devono gestire in modo esplicito la replica delle risorse DITA tramite Configuration Manager. Questa configurazione consente agli amministratori di controllare la replica dei tipi di risorse DITA supportati, tra cui mappe DITA, argomenti DITA, file XML e file Markdown (.md).

Per configurare la funzionalità di replica delle risorse DITA, visualizzare [Configurare la replica delle risorse DITA per Cloud Service](../cs-install-guide/configure-dita-assets-replication.md) o [Configurare la replica delle risorse DITA per On-Premise](../install-guide/configure-dita-asset-replication.md) in base alla configurazione in uso

