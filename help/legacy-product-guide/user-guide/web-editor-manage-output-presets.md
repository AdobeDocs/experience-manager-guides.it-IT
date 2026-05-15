---
title: Gestire i predefiniti di output per Profilo globale e Cartella
description: Scopri come creare, modificare, rinominare, duplicare ed eliminare predefiniti di output per profili globali e di cartelle come utenti amministratori in AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: 4e9cd1d5-1c28-4363-917d-f58511c4f809
TQID: https://experienceleague.adobe.com/KH-j3haVf3VmR0QpMgAOCFfdJoCUOuc-nx5Xrc2XTKI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 0%

---

# Gestire i predefiniti di output per Profilo globale e Cartella {#id22BLJ0D0V1U}

I predefiniti Profilo globale e Profilo cartella sono disponibili solo per gli utenti amministratori a livello di cartella.

In qualità di amministratore, AEM Guides ti consente di creare e gestire i predefiniti di output per i profili globali e delle cartelle. Puoi quindi utilizzare facilmente questi predefiniti di output per generare l’output per tutte le mappe correlate al profilo globale o cartella.

Per creare un predefinito di output per i profili globali e cartelle, effettua le seguenti operazioni:

1. Selezionare la mappa DITA per la quale si desidera creare un predefinito di output.
1. Selezionare l&#39;opzione **Modifica argomenti** dal menu **Opzioni** del file di mapping. Il file mappa viene aperto per la modifica nell&#39;editor Web.
1. Nella scheda **Output**, selezionare l&#39;icona + per creare un predefinito di output per la mappa DITA.

   ![](images/add-global-output-preset.png){width="350"}

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
> AEM Guides fornisce inoltre un predefinito di output predefinito per PDF per generare l&#39;output per le mappe DITA.

**Altre operazioni dal menu Opzioni**

Dal menu Opzioni (Options) potete inoltre eseguire le seguenti operazioni sul predefinito:

- Seleziona il predefinito come predefinito pdf predefinito di default. Il predefinito selezionato verrà quindi utilizzato come predefinito predefinito predefinito predefinito predefinito per generare l&#39;output di PDF utilizzando l&#39;opzione **Scarica come PDF** per una mappa.
- **Modifica**, **Rinomina**, **Duplica** o **Elimina** un predefinito di output esistente dal menu **Opzioni**.

>[!NOTE]
>
> Quando un predefinito di output in Profili globali e cartelle viene eliminato, verrà visualizzato in tutte le mappe correlate e non nella scheda **Output**.

**Argomento padre:**[ Utilizzare l&#39;editor Web](web-editor.md)
