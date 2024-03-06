---
title: Come aggiungere [!DNL Experience Manager Guides] al tuo [!DNL Experience Manager as a Cloud Service] ambiente
description: Scopri come aggiungere [!DNL AEM Guides] al tuo [!DNL AEM as a Cloud Service] ambiente
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] Distribuzione as a Cloud Service

Scopri come aggiungere [!DNL Experience Manager Guides] al tuo [!DNL Experience Manager as a Cloud Service] ambiente.


>[!NOTE]
>
> A partire dalla versione 2024.2.0, Experience Manager Guides è disponibile solo come componente aggiuntivo automatico, ad Experience Manager as a Cloud Service. Se si utilizzano distribuzioni manuali per Experience Manager Guides, rimuovere la riga `<module>dox.installer</module> from file dox/pom.xml` nel cloud gestisci la base di codice Git prima di abilitare Experience Manager Guides per il programma.

1. Accedi a [!UICONTROL Cloud Manager].

1. Modifica il programma da configurare [!DNL Experience Manager Guides].

1. Passa a **[!UICONTROL Soluzioni e componenti aggiuntivi]** scheda.

1. In **[!UICONTROL Soluzioni e componenti aggiuntivi]** tabella, fai clic su **[!UICONTROL Risorse]**.

1. Seleziona **[!UICONTROL Guide]** e seleziona **[!UICONTROL Salva]**.

Il programma per il provisioning automatico della soluzione Experience Manager Guides è stato configurato correttamente.

![Configurazione della soluzione Experience Manager Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Per installare [!DNL Experience Manager Guides] in qualsiasi ambiente del programma integrato, è necessario eseguire la pipeline associata all’ambiente. Non è necessaria alcuna configurazione aggiuntiva nel codebase Git CM per l’installazione [!DNL Experience Manager Guides].
