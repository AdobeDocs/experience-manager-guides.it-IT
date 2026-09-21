---
title: Note sulla versione | Novità di Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Scopri le funzioni nuove e migliorate di Adobe Experience Manager Guides 5.2.0 Service Pack 1
role: Leader
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 788d0b9a2e2f07d2990bcc4f984f3ba4a4aabf17
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%
---
# Novità della versione 5.2.0 Service Pack 1 (settembre 2026)

Questo articolo descrive le nuove funzioni introdotte con la versione 5.2.0 Service Pack 1 di Adobe Experience Manager Guides.

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 5.2.0 Service Pack 1](fixed-issues-5-2-0-sp1.md).

Informazioni sulle [istruzioni di aggiornamento per la versione 5.2.0 Service Pack 1](../release-info/upgrade-instructions-5-2-0-sp1.md).


## Experience Manager Guides aggiunge il supporto MCP

Experience Manager Guides ora supporta il protocollo MCP (Model Context Protocol). Puoi collegare i tuoi strumenti di intelligenza artificiale come Claude, Cursore e altri a Guide senza richiedere alcun lavoro personalizzato. Attraverso un singolo endpoint MCP, in questa versione, gli utenti autenticati possono utilizzare le Guide come sistema headless e gestire argomenti e mappe, creare ed esportare linee di base e generare rapporti, il tutto con le autorizzazioni AEM esistenti. Questo consente ai team di documentazione di lavorare in modo più efficiente utilizzando applicazioni e agenti di intelligenza artificiale.

Per ulteriori dettagli, visualizzare [Utilizzo di Adobe Experience Manager Guides MCP Server](../install-conf-guide/conf-aem-guides-mcp.md).


## Il supporto per origini dati e citazioni esterne è ora disponibile nel nuovo editor

Il nuovo editor ora supporta due funzionalità Experience Manager Guides esistenti: la possibilità di connettersi con origini dati esterne e utilizzare citazioni nei documenti.

Gli autori possono continuare a utilizzare origini dati esterne configurate durante la creazione o l’aggiornamento del contenuto nel nuovo editor. Le citazioni sono inoltre supportate, in modo che gli autori possano aggiungere e gestire riferimenti nei contenuti senza dover cambiare editor.

## Supporto per lo stile di citazione AMA

Experience Manager Guides ora supporta lo stile di citazione AMA (American Medical Association), estendendo la struttura di citazione esistente per soddisfare gli standard di documentazione richiesti dai clienti nei settori sanitario, normativo e delle scienze biologiche.

Quando AMA è selezionato come stile di citazione nelle **impostazioni Workspace**, le citazioni vengono formattate automaticamente in base alle linee guida AMA, inclusi il rendering numerico in apice, la numerazione sequenziale e l&#39;ordinamento accurato dell&#39;elenco di riferimenti. L&#39;opzione **Analizza citazione** nell&#39;editor è disponibile solo quando è selezionato AMA, consentendo agli autori di aggiungere e analizzare citazioni senza cambiare contesto.

Lo stile di citazione AMA è supportato nei formati di output PDF nativo e AEM Sites. Per configurare lo stile della citazione, passare a **Impostazioni Workspace** e selezionare AMA dalle opzioni di stile della citazione. Per ulteriori dettagli, visualizzare [Operazioni con le citazioni](../user-guide/web-editor-apply-citations.md).


