---
title: Architettura e prestazioni del microservizio di pubblicazione cloud
description: Scopri in che modo il nuovo microservizio consente la pubblicazione scalabile su AEMaaCS.
exl-id: 948fce3f-b989-48f0-9a85-e921717e2986
feature: Microservice in AEM Guides
role: User, Admin
source-git-commit: 462647f953895f1976af5383124129c3ee869fe9
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%

---

# Architettura di Cloud Publishing Microservice e analisi delle prestazioni

In questo articolo vengono condivisi approfondimenti sull’architettura e sui numeri di prestazioni del nuovo microservizio di pubblicazione cloud.

>[!NOTE]
>
> La pubblicazione basata su microservizi in AEM Guides supporta i tipi di predefiniti di output PDF (sia nativi che basati su DITA-OT), HTML5, JSON e CUSTOM.

## Problemi relativi ai flussi di lavoro di pubblicazione esistenti sul cloud

La pubblicazione DITA è un processo che richiede molte risorse e dipende principalmente dalla memoria di sistema e dalla CPU disponibili. La necessità di queste risorse aumenta ulteriormente se gli editori pubblicano mappe di grandi dimensioni con molti argomenti o se vengono attivate più richieste di pubblicazione parallela.

Se non utilizzi il nuovo servizio, tutta la pubblicazione avviene sullo stesso pod di Kubernetes(k8) che esegue anche il server cloud AEM. Un pod k8 tipico ha un limite sulla quantità di memoria e CPU che può utilizzare. Se gli utenti di AEM Guides pubblicano carichi di lavoro paralleli o di grandi dimensioni, questo limite può superare rapidamente. K8 riavvia i pod che stanno tentando di utilizzare più risorse del limite configurato, il che può avere un grave impatto sull’istanza cloud AEM stessa.

Questo vincolo di risorse è stato il motivo principale per cui è stato ideato un servizio dedicato che può consentirci di eseguire più carichi di lavoro di pubblicazione simultanei e di grandi dimensioni sul cloud.

## Introduzione alla nuova architettura

Il servizio utilizza le soluzioni cloud all’avanguardia di Adobe come App Builder, IO Eventing, IMS per creare un’offerta senza server. Questi servizi si basano su standard industriali ampiamente accettati come Kubernetes e docker.

Ogni richiesta al nuovo microservizio di pubblicazione viene eseguita in un contenitore docker isolato che esegue una sola richiesta di pubblicazione alla volta. Se si ricevono nuove richieste di pubblicazione, vengono creati automaticamente più contenitori. Questa configurazione a contenitore singolo per richiesta consente al microservizio di fornire le migliori prestazioni ai clienti senza introdurre rischi per la sicurezza. Questi contenitori vengono eliminati una volta terminata la pubblicazione, liberando così eventuali risorse inutilizzate.

Tutte queste comunicazioni sono protette da Adobe IMS utilizzando l’autenticazione e l’autorizzazione basate su JWT e vengono eseguite su HTTPS.

<img src="assets/architecture.png" alt="scheda progetti" width="600">

>[!NOTE]
>
> Il processo di pubblicazione esegue alcune parti dipendenti dal contenuto della richiesta sul server AEM stesso, come la generazione dell’elenco di dipendenze. Tuttavia, le parti più esaustive del processo di pubblicazione, come l&#39;esecuzione di DITA-OT o del motore nativo, sono state scaricate nel nuovo servizio.


## Analisi delle prestazioni

Questa sezione mostra i numeri delle prestazioni del microservizio. Confronta le prestazioni del microservizio con l’offerta on-premise di AEM Guides, in quanto la vecchia architettura cloud aveva problemi di pubblicazione simultanea o di pubblicazione di mappe molto grandi.

Se pubblichi una mappa di grandi dimensioni in locale, potrebbe essere necessario modificare i parametri dell’heap Java, altrimenti si potrebbero verificare errori di memoria insufficiente. Sul cloud, il microservizio è già profilato e dispone di un heap Java ottimale e altre configurazioni pronte all’uso.

### Esecuzione di una pubblicazione su cloud e on-prem

* Cloud

  Se esegui una singola pubblicazione sul cloud utilizzando il nuovo servizio, la pubblicazione può richiedere un po’ più di tempo rispetto alla singola pubblicazione locale. Questo periodo di tempo leggermente più lungo è dovuto alla natura distribuita della nuova architettura cloud.

  <img src="assets/cloud_single_publish.png" alt="scheda progetti" width="600">

* On-premise

  I risultati della pubblicazione singola sono migliori sulla vecchia architettura cloud o on-premise, in quanto la pubblicazione completa avviene sullo stesso pod/computer in cui è in esecuzione l’AEM.

  <img src="assets/onprem_single_publish.png" alt="scheda progetti" width="600">

### Esecuzione di più pubblicazioni su cloud rispetto a quelle on-premise

* Cloud

  Il nuovo microservizio di pubblicazione brilla in questo scenario. Come puoi vedere dall’immagine seguente, con l’aumento dei più processi di pubblicazione simultanei, cloud è in grado di pubblicarli senza alcun aumento significativo dei tempi di pubblicazione.

  <img src="assets/cloud_bulk_publish.png" alt="scheda progetti" width="600">

* On-premise

  L’esecuzione della pubblicazione simultanea su un server locale causa un grave deterioramento delle prestazioni. Questo calo delle prestazioni è più grave se gli editori pubblicano più mappe contemporaneamente.

  <img src="assets/onprem_bulk_publish.png" alt="scheda progetti" width="600">

## Vantaggi aggiuntivi

Parte di ogni richiesta di pubblicazione deve essere eseguita sull’istanza AEM per recuperare il contenuto di pubblicazione corretto da inviare al microservizio. La nuova architettura cloud utilizza i processi AEM invece dei flussi di lavoro AEM, come avveniva nella vecchia architettura. Questa modifica consente agli amministratori di AEM Guides di configurare singolarmente le impostazioni della coda di pubblicazione cloud senza influire su altri processi o configurazioni del flusso di lavoro AEM.

I dettagli sulla configurazione del nuovo microservizio di pubblicazione sono disponibili qui: [Configura microservizio](configure-microservices.md)
