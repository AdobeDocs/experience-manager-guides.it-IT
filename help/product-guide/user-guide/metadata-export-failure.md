---
title: L’esportazione dei metadati non riesce con l’eccezione "Stringa troppo lunga" in Experience Manager Guides
description: Scopri perché l’esportazione dei metadati può non riuscire per il contenuto delle Guide nell’interfaccia utente di Assets.
feature: Authoring, Publishing
role: User
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 1c61df4820e559417410d25c81800637481b040c
workflow-type: tm+mt
source-wordcount: 274
ht-degree: 0%

---

# Perché l’esportazione dei metadati per una cartella non riesce con l’eccezione &quot;Stringa è troppo lunga&quot;?

Quando si [esportano metadati](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/using/metadata#export-metadata) per una cartella dall&#39;interfaccia utente di Assets, il processo di esportazione può non riuscire con l&#39;eccezione `String is too long`. Ciò si verifica in genere quando la cartella contiene proprietà specifiche di Experience Manager Guides che memorizzano valori non stringa, ad esempio `baselineObj`.

**Perché questo accade?**

Alcune proprietà memorizzate nel nodo di metadati di una risorsa vengono utilizzate internamente da Experience Manager Guides e contengono dati, come oggetti JSON, anziché valori stringa semplici. Durante l&#39;esportazione dei metadati per una cartella, se **Proprietà da esportare** è impostato su **Tutti**, il processo di esportazione tenta di convertire ogni proprietà in una stringa e non riesce nelle proprietà che contengono questo tipo di dati.

**Come si impedisce?**

Per evitare questo errore, le seguenti proprietà sono escluse dall&#39;esportazione dei metadati per impostazione predefinita nella **configurazione di Asset Metadata Exporter**:

- `baseline`
- `namedoutputs`
- `conditionpresets`
- `nextgenbaselinestore`

**È ancora possibile esportare queste proprietà?**

Sì. Se hai bisogno di una o più di queste proprietà nell&#39;esportazione, puoi modificare la **Configurazione di Asset Metadata Exporter** e rimuoverle dall&#39;elenco di esclusione.

La rimozione di una proprietà dall’elenco di esclusione non garantisce la riuscita dell’esportazione. A seconda delle dimensioni e del contenuto dei dati sottostanti, il processo potrebbe comunque non riuscire con la stessa eccezione. Se riscontri questo problema dopo aver riattivato una proprietà, aggiungilo nuovamente all’elenco di esclusione per ripristinare il comportamento di esportazione predefinito e affidabile.
