---
title: Note sulla versione | Istruzioni per l’aggiornamento a Adobe Experience Manager Guides versione 4.6.0
description: Scopri come effettuare l’aggiornamento alla versione 4.6.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: 1880d889dc9063ef05c4f856d6082d1ea03b7946
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 5%

---

# Istruzioni per l’aggiornamento alla versione 4.6.0 (settembre 2024)

Questo articolo descrive le istruzioni per l’aggiornamento e la matrice di compatibilità per la versione 4.6.0 di Adobe Experience Manager Guides.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 4.6.0](../release-info/whats-new-4-6.md).

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 4.6.0](../release-info/fixed-issues-4-6-0.md).

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate da Experience Manager Guides versione 4.6.0.

### Adobe Experience Manager

**4.6.0 Non UUID**
Versione 6.5 Service Pack 21, 20 e 19

**4.6.0 UUID**
Versione 6.5 Service Pack 21, 20 e 19

Per ulteriori dettagli, consulta la sezione [Requisiti tecnici](../install-guide/download-install-technical-requirements.md) nella Guida all&#39;installazione e alla configurazione on-premise.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.6.0 (non UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.3 o versione successiva |
| 4.6.0 (UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.4 o versione successiva |
| | | | |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.6.0 (non UUID) | 2,8-regular-10 | 2,8-regular-10 | 1,6 | 1,6 |
| 4.6.0 (UUID) | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   |

### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti per componenti Experience Manager Guides per Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### Nuova versione del modello del sito AEM


| Versione componenti | Versione sito |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Aggiornamento alla versione 4.6.0 di Experience Manager Guides

È possibile aggiornare facilmente la versione corrente delle Guide alla versione 4.6.0. Prima di procedere con l’aggiornamento alla versione 4.6.0 di Experience Manager Guides, è necessario considerare i seguenti punti:

- Se utilizzi le versioni 4.4, 4.3.1 o 4.3.0 , puoi eseguire direttamente l’aggiornamento alla versione 4.6.0.
- Se utilizzi le versioni 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 o 4.1.x, devi effettuare l’aggiornamento alla versione 4.4 prima di eseguire l’aggiornamento alla versione 4.6.0.
- Se utilizzi la versione 4.0, devi effettuare l’aggiornamento alla versione 4.2 prima di passare alla versione 4.3.x.
- Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
- Se utilizzi una versione precedente alla 3.8.5, consulta la sezione Aggiornamento di Experience Manager Guides nella guida all&#39;installazione specifica per il prodotto disponibile nell&#39;[archivio di Adobe Experience Manager Guides help PDF](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Prima di aggiornare la versione di Experience Manager Guides è necessario installare il service pack per AEM.

Per informazioni dettagliate, visualizzare [Istruzioni per l&#39;aggiornamento per le versioni locali](../install-guide/upgrade-xml-documentation.md) di Experience Manager Guides.