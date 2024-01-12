---
title: Gestire i predefiniti di output per Profilo globale e Cartella
description: Scopri come creare, modificare, rinominare, duplicare ed eliminare i predefiniti di output dei profili globali e delle cartelle come utenti amministratori nelle guide AEM.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Gestire i predefiniti di output per Profilo globale e Cartella {#id22BLJ0D0V1U}

I predefiniti Profilo globale e Profilo cartella sono disponibili solo per gli utenti amministratori a livello di cartella.

In qualità di amministratore, AEM Guides consente di creare e gestire predefiniti di output per i profili globali e cartelle. Puoi quindi utilizzare facilmente questi predefiniti di output per generare l’output per tutte le mappe correlate al profilo globale o cartella.

Per creare un predefinito di output per i profili globali e cartelle, effettua le seguenti operazioni:

1. Selezionare la mappa DITA per la quale si desidera creare un predefinito di output.
1. Seleziona la **Modifica argomenti** opzione dalla **Opzioni** del file di mappa. Il file mappa viene aperto per la modifica nell&#39;editor Web.
1. In **Output** , selezionare l&#39;icona + per creare un predefinito di output per la mappa DITA.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Immetti i seguenti dettagli in **Aggiungi predefinito** finestra di dialogo:
   - Tipo
   - Nome
   - Target \(per predefinito Knowledge Base\)
1. Seleziona la **Aggiungi al profilo cartella** per creare un predefinito di output per il profilo di cartella correlato, quindi fare clic su **Aggiungi**. Il predefinito viene creato e visualizzato sotto **Output** di tutte le mappe correlate. \( ![](images/global-preset-icon.svg)\) indica un predefinito a livello di profilo della cartella.
1. Immetti i dettagli della configurazione. Per ulteriori dettagli sui predefiniti di output, visualizzare [Informazioni sui predefiniti di output](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Questi predefiniti aggiunti al profilo della cartella sono indipendenti dalle mappe, pertanto le configurazioni specifiche della mappa non sono presenti per questi predefiniti.

1. È possibile selezionare **Genera predefinito** nella parte superiore per generare l’output per le mappe relative al predefinito di output creato. Viene visualizzato lo stato del processo di generazione dell’output. Per visualizzare l&#39;output, posizionare il puntatore del mouse sull&#39;argomento e fare clic su **Visualizza output**.

>[!NOTE]
>
> Le guide AEM forniscono anche un predefinito di output PDF predefinito per generare l&#39;output per le mappe DITA.

**Altre operazioni dal menu Opzioni**

Dal menu Opzioni (Options) potete inoltre eseguire le seguenti operazioni sul predefinito:

- Seleziona il predefinito come predefinito pdf predefinito di default. Il predefinito selezionato viene quindi utilizzato come predefinito predefinito predefinito di default per generare l&#39;output PDF utilizzando **Scarica come PDF** opzione per una mappa.
- **Modifica**, **Rinomina**, **Duplica**, o **Elimina** un predefinito di output esistente da **Opzioni** menu.

>[!NOTE]
>
> Quando un predefinito di output in Profili globali e cartelle viene eliminato, si riflette in tutte le mappe correlate e non viene visualizzato in **Output** scheda.

**Argomento padre:**[ Utilizzare l’editor web](web-editor.md)
