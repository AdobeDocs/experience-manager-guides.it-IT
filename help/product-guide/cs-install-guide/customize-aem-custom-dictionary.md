---
title: Personalizzare il dizionario predefinito di AEM
description: Scopri come personalizzare il dizionario predefinito di AEM
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# Personalizzare il dizionario predefinito di AEM {#id209SD8000WU}

L’editor web può essere configurato per utilizzare il correttore ortografico di AEM o il correttore ortografico del browser. Se si sceglie di utilizzare il correttore ortografico di AEM, è possibile definire l&#39;elenco di parole personalizzato in modo flessibile. Queste parole personalizzate vengono quindi aggiunte al dizionario di AEM e non vengono contrassegnate come \(as correct\) nell’editor Web.

Per creare un elenco di parole personalizzato aggiunto nel dizionario AEM, effettuare le seguenti operazioni:

1. Creare il file user\_dictionary.txt con un elenco di parole da definire nel dizionario personalizzato.

   >[!NOTE]
   >
   > Ogni parola personalizzata deve essere definita su una nuova riga.

1. Salva il file nella seguente posizione nell’archivio Git di Cloud Manager:

   /apps/fmdita/config

1. Salva il file.

   Esegui il commit delle modifiche ed esegui la pipeline Cloud Manager \(CI/CD\) per distribuire le modifiche di configurazione.


Per aggiornare l&#39;elenco delle parole personalizzate nel dizionario AEM, gli autori dovranno riavviare la sessione dell&#39;editor Web.

**Argomento padre:**[ Personalizza editor Web](conf-web-editor.md)
