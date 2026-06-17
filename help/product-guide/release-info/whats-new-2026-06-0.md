---
title: Note sulla versione | Novità della versione 2026.06.0 di Adobe Experience Manager Guides
description: Scopri le funzioni nuove e migliorate della versione 2026.06.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 0%

---

# Novità della versione 2026.06.0 (giugno 2026)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2026.06.0 di Adobe Experience Manager Guides as a Cloud Service.

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 2026.06.0](fixed-issues-2026-06-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.06.0](../release-info/upgrade-instructions-2026-06-0.md).


## Nuova raccolta di mappe (Beta) per la gestione delle mappe e la pubblicazione degli output

>[!NOTE]
>
> Questa funzione è attualmente disponibile come funzionalità di Beta ed è disabilitata per impostazione predefinita. Per abilitarlo nel tuo ambiente, contatta il team Customer Success.

La nuova raccolta di mappe (Beta) riunisce le attività di gestione della raccolta di mappe e di generazione dell’output in un’unica interfaccia. Da un&#39;unica posizione è possibile gestire mappe e predefiniti, generare e pubblicare output, visualizzare la cronologia di generazione e pubblicazione e altro ancora. Riunendo le attività di pubblicazione correlate, è più semplice utilizzare le raccolte di mappe e tenere traccia delle attività di output su più mappe e sulle lingue associate.

![](assets/new-maps-collection.png)

Per ulteriori dettagli, visualizzare [Utilizza nuova raccolta mappe per la generazione di output (Beta)](../user-guide/generate-output-use-new-map-collection-output-generation.md).

## Introduzione di un nuovo motore di pubblicazione per Native PDF

È ora disponibile un nuovo motore di pubblicazione, *Motore PDF nativo v2*, per PDF nativo in Experience Manager Guides. Include miglioramenti al rendering e correzioni per i problemi del motore PDF nativo v1. Poiché il comportamento di rendering è stato aggiornato, l&#39;output PDF generato con *motore PDF nativo v2* potrebbe essere diverso dall&#39;output generato con il motore di pubblicazione PDF nativo esistente, *motore PDF nativo v1*.

Ad esempio, il testo nei PDF generati potrebbe apparire leggermente diverso a causa degli aggiornamenti dei font di base utilizzati da *Native PDF Engine v2*. Analogamente, le immagini possono apparire più nitide grazie ai miglioramenti apportati nell&#39;interpolazione e nel comportamento di rendering delle immagini.

Scopri come [abilitare il motore nativo di PDF v2](../native-pdf/conf-new-pdf-engine.md) nel tuo ambiente.

Per informazioni sul **motore PDF nativo v2**, visualizzare [Utilizzare il motore PDF nativo v2](../native-pdf/new-pdf-engine.md).


## Miglioramenti dell’editor

### Supporto per lo stile di citazione AMA

Experience Manager Guides ora supporta lo stile di citazione AMA (American Medical Association), estendendo la struttura di citazione esistente per soddisfare gli standard di documentazione richiesti dai clienti nei settori sanitario, normativo e delle scienze biologiche.

Quando AMA è selezionato come stile di citazione nelle **impostazioni Workspace**, le citazioni vengono formattate automaticamente in base alle linee guida AMA, inclusi il rendering numerico in apice, la numerazione sequenziale e l&#39;ordinamento accurato dell&#39;elenco di riferimenti. L&#39;opzione **Analizza citazione** nell&#39;editor è disponibile solo quando è selezionato AMA, consentendo agli autori di aggiungere e analizzare citazioni senza cambiare contesto.

Lo stile di citazione AMA è supportato nei formati di output PDF nativo e AEM Sites. Per configurare lo stile della citazione, passare a **Impostazioni Workspace** e selezionare AMA dalle opzioni di stile della citazione. Per ulteriori dettagli, visualizzare [Operazioni con le citazioni](../user-guide/web-editor-apply-citations.md).


### Il supporto per origini dati e citazioni esterne è ora disponibile nel nuovo editor

