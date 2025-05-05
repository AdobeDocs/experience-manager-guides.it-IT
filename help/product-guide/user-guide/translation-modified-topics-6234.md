---
title: Traduci argomenti modificati
description: Scopri come tradurre nuovamente un argomento modificato in AEM Guides.
exl-id: b3228ea9-24a8-44aa-8ba4-e8f44754ffe4
feature: Translation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---

# Traduci argomenti modificati {#id16A5A0B6072}

Se apporti modifiche ad alcuni degli argomenti, questi ultimi dovranno essere ritradicati. È possibile tenere traccia degli argomenti modificati dalla mappa DITA. Dalla cartella della copia per lingua di origine, selezionare il file di mapping DITA dalla console Mappa e selezionare la scheda Traduzione. Puoi visualizzare lo stato di ogni argomento, indipendentemente dal fatto che richieda o meno la ritraduzione.

Per inviare un argomento modificato per la ritraduzione, effettua le seguenti operazioni:

1. Selezionare il file mappa DITA dalla cartella della copia per lingua di origine dalla **Console mappe** nell&#39;editor.

1. Seleziona la scheda **Traduzione**.

1. Nel pannello **Traduzione** a sinistra, seleziona le **Lingue disponibili** di cui vuoi verificare lo stato e seleziona **Applica**.

   Puoi visualizzare lo stato della traduzione per ogni argomento. Gli argomenti per i quali è disponibile un&#39;altra revisione dell&#39;argomento rispetto a quella inviata per la traduzione mostrano lo stato **Non sincronizzato**.

   >[!NOTE]
   >
   > Il flusso di lavoro di traduzione confronta l’ultima revisione salvata del file dell’argomento nella cartella della lingua di origine con la versione tradotta.

   Se si seleziona la freccia per visualizzare ulteriori dettagli, è possibile visualizzare la copia per lingua non sincronizzata.

   ![](images/out-of-sync-uuid-new.png){align="left"}

1. Selezionare la casella di controllo per selezionare gli argomenti che si desidera inviare per la ritraduzione.

   Quando selezioni un argomento non sincronizzato, il pulsante **Segna in sincronia** viene visualizzato sopra la barra del titolo.

   È possibile utilizzare il pulsante **Segna in sincronia** per ignorare lo stato Non sincronizzato per gli argomenti nella mappa DITA.  Ad esempio, se hai apportato alcune modifiche molto piccole che non richiedono alcuna traduzione, puoi contrassegnarne lo stato su In sincronia.

   >[!NOTE]
   >
   > Se si seleziona il pulsante **Contrassegna in sincronia**, lo stato dell&#39;argomento viene impostato su In sincronia per gli argomenti non sincronizzati selezionati.

1. È possibile selezionare il pulsante **Invia per traduzione**.

1. Puoi scegliere di creare un nuovo progetto di traduzione o aggiungere argomenti a un progetto di traduzione esistente. Fornisci i dettagli richiesti per configurare il progetto di traduzione.

1. Seleziona **Invia**.

   Viene visualizzato un messaggio di conferma che indica che l&#39;argomento è stato inviato per la traduzione.

1. Passa al progetto di traduzione nella console Progetto. Nella cartella viene creata una nuova scheda del processo di traduzione. Seleziona i puntini di sospensione per visualizzare le risorse della cartella.

   ![](images/incremental-job-new.png){width="300" align="left"}

1. Per avviare la traduzione, selezionare la freccia sulla scheda del processo di traduzione e selezionare **Inizio** dall&#39;elenco. Un messaggio notifica l’avvio del processo.

   Puoi anche visualizzare lo stato dell’argomento tradotto quando selezioni i puntini di sospensione nella parte inferiore della scheda del processo di traduzione.

   >[!NOTE]
   >
   > Se utilizzi il servizio di traduzione umana, devi esportare il contenuto per la traduzione. Una volta che hai il contenuto tradotto, devi importarlo nuovamente nel progetto di traduzione.

1. Al termine della traduzione, lo stato diventa **Pronto per la revisione**. Seleziona i puntini di sospensione per visualizzare i dettagli dell’argomento ed effettua una delle seguenti operazioni dalla barra degli strumenti:

   - Seleziona **Mostra in Assets** per visualizzare e verificare la traduzione.

   - Selezionare **Accetta traduzione** se si ritiene che le modifiche siano state tradotte correttamente. Viene visualizzato un messaggio di conferma.

   - Selezionare **Rifiuta traduzione** se si ritiene che il processo debba essere rieseguito. Viene visualizzato un messaggio di rifiuto.

   >[!NOTE]
   >
   > È importante accettare o rifiutare la risorsa tradotta, altrimenti il file rimane nella posizione temporanea e non viene copiato in DAM.

1. Tornare al file mappa DITA nella cartella della lingua di origine nell&#39;interfaccia utente di Assets. Gli argomenti ritrascritti ora sono sincronizzati.


**Argomento padre:**&#x200B;[ Panoramica sulla traduzione dei contenuti](translation.md)
