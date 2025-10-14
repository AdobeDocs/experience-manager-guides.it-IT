---
title: Traduci argomenti modificati
description: Scopri come tradurre nuovamente un argomento modificato in AEM Guides.
feature: Translation
role: User
hide: true
exl-id: b623b109-8695-40e5-9e28-78f78cf57ad6
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Traduci argomenti modificati {#id16A5A0B6072}

Se apporti modifiche ad alcuni degli argomenti, questi ultimi dovranno essere ritradicati. È possibile tenere traccia degli argomenti modificati dalla mappa DITA. Dalla cartella della copia per lingua di origine, fare clic sul file di mapping DITA e quindi sulla scheda Traduzione. Puoi visualizzare lo stato di ogni argomento, indipendentemente dal fatto che richieda o meno la ritraduzione.

Per inviare un argomento modificato per la ritraduzione, effettua le seguenti operazioni:

1. Fare clic sul file di mapping DITA dalla cartella della copia per lingua di origine.

1. Fai clic sulla scheda **Traduzione**.

1. Nel pannello **Filtro** a sinistra, seleziona **Traduci lingue** di cui vuoi controllare lo stato e fai clic su **Fine**.

   Puoi visualizzare lo stato di traduzione di ciascun argomento. Gli argomenti per i quali è disponibile un&#39;altra revisione dell&#39;argomento rispetto a quella inviata per la traduzione mostrano lo stato **Non aggiornato**.

   >[!NOTE]
   >
   > Il flusso di lavoro di traduzione confronta l’ultima revisione salvata del file dell’argomento nella cartella della lingua di origine con la versione tradotta.

   Se fai clic sulla freccia per visualizzare ulteriori dettagli. è possibile visualizzare la copia per lingua non aggiornata.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Fare clic sulla casella di controllo per selezionare gli argomenti che si desidera inviare per la ritraduzione.

   Quando selezioni una data non sincronizzata, l&#39;opzione **Crea/aggiorna copie per lingua** viene visualizzata nel pannello Riferimenti e il pulsante **Ignora stato non sincronizzato** sopra l&#39;icona **Filtro**.

   È possibile utilizzare il pulsante **Ignora fuori sincronizzazione** per ignorare lo stato Non aggiornato per gli argomenti nella mappa DITA. Se ad esempio sono state apportate alcune modifiche nella versione inglese dell&#39;argomento che non richiedono traduzione, è possibile utilizzare questo pulsante e modificare lo stato Non aggiornato per l&#39;argomento selezionato.

   >[!NOTE]
   >
   > Se si fa clic sul pulsante **Ignora stato non sincronizzato**, lo stato dell&#39;argomento viene impostato su Aggiornato per gli argomenti non aggiornati selezionati.

1. Fai clic su **Aggiorna copie per lingua** e configura il processo di traduzione.

1. Puoi scegliere di creare un nuovo progetto di traduzione o aggiungere argomenti a un progetto di traduzione esistente. Fornisci i dettagli richiesti per configurare il progetto di traduzione.

1. Fare clic su **Inizio**.

   Viene visualizzato un messaggio di conferma che indica che l&#39;argomento è stato inviato per la traduzione.

1. Passa al progetto di traduzione nella console Progetto. Nella cartella viene creata una nuova scheda del processo di traduzione. Fai clic sui puntini di sospensione per visualizzare le risorse della cartella.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Per avviare la traduzione, fare clic sulla freccia sulla scheda del processo di traduzione e selezionare **Inizio** dall&#39;elenco. Un messaggio notifica l’avvio del processo.

   Puoi anche visualizzare lo stato dell’argomento tradotto quando fai clic sui puntini di sospensione nella parte inferiore della scheda del processo di traduzione.

   >[!NOTE]
   >
   > Se utilizzi il servizio di traduzione umana, devi esportare il contenuto per la traduzione. Una volta che hai il contenuto tradotto, devi importarlo nuovamente nel progetto di traduzione.

1. Al termine della traduzione, lo stato diventa **Pronto per la revisione**. Fai clic sui puntini di sospensione per visualizzare i dettagli dell’argomento ed effettua una delle seguenti operazioni dalla barra degli strumenti:

   - Fai clic su **Mostra in Assets** per visualizzare e verificare la traduzione.

   - Fare clic su **Accetta traduzione** se si ritiene che le modifiche siano state tradotte correttamente. Viene visualizzato un messaggio di conferma.

   - Fare clic su **Rifiuta traduzione** se si ritiene che il processo debba essere rieseguito. Viene visualizzato un messaggio di rifiuto.

   >[!NOTE]
   >
   > È importante accettare o rifiutare la risorsa tradotta, altrimenti il file rimane nella posizione temporanea e non viene copiato in DAM.

1. Tornare al file mappa DITA nella cartella della lingua di origine nell&#39;interfaccia utente di Assets. Gli argomenti ritradicati sono ora sincronizzati.


**Argomento padre:**&#x200B;[&#x200B; Traduci contenuto](translation.md)
