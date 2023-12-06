---
title: Personalizza dizionario predefinito AEM
description: Scopri come personalizzare il dizionario predefinito per AEM
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# Personalizza dizionario predefinito AEM {#id209SD8000WU}

L&#39;editor Web può essere configurato in modo da utilizzare il controllo ortografico AEM o il controllo ortografico del browser. Se si sceglie di utilizzare il controllo ortografico AEM, è possibile definire l&#39;elenco di parole personalizzato in modo flessibile. Queste parole personalizzate vengono quindi aggiunte al dizionario AEM e non vengono contrassegnate con il simbolo \(as correct\) nell&#39;editor Web.

Per creare un elenco di parole personalizzato aggiunto nel dizionario AEM, effettuare le seguenti operazioni:

1. Creare il file user\_dictionary.txt con un elenco di parole da definire nel dizionario personalizzato.

   >[!NOTE]
   >
   > Ogni parola personalizzata deve essere definita su una nuova riga.

1. Salva il file nella seguente posizione nell’archivio Git di Cloud Manager:

   /apps/fmdita/config

1. Salva il file.

   Apporta le modifiche ed esegui la pipeline di Cloud Manager \(CI/CD\) per distribuire le modifiche di configurazione.


Per aggiornare l&#39;elenco delle parole personalizzate nel dizionario AEM, gli autori dovranno riavviare la sessione dell&#39;editor Web.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
