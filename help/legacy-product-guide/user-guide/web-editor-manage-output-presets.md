---
title: Gestire i predefiniti di output per Profilo globale e Cartella
description: Scopri come creare, modificare, rinominare, duplicare ed eliminare predefiniti di output per profili globali e di cartelle come utenti amministratori in AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Gestire i predefiniti di output per Profilo globale e Cartella {#id22BLJ0D0V1U}

I predefiniti Profilo globale e Profilo cartella sono disponibili solo per gli utenti amministratori a livello di cartella.

In qualità di amministratore, AEM Guides ti consente di creare e gestire i predefiniti di output per i profili globali e delle cartelle. Puoi quindi utilizzare facilmente questi predefiniti di output per generare l’output per tutte le mappe correlate al profilo globale o cartella.

Per creare un predefinito di output per i profili globali e cartelle, effettua le seguenti operazioni:

1. Selezionare la mappa DITA per la quale si desidera creare un predefinito di output.
1. Selezionare l&#39;opzione **Modifica argomenti** dal menu **Opzioni** del file di mapping. Il file mappa viene aperto per la modifica nell&#39;editor Web.
1. Nella scheda **Output**, selezionare l&#39;icona + per creare un predefinito di output per la mappa DITA.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Immetti i seguenti dettagli nella finestra di dialogo **Aggiungi predefinito**:
   - Tipo
   - Nome
   - Target \(per predefinito Knowledge Base\)
1. Selezionare la casella di controllo **Aggiungi al profilo cartella** per creare un predefinito di output per il profilo cartella correlato, quindi fare clic su **Aggiungi**. Il predefinito viene creato e visualizzato nella scheda **Output** di tutte le mappe correlate. L&#39;icona \( ![](images/global-preset-icon.svg)\) indica un predefinito a livello di profilo della cartella.
1. Immetti i dettagli della configurazione. Per ulteriori dettagli sui predefiniti di output, visualizzare [Informazioni sui predefiniti di output](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Questi predefiniti aggiunti al profilo della cartella sono indipendenti dalle mappe, pertanto le configurazioni specifiche della mappa non sono presenti per questi predefiniti.

1. Puoi selezionare l&#39;icona **Genera predefinito** nella parte superiore per generare l&#39;output per le mappe relative al predefinito di output creato. Viene visualizzato lo stato del processo di generazione dell’output. Per visualizzare l&#39;output, posizionare il puntatore del mouse sull&#39;argomento e fare clic su **Visualizza output**.

>[!NOTE]
>
> AEM Guides fornisce inoltre un predefinito di output PDF predefinito per generare l&#39;output per le mappe DITA.

**Altre operazioni dal menu Opzioni**

Dal menu Opzioni (Options) potete inoltre eseguire le seguenti operazioni sul predefinito:

- Seleziona il predefinito come predefinito pdf predefinito di default. Il predefinito selezionato verrà quindi utilizzato come predefinito predefinito predefinito predefinito predefinito per generare l&#39;output di PDF utilizzando l&#39;opzione **Scarica come PDF** per una mappa.
- **Modifica**, **Rinomina**, **Duplica** o **Elimina** un predefinito di output esistente dal menu **Opzioni**.

>[!NOTE]
>
> Quando un predefinito di output in Profili globali e cartelle viene eliminato, verrà visualizzato in tutte le mappe correlate e non nella scheda **Output**.

**Argomento padre:**[ Utilizzare l&#39;editor Web](web-editor.md)
