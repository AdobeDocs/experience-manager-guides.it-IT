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

In qualità di amministratore, puoi configurare la funzione Suggerimenti avanzati per gli autori. Il servizio di suggerimenti avanzati è protetto dall’autenticazione basata sull’autenticazione di Adobe IMS. Integra il tuo ambiente con i flussi di lavoro di autenticazione sicuri basati su token di Adobe e inizia a utilizzare la nuova funzione di suggerimenti avanzati. La seguente configurazione consente di aggiungere **Configurazione IA** al profilo della cartella. Una volta aggiunta, è possibile utilizzare la funzionalità di suggerimenti avanzati nell’editor web.

## Creare configurazioni IMS nella console di Adobe Developer

Per creare configurazioni IMS nella console Adobe Developer, effettua le seguenti operazioni:

>[!NOTE]
>
>Se hai già creato un progetto OAuth per configurare la pubblicazione basata su microservizi, puoi saltare i seguenti passaggi per creare il progetto.

1. Launch [Console Adobe Developer](https://developer.adobe.com/console).
1. Dopo aver effettuato correttamente l’accesso a Console sviluppatori, visualizzerai **Home** schermo. Il **Home** è la schermata in cui puoi trovare facilmente informazioni e collegamenti rapidi, inclusi i collegamenti di navigazione superiore per Progetti e Download.
1. Per creare un nuovo progetto vuoto, seleziona  **Crea nuovo progetto** dal  **Guida rapida** collegamenti.
   ![Collegamenti di avvio rapido](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Crea un nuovo progetto.*

1. Seleziona  **Aggiungi API**  dal  **Progetti** schermo.  Il **Aggiungere un’API** viene visualizzata la schermata. Questa schermata mostra tutte le API, gli eventi e i servizi disponibili per prodotti e tecnologie di Adobe con cui puoi sviluppare applicazioni.

1. Seleziona la **API di gestione I/O** per aggiungerlo al progetto.
   ![API di gestione I/O](assets/confi-ss-io-management.png)
   *Aggiungi l’API di gestione I/O al progetto.*

1. Crea un nuovo **Credenziali OAuth** e salvalo.

   ![Riquadro delle credenziali OAuth nell’API di configurazione](assets/conf-ss-OAuth-credential.png)

   *Configura le credenziali OAuth nell’API.*

1. In  **Progetti** , scegli **OAuth Server to Server** e quindi selezionare le credenziali appena create.

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

1. Apri Experience Manager e quindi seleziona il programma contenente l’ambiente da configurare.
1. Passa a **Ambienti** scheda.
1. Seleziona il nome dell’ambiente da configurare. Dovresti passare alla sezione **Informazioni sull&#39;ambiente** pagina.
1. Passa a **Configurazione** scheda.
1. Aggiornare il campo JSON SERVICE_ACCOUNT_DETAILS. Assicurati di usare lo stesso nome e la stessa configurazione forniti nella schermata seguente.

![configurazione dell’account del servizio ims](assets/ims-service-account-config.png){width="800" align="left"}


*Aggiungi i dettagli di configurazione dell’ambiente.*




Dopo aver aggiunto la configurazione IMS all’ambiente, effettua le seguenti operazioni per collegare queste proprietà alle guide dell’AEM utilizzando OSGi:

1. Nel codice del progetto Git di Cloud Manager, aggiungi i due file seguenti (per il contenuto dei file, visualizza [Appendice](#appendix)).

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
| instance.type | Tipo di istanza dell’AEM. Assicurati che questo sia univoco per ogni istanza AEM su cui sono configurati i suggerimenti avanzati. Un caso d’uso potrebbe essere quello di testare la funzione nell’ambiente di stage con &quot;instance.type&quot; = &quot;stage&quot; mentre, allo stesso tempo, la funzione è configurata anche su &quot;prod&quot;. | Qualsiasi chiave univoca che identifica l’ambiente. Solo *alfanumerico* sono consentiti. &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; | &quot;prod&quot; |

Dopo aver configurato, l’icona dei suggerimenti avanzati viene visualizzata nel pannello a destra dell’Editor web. Quando modifichi gli argomenti, puoi visualizzare l’elenco dei suggerimenti avanzati. Per ulteriori dettagli, vedi [Suggerimenti avanzati basati sull’intelligenza artificiale per l’authoring](../user-guide/authoring-ai-based-smart-suggestions.md) nella Guida utente di Experience Manager.
