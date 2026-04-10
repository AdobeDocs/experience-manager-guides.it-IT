---
title: Distribuzione dell’indicizzazione personalizzata per la configurazione locale
description: Scopri come personalizzare il contenuto dell’indice per la configurazione locale
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 5b9e4936-f674-41d3-a7b2-3d42a2523693
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# Reindicizzazione per la funzione Trova e sostituisci (visualizzazione Source)

La reindicizzazione è necessaria per abilitare la funzionalità **Trova e sostituisci (visualizzazione Source)**, che consente di analizzare l&#39;intero contenuto visibile nella visualizzazione Autore e anche il contenuto Source sottostante (struttura XML, inclusi elementi, tag e valori di attributi) per la stringa cercata.

## Reindicizzazione

Per le impostazioni on-premise, la definizione dell’indice è inclusa nel pacchetto. Per abilitare la funzione, devi reindicizzare il contenuto.

Avviare la reindicizzazione impostando la proprietà `reindex=true (Boolean)` sul nodo: ` /oak:index/guidesAssetLucene` per reindicizzare il contenuto acquisito in precedenza.

Il processo di reindicizzazione continuerà fino a quando il sistema non riassegnerà automaticamente questa proprietà a false. Puoi monitorare l’avanzamento dell’operazione di reindicizzazione nei registri di sistema.
