---
title: Personalizzare il dizionario predefinito di AEM
description: Scopri come personalizzare il dizionario predefinito di AEM
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/q1L3-BdWTGmgtrqjOipnk-39Tw-50NT6R--khdTXhbI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 172
ht-degree: 2%

---

# Personalizzare il dizionario predefinito di AEM {#id209SD8000WU}

L’editor web può essere configurato per utilizzare il correttore ortografico di AEM o il correttore ortografico del browser. Se si sceglie di utilizzare il correttore ortografico di AEM, è possibile definire l&#39;elenco di parole personalizzato in modo flessibile. Queste parole personalizzate vengono quindi aggiunte al dizionario di AEM e non vengono contrassegnate come \(as correct\) nell’editor Web.

Per creare un elenco di parole personalizzato aggiunto nel dizionario AEM, effettuare le seguenti operazioni:

1. Accedi ad AEM e apri la modalità CRXDE Lite.

1. Passa al seguente nodo:

   /apps/fmdita/config

1. Crea un nuovo file denominato user\_dictionary.txt.

1. Aprire il file e aggiungere un elenco di parole che si desidera definire nel dizionario personalizzato.

   La schermata seguente mostra l&#39;elenco di parole personalizzate aggiunto al file user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650"}

1. Salva e chiudi il file.


Per aggiornare l&#39;elenco delle parole personalizzate nel dizionario AEM, gli autori dovranno riavviare la sessione dell&#39;editor Web.

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
