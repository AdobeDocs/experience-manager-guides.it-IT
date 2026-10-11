---
title: Distribuzione dell’indicizzazione personalizzata per la configurazione locale
description: Scopri come personalizzare il contenuto dell’indice per la configurazione locale
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 5b9e4936-f674-41d3-a7b2-3d42a2523693
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
source-wordcount: '132'
ht-degree: 0%
---
# Reindicizzazione per la funzione Trova e sostituisci (visualizzazione Source)

La reindicizzazione è necessaria per abilitare la funzionalità **Trova e sostituisci (visualizzazione Source)**, che consente di analizzare l&#39;intero contenuto visibile nella visualizzazione Autore e anche il contenuto Source sottostante (struttura XML, inclusi elementi, tag e valori di attributi) per la stringa cercata.

## Reindicizzazione

Per le impostazioni on-premise, la definizione dell’indice è inclusa nel pacchetto. Per abilitare la funzione, devi reindicizzare il contenuto.

Avviare la reindicizzazione impostando la proprietà `reindex=true (Boolean)` sul nodo: ` /oak:index/guidesAssetLucene` per reindicizzare il contenuto acquisito in precedenza.

Il processo di reindicizzazione continuerà fino a quando il sistema non riassegnerà automaticamente questa proprietà a false. Puoi monitorare l’avanzamento dell’operazione di reindicizzazione nei registri di sistema.
