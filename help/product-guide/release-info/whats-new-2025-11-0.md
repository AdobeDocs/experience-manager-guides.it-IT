---
title: Note sulla versione | Novità di Adobe Experience Manager Guides versione 2025.11.0
description: Scopri le funzioni nuove e migliorate della versione 2025.11.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: a13fdb36efb5cfb548f8e128977469763836537a
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 3%

---

# Novità della versione 2025.11.0 (novembre 2025)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2025.11.0 di Adobe Experience Manager Guides as a Cloud Service.

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2025.11.0](fixed-issues-2025-11-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.11.0](../release-info/upgrade-instructions-2025-11-0.md).


## Introduzione di un nuovo archivio sulla pagina Home e di un’esperienza di ricerca avanzata

L’archivio, ora accessibile direttamente dalla home page, funge da spazio centralizzato per migliorare la reperibilità di cartelle e file. Sono disponibili **il pannello di navigazione delle cartelle** dedicato e una **visualizzazione tabulare personalizzabile dell&#39;archivio**. La rinnovata esperienza di ricerca e filtro semplifica notevolmente la ricerca e l’individuazione dei file. Per ulteriori dettagli, visualizzare [Conoscere l&#39;interfaccia dell&#39;archivio](../user-guide/home-page-repository-view.md).

![](assets/repository-view-home.png){align="left"}

Nell’editor, l’esperienza di ricerca e filtro per i file è ora coerente con la pagina Home. Per visualizzare i risultati della ricerca viene introdotto un nuovo [pannello di ricerca](../user-guide/search-panel-explorer.md) che si trova nella parte inferiore dell&#39;interfaccia dell&#39;editor. Inoltre, il repository è ora rinominato in **Explorer** nell&#39;editor, consentendo di sfogliare cartelle e file come prima.

![](assets/search-panel-explorer.png){align="left"}


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




