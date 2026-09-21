---
title: Configurazione delle impostazioni di connessione MCP per AEM Guides On-Premise
description: Scopri come configurare le impostazioni di connessione MCP per AEM Guides On-Premise.
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: Admin
meta-type: Documentation
source-git-commit: e234425f1e277990de25057971f3e2453c93360f
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%
---

# Configurazione delle impostazioni di connessione MCP per Experience Manager Guides (on-premise)

Gli strumenti di intelligenza artificiale come Claude, Cursor e Codex possono connettersi a Experience Manager Guides utilizzando il protocollo MCP (Model Context Protocol). È possibile configurare le impostazioni di autenticazione e connessione MCP dalla pagina Configurazione della console Web Adobe Experience Manager.

Le configurazioni disponibili controllano la gestione dei token, le richieste senza informazioni sul referente e l’URL esterno per l’istanza di authoring di AEM.

## Configurare la gestione dei token di accesso

Per configurare la gestione dei token di accesso, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Cerca e seleziona **AEM Guides OAuth PKCE Token Wrapper**.

3. Configura le seguenti proprietà:

   | Proprietà | Predefiniti | Descrizione |
   |---|---|---|
   | URL di base Granite | `http://localhost:4502` | Specifica l’URL utilizzato da AEM per comunicare con l’istanza Autore durante l’autenticazione. Modificare la porta predefinita 4502 solo se l&#39;istanza di authoring utilizza una porta diversa. |
   | Timeout Granite (ms) | `5000` | Specifica il tempo massimo, in millisecondi, di attesa del completamento della richiesta di autenticazione. |

4. Seleziona **Salva**.

## Configurare le richieste senza informazioni sul referente

>[!NOTE]
>
> Questa impostazione deve essere configurata solo se si utilizza Cursore.

Alcuni client MCP, tra cui Cursor, potrebbero inviare richieste senza informazioni sul referente. Per consentire queste richieste, configura il filtro Apache Sling Referrer come segue:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Cerca e seleziona **Filtro referrer Apache Sling**.

3. Nella proprietà **Consenti vuoto**, impostare il valore su `true`.

   Questa impostazione consente le richieste che non contengono informazioni sul referente durante l’autenticazione.

4. Seleziona **Salva**.

## Configurare l’URL esterno per l’istanza di authoring

Il servizio **Day CQ Link Externalizer** ti consente di definire centralmente gli URL esterni utilizzati per prefissare i percorsi delle risorse, incluso l&#39;URL dell&#39;istanza di authoring di AEM.

Per configurare l’URL esterno, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Cerca e seleziona **Day CQ Link Externalizer**.

3. In **Domains**, aggiungere o aggiornare la mappatura `author` utilizzando il seguente formato:

   ```
   author [scheme://]server[:port][/contextpath]
   ```

   Ad esempio:

   ```
   author https://author.mycompany.com
   ```

4. Seleziona **Salva**.