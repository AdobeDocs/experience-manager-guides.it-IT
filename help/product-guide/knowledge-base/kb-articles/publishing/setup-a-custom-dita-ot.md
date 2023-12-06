---
title: Configurazione DITA-OT personalizzato in [!DNL AEM Guides]
description: Scopri come impostare DITA-OT personalizzato in [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Configurazione DITA-OT personalizzato in [!DNL AEM Guides] per AEM

I passaggi per aggiungere un DITA-OT personalizzato sono documentati nella sezione _Usa plug-in DITA-OT personalizzati_ del _Guida all’installazione e alla configurazione_.

Ad alto livello, i passaggi sono i seguenti:

+ Ottieni il DITA-OT di base
   + Se desideri ottenere una copia di DITA-OT preconfigurato da [!DNL AEM Guides], scaricalo dal percorso `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Se desideri ottenere una versione diversa puoi scaricare da [repository dita-ot](https://www.dita-ot.org/download)
+ Apporta modifiche a DITA-OT come [aggiunta di un nuovo plug-in](https://www.dita-ot.org/dev/topics/plugins-installing.html), o personalizzazione dei plug-in esistenti (vedi esempio nella sezione collegamenti correlati più avanti)
+ Carica `DITA-OT.zip` ricevuto in `/apps/<project-folder>/dita_resources` (si consiglia di creare una cartella di progetto personalizzata)
+ Aggiungi profilo DITA tramite **[!UICONTROL Strumenti]** > **[!UICONTROL Guide]** > **[!UICONTROL Profili DITA]** (utilizzare il percorso DITA-OT in cui viene caricato il DITA-OT personalizzato, fare riferimento alla schermata seguente)
  ![Profili DITA](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Personalizzazione degli esempi di plug-in DITA-OT](https://www.dita-ot.org/dev/topics/pdf-customization.html)
