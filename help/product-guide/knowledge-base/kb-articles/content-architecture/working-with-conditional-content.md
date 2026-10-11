---
title: Utilizzo di contenuti condizionali
description: Scopri come creare le condizioni, quindi configurare la generazione di contenuti condizionali in [!DNL AEM Guides]
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
feature: Publishing
TQID: 'https://experienceleague.adobe.com/3Gz6-sJn7dvzJSlnKgRoRqpFTqtj5fiVlAjOv0lbD1o'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%
---
# Utilizzo di contenuti condizionali

**Caso d&#39;uso**

* Gli autori possono impostare condizioni su un contenuto in modo da controllare se viene visualizzato nell’output.

* Gli autori possono scegliere di mostrare/nascondere condizioni diverse al momento della pubblicazione.

* Ad esempio, gli autori possono aggiungere nel contenuto attributi come versione 1.0 e versione 2.0 e utilizzare le condizioni per includere la versione 1.0 per la versione 1.0 ed escludere la versione 2.0.

**Passaggio 1**

Definisci le condizioni relative alla documentazione in [!UICONTROL Profili cartella]:
Consulta la sezione **Configurare gli attributi condizionali per i profili globali o a livello di cartella** in [Pagina 69 della Guida all&#39;installazione e alla configurazione](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

![Configura condizioni nei profili cartella](assets/conditions-in-profiles.png)

**Passaggio 2**

Selezionare il **[!UICONTROL Profilo cartella]** definito nel passaggio 1 in **Preferenze utente** nell&#39;editor XML:
Consulta la sezione **Preferenze utente** in [Pagina 41 della Guida utente](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)


**Passaggio 3**

Utilizza le condizioni per condizionare le sezioni del contenuto:
Consulta la sezione **Condizioni** in [Pagina 90 della Guida utente](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)

![Condizioni d&#39;uso nell&#39;editor](assets/conditions-in-web-editor.png)

**Passaggio 4**

Definisci i predefiniti per le condizioni a livello di mappa per scegliere quali condizioni abilitare nell’output:
Consulta la sezione **Utilizzare i predefiniti per le condizioni** in [Pagina 249 della Guida utente](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)
