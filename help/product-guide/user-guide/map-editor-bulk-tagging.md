---
title: Applicazione di tag in blocco a contenuto DITA
description: Utilizza l’assegnazione tag in blocco dei contenuti in AEM Guides per migliorare la reperibilità dei contenuti DITA. Scopri come applicare, rimuovere, mostrare o nascondere tag in blocco su uno o più argomenti.
exl-id: 4c6639a3-333b-44ad-9aec-735a327c3320
feature: Metadata Management
role: User
TQID: https://experienceleague.adobe.com/aIDAXlejB9zW12EYhH0cOwCJpGTKwU42gfvrbUmMqJ4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 722
ht-degree: 0%

---

# Applicazione di tag in blocco a contenuto DITA {#id179SG0TN05Z}

![](images/test-version-info-table.svg){width="650"}

I tag ti consentono di raggruppare o classificare il contenuto all’interno dell’archivio dei contenuti e anche nell’output pubblicato. Se sono stati applicati tag al contenuto, è possibile trovare facilmente argomenti correlati all&#39;interno di una mappa DITA che possono essere utili per l&#39;authoring dei contenuti. Con l’output pubblicato, gli utenti finali saranno in grado di individuare più rapidamente il contenuto corretto con i tag corretti.

Adobe Experience Manager Guides consente di assegnare tag al contenuto DITA in pochi passaggi. È possibile utilizzare la funzione di assegnazione tag in blocco per applicare più tag a più argomenti, a una mappa DITA o a una mappa secondaria. In alternativa, è possibile applicare i tag anche a un singolo argomento. L&#39;assegnazione tag è la funzionalità nativa di Adobe Experience Manager. Per ulteriori informazioni sulla creazione e la gestione dei tag, vedere la sezione [Amministrazione dei tag](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=it) nella documentazione di Adobe Experience Manager.

Per impostazione predefinita, Experience Manager Guides non concede l’accesso in lettura ad alcun utente della cartella in cui sono memorizzati tutti i tag nell’archivio di Adobe Experience Manager. Per utilizzare i tag definiti nel repository di Adobe Experience Manager, è necessario chiedere all&#39;amministratore di sistema di concedere l&#39;accesso alla cartella in cui sono memorizzati i tag.

## Applicare tag collettivi

Utilizza la funzione di assegnazione tag in blocco per applicare più tag contemporaneamente. Per applicare tag agli argomenti di una mappa DITA, effettuare le seguenti operazioni:

1. Nell&#39;interfaccia utente di Assets, spostarsi e selezionare il file di mapping DITA.

   Viene visualizzata la console Mappa DITA con l&#39;elenco dei predefiniti di output disponibili per generare l&#39;output.

1. Seleziona **Argomenti**.

   Viene visualizzato un elenco di argomenti disponibili nella mappa DITA. Gli UUID degli argomenti sono mostrati sotto il titolo dell’argomento.

1. Selezionare gli argomenti o la mappa secondaria a cui si desidera applicare i tag.

   ![](images/apply-tags-uuid.png){width="650"}


   >[!NOTE]
   >
   > La schermata precedente mostra una mappa secondaria selezionata ed espansa. Quando selezioni la mappa secondaria, vengono selezionati anche tutti gli argomenti sotto la mappa secondaria.

1. Selezionare **Applica tag**.

   Viene visualizzata la finestra di dialogo Seleziona tag.

1. Selezionare uno o più tag da applicare agli argomenti selezionati.

1. Conferma la selezione.

   I tag selezionati vengono applicati agli argomenti e visualizzati accanto al titolo dell&#39;argomento.

   >[!NOTE]
   >
   > Dopo aver aggiunto i tag agli argomenti, se si sposta o si elimina un argomento, verranno rimossi anche i tag per tali argomenti. Tuttavia, l&#39;argomento rimane nella mappa fino a quando non viene rimosso.


## Applicare tag a un singolo argomento

Per applicare i tag a un singolo argomento, effettuare le operazioni riportate di seguito.

1. Nell’interfaccia utente di Assets, individua e seleziona il file di argomenti a cui desideri applicare i tag.

1. Nella barra degli strumenti, seleziona **Proprietà**.

   Viene visualizzata la pagina delle proprietà dell&#39;argomento.

1. Nella scheda Base, seleziona l&#39;icona Sfoglia accanto al campo **Tag**.

1. Selezionare uno o più tag da applicare all&#39;argomento selezionato.

1. Conferma la selezione.

1. Selezionare **Applica tag**.

   I tag selezionati vengono applicati all&#39;argomento e visualizzati nel campo Tag.

1. Seleziona **Salva e chiudi**.


## Rimuovi tag

In base alle esigenze aziendali, è possibile modificare le informazioni sui tag per qualsiasi argomento DITA. È possibile rimuovere tutti i tag contemporaneamente o solo quelli non validi per l&#39;argomento.

Per rimuovere tutti i tag da uno o più argomenti, effettua le seguenti operazioni:

1. Nell&#39;interfaccia utente di Assets, passare al file di mapping DITA e selezionarlo.

   Viene visualizzata la console Mappa DITA con l&#39;elenco dei predefiniti di output disponibili per generare l&#39;output.

1. Seleziona **Argomenti**.

   Viene visualizzato un elenco di argomenti disponibili nella mappa DITA.

1. Selezionare gli argomenti da cui si desidera rimuovere i tag.

1. Selezionare **Rimuovi tag**.

   >[!NOTE]
   >
   > Se l’icona Elimina tag non è visibile, accertati di non aver attivato la funzione Nascondi tag.

1. Nella finestra di dialogo Conferma eliminazione selezionare **OK** per rimuovere i tag dagli argomenti selezionati.


## Mostra o nascondi tag

Se agli argomenti sono stati applicati numerosi tag, la navigazione potrebbe risultare un po&#39; complicata. È possibile nascondere facilmente i tag nella vista della console delle mappe DITA selezionando l&#39;icona Nascondi tag. Allo stesso modo, quando i tag non sono visibili, selezionando Mostra tag vengono visualizzati tutti i tag.

**Argomento padre:**&#x200B;[&#x200B; Gestisci metadati](manage-metadata.md)
