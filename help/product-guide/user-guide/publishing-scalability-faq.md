---
title: Domande frequenti sulle prestazioni di pubblicazione e la scalabilità in Adobe Experience Manager Guides
description: Scopri le domande frequenti su Prestazioni di pubblicazione e scalabilità in Adobe Experience Manager Guides.
source-git-commit: d128860bdff78c100ba348b54a237b237171635f
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 0%

---

# Domande frequenti

Di seguito è riportato un elenco di risposte alle domande frequenti che forniscono informazioni dettagliate su come Adobe Experience Manager Guides gestisce i flussi di lavoro di pubblicazione, il comportamento di scalabilità e le prestazioni dell’infrastruttura. È destinato agli utenti aziendali, agli amministratori e ai team di documentazione che utilizzano Experience Manager Guides per la pubblicazione su larga scala. Il diagramma illustra il flusso di lavoro complessivo di Experience Manager Guides Publishing Architecture.

![](images/IO_runtime.drawio.png){align="left"}


## Quante richieste di pubblicazione può eseguire Experience Manager Guides al giorno?

Il numero di richieste di pubblicazione che Experience Manager Guides può elaborare al giorno dipende dalle dimensioni e dal tipo di contenuto. In base alla configurazione, il sistema consente un processo di pubblicazione per ogni core del processore. Nella configurazione corrente, è possibile eseguire in parallelo 20 processi di pubblicazione (2 pod × 10 core ciascuno).

Quando l’ambiente di produzione viene ridimensionato automaticamente, questo numero può aumentare a 40 processi di pubblicazione simultanei quando i pod raggiungono la scalabilità 4.

## Quante richieste di pubblicazione possono essere eseguite contemporaneamente prima che vengano messe in coda?

- Minimo (predefinito): 20 processi di pubblicazione (2 pod)
- Massimo (ridimensionato): 40 processi di pubblicazione (4 pod)

Questo numero può variare in base al carico complessivo del server. Se sono in esecuzione altri processi Sling in background, questi condividono i core di elaborazione, riducendo potenzialmente la concorrenza a meno di 20.

## L’esecuzione di più richieste di pubblicazione influisce su altre funzionalità dell’applicazione, ad esempio la modifica di file .dita?

Potrebbe esserci un certo impatto sulle prestazioni, ma in genere è minimo. La maggior parte dell’elaborazione avviene in fase di esecuzione I/O (servizio di pubblicazione senza server), mentre l’istanza di AEM esegue principalmente operazioni di I/O per la generazione delle dipendenze e il polling dello stato. Di conseguenza, l’utilizzo di CPU all’interno di AEM rimane basso e le esperienze di authoring/editing non subiscono modifiche.

## In che modo Experience Manager Guides gestisce file e immagini di grandi dimensioni, come file SVG o file .dita di dimensioni superiori a 500 KB?

Tutti i file di grandi dimensioni vengono compressi e memorizzati nel JCR (Java Content Repository). Il runtime di I/O recupera il pacchetto zip completo prima di avviare la pubblicazione. Anche quando si gestiscono più file di grandi dimensioni (ad esempio, 500 KB ciascuno), questo non influisce in modo significativo sulla velocità di download o trasferimento a causa della creazione di pacchetti ottimizzati e della gestione parallela di I/O.

## Quali sono l’infrastruttura e la configurazione di pubblicazione utilizzate da Experience Manager Guides?

Experience Manager Guides utilizza microservizi senza server containerizzati per la pubblicazione. Ogni nuova versione del servizio di pubblicazione viene rilasciata come immagine Docker e distribuita automaticamente nell’ambiente cloud di Adobe. Questo design garantisce:

- Nessuna manutenzione dell&#39;infrastruttura dedicata per i clienti
- Ridimensionamento automatico per gestire la domanda di pubblicazione
- Aggiornamenti rapidi e tempi di inattività minimi

## Se la coda di pubblicazione o il sistema di gestione si arresta a causa di un sovraccarico, saranno interessate altre funzionalità di AEM?

No, Experience Manager Guides è costruito con un&#39;architettura a tolleranza di errore. Se le esperienze della coda di pubblicazione si sovraccaricano, le richieste vengono automaticamente ritentate e i pod vengono ridimensionati automaticamente per gestire il carico aggiuntivo. Al di là di una certa soglia, la limitazione del carico viene applicata per mantenere la stabilità. Altre aree applicative (authoring, revisione, gestione delle risorse) rimangono invariate.

## È disponibile uno strumento di monitoraggio o un accesso al registro per identificare quando Experience Manager Guides è soggetto a un carico elevato (simile al monitoraggio Jenkins)?

