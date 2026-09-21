---
title: Configurazione di MCP per Adobe Experience Manager Guides
description: Scopri come collegare un assistente AI al server Experience Manager Guides MCP per le distribuzioni Cloud Service e on-premise
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: User
meta-type: Documentation
source-git-commit: e234425f1e277990de25057971f3e2453c93360f
workflow-type: tm+mt
source-wordcount: '1539'
ht-degree: 1%
---

# Configurare il server Experience Manager Guides MCP

Questo articolo descrive i dettagli specifici dell&#39;ambiente per la connessione al server MCP di Experience Manager Guides. La configurazione varia a seconda che l’istanza Experience Manager Guides esegua as a Cloud Service o on-premise. Seleziona la scheda che corrisponde all’ambiente.

>[!BEGINTABS]

>[!TAB Cloud Service]

## Endpoint server MCP

Experience Manager Guides espone le sue funzionalità MCP tramite un singolo endpoint HTTP.

| Server MCP | Endpoint | Descrizione |
|---|---|---|
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Utilizza argomenti e mappe, [nuove linee di base](../user-guide/web-editor-baseline-v2.md) e rapporti in Experience Manager Guides. |

Per scoprire l’elenco di strumenti corrente per il tuo ambiente, chiedi all’assistente:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Richiedi l’accesso per la tua organizzazione

L&#39;accesso al server Experience Manager Guides MCP è **opt-in per organizzazione**. Prima che chiunque nell’organizzazione possa connettersi:

- Experience Manager Guides deve essere abilitato nell’ambiente AEM as a Cloud Service.
- L’ID organizzazione IMS (ID organizzazione) della tua organizzazione deve essere inserito nell’elenco Consentiti dal team Adobe Guides.

Per richiedere l’accesso, contatta il team Customer Success di Adobe.

## Configurazione

Non si installa nulla localmente. Puntare il client all’URL del server e autenticarsi tramite il flusso di accesso di Adobe IMS.

### Claude antropico

Segui la procedura dettagliata ufficiale: [Configura Claude per AEM MCP](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/ai-in-aem/mcp-support/chat-applications/setup-claude). Quando aggiungi il connettore personalizzato, utilizza l’endpoint Experience Manager Guides:

```
https://mcp.adobeaemcloud.com/adobe/mcp/guides
```

### Cursore / Codice di Visual Studio

Aggiungi il server alla configurazione MCP. Per il cursore, aggiungerlo a `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "aem-guides": {
      "url": "https://mcp.adobeaemcloud.com/adobe/mcp/guides"
    }
  }
}
```

Per i client che supportano solo server locali (stadio), eseguire il bridge all&#39;endpoint remoto con [`mcp-remote`](https://www.npmjs.com/package/mcp-remote):

```json
{
  "mcpServers": {
    "aem-guides": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.adobeaemcloud.com/adobe/mcp/guides"]
    }
  }
}
```

>[!TAB On-Premise]

Puoi collegare i client di intelligenza artificiale supportati a un’istanza Experience Manager Guides on-premise utilizzando il protocollo MCP (Model Context Protocol). Dopo aver stabilito la connessione, il client può accedere alle operazioni Experience Manager Guides disponibili per il tuo account utente AEM.

Tutte le operazioni vengono eseguite utilizzando **l&#39;identità e le autorizzazioni AEM**. Il client connesso può visualizzare o modificare solo il contenuto e le risorse a cui il tuo account AEM è autorizzato ad accedere.

L’autenticazione utilizza il flusso del codice di autorizzazione OAuth 2.0 con Proof Key for Code Exchange (PKCE). Effettua l’autenticazione con AEM quando connetti un client per la prima volta. Dopo l&#39;autenticazione, la connessione aggiorna automaticamente i token di accesso.

È possibile connettere i seguenti client:

| Client | Metodo di connessione | Requisiti dell’istanza di AEM |
| ------------------ | ----------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Claude Desktop** | Estensione desktop (`.mcpb`) | Supporta gli endpoint HTTP e HTTPS, inclusi gli host interni accessibili dalla rete aziendale. |
| **ChatGPT (Web e desktop)** | Connettore personalizzato | Richiede un endpoint HTTPS accessibile al pubblico con un certificato TLS valido e disponibile al pubblico. |
| **Cursore** | Configurazione MCP in `~/.cursor/mcp.json` | Supporta gli endpoint HTTP e HTTPS, inclusi gli host interni accessibili dalla rete aziendale. |

## Prerequisiti

Prima di connettere un client, rivolgiti al tuo amministratore AEM per verificare la seguente configurazione:

1. **Verificare che la funzionalità MCP sia distribuita.**: verificare che la funzionalità MCP sia distribuita e in esecuzione nell&#39;istanza di Experience Manager Guides.

