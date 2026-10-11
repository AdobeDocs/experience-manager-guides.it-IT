---
title: Come aggiungere [!DNL Experience Manager Guides] all'ambiente [!DNL Experience Manager as a Cloud Service]
description: Scopri come aggiungere [!DNL AEM Guides] all'ambiente [!DNL AEM as a Cloud Service]
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
TQID: 'https://experienceleague.adobe.com/lb5mjLR6M3pdFlsdQpwGXotEhbPeyetJ4zVwKV-J-Yg'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%
---
# Distribuzione di as a Cloud Service [!DNL Adobe Experience Manager Guides]

Scopri come aggiungere [!DNL Experience Manager Guides] all&#39;ambiente [!DNL Experience Manager as a Cloud Service].


>[!NOTE]
>
> A partire dalla versione 2024.2.0, Experience Manager Guides è disponibile solo come componente aggiuntivo automatico per Experience Manager as a Cloud Service. Se utilizzi le distribuzioni manuali per Experience Manager Guides, rimuovi la riga `<module>dox.installer</module> from file dox/pom.xml` nella base di codice per la gestione Git del cloud prima di abilitare Experience Manager Guides per il programma.

1. Accedi a [!UICONTROL Cloud Manager].

1. Modificare il programma per il quale si desidera configurare [!DNL Experience Manager Guides].

1. Passa alla scheda **[!UICONTROL Soluzioni e componenti aggiuntivi]**.

1. Nella tabella **[!UICONTROL Soluzioni e componenti aggiuntivi]**, fai clic su **[!UICONTROL Assets]**.

1. Seleziona **[!UICONTROL Guide]** e seleziona **[!UICONTROL Salva]**.

Il programma per il provisioning automatico della soluzione Experience Manager Guides è stato configurato correttamente.

![Configurazione della soluzione Experience Manager Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Per installare [!DNL Experience Manager Guides] in qualsiasi ambiente del programma integrato, è necessario eseguire la pipeline associata all&#39;ambiente. Per l&#39;installazione di [!DNL Experience Manager Guides] non è richiesta alcuna configurazione aggiuntiva nel codebase Git CM.
