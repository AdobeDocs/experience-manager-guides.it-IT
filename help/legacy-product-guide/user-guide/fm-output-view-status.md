---
title: Visualizza lo stato dell'attività di generazione output
description: Visualizzare la coda di generazione output dei documenti di FrameMaker. Scopri come visualizzare lo stato di un’attività di generazione output.
feature: Publishing FrameMaker Documents
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Visualizza lo stato dell&#39;attività di generazione output {#viewing_output_history}

Dopo aver avviato l&#39;operazione di generazione dell&#39;output per un documento di FrameMaker, AEM Guides invia l&#39;operazione alla coda di generazione dell&#39;output. Questa coda viene aggiornata in tempo reale, mostrando lo stato di ogni operazione di generazione output nella coda.

Per visualizzare la coda di generazione dell’output, effettua le seguenti operazioni:

1. Nell’interfaccia utente di Assets, passa a e fai clic sul documento del FrameMaker per il quale desideri controllare lo stato di generazione dell’output.

1. Fare clic su Output.

   ![](images/output-queued-fm.png){width="800" align="left"}

1. La pagina Output è divisa in due parti:

   - **Output in coda:**

     Elenca gli output in attesa di generazione o in fase di generazione. È inoltre possibile trovare l&#39;impostazione di generazione dell&#39;output o il predefinito utilizzato per l&#39;attività in coda, il tipo, l&#39;utente che ha avviato l&#39;attività, il tempo trascorso dalla data di accodamento dell&#39;attività e lo stato corrente.

   - **Output generati**

     Elenca le attività di output completate. Anche in questo caso, le informazioni visualizzate sono simili a quelle della sezione Output in coda, con l&#39;unica differenza del tempo di generazione dell&#39;output.

     In questo elenco è possibile che siano presenti attività eseguite correttamente o attività non riuscite. Per le attività completate correttamente, il processo di pubblicazione crea un file di registro \(logs.txt\) a cui è possibile accedere facendo clic sul collegamento nella colonna Generato a.


**Argomento padre:**[ Genera output dei documenti di FrameMaker](fm-output-generatation.md)
