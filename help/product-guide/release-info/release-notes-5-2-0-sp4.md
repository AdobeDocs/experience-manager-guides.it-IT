---
title: Note sulla versione | Note sulla versione di Adobe Experience Manager Guides 5.2.0 Service Pack 4
description: Scopri il processo di aggiornamento e le correzioni di bug nella versione 5.2.0 Service Pack 4 di Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: a232c8a03cda9b0ef7ae8114c3d901df5fb5bcb4
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 1%
---
# Note sulla versione 5.2.0 Service Pack 4 (novembre 2026)

Questo articolo fornisce informazioni sulle istruzioni di aggiornamento, sulla compatibilità di Java SDK, sui problemi risolti e sui problemi noti nella versione 5.2.0 Service Pack 4 di Adobe Experience Manager Guides.

## Risorse Java SDK

Utilizza le seguenti risorse per sviluppare plug-in Java personalizzati o integrazioni con Experience Manager Guides. Assicurati che la versione di SDK corrisponda alla versione di Experience Manager Guides installata.

| Versione | Versione Java SDK | Maven Central | Riferimento API Java |
|---|---|---|----|
| 5.2.0 Service Pack 4 (UUID) | 5.2.2 | [API SDK AEM Guides 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Per ulteriori dettagli, visualizza [Configura e utilizza l&#39;API JAR dall&#39;archivio centrale Maven](https://experienceleague.adobe.com/it/docs/experience-manager-guides/using/api-reference/introduction).

## Aggiornamento alla versione 5.2.0 Service Pack 4 di Experience Manager Guides

Scopri come installare Experience Manager Guides 5.2.0 Service Pack 4.

>[!NOTE]
>
>Questa versione è disponibile solo per AEM 6.5 LTS. Il service pack supportato è AEM 6.5 LTS Service Pack 2.

### Prerequisiti

Prima di avviare il processo di aggiornamento di Experience Manager Guides 5.2.0 Service Pack 4, verificare di utilizzare la versione 5.2.0 di Service Pack 1.

### Processo di aggiornamento per la versione 5.2.0 Service Pack 4

1. Scarica il pacchetto Experience Manager Guides versione 5.2.0 Service Pack 4.
1. Caricare il pacchetto nell&#39;istanza utilizzando Gestione pacchetti (`/crx/packmgr`).
1. Installa il pacchetto. Verificare quindi che i bundle `fmdita` siano tornati allo stato **Attivo**. È possibile controllare lo stato del bundle in `/system/console/bundles`.
1. Cancella la cache del browser.

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Quando trascini e rilasci una risorsa in una mappa dal pannello Esplora risorse che non è stata aggiornata dopo che un altro autore ha spostato tale risorsa, alla mappa viene aggiunto un riferimento interrotto. (GUIDES-57869)

### Gestione risorse

- Quando sovrascrivi una risorsa non DITA esistente, ad esempio un&#39;immagine, utilizzando l&#39;opzione **Sovrascrivi file esistenti**, la nuova versione per l&#39;immagine caricata non viene creata. Di conseguenza, l’output generato utilizzando la baseline contiene la risorsa precedente. (GUIDES-59287)

- Quando una risorsa non DITA, come un’immagine, migrata da una configurazione non UUID a una configurazione UUID viene ripristinata o diramata in un’altra versione, il relativo UUID cambia. I riferimenti esistenti alla risorsa non vengono più risolti e l’immagine appare interrotta negli argomenti che vi fanno riferimento. (GUIDES-58414)

### Pubblicazione

- Quando si pubblica una mappa durante l&#39;esportazione di altre mappe, l&#39;output utilizza in modo intermittente un formato immagine di qualità inferiore invece dell&#39;immagine vettoriale originale. (GUIDES-55221)

## Problemi noti

Adobe ha identificato il seguente problema noto nella versione 5.2.0 Service Pack 4:

- Quando si trascina e rilascia un elemento in una posizione non valida, l&#39;editor lo sposta nella posizione valida più vicina, durante la quale il riferimento può mantenere il percorso dell&#39;archivio. Analogamente, quando sostituite un riferimento esistente in una mappa DITA mediante trascinamento, il nuovo riferimento potrebbe mantenere il proprio percorso di repository. (GUIDES-60688)