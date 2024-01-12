---
title: Come aggiungere [!DNL AEM Guides] al tuo [!DNL AEM as a Cloud Service] ambiente
description: Scopri come aggiungere [!DNL AEM Guides] al tuo [!DNL AEM as a Cloud Service] ambiente
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# [!DNL AEM Guides] Distribuzione as a Cloud Service

Scopri come aggiungere [!DNL Guides] al tuo [!DNL AEM as a Cloud Service] ambiente.

## Distribuzione manuale tramite pipeline Git di Cloud Manager

Se hai acquistato [!DNL AEM Guides] as a Cloud Service prima del 29 marzo 2022, segui queste istruzioni di distribuzione:

* Se stai iniziando da nuovo, puoi sostituire il codice generato automaticamente da [!UICONTROL Cloud Manager] con il codice dell’archivio seguente con plug-in XML già integrato: https://github.com/Adobe-TCS/XML-documentation-for-AEMaaCS

* Se sono già state archiviate personalizzazioni in [!UICONTROL Cloud Manager] archivio git, puoi fare riferimento al repository seguente per le istruzioni su come aggiungere il plug-in XML nel codice esistente: https://github.com/Adobe-TCS/DoX-Installer-for-AEMaaCS

## Implementazione Tramite Cloud Manager

Se sei un cliente che ha acquistato [!DNL AEM Guides] as a Cloud Service il 03/29/2022 o dopo il, seguire queste istruzioni per aggiungere [!DNL Guides] al tuo [!DNL AEM as a Cloud Service] ambiente:

1. Accedi a [!UICONTROL Cloud Manager].

1. Modifica il programma da configurare [!DNL AEM Guides].

1. Passa a **[!UICONTROL Soluzioni e componenti aggiuntivi]** scheda.

1. In **[!UICONTROL Soluzioni e componenti aggiuntivi]** tabella, fai clic su **[!UICONTROL Risorse]**.

1. Seleziona **[!UICONTROL Guide]** e seleziona **[!UICONTROL Salva]**.

Il programma per il provisioning automatico della soluzione Guide AEM è stato configurato correttamente.

![Configurazione della soluzione AEM Guides](assets/addon-configuration.png)

>[!NOTE]
>
>Per installare [!DNL AEM Guides] in qualsiasi ambiente del programma integrato, è necessario eseguire la pipeline associata all’ambiente. Non è necessaria alcuna configurazione aggiuntiva nel codebase Git CM per l’installazione [!DNL AEM Guides].
