---
title: Aggiornamento delle guide AEM
description: Scopri come aggiornare le guide AEM
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---

# Aggiornamento delle guide AEM {#id213BD050YPH}

1. Accedi all’archivio Git di Cloud Manager.

1. Aggiorna il file dox/dox.installer/pom.xml.

1. Aggiorna il valore della variabile dox.version ai dettagli della versione forniti da Adobe.

1. Apporta le modifiche ed esegui la pipeline di Cloud Manager per distribuire il pacchetto aggiornato.


>[!NOTE]
>
> Per ulteriori dettagli sull’utilizzo della pipeline CI/CD, consulta [Utilizzare la pipeline CI/CD in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Cancella cache del browser

Dopo aver completato il processo di aggiornamento, tutti gli utenti devono cancellare la cache del browser prima di utilizzare la versione aggiornata delle guide AEM.

**Argomento padre:**[ Scarica e installa](download-install.md)
