---
title: Scarica e installa AEM Guides per la prima volta
description: Scopri come scaricare e installare AEM Guides per la prima volta
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: 1c4a93c2-e477-4466-8390-3fda21ead9ff
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 3%
---
# Scarica e installa AEM Guides per la prima volta {#id213BCL00KEV}

Per scaricare e installare AEM Guides per la prima volta, effettua le seguenti operazioni:

>[!IMPORTANT]
>
> Se desideri utilizzare Livefyre insieme ad AEM Guides, assicurati di installare le versioni di Livefyre precedenti alla 3.0 prima di installare AEM Guides. Se utilizzi Livefyre versione 3.0 o successiva, non esiste alcuna restrizione di questo tipo.

1. Scarica AEM Guides da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).

   >[!NOTE]
   >
   >Prima di installare Experience Manager Guides, assicurati che il tuo sistema soddisfi i [requisiti tecnici](../install-conf-guide/aemg-technical-requirements.md).

1. Accedi all’istanza di AEM e passa a Gestione pacchetti CRX. L’URL predefinito per accedere al gestore di pacchetti è:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   Gestione pacchetti gestisce i pacchetti nell’installazione AEM locale. Per ulteriori informazioni sull&#39;utilizzo di Gestione pacchetti, vedere [Come utilizzare i pacchetti](https://helpx.adobe.com/it/experience-manager/6-5/sites/administering/using/package-manager.html) nella documentazione di AEM.

   ![](assets/package-manager.png){width="650"}

1. Per caricare il pacchetto AEM Guides, fai clic su **Carica pacchetto**.

1. Nella finestra di dialogo Carica pacchetto, individua il file AEM Guides scaricato al passaggio 1 e fai clic su **OK**.

   Il pacchetto viene caricato nella tua istanza di AEM.

1. Per installare il pacchetto, fare clic su **Installa**.

   ![](assets/install-package.png){width="650"}

1. Nella finestra di dialogo Installa pacchetto, fai clic su **Installa**.

1. Per iniziare a utilizzare AEM Guides, fare clic sul pulsante Home ![](assets/home-button.png) nell&#39;angolo superiore sinistro di Gestione pacchetti CRX.


>[!NOTE]
>
> Esegui la procedura di installazione su tutte le istanze dei server AEM presenti nella configurazione.