2. **Configura l&#39;URL di base Granite.**: in Gestione configurazione console Web AEM (`/system/console/configMgr`), individuare la configurazione **Wrapper token PKCE OAuth Experience Manager Guides** e verificare che l&#39;URL di base Granite sia configurato. Se l’URL di base di Granite non è configurato correttamente, il client non può stabilire la connessione.

3. **Configura Day CQ Link Externalizer.**: in AEM Web Console Configuration Manager, individua la configurazione **Day CQ Link Externalizer** e verifica che l&#39;URL dell&#39;autore esterno punti all&#39;istanza di authoring AEM corretta. Durante l’individuazione OAuth viene utilizzato l’URL dell’autore esterno. Un URL errato può impedire al client di completare la connessione.

   Per ulteriori dettagli, visualizza [Configurare le impostazioni di connessione MCP per AEM Guides On-Premise](./configure-aem-guides-mcp-on-prem.md)

4. **Ottenere l&#39;URL del server MCP.**: l&#39;URL del server MCP utilizza il seguente formato:

   ```
   http(s)://<AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   >[!NOTE]
   >
   > Utilizza l’endpoint SSE completo durante la configurazione di un client. Non aggiungere una barra finale all’URL.

   Ad esempio:

   **Istanza di authoring interna di AEM:**

   ```
   http://10.42.42.20:4502/bin/guides/v1/mcp/sse
   ```

   **Istanza autore AEM pubblica:**

   ```
   https://author.example.com/bin/guides/v1/mcp/sse
   ```



5. **Verifica le credenziali e le autorizzazioni di AEM.**: è necessario disporre di un account valido per l&#39;istanza di AEM. Utilizza le stesse credenziali utilizzate per accedere all’interfaccia utente di AEM. Le operazioni disponibili tramite MCP sono determinate dalle autorizzazioni assegnate a questo account.

## Connetti Claude Desktop

Claude Desktop supporta le estensioni desktop (`.mcpb`). L’estensione MCP di Experience Manager Guides crea pacchetti per la configurazione della connessione in modo che non sia necessario modificare manualmente una configurazione JSON MCP.

1. Estrarre il file zip [AEM Guides .mcpb](./mcpbfile.zip) e ottenere il file di estensione `aem-guides-mcp.mcpb`.

2. Apri **Claude Desktop** e passa a **Impostazioni > Estensioni**.

3. Installare `aem-guides-mcp.mcpb` facendo doppio clic sul file o trascinandolo nella finestra Estensioni.

   **Adobe Experience Manager Guides MCP** viene visualizzato nella finestra di dialogo di installazione.

4. Selezionare **Installa**.

5. Nel campo **URL server MCP Experience Manager Guides**, immetti l&#39;endpoint SSE completo per l&#39;istanza AEM.

   Ad esempio:

   ```
   http://<AEM-HOST>:4502/bin/guides/v1/mcp/sse
   ```

6. Seleziona **Salva** e assicurati che l&#39;estensione sia abilitata.

## Connetti ChatGPT

Puoi configurare il server Experience Manager Guides MCP come connettore personalizzato in ChatGPT.

>[!IMPORTANT]
>
> ChatGPT richiede che il server MCP sia disponibile tramite un endpoint HTTPS **accessibile pubblicamente con un certificato TLS valido e attendibile**.
>
> Gli endpoint HTTP, `localhost`, gli indirizzi IP privati e i certificati autofirmati non sono supportati. L’istanza di AEM deve essere esposta tramite un host HTTPS, ad esempio un load balancer, un proxy inverso o un Dispatcher configurato con TLS.
>
> Anche l&#39;URL dell&#39;autore esterno configurato in **Day CQ Link Externalizer** deve puntare all&#39;indirizzo HTTPS pubblico. In caso contrario, i metadati di individuazione OAuth possono annunciare endpoint di autenticazione non corretti e impedire l’accesso.

1. Verifica che il server MCP sia disponibile a un URL HTTPS pubblico nel seguente formato:

   ```
   https://<PUBLIC-AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   Apri l’endpoint in un browser e verifica di poter raggiungere l’host senza un avviso di certificato o un errore di connessione.

2. In ChatGPT, apri **Impostazioni > Plugin**.

   >[!NOTE]
   >
   > La disponibilità del connettore dipende dal piano ChatGPT e dalla configurazione dell’area di lavoro. L’amministratore dell’area di lavoro potrebbe dover abilitare connettori personalizzati o per sviluppatori.

3. Seleziona l’opzione per aggiungere o creare un plug-in.

4. Specifica i dettagli del connettore:

   * **Nome:** Immettere `Experience Manager Guides` o un altro nome descrittivo.
   * **URL server MCP:** Immettere l&#39;endpoint SSE HTTPS pubblico.
   * **Autenticazione:** Seleziona **OAuth**.

   Non è necessario fornire un ID client OAuth o un segreto client. Il server MCP supporta la registrazione client automatica.

5. Crea il connettore.

## Connetti cursore

