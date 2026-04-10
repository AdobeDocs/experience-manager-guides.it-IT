---
title: 'Come aggiungere  [!DNL Experience Manager Guides]  all''ambiente  [!DNL Experience Manager as a Cloud Service] '
description: 'Scopri come aggiungere  [!DNL AEM Guides]  all''ambiente  [!DNL AEM as a Cloud Service] '
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
hidefromtoc: true
source-git-commit: 55edd53d1dda7a68352e53b2e59eafd15b677fdd
workflow-type: tm+mt
source-wordcount: '155'
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
