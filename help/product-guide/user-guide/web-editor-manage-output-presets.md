---
title: Gestire i predefiniti di output per Profilo globale e Cartella
description: Scopri come creare, modificare, rinominare, duplicare ed eliminare predefiniti di output per profili globali e di cartelle come utenti amministratori in AEM Guides.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: f6ff978305d9a1587366acbe96d274408bf457f4
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Gestire i predefiniti di output per Profilo globale e Cartella {#id22BLJ0D0V1U}

I predefiniti Profilo globale e Profilo cartella sono disponibili solo per gli utenti amministratori a livello di cartella.

In qualità di amministratore, Adobe Experience Manager Guides ti consente di creare e gestire i predefiniti di output per i profili globali e delle cartelle. Puoi quindi utilizzare facilmente questi predefiniti di output per generare l’output per tutte le mappe correlate al profilo globale o cartella.

Per creare un predefinito di output per i profili globali e cartelle, effettua le seguenti operazioni:

1. Selezionare la mappa DITA per la quale si desidera creare un predefinito di output.
1. Selezionare l&#39;opzione **Modifica argomenti** dal menu **Opzioni** del file di mapping. Il file di mappa viene aperto per la modifica nell&#39;editor.
1. Seleziona l&#39;icona **Apri nella console delle mappe** per aprire il file delle mappe nella console delle mappe.
1. Nella console Mappa passare alla scheda **Predefiniti di output**, quindi selezionare l&#39;icona + per creare un predefinito di output per la mappa DITA.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Immetti i seguenti dettagli nella finestra di dialogo **Aggiungi predefinito**:
   - Tipo
   - Nome
   - Target \(per predefinito Knowledge Base\)
1. Selezionare la casella di controllo **Aggiungi al profilo cartella** per creare un predefinito di output per il profilo cartella correlato, quindi selezionare **Aggiungi**. Il predefinito viene creato e visualizzato nella scheda **Predefiniti di output** di tutte le mappe correlate. L&#39;icona \( ![](images/global-preset-icon.svg)\) indica un predefinito a livello di profilo della cartella.
1. Immetti i dettagli della configurazione. Per ulteriori dettagli sui predefiniti di output, visualizzare [Informazioni sui predefiniti di output](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Questi predefiniti aggiunti al profilo della cartella sono indipendenti dalle mappe, pertanto le configurazioni specifiche della mappa non sono presenti per questi predefiniti.

1. È possibile selezionare l&#39;icona **Genera output** nell&#39;angolo superiore destro per generare l&#39;output per le mappe relative al predefinito di output creato. È possibile visualizzare lo stato del processo di generazione dell&#39;output. Per visualizzare l&#39;output, selezionare **Visualizza output** nella finestra di dialogo **Operazione riuscita**.

>[!NOTE]
>
> Experience Manager Guides fornisce inoltre un predefinito di output predefinito per PDF per generare l&#39;output per le mappe DITA.

**Altre operazioni dal menu Opzioni**

Dal menu Opzioni (Options) potete inoltre eseguire le seguenti operazioni sul predefinito:

- **Genera output**: consente di generare un output per un predefinito esistente.
- **Visualizza output** e **Visualizza log**: collegamenti rapidi per visualizzare l&#39;output e i log generati.
- **Rinomina**, **Duplica** o **Elimina** un predefinito di output esistente dal menu **Opzioni**.
- **PDF predefinito**: consente di selezionare il predefinito PDF esistente come predefinito pdf predefinito predefinito. Il predefinito selezionato è, quindi viene utilizzato come predefinito predefinito predefinito predefinito predefinito per generare l&#39;output di PDF utilizzando l&#39;opzione **Scarica come PDF** per una mappa.

>[!NOTE]
>
> Quando un predefinito di output in Profili globali e cartelle viene eliminato, si riflette in tutte le mappe correlate e non viene visualizzato nella scheda **Predefiniti di output**.

**Argomento padre:**[ Utilizzare l&#39;editor Web](web-editor.md)
