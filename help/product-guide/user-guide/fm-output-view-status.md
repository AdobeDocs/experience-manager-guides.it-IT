---
title: Visualizza lo stato dell'attività di generazione output
description: Visualizzare la coda di generazione output dei documenti FrameMaker. Scopri come visualizzare lo stato di un’attività di generazione output.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
feature: Publishing FrameMaker Documents
role: User
source-git-commit: b78a34430476c15cadacb23d65bd978b3c25bd23
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Visualizza lo stato dell&#39;attività di generazione output {#viewing_output_history}

Dopo aver avviato l’attività di generazione dell’output per un documento FrameMaker, Adobe Experience Manager Guides invia questa attività alla coda di generazione dell’output. Questa coda viene aggiornata in tempo reale, mostrando lo stato di ogni operazione di generazione output nella coda.

Per visualizzare la coda di generazione dell’output, effettua le seguenti operazioni:

1. Nell’interfaccia utente di Assets, individua e seleziona il documento FrameMaker per il quale vuoi controllare lo stato di generazione dell’output.

1. Selezionare Output.

   ![](images/output-queued-fm.png){align="left"}

1. La pagina Output è divisa in due parti:

   - **Output in coda:**

     Elenca gli output in attesa di generazione o in fase di generazione. È inoltre possibile trovare l&#39;impostazione di generazione dell&#39;output o il predefinito utilizzato per l&#39;attività in coda, il tipo, l&#39;utente che ha avviato l&#39;attività, il tempo trascorso dalla data di accodamento dell&#39;attività e lo stato corrente.

   - **Output generati**

     Elenca le attività di output completate. Anche in questo caso, le informazioni visualizzate sono simili a quelle della sezione Output in coda, con l&#39;unica differenza del tempo di generazione dell&#39;output.

     In questo elenco è possibile che siano presenti attività eseguite correttamente o attività non riuscite. Per le attività completate correttamente, il processo di pubblicazione crea un file di registro \(logs.txt\) a cui è possibile accedere selezionando il collegamento nella colonna Generato a.


**Argomento padre:**[ Genera output di documenti FrameMaker](fm-output-generatation.md)
