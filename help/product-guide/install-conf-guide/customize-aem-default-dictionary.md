---
title: Personalizzare il dizionario predefinito di AEM
description: Scopri come personalizzare il dizionario predefinito di AEM
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 51099b42-706f-42b4-993e-7d9577b5a4f0
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Personalizzare il dizionario predefinito di AEM {#id209SD8000WU}

L’editor può essere configurato per utilizzare il correttore ortografico di AEM o il correttore ortografico del browser. Se si sceglie di utilizzare il correttore ortografico di AEM, è possibile definire l&#39;elenco di parole personalizzato in modo flessibile. Queste parole personalizzate vengono quindi aggiunte al dizionario di AEM e non vengono contrassegnate come \(as correct\) nell’editor.

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


Gli autori devono riavviare la sessione dell&#39;editor per aggiornare l&#39;elenco delle parole personalizzate nel dizionario AEM.

>[!TAB On-Premise]

1. Accedi ad AEM e apri la modalità CRXDE Lite.

1. Passa al seguente nodo:

   /apps/fmdita/config

1. Crea un nuovo file denominato user\_dictionary.txt.

1. Aprire il file e aggiungere un elenco di parole che si desidera definire nel dizionario personalizzato.

   La schermata seguente mostra l&#39;elenco di parole personalizzate aggiunto al file user\_dictionary.txt:

   ![](assets/custom-words-list-dictionary.png){width="650"}

1. Salva e chiudi il file.


Gli autori devono riavviare la sessione dell&#39;editor per aggiornare l&#39;elenco delle parole personalizzate nel dizionario AEM.

>[!ENDTABS]

**Argomento padre:**[ Personalizza editor](customize-overview.md)
