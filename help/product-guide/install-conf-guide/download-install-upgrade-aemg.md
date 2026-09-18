---
title: Aggiornare AEM Guides per Cloud Service
description: Scopri come aggiornare AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 9d48a7c4-384d-4ad4-a1d3-4c50d97e5d5b
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 2%
---
# Aggiornare AEM Guides per Cloud Service {#id213BD050YPH}

Per aggiornare AEM Guides, effettua le seguenti operazioni:

1. Accedi all’archivio Git di Cloud Manager.

1. Aggiornare il file `dox/dox.installer/pom.xml`.

1. Aggiornare il valore della variabile `dox.version` ai dettagli della versione forniti da Adobe.

1. Esegui il commit delle modifiche ed esegui la pipeline Cloud Manager per distribuire il pacchetto aggiornato.


>[!NOTE]
>
> Per ulteriori dettagli sull&#39;utilizzo della pipeline CI/CD, vedi [Utilizzare la pipeline CI/CD in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Cancella la cache del browser

Dopo aver completato il processo di aggiornamento, tutti gli utenti devono cancellare la cache del browser prima di utilizzare la versione aggiornata di AEM Guides.
