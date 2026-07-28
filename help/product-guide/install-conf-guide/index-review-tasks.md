---
title: Esegui l'indicizzazione per includere tutte le attività di revisione nel pannello Commenti
description: Scopri come indicizzare le attività di revisione esistenti in modo che vengano visualizzate insieme a quelle più recenti nel menu a discesa delle attività di revisione del pannello Commenti.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 7d0c757b647a2e6c5e563f0ed7db6a7225769033
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