Il nuovo editor ora supporta due funzionalità Experience Manager Guides esistenti: la possibilità di connettersi con origini dati esterne e utilizzare citazioni nei documenti.

Gli autori possono continuare a utilizzare origini dati esterne configurate durante la creazione o l’aggiornamento del contenuto nel nuovo editor. Le citazioni sono inoltre supportate, in modo che gli autori possano aggiungere e gestire riferimenti nei contenuti senza dover cambiare editor.

## Miglioramenti della revisione

### Sincronizza il completamento dell’attività di revisione tra l’interfaccia utente di revisione e la casella in entrata di AEM (Beta)

>[!NOTE]
>
> Questa funzione è attualmente disponibile come funzionalità di Beta ed è disabilitata per impostazione predefinita. Per abilitarlo nel tuo ambiente, contatta il team Customer Success.

Ora puoi mantenere sincronizzato il completamento dell’attività di revisione tra l’interfaccia utente di revisione e la casella in entrata di AEM. Quando questa funzione viene abilitata, il completamento di un’attività nell’interfaccia utente di revisione la rimuove dalla casella in entrata di AEM e il completamento di tale attività dalla casella in entrata di AEM la contrassegna come completata nell’interfaccia utente di revisione. In questo modo è possibile evitare di completare la stessa attività due volte e semplificare il flusso di lavoro di revisione. Gli autori e gli iniziatori delle attività possono continuare a rivedere il feedback e riassegnare le attività quando è necessaria una revisione aggiuntiva. Quando un’attività viene riassegnata, viene generata una nuova notifica Casella in entrata AEM per il revisore, che consente al ciclo di revisione di continuare senza problemi.

Per ulteriori dettagli, visualizzare [Completa l&#39;attività di revisione come revisore](../user-guide/review-complete-review-tasks.md).

## Miglioramenti dei contenuti di apprendimento

In questa versione sono disponibili i seguenti miglioramenti per la funzione dei contenuti di formazione e apprendimento del prodotto:

- Gli autori possono ora rendere obbligatorio un controllo della conoscenza per gli Allievi prima di avanzare in un corso. È stata introdotta una nuova opzione **Richiedi verifica conoscenza per procedere** per i controlli conoscenza nei corsi. Quando questa opzione è abilitata, agli Allievi viene richiesto di effettuare un controllo della conoscenza prima di passare al contenuto del corso successivo. Questo aiuta a garantire che i controlli delle conoscenze richiesti vengano completati in punti designati del corso. Per ulteriori dettagli, visualizzare [Altre opzioni nel menu Inserisci](../learning-content/lc-other-insert-options.md).
- È ora possibile utilizzare campi di input di testo su più righe durante la creazione di contenuti di apprendimento. Questo miglioramento semplifica l’acquisizione di risposte più lunghe da parte degli Allievi, grazie al supporto di interruzioni di riga e testo a capo in un singolo campo, senza ricorrere a script personalizzati. Ulteriori informazioni su [Altre opzioni nel menu Inserisci](../learning-content/lc-other-insert-options.md).
- I modelli di output SCORM ora supportano l’assegnazione di layout di pagina diversi a diversi tipi di argomenti all’interno di un corso. Questo consente di configurare layout dedicati per lezioni, quiz, pagine di panoramica e altri tipi di argomenti direttamente dalle impostazioni del modello di output.

  Questo consente a ogni tipo di argomento di utilizzare un layout appropriato per il contenuto e la struttura, anziché applicare lo stesso layout in tutte le pagine del corso. Per ulteriori dettagli sulla configurazione dei layout di pagina per i modelli di output SCORM, visualizzare [Configura profili cartella](../lc-config-guide/lc-folder-profile.md).
- Experience Manager Guides ora supporta la pubblicazione diretta di contenuti SCORM su Adobe Learning Manager (ALM). Dopo aver configurato un profilo di pubblicazione ALM, gli autori possono generare l’output SCORM e caricarlo direttamente in Adobe Learning Manager senza scaricare e importare manualmente il pacchetto.

  Per ulteriori dettagli, visualizzare [Configurare il predefinito SCORM](../learning-content/config-scorm-preset.md).


