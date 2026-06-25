---
title: Visualizza lo stato dell'attività di generazione output
description: Visualizzare la coda di generazione output dei documenti FrameMaker. Scopri come visualizzare lo stato di un’attività di generazione output.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: bf5a4365-0183-43d5-a39a-b9eb8a34b27d
TQID: https://experienceleague.adobe.com/FP5RxNtyWcdS-xpw2Atttt3x6DHx73Ljv-Ym91IxY5s
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: c1b7d852b148187cb5d33256223d5e0f5498aa7e
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 0%

---

# Visualizza lo stato dell&#39;attività di generazione output {#viewing_output_history}

Dopo aver avviato l’attività di generazione dell’output per un documento FrameMaker, AEM Guides invia questa attività alla coda di generazione dell’output. Questa coda viene aggiornata in tempo reale, mostrando lo stato di ogni operazione di generazione output nella coda.

Per visualizzare la coda di generazione dell’output, effettua le seguenti operazioni:

1. Nell’interfaccia utente di Assets, passa a e fai clic sul documento FrameMaker di cui desideri controllare lo stato di generazione dell’output.

1. Fare clic su Output.

   ![](images/output-queued-fm.png){width="800"}

1. La pagina Output è divisa in due parti:

   - **Output in coda:**

     Elenca gli output in attesa di generazione o in fase di generazione. È inoltre possibile trovare l&#39;impostazione di generazione dell&#39;output o il predefinito utilizzato per l&#39;attività in coda, il tipo, l&#39;utente che ha avviato l&#39;attività, il tempo trascorso dalla data di accodamento dell&#39;attività e lo stato corrente.

   - **Output generati**

     Elenca le attività di output completate. Anche in questo caso, le informazioni visualizzate sono simili a quelle della sezione Output in coda, con l&#39;unica differenza del tempo di generazione dell&#39;output.

     In questo elenco è possibile che siano presenti attività eseguite correttamente o attività non riuscite. Per le attività completate correttamente, il processo di pubblicazione crea un file di registro \(logs.txt\) a cui è possibile accedere facendo clic sul collegamento nella colonna Generato a.

> **Come definire gli attributi su più celle, righe intere o colonne di una tabella**
>
> È possibile definire attributi a livello di cella, riga o colonna
>
> <details>
&gt; <summary>Mostra passaggi</summary>
>
> È inoltre possibile definire attributi su più celle, righe intere o colonne di una tabella. Ad esempio, per allineare la cella della tabella, trascinare e selezionare la cella desiderata. Nel pannello Proprietà contenuto (a destra), la proprietà **Type** diventa **entry**.
>
> 1. Nella sezione **Attributi**, seleziona **+Aggiungi**.
> 1. Selezionare l&#39;attributo `@valign` dall&#39;elenco a discesa **Attributo**.
> 1. Dall&#39;elenco a discesa valore, selezionare l&#39;allineamento del testo che si desidera applicare alle celle di tabella selezionate.
> 1. Seleziona **Aggiungi.**
>
> ![](images/align-table-cell_cs.png)
>
> </details>

## Definire gli attributi su più celle, righe intere o colonne di una tabella

È possibile definire attributi a livello di cella, riga o colonna.

> <details>
&gt; <summary>Mostra passaggi</summary>
>
> È inoltre possibile definire attributi su più celle, righe intere o colonne di una tabella. Ad esempio, per allineare la cella della tabella, trascinare e selezionare la cella desiderata. Nel pannello Proprietà contenuto (a destra), la proprietà **Type** diventa **entry**.
>
> 1. Nella sezione **Attributi**, seleziona **+Aggiungi**.
> 1. Selezionare l&#39;attributo `@valign` dall&#39;elenco a discesa **Attributo**.
> 1. Dall&#39;elenco a discesa valore, selezionare l&#39;allineamento del testo che si desidera applicare alle celle di tabella selezionate.
> 1. Seleziona **Aggiungi.**
>
> ![](images/align-table-cell_cs.png)
>
> </details>

**Argomento padre:**[ Genera output di documenti FrameMaker](fm-output-generatation.md)
