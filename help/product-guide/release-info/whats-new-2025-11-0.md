---
title: Note sulla versione | Novità della versione 2025.11.0 di Adobe Experience Manager Guides
description: Scopri le funzioni nuove e migliorate della versione 2025.11.0 di Adobe Experience Manager Guides
role: Leader
exl-id: 270a5faa-a16f-4939-900e-3c6c54660d2c
TQID: https://experienceleague.adobe.com/IuRSYXzBeHanuEsfc3-dPZuIGW3r67zPMeBILR34FvA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 3%

---

# Novità della versione 2025.11.0 (novembre 2025)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2025.11.0 di Adobe Experience Manager Guides as a Cloud Service.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2025.11.0](fixed-issues-2025-11-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.11.0](../release-info/upgrade-instructions-2025-11-0.md).


## Introduzione di un nuovo archivio sulla pagina Home e di un’esperienza di ricerca avanzata

L’archivio, ora accessibile direttamente dalla home page, funge da spazio centralizzato per migliorare la reperibilità di cartelle e file. Sono disponibili **il pannello di navigazione delle cartelle** dedicato e una **visualizzazione tabulare personalizzabile dell&#39;archivio**. La rinnovata esperienza di ricerca e filtro semplifica notevolmente la ricerca e l’individuazione dei file. Per ulteriori dettagli, visualizzare [Conoscere l&#39;interfaccia dell&#39;archivio](../user-guide/home-page-repository-view.md).

![](assets/repository-view-home.png)

Nell’editor, l’esperienza di ricerca e filtro per i file è ora coerente con la pagina Home. Per visualizzare i risultati della ricerca viene introdotto un nuovo [pannello di ricerca](../user-guide/search-panel-explorer.md) che si trova nella parte inferiore dell&#39;interfaccia dell&#39;editor. Inoltre, il repository è ora rinominato in **Explorer** nell&#39;editor, consentendo di sfogliare cartelle e file come prima.

![](assets/search-panel-explorer.png)


## Indicizzazione migliorata per suggerimenti avanzati nell’Assistente IA

Ora è possibile tracciare facilmente lo stato di ogni tentativo di indicizzazione di suggerimenti avanzati in AI Assistant con nuovi indicatori di stato: Indicizzazione completata, Non sincronizzato, In corso e Indicizzazione non riuscita. L’ultima marca temporale di indicizzazione viene ora registrata a livello del profilo della cartella per una migliore tracciabilità. Inoltre, quando si specifica una cartella o un percorso di file per l’indicizzazione, vengono applicate le restrizioni per le cartelle padre-figlio.

Per ulteriori dettagli, visualizzare [Configurare l&#39;Assistente di intelligenza artificiale per la Guida e l&#39;authoring](../cs-install-guide/conf-folder-level.md#configure-ai-assistant-for-smart-help-and-authoring).

## Miglioramenti delle prestazioni

### Pulizia automatizzata dell&#39;albero B per prestazioni ottimali

Per mantenere l&#39;efficienza del sistema e prevenire la congestione delle risorse, un nuovo processo di background ripulisce regolarmente gli alberi B a livello di sistema. In questo modo, le risorse che non esistono più o che sono state aggiunte temporaneamente non occupano spazio superfluo.

Il sistema identifica in modo intelligente i candidati per la pulizia ed esegue la rimozione automatica. Inoltre, questa funzione è configurabile e consente agli amministratori di controllarne il comportamento in base alle esigenze operative.

Per ulteriori dettagli, visualizzare [Configura pulizia albero B](../cs-install-guide/configure-btree-cleanup-cs.md).

### Gestione migliorata delle mappe DITA con un numero elevato di chiavi

È ora possibile lavorare senza problemi con le mappe DITA che contengono un numero elevato di chiavi. Questo miglioramento garantisce un caricamento più rapido e prestazioni migliori, semplificando la gestione di mappe complesse senza interruzioni.

Dopo l’aggiornamento della build, il sistema potrebbe notare un aumento temporaneo del carico, che causa un ritardo nella post-elaborazione dei nuovi dati caricati. Ciò è dovuto all&#39;esecuzione in background di uno script in esecuzione una tantum automatico. Al termine dello script, le prestazioni del sistema torneranno alla normalità.

### Elaborazione delle risorse migliorata

È stato introdotto un processo automatizzato per mantenere aggiornate le risorse in `/content/dam`. Il sistema attiva la rielaborazione delle risorse ogni 15 minuti. Durante ogni ciclo, le risorse aggiunte o non elaborate nell’intervallo di 15 minuti più recente vengono prelevate e rielaborate, migliorando l’efficienza e la coerenza nell’archivio dei contenuti.

Per ulteriori dettagli, visualizza [Elabora risorse](../user-guide/asset-processor.md).
