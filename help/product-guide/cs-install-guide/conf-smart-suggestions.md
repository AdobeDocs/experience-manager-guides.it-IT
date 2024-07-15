---
title: Configurare i suggerimenti avanzati per la creazione
description: Scopri come configurare i suggerimenti avanzati per l’authoring
exl-id: a595ca1f-0123-40d3-a79c-a066bc6517b4
source-git-commit: d3e0c475ebd50a2664ea45c293d34b3a10772633
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# Configurare i suggerimenti avanzati basati sull’intelligenza artificiale per la creazione

In qualità di amministratore, puoi configurare la funzione Suggerimenti avanzati per gli autori. Il servizio di suggerimenti avanzati è protetto dall’autenticazione basata sull’autenticazione di Adobe IMS. Integra il tuo ambiente con i flussi di lavoro di autenticazione sicuri basati su token di Adobe e inizia a utilizzare la nuova funzione di suggerimenti avanzati. La configurazione seguente consente di aggiungere la scheda **Configurazione IA** al profilo della cartella. Una volta aggiunta, è possibile utilizzare la funzionalità di suggerimenti avanzati nell’editor web.

## Creare configurazioni IMS in Adobe Developer Console

Per creare configurazioni IMS in Adobe Developer Console, effettua le seguenti operazioni:

>[!NOTE]
>
>Se hai già creato un progetto OAuth per configurare la pubblicazione basata su microservizi, puoi saltare i seguenti passaggi per creare il progetto.

1. Avvia [Adobe Developer Console](https://developer.adobe.com/console).
1. Dopo aver effettuato correttamente l&#39;accesso a Developer Console, verrà visualizzata la schermata **Home**. Nella schermata **Home** è possibile trovare facilmente informazioni e collegamenti rapidi, inclusi i collegamenti di navigazione superiore a progetti e download.
1. Per creare un nuovo progetto vuoto, seleziona **Crea nuovo progetto** dai collegamenti **Avvio rapido**.
   ![Collegamenti rapidi](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Crea un nuovo progetto.*

1. Selezionare **Aggiungi API** dalla schermata **Progetti**.  Viene visualizzata la schermata **Aggiungi API**. Questa schermata mostra tutte le API, gli eventi e i servizi disponibili per prodotti e tecnologie di Adobe con cui puoi sviluppare applicazioni.

1. Seleziona l&#39;**API di gestione I/O** per aggiungerla al progetto.
   ![API di gestione IO](assets/confi-ss-io-management.png)
   *Aggiungi API di gestione I/O al progetto.*

1. Crea una nuova **credenziale OAuth** e salvala.

   ![Riquadro delle credenziali OAuth nella configurazione API](assets/conf-ss-OAuth-credential.png)

   *Configura le credenziali OAuth nell&#39;API.*

1. Nella scheda **Progetti**, scegli l&#39;opzione **OAuth Server to Server**, quindi seleziona le credenziali appena create.

1. Seleziona il collegamento **OAuth Server-to-Server** per visualizzare i dettagli delle credenziali del progetto.

   ![credenziali connesse](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Connettersi al progetto per visualizzare i dettagli delle credenziali.*

1. Torna alla scheda **Progetti** e seleziona **Panoramica progetto** a sinistra.

   <img src="assets/project-overview.png" alt="panoramica del progetto" width="500">

   *Introduzione al nuovo progetto.*

1. Fai clic sul pulsante **Scarica** nella parte superiore per scaricare il JSON del servizio.

   <img src="assets/download-json.png" alt="scarica json" width="500">

   *Scarica i dettagli del servizio JSON.*

Hai configurato i dettagli di autenticazione OAuth e scaricato i dettagli del servizio JSON. Mantieni il file a portata di mano in quanto richiesto nella sezione successiva.

### Aggiungere la configurazione IMS all’ambiente

Per aggiungere la configurazione IMS all’ambiente, effettua le seguenti operazioni:

1. Apri Experience Manager e quindi seleziona il programma contenente l’ambiente da configurare.
1. Passa alla scheda **Ambienti**.
1. Seleziona il nome dell’ambiente da configurare. Dovresti passare alla pagina **Informazioni sull&#39;ambiente**.
1. Passa alla scheda **Configurazione**.
1. Aggiornare il campo JSON SERVICE_ACCOUNT_DETAILS. Assicurati di usare lo stesso nome e la stessa configurazione forniti nella schermata seguente.

![configurazione account del servizio ims](assets/ims-service-account-config.png){width="800" align="left"}


*Aggiungi i dettagli di configurazione dell&#39;ambiente.*




Dopo aver aggiunto la configurazione IMS all’ambiente, esegui i seguenti passaggi per collegare queste proprietà ad AEM Guides utilizzando OSGi:

1. Nel codice del progetto Git di Cloud Manager, aggiungi i due file seguenti (per il contenuto del file, visualizza [Appendice](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Assicurati che i file appena aggiunti siano coperti dal tuo `filter.xml`.
1. Esegui il commit e invia le modifiche Git.
1. Esegui la pipeline per applicare le modifiche all’ambiente.

Al termine dell’operazione, dovresti essere in grado di utilizzare la funzione di suggerimenti avanzati.



## Appendice {#appendix}

**File**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Contenuto**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```

**File**: `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`

**Contenuto**:

```
{
  "smart.suggestion.flag":true,
  "conref.inline.threshold":0.6,
  "conref.block.threshold":0.7,
  "emerald.url":"https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1",
  "instance.type":"prod"
}
```

## Dettagli della configurazione di Smart Suggestions

| Chiave | Descrizione | Valori consentiti | Valore predefinito |
|---|---|---|---|
| smart.suggestion.flag | Controlla se i suggerimenti avanzati sono abilitati o meno | true/false | false |
| conref.inline.threshold | Soglia che controlla la precisione/il richiamo dei suggerimenti recuperati per il tag attualmente digitato dall’utente. | Qualsiasi valore compreso tra -1,0 e 1,0. | 0,6 |
| conref.block.threshold | Soglia che controlla la precisione/il richiamo dei suggerimenti recuperati per i tag nell’intero file. | Qualsiasi valore compreso tra -1,0 e 1,0. | 0,7 |
| emerald.url | Endpoint per il database vettoriale Emerald | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| instance.type | Tipo di istanza dell’AEM. Assicurati che questo sia univoco per ogni istanza AEM su cui sono configurati i suggerimenti avanzati. Un caso d’uso potrebbe essere quello di testare la funzione nell’ambiente di stage con &quot;instance.type&quot; = &quot;stage&quot; mentre, allo stesso tempo, la funzione è configurata anche su &quot;prod&quot;. | Qualsiasi chiave univoca che identifica l’ambiente. Sono consentiti solo valori *alfanumerici*. &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; | &quot;prod&quot; |

Dopo aver configurato, l’icona dei suggerimenti avanzati viene visualizzata nel pannello a destra dell’Editor web. Quando modifichi gli argomenti, puoi visualizzare l’elenco dei suggerimenti avanzati. Per ulteriori dettagli, visualizza la sezione [Suggerimenti avanzati basati su IA per l&#39;authoring](../user-guide/authoring-ai-based-smart-suggestions.md) nella Guida utente di Experience Manager.
