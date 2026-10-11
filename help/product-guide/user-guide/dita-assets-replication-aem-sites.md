---
title: Gestire la replica delle risorse di origine DITA
description: Scopri come eseguire la replica delle risorse di origine DITA
feature: Publishing
role: User
exl-id: 71aec782-2cc1-4fd5-b35b-97a603c3dd48
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%
---
# Gestire la replica delle risorse di origine DITA

Quando l&#39;output generato dal contenuto DITA viene pubblicato utilizzando **Pubblicazione rapida** o **Gestisci pubblicazione** in alcuni ambienti di pubblicazione, AEM tenta anche di pubblicare le risorse di origine DITA associate, ad esempio le mappe DITA e, in alcuni casi, gli argomenti DITA. Ciò si verifica perché AEM tratta le risorse DITA come dipendenze delle pagine Sites generate.

![](images/quick-publish-site-instance.png){width="350"}

Per evitare la replica involontaria del contenuto DITA nell&#39;ambiente di pubblicazione e problemi di prestazioni, gli amministratori devono gestire in modo esplicito la replica delle risorse DITA tramite Configuration Manager. Questa configurazione consente agli amministratori di controllare la replica dei tipi di risorse DITA supportati, tra cui mappe DITA, argomenti DITA, file XML e file Markdown (.md).

Per configurare la funzionalità di replica delle risorse DITA, visualizzare [Configurare la replica delle risorse DITA per Cloud Service](../cs-install-guide/configure-dita-assets-replication.md) o [Configurare la replica delle risorse DITA per On-Premise](../install-guide/configure-dita-asset-replication.md) in base alla configurazione in uso
