---
title: Personalizzare il dizionario predefinito di AEM
description: Scopri come personalizzare il dizionario predefinito di AEM
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 2%

---

# Personalizzare il dizionario predefinito di AEM {#id209SD8000WU}

L’editor web può essere configurato per utilizzare il correttore ortografico di AEM o il correttore ortografico del browser. Se si sceglie di utilizzare il correttore ortografico di AEM, è possibile definire l&#39;elenco di parole personalizzato in modo flessibile. Queste parole personalizzate vengono quindi aggiunte al dizionario di AEM e non vengono contrassegnate come \(as correct\) nell’editor Web.

Le schede seguenti forniscono istruzioni per creare l’elenco di parole personalizzato, che vengono aggiunte nel dizionario di AEM in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Creare il file user\_dictionary.txt con un elenco di parole da definire nel dizionario personalizzato.

   >[!NOTE]
   >
   > Ogni parola personalizzata deve essere definita su una nuova riga.

1. Salva il file nella seguente posizione nell’archivio Git di Cloud Manager:

   /apps/fmdita/config

1. Salva il file.

   Esegui il commit delle modifiche ed esegui la pipeline Cloud Manager \(CI/CD\) per distribuire le modifiche di configurazione.


Per aggiornare l&#39;elenco delle parole personalizzate nel dizionario AEM, gli autori dovranno riavviare la sessione dell&#39;editor Web.

>[!TAB On-Premise]

1. Accedi ad AEM e apri la modalità CRXDE Lite.

1. Passa al seguente nodo:

   /apps/fmdita/config

1. Crea un nuovo file denominato user\_dictionary.txt.

1. Aprire il file e aggiungere un elenco di parole che si desidera definire nel dizionario personalizzato.

   La schermata seguente mostra l&#39;elenco di parole personalizzate aggiunto al file user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Salva e chiudi il file.


Per aggiornare l&#39;elenco delle parole personalizzate nel dizionario AEM, gli autori dovranno riavviare la sessione dell&#39;editor Web.

>[!ENDTABS]

**Argomento padre:**[ Personalizza editor Web](customize-overview.md)
