---
title: Personalizzare il dizionario predefinito di AEM
description: Scopri come personalizzare il dizionario predefinito di AEM
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/omWGECpXvtuNBUH8dcOnggOHmG8z1PevjBmZ-ZcYWjY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 174
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
