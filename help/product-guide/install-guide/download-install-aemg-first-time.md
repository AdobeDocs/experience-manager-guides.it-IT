---
title: Scarica e installa AEM Guides per la prima volta
description: Scopri come scaricare e installare AEM Guides per la prima volta
exl-id: 830a4381-303c-419c-b87f-9563352a7eeb
feature: Introduction, Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/9EMSF4ux-NFRH6AuxPWneqRyp7AEGwm8ZTjbCvAx-XQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 3%

---

# Scarica e installa AEM Guides per la prima volta {#id213BCL00KEV}

Per scaricare e installare AEM Guides per la prima volta in un computer, effettua le seguenti operazioni:

>[!IMPORTANT]
>
> Se desideri utilizzare Livefyre insieme ad AEM Guides, assicurati di installare le versioni di Livefyre precedenti alla 3.0 prima di installare AEM Guides. Se utilizzi Livefyre versione 3.0 o successiva, non esiste alcuna restrizione di questo tipo.

1. Scarica AEM Guides da [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/it/aem.html).

   >[!NOTE]
   >
   >Prima di installare Experience Manager Guides, assicurati che il tuo sistema soddisfi i [requisiti tecnici](../install-guide/download-install-technical-requirements.md).

1. Accedi all’istanza di AEM e passa a Gestione pacchetti CRX. L’URL predefinito per accedere al gestore di pacchetti è:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   Gestione pacchetti gestisce i pacchetti nell’installazione AEM locale. Per ulteriori informazioni sull&#39;utilizzo di Gestione pacchetti, vedere [Come utilizzare i pacchetti](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html) nella documentazione di AEM.

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

**Argomento padre:**&#x200B;[&#x200B; Scarica e installa](download-install.md)
