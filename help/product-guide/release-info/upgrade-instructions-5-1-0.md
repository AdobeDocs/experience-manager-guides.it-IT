---
title: Note sulla versione | Istruzioni per l’aggiornamento a Adobe Experience Manager Guides versione 5.1.0
description: Scopri la matrice di compatibilità e come effettuare l’aggiornamento alla versione 5.1.0 di Adobe Experience Manager Guides.
exl-id: 4b7b6756-d260-4baf-a9cb-d99fc02f020f
TQID: https://experienceleague.adobe.com/kHyj1IRvP47upA7sClT-Vl7PQAq4UD9aX8lBfL8pFRA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: afb45297-4313-4f67-818e-bc0b03abe086id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: cda0baeb-996e-4aaa-92d1-41032e34fd68id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 519
ht-degree: 7%

---

# Istruzioni per l’aggiornamento alla versione 5.1.0 (settembre 2025)

Questo articolo descrive le istruzioni per l’aggiornamento e la matrice di compatibilità per la versione 5.1.0 di Adobe Experience Manager Guides.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 5.1.0](../release-info/whats-new-5-1-0.md).

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 5.1.0](../release-info/fixed-issues-5-1-0.md).

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate da Experience Manager Guides versione 5.1.0.

| AEM Guides | Versione di AEM | Service Pack |
| --- | --- | --- |
| 5.1.0 (UUID) | 6.5 LTS | 1 |
| 5.1.0 (UUID) | 6,5 | 23, 22, 21 |

Per ulteriori dettagli, consulta la sezione [Requisiti tecnici](../install-guide/download-install-technical-requirements.md) nella Guida all&#39;installazione e alla configurazione on-premise.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione | FMPS | FM |
| --- | --- | --- |
| 5.1.0 (UUID) | Funzione supportata | 2022 o versione successiva |

### Connettore ossigeno

| Versione | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.1.0 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti per componenti Experience Manager Guides per Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Nuova versione del modello del sito AEM


| AEM Guides | Versione AEM | Versione componenti | Versione sito |
|---|---|---| ---|
| 5.1.0 UUID | 6.5 LTS | guides-components.all-1.4.1 | aemg-docs.all-1.2.0 |
| 5.1.0 UUID | 6,5 | guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |

## Aggiornamento a Experience Manager Guides 5.1.0

Puoi aggiornare facilmente la versione corrente di Experience Manager Guides alla versione 5.1.0 in **AEM 6.5** o **AEM 6.5 LTS**.

>[!NOTE]
>
> Se al momento utilizzi AEM 6.5 e prevedi di passare ad AEM 6.5 LTS, assicurati di completare l’aggiornamento ad AEM prima di procedere con l’aggiornamento a Experience Manager Guides 5.1.0. Per informazioni dettagliate, visualizzare [Aggiornamento a Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Prima di procedere con l’aggiornamento alla versione 5.1.0 di Experience Manager Guides, è necessario considerare i seguenti punti:

- Se utilizzi le versioni 4.6.3, 4.6.4, 5.0.0 o 5.0.0 Service Pack 1, puoi eseguire direttamente l’aggiornamento alla versione 5.1.0.
- Se utilizzi le versioni 4.6.0, 4.6.1, devi effettuare l’aggiornamento alla versione 4.6.3, 4.6.4 o 5.0.0 prima di eseguire l’aggiornamento alla versione 5.1.0.
- Se utilizzi le versioni 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 o 4.1.x, devi effettuare l’aggiornamento alla versione 4.4 prima di eseguire l’aggiornamento alla versione 5.1.0.
- Se utilizzi la versione 4.0, devi effettuare l’aggiornamento alla versione 4.2 prima di passare alla versione 4.3.x.
- Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
- Se utilizzi una versione precedente alla 3.8.5, consulta la sezione Aggiornamento di Experience Manager Guides nella guida all&#39;installazione specifica per il prodotto, disponibile in [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>È necessario installare AEM Service Pack prima di aggiornare la versione di Experience Manager Guides.

Per informazioni dettagliate, visualizzare [Istruzioni per l&#39;aggiornamento per le versioni locali](../install-guide/upgrade-xml-documentation.md) di Experience Manager Guides.


