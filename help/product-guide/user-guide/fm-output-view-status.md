---
title: Visualizza lo stato dell'attività di generazione output
description: Visualizzare la coda di generazione output dei documenti FrameMaker. Scopri come visualizzare lo stato di un’attività di generazione output.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
feature: Publishing FrameMaker Documents
role: User
TQID: https://experienceleague.adobe.com/YL5ug0bhsYa-00J2fGQ-K-Cp6VE46KpC4Ss7hG64yRk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
subfeature_v2:
  - id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 248
ht-degree: 0%

---

# Visualizza lo stato dell&#39;attività di generazione output {#viewing_output_history}

Dopo aver avviato l’attività di generazione dell’output per un documento FrameMaker, Adobe Experience Manager Guides invia questa attività alla coda di generazione dell’output. Questa coda viene aggiornata in tempo reale, mostrando lo stato di ogni operazione di generazione output nella coda.

Per visualizzare la coda di generazione dell’output, effettua le seguenti operazioni:

1. Nell’interfaccia utente di Assets, individua e seleziona il documento FrameMaker per il quale vuoi controllare lo stato di generazione dell’output.

1. Selezionare Output.

   ![](images/output-queued-fm.png)

1. La pagina Output è divisa in due parti:

   - **Output in coda:**

     Elenca gli output in attesa di generazione o in fase di generazione. È inoltre possibile trovare l&#39;impostazione di generazione dell&#39;output o il predefinito utilizzato per l&#39;attività in coda, il tipo, l&#39;utente che ha avviato l&#39;attività, il tempo trascorso dalla data di accodamento dell&#39;attività e lo stato corrente.

   - **Output generati**

     Elenca le attività di output completate. Anche in questo caso, le informazioni visualizzate sono simili a quelle della sezione Output in coda, con l&#39;unica differenza del tempo di generazione dell&#39;output.

     In questo elenco è possibile che siano presenti attività eseguite correttamente o attività non riuscite. Per le attività completate correttamente, il processo di pubblicazione crea un file di registro \(logs.txt\) a cui è possibile accedere selezionando il collegamento nella colonna Generato a.


**Argomento padre:**&#x200B;[&#x200B; Genera output di documenti FrameMaker](fm-output-generatation.md)
