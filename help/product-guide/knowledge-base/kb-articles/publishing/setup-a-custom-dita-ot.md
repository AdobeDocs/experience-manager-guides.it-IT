---
title: Configura DITA-OT personalizzato in [!DNL AEM Guides]
description: Scopri come impostare DITA-OT personalizzato in [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
feature: DITA-OT Configuration
TQID: https://experienceleague.adobe.com/EaU6rkZL-RBkkYDhKxHNkizIVSqNzEDd-TtFlJAmREw
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 0%

---

# Configura DITA-OT personalizzato in [!DNL AEM Guides] per AEM

I passaggi per aggiungere un DITA-OT personalizzato sono documentati nella sezione _Utilizzare plug-in DITA-OT personalizzati_ della _Guida all&#39;installazione e alla configurazione_.

Ad alto livello, i passaggi sono i seguenti:

+ Ottieni il DITA-OT di base
   + Se si desidera ottenere una copia di DITA-OT preconfigurato da [!DNL AEM Guides], scaricarla dal percorso `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Se desideri ottenere una versione diversa, puoi scaricarla dall&#39;[archivio dita-ot](https://www.dita-ot.org/download)
+ Apportare modifiche in DITA-OT come [l&#39;aggiunta di un nuovo plug-in](https://www.dita-ot.org/dev/topics/plugins-installing.html) o la personalizzazione di plug-in esistenti (fare riferimento ad esempio nella sezione collegamenti correlati di seguito)
+ Caricamento di `DITA-OT.zip` ricevuto in `/apps/<project-folder>/dita_resources` (è consigliabile creare una cartella di progetto personalizzata)
+ Aggiungi profilo DITA tramite **[!UICONTROL Strumenti]** > **[!UICONTROL Guide]** > **[!UICONTROL Profili DITA]** (utilizza il percorso DITA-OT in cui viene caricato il DITA-OT personalizzato, fai riferimento alla schermata seguente)
  ![Profili DITA](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Personalizzazione degli esempi di plug-in DITA-OT](https://www.dita-ot.org/dev/topics/pdf-customization.html)
