---
title: Utilizzo di MCP con Adobe Experience Manager Guides
description: Scopri come utilizzare MCP (Model Context Protocol) con AEM Guides per lavorare con argomenti, mappe, linee di base e rapporti tramite un assistente AI
feature: Authoring, Publishing
role: User
source-git-commit: c724946a3426e28a1270ba01cdf2646bbf5f2a0d
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 0%

---


# Utilizzo del server Adobe Experience Manager Guides MCP

Il protocollo MCP (Model Context Protocol) è un metodo standard per consentire agli assistenti AI di connettersi a dati e strumenti esterni, anziché passare da un contesto all’altro per utilizzare tali strumenti.

Il server MCP di Adobe Experience Manager Guides porta questo a Experience Manager Guides. Consente a un assistente AI abilitato per MCP, come ad esempio Anthropic Claude, di connettersi al tuo ambiente Experience Manager Guides e di agire per tuo conto, con le tue autorizzazioni AEM. Una volta connessi, puoi lavorare con le tue mappe, argomenti, linee di base e rapporti su Experience Manager Guides as a Cloud Service utilizzando un linguaggio naturale semplice.

Questo articolo spiega perché MCP è utile per Experience Manager Guides, cosa copre il server MCP, quali applicazioni utilizza, come configurarlo e come utilizzarlo.

## Perché è utile MCP per Experience Manager Guides

I team di documentazione spesso dedicano molto tempo ad attività ripetitive e laboriose, come la ricerca di argomenti in una mappa di grandi dimensioni, il controllo degli stati dei documenti, il tracciamento dei collegamenti interrotti, la creazione di linee di base per una versione o l’esportazione di rapporti. Con il server MCP di Experience Manager Guides, puoi chiedere a un assistente AI di gestirli direttamente, senza passare all’interfaccia utente di Experience Manager Guides.

Ad esempio:

- Invece di aprire una mappa e controllare singolarmente lo stato di ogni argomento, chiedere all&#39;assistente di elencare gli argomenti e i relativi stati.
- Invece di avviare manualmente un rapporto sui collegamenti interrotti e di attendere che venga visualizzato l’interfaccia utente di Experience Manager Guides, chiedi all’assistente di eseguire il rapporto e indica quando è pronto.
- Invece di passare alla schermata della linea di base, chiedi all’assistente di creare una linea di base per una mappa specifica.

## Server MCP fornito da Experience Manager Guides

Experience Manager Guides espone le sue funzionalità MCP tramite un singolo endpoint HTTP.

| Server MCP | Endpoint | Descrizione |
| --- | --- | --- |
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Utilizzare argomenti e mappe, linee di base e rapporti in Experience Manager Guides. |

Questo endpoint copre quattro aree:

- **Argomenti e mappe** - Crea, leggi, aggiorna, elimina, versione e blocca argomenti e mappe.
- **Previsioni** - Crea, elenca, esporta, duplica, ricompila ed etichetta le previsioni.
- **Rapporti** - Elenchi argomenti, metadati, collegamenti interrotti e utilizzo multimediale.
- **Sistema** - Versione del pacchetto, integrità del bundle e diagnostica dell&#39;ambiente.

Gli strumenti esatti disponibili possono cambiare nel tempo. Invece di affidarti a un elenco fisso, chiedi all’assistente di mostrarti cosa è disponibile:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Richiedi l’accesso per la tua organizzazione

L&#39;accesso al server Experience Manager Guides MCP è **opt-in per organizzazione**. Prima che chiunque nell’organizzazione possa connettersi:

- Experience Manager Guides deve essere abilitato nell’ambiente AEM as a Cloud Service.
- L’ID organizzazione IMS (ID organizzazione) della tua organizzazione deve essere inserito nell’elenco Consentiti dal team Adobe Guides.

Per richiedere l’accesso, contatta il team Customer Success di Adobe.

## Applicazioni supportate

Il server MCP di Experience Manager Guides è un server **remoto**. Funziona con qualsiasi client MCP che supporta server remoti, tra cui:

### Applicazioni di chat

- Claude antropico (web e desktop)

### Strumenti per sviluppatori

- Cursore
- Codice di Visual Studio
- Altri IDE compatibili con MCP

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

## Autenticazione

Il server Experience Manager Guides MCP utilizza **Adobe IMS** per l&#39;autenticazione.

- Alla prima connessione, il client apre una finestra di accesso del browser. Accedi con il tuo Adobe ID per completare la connessione.
- Dopo che accedi, ogni azione viene eseguita con le autorizzazioni AEM esistenti. Se non disponi dell’autorizzazione per un’azione in AEM, la stessa azione non riesce tramite MCP.

## Utilizzo del server Experience Manager Guides MCP

Una volta connessi, descrivi ciò che desideri in linguaggio semplice. L&#39;assistente seleziona lo strumento appropriato e inserisce i relativi parametri, ad esempio il percorso della mappa o il nome della linea di base.

>[!IMPORTANT]
>
>Le richieste che richiedono diversi passaggi o tempo di completamento, come esportazioni, build della linea di base e aggiornamenti in blocco, funzionano al meglio con un modello pensante. Questi vengono eseguiti in background: l’assistente avvia il processo, quindi ne controlla lo stato fino a quando il risultato, o un collegamento per il download, non è pronto.

### Esempi di prompt

I seguenti prompt illustrano le tipiche richieste che attivano ciascuna uno strumento diverso:

1. **Controllare gli stati degli argomenti in una mappa**

   > Elencare tutti gli argomenti nella mappa in `/content/dam/docs/user-guide.ditamap` e visualizzarne titoli e stati.

1. **Creare una previsione**

   > Creare una baseline statica di `/content/dam/docs/user-guide.ditamap` denominata &quot;Release 3.2&quot;.

1. **Esegui un report**

   > Esegui il rapporto dei collegamenti interrotti per la guida utente e dammi il collegamento di download quando è pronto.

## Gestione delle aspettative

- **Convalida il risultato** - L&#39;assistente può commettere errori, ad esempio scegliendo una mappa o un argomento errato. Esaminare un rapporto o una nuova previsione prima di utilizzarla.
- **Migliora nel tempo** - Man mano che l&#39;assistente migliora, le attività che richiedono alcune richieste oggi potrebbero richiedere una richiesta più tardi.
- **La chiamata è ancora in corso**. L&#39;assistente può segnalare lo stato di un argomento o elencare collegamenti interrotti, ma spetta comunque al revisore o all&#39;editore decidere se il contenuto è pronto per la pubblicazione.
- **Presta attenzione all&#39;approvazione automatica** - Alcuni client MCP, incluso Claude, ti consentono di approvare automaticamente le azioni invece di confermarle tutte. Questa opzione è accettabile per le azioni di sola lettura, ad esempio l’esecuzione di un rapporto. Per le azioni che creano, modificano o bloccano il contenuto, conferma ciascuna di esse in modo da poterla esaminare prima che diventi effettiva.

Per domande su Experience Manager Guides MCP, contatta il tuo team Customer Success di Adobe.


