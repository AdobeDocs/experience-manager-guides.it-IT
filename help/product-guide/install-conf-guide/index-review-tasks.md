---
title: Esegui l'indicizzazione per includere tutte le attività di revisione nel pannello Commenti
description: Scopri come indicizzare le attività di revisione esistenti in modo che vengano visualizzate insieme a quelle più recenti nel menu a discesa delle attività di revisione del pannello Commenti.
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%
---
# Eseguire l&#39;indicizzazione per includere tutte le attività di revisione per un argomento nel pannello Commenti

La funzionalità [Visualizza tutte le attività di revisione per un argomento](../user-guide/review-address-review-comments.md#view-all-review-tasks-for-a-topic), disponibile nel pannello Commenti, consente agli autori di selezionare qualsiasi attività di revisione (aperta o chiusa) associata all&#39;argomento attualmente aperto, senza passare da un progetto di revisione all&#39;altro. Quando è attivato, il pannello **Commenti** nell&#39;editor include un elenco a discesa di tutte le attività di revisione di cui fa parte l&#39;argomento, insieme allo stato di ogni attività e al progetto a cui appartiene.

Per impostazione predefinita, quando questa funzione è abilitata su un’istanza, le attività di revisione vengono indicizzate durante la creazione e sono quindi automaticamente disponibili in questo elenco a discesa.

Tuttavia, se la funzione è disabilitata al momento della distribuzione di Experience Manager Guides su un’istanza, le attività di revisione create mentre rimane disabilitata non vengono indicizzate. In qualità di amministratore, se abiliti la funzione dopo che tali attività di revisione sono già presenti, tali attività non vengono visualizzate nel menu a discesa fino a quando non vengono indicizzate. Per renderle disponibili, è necessario eseguire uno script occasionale per indicizzare le attività di revisione esistenti.

Esegui il seguente comando cURL una volta per indicizzare le attività di revisione esistenti:

```bash
curl --location 'http://<host>:<port>/bin/guides/script/start' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic <base64-encoded-credentials>' \
--header 'Cookie: cq-authoring-mode=TOUCH' \
--data-urlencode 'jobType=review-topic-guids-migration'
```
