---
title: Note sulla versione | Istruzioni per l’aggiornamento a Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Scopri la matrice di compatibilità e come effettuare l’aggiornamento alla versione 5.1.0 Service Pack 3 di Adobe Experience Manager Guides.
source-git-commit: 7ffaa292f2323a9d4b166ab20d20c986752c1c1d
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 3%

---

# Istruzioni per l’aggiornamento alla versione 5.1.0 Service Pack 3 (dicembre 2025)

Questo articolo descrive le istruzioni per l’aggiornamento e la matrice di compatibilità per la versione 5.1.0 Service Pack 3 di Adobe Experience Manager Guides.

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 5.1.0 Service Pack 3](../release-info/fixed-issues-5-1-0-sp3.md).

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate da Experience Manager Guides 5.1.0 Service Pack 3 release.

| AEM Guides | Versione di AEM | Service Pack |
| --- | --- | --- |
| 5.1.0 Service Pack 3 (UUID) | 6.5 LTS | 1 |
| 5.1.0 Service Pack 3 (UUID) | 6,5 | 23, 22, 21 |

Per ulteriori dettagli, consulta la sezione [Requisiti tecnici](../install-guide/download-install-technical-requirements.md) nella Guida all&#39;installazione e alla configurazione on-premise.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione | FMPS | FM |
| --- | --- | --- |
| 5.1.0 Service Pack 3 (UUID) | Funzione supportata | 2022 o versione successiva |

### Connettore ossigeno

| Versione | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.1.0 Service Pack 3 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti per componenti Experience Manager Guides per Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Nuova versione del modello del sito AEM

| AEM Guides | Versione AEM | Versione componenti | Versione sito |
|---|---|---| ---|
| 5.1.0 Service Pack 3 UUID | 6.5 LTS | guides-components.all-1.4.1 | aemg-docs.all-1.2.0 |
| 5.1.0 Service Pack 3 UUID | 6,5 | guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |


## Prerequisiti

In base al comportamento DITA standard, l&#39;attributo scope=`external` non deve essere applicato ai collegamenti interni, in quanto è destinato solo a riferimenti a risorse esterne. L’applicazione di questo attributo ai collegamenti interni potrebbe interrompere i flussi di lavoro. Per il contenuto gestito in Experience Manager Guides, utilizzare invece l&#39;ambito predefinito=`local` o i riferimenti basati su chiave.

## Aggiornamento alla versione 5.1.0 Service Pack 3 di Experience Manager Guides

Puoi aggiornare facilmente la versione corrente di Experience Manager Guides alla versione 5.1.0 Service Pack 3 in **AEM 6.5** o **AEM 6.5 LTS**.

>[!NOTE]
>
> Se sei attualmente in AEM 6.5 e prevedi di passare ad AEM 6.5 LTS, visualizza [Aggiornamento a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/it/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Prima di procedere con l&#39;aggiornamento alla versione 5.1.0 Service Pack 3 di Experience Manager Guides, è necessario considerare i punti seguenti:

- Se utilizzi le versioni 5.1.0 o 5.1.x , puoi eseguire direttamente l’aggiornamento alla versione 5.1.0 Service Pack 3.
- Se utilizzi le versioni 4.6.0, 4.6.x, 5.0.0 o 5.0.x, devi effettuare l’aggiornamento alla versione 5.1.0.
- Se utilizzi le versioni 4.6.3, 4.6.1, 4.6 o 4.4 di, devi effettuare l’aggiornamento alla versione 5.0.0.
- Se utilizzi le versioni 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 o 4.1.x, devi effettuare l’aggiornamento alla versione 4.4 prima di eseguire l’aggiornamento alla versione 5.0.0.
- Se utilizzi la versione 4.0, devi effettuare l’aggiornamento alla versione 4.2 prima di passare alla versione 4.3.x.
- Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
- Se utilizzi una versione precedente alla 3.8.5, consulta la sezione Aggiornamento di Experience Manager Guides nella guida all&#39;installazione specifica per il prodotto, disponibile in [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/it/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
> È necessario installare AEM Service Pack prima di aggiornare la versione di Experience Manager Guides.

Per informazioni dettagliate, visualizzare [Istruzioni per l&#39;aggiornamento per le versioni locali](../install-guide/upgrade-xml-documentation.md) di Experience Manager Guides.
