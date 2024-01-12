---
title: Traduci argomenti modificati
description: Scopri come tradurre nuovamente un argomento modificato nelle guide dell’AEM.
exl-id: b3228ea9-24a8-44aa-8ba4-e8f44754ffe4
feature: Translation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Traduci argomenti modificati {#id16A5A0B6072}

Se apporti modifiche ad alcuni degli argomenti, questi ultimi dovranno essere ritradicati. È possibile tenere traccia degli argomenti modificati dalla mappa DITA. Dalla cartella della copia per lingua di origine, fare clic sul file di mapping DITA e quindi sulla scheda Traduzione. Puoi visualizzare lo stato di ogni argomento, indipendentemente dal fatto che richieda o meno la ritraduzione.

Per inviare un argomento modificato per la ritraduzione, effettua le seguenti operazioni:

1. Fare clic sul file di mapping DITA dalla cartella della copia per lingua di origine.

1. Fai clic su **Traduzione** scheda.

1. In **Filtro** a sinistra, seleziona la **Traduci lingue** di cui desideri verificare lo stato e fai clic su **Fine**.

   Puoi visualizzare lo stato di traduzione di ciascun argomento. Gli argomenti per i quali è disponibile un&#39;altra revisione dell&#39;argomento rispetto a quella inviata per la traduzione mostrano un **Non aggiornato** stato.

   >[!NOTE]
   >
   > Il flusso di lavoro di traduzione confronta l’ultima revisione salvata del file dell’argomento nella cartella della lingua di origine con la versione tradotta.

   Se fai clic sulla freccia per visualizzare ulteriori dettagli. è possibile visualizzare la copia per lingua non aggiornata.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Fare clic sulla casella di controllo per selezionare gli argomenti che si desidera inviare per la ritraduzione.

   Quando si seleziona una data non sincronizzata, il **Crea/aggiorna copie per lingua** viene visualizzata nel pannello Riferimenti e nel **Ignora stato non sincronizzato** sopra il **Filtro** icona.

   È possibile utilizzare **Ignora fuori sincronizzazione** per ignorare lo stato Non aggiornato per gli argomenti nella mappa DITA. Se ad esempio sono state apportate alcune modifiche nella versione inglese dell&#39;argomento che non richiedono traduzione, è possibile utilizzare questo pulsante e modificare lo stato Non aggiornato per l&#39;argomento selezionato.

   >[!NOTE]
   >
   > Se si fa clic su **Ignora stato non sincronizzato** , imposta lo stato dell&#39;argomento su Aggiornato per gli argomenti non aggiornati selezionati.

1. Clic **Aggiorna copie per lingua** e configura il processo di traduzione.

1. Puoi scegliere di creare un nuovo progetto di traduzione o aggiungere argomenti a un progetto di traduzione esistente. Fornisci i dettagli richiesti per configurare il progetto di traduzione.

1. Clic **Inizio**.

   Viene visualizzato un messaggio di conferma che indica che l&#39;argomento è stato inviato per la traduzione.

1. Passa al progetto di traduzione nella console Progetto. Nella cartella viene creata una nuova scheda del processo di traduzione. Fai clic sui puntini di sospensione per visualizzare le risorse della cartella.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Per avviare la traduzione, fai clic sulla freccia sulla scheda del processo di traduzione e seleziona **Inizio** dall&#39;elenco. Un messaggio notifica l’avvio del processo.

   Puoi anche visualizzare lo stato dell’argomento tradotto quando fai clic sui puntini di sospensione nella parte inferiore della scheda del processo di traduzione.

   >[!NOTE]
   >
   > Se utilizzi il servizio di traduzione umana, devi esportare il contenuto per la traduzione. Una volta che hai il contenuto tradotto, devi importarlo nuovamente nel progetto di traduzione.

1. Al termine della traduzione, lo stato cambia in **Pronto per la revisione**. Fai clic sui puntini di sospensione per visualizzare i dettagli dell’argomento ed effettua una delle seguenti operazioni dalla barra degli strumenti:

   - Clic **Mostra in Assets** per visualizzare e verificare la traduzione.

   - Clic **Accetta traduzione** se pensi che le modifiche siano state tradotte correttamente. Viene visualizzato un messaggio di conferma.

   - Clic **Rifiuta traduzione** se pensi che il lavoro debba essere rifatto. Viene visualizzato un messaggio di rifiuto.

   >[!NOTE]
   >
   > È importante accettare o rifiutare la risorsa tradotta, altrimenti il file rimane nella posizione temporanea e non viene copiato in DAM.

1. Nell’interfaccia utente di Assets, torna al file mappa DITA nella cartella della lingua di origine. Gli argomenti ritradicati sono ora sincronizzati.


**Argomento padre:**[ Traduci contenuto](translation.md)