No, al momento non hai accesso agli strumenti di monitoraggio interni. Per i team interni di Adobe, il monitoraggio può essere eseguito utilizzando:

- Splunk per il registro e il tracciamento degli errori
- CLI Kubernetes (K8s) per la verifica delle prestazioni e del comportamento di scalabilità a livello di pod

Se si nota un deterioramento delle prestazioni, i clienti devono contattare il supporto Adobe per avviare indagini e analisi.

## Quale elaborazione viene eseguita prima dell’invio di una richiesta di pubblicazione al microservizio?

Quando attivi una richiesta di pubblicazione dalla scheda Predefiniti nella console Mappa, si verificano i seguenti passaggi:

1. Il sistema accetta la richiesta e convalida i predefiniti della linea di base e i predefiniti condizionali.
2. AEM aggrega tutte le risorse e le dipendenze DITA qualificate.
3. Queste risorse sono incluse in un pacchetto zip.
4. Il servizio di pubblicazione senza server esegue l’inversione di un contenitore Docker, scarica le risorse, esegue l’operazione di pubblicazione e inserisce nuovamente gli artefatti di output generati in Experience Manager Guides.

Questo flusso di lavoro garantisce un’esecuzione di pubblicazione affidabile, isolata e scalabile.

## Quanto tempo ci vuole per avviare la pubblicazione di una mappa sul contenitore dei microservizi e quali sono i fattori che la definiscono?

In genere, una richiesta di pubblicazione richiede alcuni minuti prima di essere inviata al contenitore dei microservizi. Questo tempo iniziale viene utilizzato per l’aggregazione delle dipendenze in AEM.

Una volta ricevuta la richiesta sul servizio di pubblicazione senza server, il tempo totale di pubblicazione dipende da:

- Dimensioni della mappa DITA
- Numero di argomenti e risorse multimediali
- Complessità del contenuto condizionale e regole di formattazione

Mappe più grandi o più complesse possono richiedere proporzionalmente più tempo per la pubblicazione.

## Experience Manager Guides può dare priorità alle richieste di pubblicazione nella coda (anziché First-Come, First-Serve)?

Attualmente, tutti i processi di pubblicazione vengono trattati allo stesso modo e seguono un modello First-Come, First-Serve (FCFS). Al momento non è disponibile alcun meccanismo di definizione delle priorità.

Tuttavia, nelle versioni future, la logica di definizione delle priorità (ad esempio, in base alle dimensioni dei processi o all’importanza aziendale) potrebbe essere introdotta come parte dei miglioramenti apportati all’ottimizzazione delle code.

## In che modo Experience Manager Guides gestisce il ridimensionamento automatico per le richieste di pubblicazione?

L&#39;infrastruttura di pubblicazione Experience Manager Guides supporta il ridimensionamento automatico in base al carico. Quando la pubblicazione aumenta la domanda:

- Vengono attivati automaticamente altri contenitori.
- Ogni pod può elaborare più processi di pubblicazione in parallelo.
- Una volta diminuito il carico, i pod si riducono per ottimizzare costi e prestazioni.

Ciò garantisce elevata disponibilità, prestazioni coerenti e un tempo di coda minimo durante il picco di carico.

## Cosa succede se un processo di pubblicazione ha esito negativo o si interrompe per timeout?

Se una richiesta di pubblicazione non riesce a causa di un problema transitorio (ad esempio, interruzione della rete, timeout del servizio):

- viene ritentato automaticamente in base alla logica retry configurata nel servizio di pubblicazione.
- i registri e i messaggi di errore vengono acquisiti nel back-end a scopo diagnostico.
- se necessario, puoi visualizzare lo stato dell’errore e riprovare a pubblicare manualmente dalla console Mappa.

## È possibile monitorare o tenere traccia dell’avanzamento di un processo di pubblicazione?

Sì, Experience Manager Guides fornisce aggiornamenti in tempo reale sullo stato dei processi nella scheda Predefiniti della console Mappa, tra cui:

- Ora di inizio e di completamento del processo
- Fase corrente (compressione, invio, pubblicazione o caricamento dei risultati)
- Notifiche di errore (se presenti)

Questo ti aiuta a capire l’avanzamento del lavoro e a identificare potenziali ritardi.

## Quali best practice possono migliorare le prestazioni di pubblicazione in Experience Manager Guides?

Per garantire una velocità di pubblicazione ottimale, segui queste best practice:

- Evita file di immagine di grandi dimensioni o argomenti senza riferimenti
- Utilizzare le linee di base per limitare l’ambito di pubblicazione
- Gestione e organizzazione delle gerarchie di mappe DITA
- Pianificazione della pubblicazione intensiva nelle ore di minore utilizzo
- Utilizzare i filtri condizionali in modo efficace per ridurre il carico di elaborazione




