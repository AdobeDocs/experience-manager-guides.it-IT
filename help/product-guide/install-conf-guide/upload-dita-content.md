---
title: Carica contenuto DITA esistente
description: Scopri come caricare contenuti DITA esistenti in Experience Manager Guides utilizzando lo strumento WebDAV e FrameMaker
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# Carica contenuto DITA esistente utilizzando lo strumento WebDAV e FrameMaker for On-Premise

Probabilmente si dispone di un archivio di contenuti DITA esistenti che si desidera utilizzare con AEM Guides. Per tali contenuti esistenti, puoi utilizzare uno dei seguenti approcci per caricare in blocco i contenuti nell’archivio AEM.

- [Utilizzare uno strumento WebDAV](#use-a-webdav-tool)
- [Usa FrameMaker](#use-framemaker)

## Utilizzare uno strumento WebDAV

Se si creano argomenti e mappe in qualsiasi altro editor DITA, è possibile utilizzare qualsiasi strumento WebDAV per caricare i file. La procedura descritta in questa sezione utilizza WinSCP come strumento WebDAV per caricare contenuti.

Per utilizzare WinSCP per caricare i file, effettuare le seguenti operazioni:

1. Scarica e installa WinSCP sul computer.

1. Avvia l&#39;app WinSCP.

   Viene visualizzata la finestra di dialogo Login (Accesso).

1. Nella finestra di dialogo Accesso specificare un&#39;impostazione Nuovo sito scegliendo WebDAV come **File Protocol** e fornendo altri dettagli di connessione, ad esempio:

   - l’URL in cui è ospitato il server AEM,

   - il numero di porta `\(default is 4502\)` e

   - il nome utente e la password per accedere al server AEM.

1. Seleziona **Accesso**.

   Una volta stabilita la connessione, nell&#39;interfaccia utente WinSCP verranno visualizzati i contenuti di AEM Assets. È possibile sfogliare, creare, aggiornare o eliminare facilmente il contenuto utilizzando Esplora file WinSCP.

## Caricare contenuti con UUID utilizzando uno strumento WebDav {#id201MI0I04Y4}

Per caricare il contenuto con UUID, puoi utilizzare uno dei seguenti metodi:

- Trascinare i contenuti dal sistema locale.
- Utilizza il flusso di lavoro **Crea** \> **File** dall&#39;interfaccia utente Assets di AEM.
- Utilizza uno strumento come WinSCP.

Se si utilizza uno strumento come WinSCP, è possibile definire l&#39;azione da eseguire su un file duplicato impostando l&#39;opzione **Sposta il file precedente con lo stesso UUID in una nuova cartella** in configMgr. Questa opzione definisce l’azione eseguita su un file disponibile in un’altra posizione nell’archivio AEM. Questa impostazione è disponibile nel bundle `*com.adobe.fmdita.config.ConfigManager*` in configMgr.

Per impostazione predefinita, l&#39;opzione **Sposta il vecchio file con lo stesso UUID in una nuova cartella** è attivata. Ciò implica che quando il file che viene caricato è presente in un’altra cartella nell’archivio, il file esistente viene spostato nella posizione corrente e sovrascritto con il file che viene caricato. Se non si seleziona questa opzione, il file viene sovrascritto nella posizione esistente.

**Note aggiuntive sull&#39;utilizzo dei file basati su UUID**:

Durante lo spostamento o la copia di contenuti nell’archivio AEM, è necessario tenere in considerazione i seguenti punti:

- Quando si copiano uno o più file da una posizione a un’altra, viene generato un nuovo UUID per i file privi di UUID. Questo UUID viene aggiunto nei metadati del file.

- Se un file presenta un conflitto o un duplicato, viene generato un nome di file univoco per il nuovo file da copiare o spostare.

- Non ci sono due file con lo stesso UUID. A tutti i nuovi file viene assegnato un UUID univoco.


Durante lo spostamento o la copia del contenuto dal sistema locale all’archivio AEM, è necessario tenere in considerazione i seguenti punti:

- Se un file viene caricato contemporaneamente da due utenti diversi, il file elaborato successivamente sovrascrive quello precedente. Tuttavia, tale pratica è rara e deve essere evitata.

- Quando estrai il contenuto dall’archivio di AEM e apporti modifiche sul sistema locale, assicurati che il nome del file non venga modificato al momento del caricamento.

## Usa FrameMaker

Adobe FrameMaker viene fornito con un potente connettore AEM che consente di caricare facilmente in AEM i documenti DITA e FrameMaker esistenti `\(.book and .fm\)`. Puoi utilizzare varie funzionalità di caricamento dei file, ad esempio il caricamento di un singolo file e di una cartella completa con o senza dipendenze \(come riferimenti a contenuti, riferimenti incrociati e elementi grafici\).

Per utilizzare il connettore AEM di FrameMaker per caricare il contenuto, effettua le seguenti operazioni:

1. Avvia FrameMaker.

1. Aprire la finestra di dialogo **Connection Manager**.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Immetti i seguenti dettagli per connetterti al repository di AEM:

   - **Nome**: immetti un nome descrittivo per identificare la connessione al server AEM.
   - **Server**: immettere l&#39;URL e il numero di porta del server AEM.

   - **Nome utente**/**Password**: immettere il nome utente e la password per accedere al server AEM.

1. Seleziona **Connetti**.

   Una volta stabilita la connessione, Assets dall’archivio AEM viene visualizzato nella finestra Gestione archivio.

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Facendo clic con il pulsante destro del mouse su un file o una cartella è possibile eseguire operazioni correlate. Ad esempio, se fai clic con il pulsante destro del mouse su una cartella, ottieni le opzioni per caricare un file, caricare un file con dipendenze, caricare un’intera cartella e così via.






**Argomento padre:**[ Esegui migrazione contenuto esistente](migrate-content.md)
