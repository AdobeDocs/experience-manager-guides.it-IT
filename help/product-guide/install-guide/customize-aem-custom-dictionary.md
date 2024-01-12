---
title: Personalizza dizionario predefinito AEM
description: Scopri come personalizzare il dizionario predefinito per AEM
exl-id: 8bfd3ea7-0be8-4e7a-b389-5face043200b
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Personalizza dizionario predefinito AEM {#id209SD8000WU}

L&#39;editor Web può essere configurato in modo da utilizzare il controllo ortografico AEM o il controllo ortografico del browser. Se si sceglie di utilizzare il controllo ortografico AEM, è possibile definire l&#39;elenco di parole personalizzato in modo flessibile. Queste parole personalizzate vengono quindi aggiunte al dizionario AEM e non vengono contrassegnate con il simbolo \(as correct\) nell&#39;editor Web.

Per creare un elenco di parole personalizzato aggiunto nel dizionario AEM, effettuare le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passa al seguente nodo:

   /apps/fmdita/config

1. Crea un nuovo file denominato user\_dictionary.txt.

1. Aprire il file e aggiungere un elenco di parole che si desidera definire nel dizionario personalizzato.

   La schermata seguente mostra l&#39;elenco di parole personalizzate aggiunto al file user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Salva e chiudi il file.


Per aggiornare l&#39;elenco delle parole personalizzate nel dizionario AEM, gli autori dovranno riavviare la sessione dell&#39;editor Web.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
