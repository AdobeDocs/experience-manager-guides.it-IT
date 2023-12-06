---
title: Configurare una nuova pubblicazione basata su microservizi per le guide AEM as a Cloud Service
description: Scopri come configurare una nuova pubblicazione basata su microservizi per le guide AEM.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Configurare una nuova pubblicazione basata su microservizi per le guide AEM as a Cloud Service

Il nuovo microservizio di pubblicazione consente agli utenti di eseguire contemporaneamente carichi di lavoro di pubblicazione di grandi dimensioni su guide AEM as a Cloud Service e di sfruttare la piattaforma senza server Adobe I/O Runtime leader del settore.

Per ogni richiesta di pubblicazione, le guide AEM as a Cloud Service eseguono un contenitore separato che viene ridimensionato orizzontalmente in base alle richieste dell’utente. In questo modo gli utenti possono eseguire più richieste di pubblicazione e ottenere prestazioni migliori rispetto ai server AEM locali di grandi dimensioni.

>[!NOTE]
>
> La pubblicazione basata su microservizi nelle guide AEM supporta i tipi di predefiniti di output PDF (sia nativi che basati su DITA-OT), HTML5, JSON e CUSTOM.

Poiché il nuovo servizio di pubblicazione cloud è protetto dall’autenticazione basata su JWT di Adobe IMS, i clienti devono seguire i passaggi riportati di seguito per integrare i propri ambienti con i flussi di lavoro di autenticazione sicuri basati su token di Adobe e iniziare a utilizzare la nuova soluzione di pubblicazione scalabile basata su cloud.


## Creare configurazioni IMS nella console di Adobe Developer

**Ruolo richiesto per creare le configurazioni**: Amministratore di sistema

Per creare configurazioni IMS nella console Adobe Developer, effettua le seguenti operazioni:

1. Apri Developer Console: `https://developer.adobe.com/console`.

1. Passa a **Progetti** dall’alto.

   <img src="assets/projects-tab.png" alt="scheda progetti" width="500">

1. Per creare un nuovo progetto vuoto, seleziona **Progetto vuoto** dal **Crea nuovo progetto** a discesa.

   <img src="assets/create-new-project.png" alt="crea nuovo progetto" width="500">

1. Seleziona **API** dal **Aggiungi al progetto** per aggiungere l&#39;API di gestione IO al progetto.

   <img src="assets/add-project.png" alt="aggiungi progetto" width="300">

   <img src="assets/io-management-api.png" alt="gestione io" width="500">

1. Crea una nuova coppia di chiavi pubblica/privata durante l’aggiunta dell’API. La chiave privata verrà scaricata automaticamente sul sistema.

   <img src="assets/generate-key-pair.png" alt="genera coppia di chiavi" width="500">

1. Salva l’API configurata.

   <img src="assets/save-api.png" alt="salva api" width="600">

1. Torna a **Progetti** e fai clic su **Panoramica del progetto** a sinistra.

   <img src="assets/project-overview.png" alt="panoramica del progetto" width="500">

1. Clic **Scarica** per scaricare il servizio JSON.

   <img src="assets/download-json.png" alt="scarica json" width="500">

Ora hai configurato i dettagli di autenticazione JWT e hai scaricato anche la chiave privata e i dettagli del servizio JSON. Tenere a portata di mano questi due file in quanto sono necessari nella sezione successiva.

### Aggiungere la configurazione IMS all’ambiente

Per aggiungere la configurazione IMS all’ambiente, effettua le seguenti operazioni:

1. Apri Experience Manager, quindi seleziona il programma contenente l’ambiente da configurare.
1. Passa a **Ambienti** scheda.
1. Fai clic sul nome dell’ambiente da configurare. Dovresti passare alla pagina Informazioni ambiente.
1. Passa a **Configurazione** scheda.
1. Carica la chiave privata e il progetto JSON come mostrato nella schermata seguente. Assicurati di utilizzare gli stessi nomi e la stessa configurazione evidenziati di seguito.

   <img src="assets/ims-config-environment.png" alt="configurazioni ims" width="500">

>[!NOTE]
>
> Apri, copia e incolla il contenuto del file JSON della chiave privata e dei dettagli del servizio nella colonna del valore del pannello Configurazione, come illustrato nella schermata precedente.

Dopo aver aggiunto la configurazione IMS all’ambiente, effettua le seguenti operazioni per collegare queste proprietà alle guide dell’AEM utilizzando OSGi:

1. Nel codice del progetto Git di Cloud Manager, aggiungi i due file seguenti (per il contenuto dei file, vedi [Appendice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Assicurati che i file appena aggiunti siano coperti dal tuo `filter.xml`.
1. Esegui il commit e invia le modifiche Git.
1. Esegui la pipeline per applicare le modifiche all’ambiente.

Al termine dell’operazione, dovresti essere in grado di utilizzare la nuova pubblicazione cloud basata su microservizi.

## Domande frequenti

1. È possibile utilizzare una singola chiave in più ambienti cloud?
   * Sì, puoi generare una chiave privata e utilizzarla per tutti gli ambienti, ma devi configurare le variabili di ambiente per tutti gli ambienti e utilizzare la stessa chiave.
1. Se le configurazioni OSGi per l’utilizzo del microservizio sono abilitate, il processo di pubblicazione funzionerà sul server AEM locale con la stessa base di codice?
   * No, se il flag `dxml.use.publish.microservice` è impostato su `true` cerca sempre le configurazioni dei microservizi. Imposta `dxml.use.publish.microservice` a `false` affinché la pubblicazione funzioni sul tuo sistema locale.
1. Quanta memoria viene allocata al processo DITA quando si utilizza la pubblicazione basata su microservizi? È guidato tramite i parametri ant del profilo DITA?
   * Con la pubblicazione basata su microservizi, l’allocazione della memoria non viene guidata tramite i parametri di ant del profilo DITA. La memoria totale disponibile nel contenitore del servizio è di 8 GB, di cui 6 GB allocati al processo DITA-OT.


## Appendice {#appendix}

**File**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenuto**:

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
}
```

**File**: `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**Contenuto**:
* `dxml.use.publish.microservice`: consente di abilitare la pubblicazione basata su microservizi utilizzando DITA-OT
* `dxml.use.publish.microservice.native.pdf`: consente di abilitare la pubblicazione di PDF nativi basata su microservizi

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