Configura il server MCP di Experience Manager Guides in Cursor aggiungendo i dettagli del server alla configurazione MCP.

1. In Cursore, passa a **Personalizza > MCP > Nuovo**.

   Il cursore apre il file di configurazione `~/.cursor/mcp.json`.

2. Aggiungi la configurazione del server Experience Manager Guides MCP.

   Ad esempio:

   ```json
   {
     "mcpServers": {
       "aem-guides": {
         "url": "http://10.42.34.176:4502/bin/guides/v1/mcp/sse",
         "type": "http"
       }
     }
   }
   ```

3. Sostituisci l’URL di esempio con l’endpoint SSE MCP per l’istanza di AEM.

4. Salva la configurazione.

5. Abilita il server MCP configurato.

>[!ENDTABS]

## Autenticazione e utilizzo di Experience Manager Guides

Dopo aver configurato la connessione MCP nel client, esegui l’autenticazione con il tuo account AEM.

1. Avvia il processo di autenticazione dal client.

   * **Claude Desktop:** Il flusso di autenticazione viene avviato quando Claude tenta per la prima volta di utilizzare la connessione Experience Manager Guides.
   * **ChatGPT:** l&#39;autenticazione viene avviata dopo la creazione e la connessione del connettore Experience Manager Guides.
   * **Cursore:** Abilitare il server MCP configurato e selezionare **Autentica**.

2. Quando la pagina di accesso di AEM si apre nel browser, effettua l’accesso con le credenziali AEM.

3. Approva la richiesta di accesso quando richiesto.

4. Al termine dell’autenticazione, torna al client.

Ora puoi utilizzare le operazioni Experience Manager Guides disponibili per il tuo account. Ad esempio, prova a visualizzare le seguenti richieste:

```
List the available Experience Manager Guides operations.
```

```
Get the topic list for my map in Experience Manager Guides.
```

```
Show me the broken-link report for my map.
```

>[!NOTE]
>
> Le operazioni e i contenuti disponibili tramite MCP sono determinati dalle autorizzazioni dell’account AEM utilizzato per l’autenticazione. La connessione MCP non fornisce privilegi AEM aggiuntivi.

Dopo l’autenticazione, il client aggiorna automaticamente i token di autenticazione. In genere non è necessario accedere di nuovo a meno che la sessione non scada o l&#39;accesso non venga revocato.

## Risoluzione dei problemi di connessione

Utilizzare le informazioni seguenti per risolvere i problemi comuni di connessione e autenticazione.

| Client | Problema | Possibile causa e risoluzione |
| -------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Claude Desktop | L&#39;estensione non può essere installata o è disabilitata. | La versione di Claude Desktop in uso potrebbe non supportare l&#39;estensione. Aggiorna Claude Desktop e riprova. |
| Claude Desktop | Il browser non si apre per l’autenticazione o la connessione non viene completata. | Verifica l’URL del server MCP. Deve terminare con `/bin/guides/v1/mcp/sse` e non deve contenere una barra finale. Verifica inoltre che l’istanza di AEM sia accessibile dal computer. |
| ChatGPT | ChatGPT non può raggiungere il server MCP o non consente di aggiungere il connettore. | Verifica che l’endpoint sia accessibile al pubblico tramite HTTPS. Gli endpoint HTTP, `localhost`, gli indirizzi IP privati e gli endpoint di rete privati non sono supportati. |
| ChatGPT | Viene visualizzato un errore di certificato o di sicurezza. | Verificare che il server utilizzi un certificato valido e non scaduto rilasciato da un&#39;autorità di certificazione pubblica. I certificati autofirmati non sono supportati. |
| ChatGPT | L&#39;autenticazione viene reindirizzata a un host errato o non riesce durante l&#39;individuazione. | Verifica che l&#39;URL dell&#39;autore esterno in **Day CQ Link Externalizer** punti all&#39;indirizzo dell&#39;autore pubblico di HTTPS AEM. |
| Tutti i client | La registrazione non riesce durante l&#39;autenticazione. | Verifica la configurazione della registrazione OAuth lato server con il tuo amministratore AEM. |
| Tutti i client | Autenticazione non riuscita o non completata. | Verifica l’URL di base di Granite, la configurazione di Day CQ Link Externalizer, l’URL del server MCP e la connettività all’istanza di AEM. |
| Tutti i client | La connessione ha esito positivo, ma le operazioni o i risultati di Experience Manager Guides non sono disponibili. | Verifica che l’account AEM autenticato disponga delle autorizzazioni Experience Manager Guides richieste e che l’operazione richiesta sia disponibile per l’account. |
| Tutti i client | Il client richiede l’autenticazione dopo che la connessione aveva funzionato in precedenza. | La sessione di autenticazione potrebbe essere scaduta o l&#39;accesso potrebbe essere stato revocato. Esegui di nuovo l’autenticazione con AEM. |



