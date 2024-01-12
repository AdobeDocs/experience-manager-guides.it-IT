---
title: Scarica e installa per la prima volta le guide AEM
description: Scopri come scaricare e installare le guide AEM per la prima volta
exl-id: 830a4381-303c-419c-b87f-9563352a7eeb
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Scarica e installa per la prima volta le guide AEM {#id213BCL00KEV}

Per scaricare e installare le guide AEM per la prima volta in un computer, effettuare le seguenti operazioni:

>[!IMPORTANT]
>
> Se desideri utilizzare Livefyre insieme alle Guide AEM, assicurati di installare le versioni di Livefyre precedenti alla 3.0 prima di installare le Guide AEM. Se utilizzi Livefyre versione 3.0 o successiva, non esiste alcuna restrizione di questo tipo.

1. Scarica le guide AEM dal portale di distribuzione software Adobe.

1. Accedi all’istanza AEM e passa a Gestione pacchetti CRX. L’URL predefinito per accedere al gestore di pacchetti è:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   Gestione pacchetti gestisce i pacchetti nell’installazione AEM locale. Per ulteriori informazioni sull’utilizzo di Gestione pacchetti, consulta [Come utilizzare i pacchetti](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html) nella documentazione AEM.

   ![](assets/package-manager.png){width="650" align="left"}

1. Per caricare il pacchetto delle guide dell’AEM, fai clic su **Carica pacchetto**.

1. Nella finestra di dialogo Carica pacchetto, individua il file Guide AEM scaricato al punto 1 e fai clic su **OK**.

   Il pacchetto viene caricato nell’istanza AEM.

1. Per installare il pacchetto, fai clic su **Installa**.

   ![](assets/install-package.png){width="650" align="left"}

1. Nella finestra di dialogo Installa pacchetto, fai clic su **Installa**.

1. Per iniziare a utilizzare le guide AEM, fare clic sul pulsante Home ![](assets/home-button.png) nell’angolo superiore sinistro di Gestione pacchetti CRX.


>[!NOTE]
>
> Eseguire la procedura di installazione su tutte le istanze dei server AEM presenti nella configurazione.

**Argomento padre:**[ Scarica e installa](download-install.md)
