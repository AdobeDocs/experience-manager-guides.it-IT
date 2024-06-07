---
title: Configurare l’assistente Guide per cercare il contenuto
description: Scopri come configurare l’Assistente Guide per eseguire ricerche nel contenuto
source-git-commit: 8ac0ed6b867a3efdef750cb19ed4955a67def9ee
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---


# Configurare l’Assistente alle guide basato sull’intelligenza artificiale per cercare contenuti

In qualità di amministratore, puoi configurare la funzione Assistente guide per gli autori. Il servizio Assistente Guide è protetto dall’autenticazione basata su autenticazione Adobe IMS. Integra il tuo ambiente con i flussi di lavoro di autenticazione sicuri basati su token di Adobe e inizia a utilizzare la nuova funzione Assistente Guide. Le seguenti configurazioni consentono di aggiungere **Configurazione IA** a un profilo di cartella. Una volta aggiunto, è possibile utilizzare la funzionalità Assistente Guide nell&#39;editor Web.

## Creare configurazioni IMS nella console di Adobe Developer

Per creare configurazioni IMS nella console Adobe Developer, effettua le seguenti operazioni:

>[!NOTE]
>
>Se hai già creato un progetto OAuth per configurare la funzione Suggerimenti avanzati o la pubblicazione basata su microservizi, puoi saltare i seguenti passaggi per creare il progetto.

1. Launch [Console Adobe Developer](https://developer.adobe.com/console).
1. Dopo aver effettuato correttamente l’accesso a Console sviluppatori, visualizzerai **Home** schermo. Il **Home** è la schermata in cui puoi trovare facilmente informazioni e collegamenti rapidi, inclusi i collegamenti di navigazione superiore per Progetti e Download.
1. Per creare un nuovo progetto vuoto, seleziona **Crea nuovo progetto** dal **Guida rapida** collegamenti.
   ![Collegamenti di avvio rapido](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Crea un nuovo progetto.*

1. Seleziona **Aggiungi API** dal **Progetti** schermo.  Il **Aggiungere un’API** viene visualizzata la schermata. Questa schermata mostra tutte le API, gli eventi e i servizi disponibili per prodotti e tecnologie di Adobe con cui puoi sviluppare applicazioni.

1. Seleziona la **API di gestione I/O** per aggiungerlo al progetto.
   ![API di gestione I/O](assets/confi-ss-io-management.png)
   *Aggiungi l’API di gestione I/O al progetto.*

1. Crea un nuovo **Credenziali OAuth** e salvalo.
   ![Riquadro delle credenziali OAuth nell’API di configurazione](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Configura le credenziali OAuth nell’API.*

1. In  **Progetti** , scegli la scheda **OAuth Server to Server** e quindi selezionare le credenziali appena create.

1. Seleziona la **OAuth Server-to-Server** per visualizzare i dettagli delle credenziali del progetto.

   ![credenziali connesse](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Connettiti al progetto per visualizzare i dettagli delle credenziali.*

1. Torna a **Progetti** e seleziona **Panoramica del progetto** a sinistra.

   <img src="assets/project-overview.png" alt="panoramica del progetto" width="500">

   *Introduzione al nuovo progetto.*

1. Fai clic su **Scarica** per scaricare il servizio JSON.

   <img src="assets/download-json.png" alt="scarica json" width="500">

   *Scarica i dettagli del servizio JSON.*

Hai configurato i dettagli di autenticazione OAuth e scaricato i dettagli del servizio JSON. Mantieni il file a portata di mano in quanto richiesto nella sezione successiva.

### Aggiungere la configurazione IMS all’ambiente

Per aggiungere la configurazione IMS all’ambiente, effettua le seguenti operazioni:

1. Apri Experience Manager e seleziona il programma, che contiene l’ambiente da configurare.
1. Passa a **Ambienti** scheda.
1. Seleziona il nome dell’ambiente da configurare. Dovresti passare alla sezione **Informazioni sull&#39;ambiente** pagina.
1. Passa a **Configurazione** scheda.
1. Aggiornare il campo JSON SERVICE_ACCOUNT_DETAILS. Assicurati di usare lo stesso nome e la stessa configurazione forniti nella schermata seguente.

![configurazione dell’account del servizio ims](assets/ims-service-account-config.png){width="800" align="left"}


*Aggiungi i dettagli di configurazione dell’ambiente.*




Dopo aver aggiunto la configurazione IMS all’ambiente, effettua le seguenti operazioni per collegare queste proprietà alle guide dell’AEM utilizzando OSGi:

1. Nel codice del progetto Git di Cloud Manager, aggiungi i due file seguenti (per il contenuto dei file, visualizza [Appendice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Assicurati che i file appena aggiunti siano coperti dal tuo `filter.xml`.
1. Esegui il commit e invia le modifiche Git.
1. Esegui la pipeline per applicare le modifiche all’ambiente.

Al termine dell’operazione, dovresti essere in grado di utilizzare **Assistente Guide** funzionalità.



## Appendice {#appendix}

**File**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenuto**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


Dopo aver configurato, il **Assistente Guide** ![Assistente Guide](assets/guides-assistant-icon.svg) viene visualizzata nel pannello di destra dell’Editor web. Seleziona l’icona per visualizzare **Assistente Guide** pannello.
Per ulteriori dettagli, vedi [Assistente alle guide basate sull’intelligenza artificiale per cercare contenuti](../user-guide/ai-based-guides-assistant.md) nella Guida utente di Experience Manager.
