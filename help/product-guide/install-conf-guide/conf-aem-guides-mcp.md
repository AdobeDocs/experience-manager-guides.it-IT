---
title: Utilizzo di MCP con Adobe Experience Manager Guides
description: Scopri come utilizzare MCP (Model Context Protocol) con AEM Guides per lavorare con argomenti, mappe, linee di base e rapporti tramite un assistente AI
feature: Authoring
role: User
source-git-commit: 20e5b1099b3d9a7230a40415495ba8e77f438b2a
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 0%
---

# Utilizzo del server Adobe Experience Manager Guides MCP

Il protocollo MCP (Model Context Protocol) è un metodo standard per consentire agli assistenti AI di connettersi a dati e strumenti esterni, anziché passare da un contesto all’altro per utilizzare tali strumenti.

Il server MCP di Adobe Experience Manager Guides porta questo a Experience Manager Guides. Consente a un assistente AI abilitato per MCP, come ad esempio Anthropic Claude, di connettersi al tuo ambiente Experience Manager Guides e di agire per tuo conto, con le tue autorizzazioni AEM. Una volta connessi, puoi lavorare con le tue mappe, argomenti, linee di base e rapporti su Experience Manager Guides as a Cloud Service utilizzando un linguaggio naturale semplice.

Questo articolo spiega perché MCP è utile per Experience Manager Guides, cosa copre il server MCP, quali applicazioni utilizza e come utilizzarlo.

## Perché è utile MCP per Experience Manager Guides

I team di documentazione spesso dedicano molto tempo ad attività ripetitive e laboriose, come la ricerca di argomenti in una mappa di grandi dimensioni, il controllo degli stati dei documenti, il tracciamento dei collegamenti interrotti, la creazione di linee di base per una versione o l’esportazione di rapporti. Con il server MCP di Experience Manager Guides, puoi chiedere a un assistente AI di gestirli direttamente, senza passare all’interfaccia utente di Experience Manager Guides.

Ad esempio:

- Invece di aprire una mappa e controllare singolarmente lo stato di ogni argomento, chiedere all&#39;assistente di elencare gli argomenti e i relativi stati.
- Invece di avviare manualmente un rapporto sui collegamenti interrotti e di attendere che venga visualizzato l’interfaccia utente di Experience Manager Guides, chiedi all’assistente di eseguire il rapporto e indica quando è pronto.
- Invece di passare alla schermata della linea di base, chiedi all’assistente di creare una linea di base per una mappa specifica.

## Server MCP fornito da Experience Manager Guides

Experience Manager Guides espone le funzionalità MCP per l’utilizzo dei contenuti Experience Manager Guides e dei relativi flussi di lavoro. A seconda delle autorizzazioni di AEM, il server MCP fornisce l’accesso alle seguenti funzionalità:

* **Argomenti e mappe**: Utilizzare argomenti e mappe durante l&#39;intero ciclo di vita del contenuto, dalla creazione e visualizzazione del contenuto all&#39;aggiornamento, al controllo delle versioni, al blocco e all&#39;eliminazione.
* **Baseline**: utilizzare le baseline creando, elencando, esportando, duplicando, ricompilando ed etichettandole.
  >[!NOTE]
  >
  > Per gli ambienti Cloud Service e on-premise, le funzionalità di base sono disponibili solo quando è abilitata la [nuova linea di base](../user-guide/web-editor-baseline-v2.md).
* **Rapporti**: ottieni informazioni approfondite sul tuo contenuto accedendo a elenchi di argomenti e metadati, identificando collegamenti interrotti e verificando l&#39;utilizzo di contenuti multimediali.
* **Sistema**: comprendere lo stato del sistema verificando le versioni dei pacchetti, lo stato del bundle e la diagnostica dell&#39;ambiente.

Se non disponi dell’autorizzazione per eseguire un’azione in AEM, non puoi eseguire la stessa azione tramite MCP.


## Applicazioni supportate

Il server MCP di Experience Manager Guides è un server MCP remoto in grado di connettersi con client MCP compatibili. In base all&#39;ambiente in uso, connettere il client MCP e autenticarsi sul server MCP di Experience Manager Guides. Per ulteriori dettagli, visualizzare [Configurare il server Experience Manager Guides MCP](./configure-aem-guides-mcp.md).

## Utilizzo del server Experience Manager Guides MCP

Una volta connessi, descrivi ciò che desideri in linguaggio semplice. L&#39;assistente seleziona lo strumento appropriato e inserisce i relativi parametri, ad esempio il percorso della mappa o il nome della linea di base.

>[!IMPORTANT]
>
> Le richieste che richiedono diversi passaggi o tempo di completamento, come esportazioni, build della linea di base e aggiornamenti in blocco, funzionano al meglio con un modello pensante. Questi vengono eseguiti in background: l’assistente avvia il processo, quindi ne controlla lo stato fino a quando il risultato, o un collegamento per il download, non è pronto.

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


