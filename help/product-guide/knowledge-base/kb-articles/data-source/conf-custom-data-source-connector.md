---
title: Configurare un connettore personalizzato per le origini dati
description: Scopri come configurare un connettore personalizzato per le origini dati.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: ef7ab117-7541-4e89-9ba4-22254a17efc0
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1521'
ht-degree: 0%

---

# Configurare connettori di origini dati personalizzati

Experience Manager Guides consente di personalizzare i connettori in base alle proprie esigenze e quindi di utilizzarli con le diverse origini dati. Per personalizzare un connettore, è necessario implementare l&#39;interfaccia del connettore e le relative funzioni importanti, quindi configurare l&#39;interfaccia. Puoi anche fornire le risorse insieme ai connettori personalizzati.


- [Personalizzare un connettore per Experience Manager Guides](#customize-connector)
- [Implementare l’interfaccia del connettore](#implement-interface)
- [Funzioni importanti](#important-functions)
- [Tipi di implementazioni connettore predefinite](#default-connectors)
   - [Interfaccia di configurazione](#config-interface)
   - [Tipi di implementazioni di configurazioni predefinite](#default-config-types)
   - [Implementazioni di configurazione concrete](#concrete-config-implementation)
   - [Risorse aggiuntive](#resources)



## Personalizzare un connettore per Experience Manager Guides {#customize-connector}

È possibile personalizzare o configurare un connettore per un&#39;origine dati utilizzando interfacce predefinite e classi astratte. L&#39;intero codice sorgente è disponibile all&#39;indirizzo [https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions](https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions).


Fare riferimento a [![javadoc](https://javadoc.io/badge2/com.adobe.aem.addon.guides/konnect-definitions/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem.addon.guides/konnect-definitions) per le definizioni konnect.

## Implementare l’interfaccia del connettore {#implement-interface}

Per implementare l’interfaccia e le relative funzioni in base alle tue esigenze, effettua le seguenti operazioni:

1. Definisci un modo standardizzato per l’integrazione dei connettori con un sistema, che consenta l’esecuzione di query, la convalida delle connessioni e il recupero dei metadati.
1. Semplifica l’integrazione dell’interfaccia utente fornendo i metodi predefiniti per la configurazione di modelli, loghi, query e altre impostazioni.
1. Verificare che i connettori siano convalidati correttamente e possano gestire gli errori (`KonnectException`) durante l&#39;interazione con le origini dati.

L’interfaccia funge da blueprint per l’implementazione di vari tipi di connettori dati, garantendo che i connettori soddisfino eventuali requisiti operativi e di integrazione specifici all’interno di un ecosistema software più ampio.

## Funzioni importanti {#important-functions}

Implementa le seguenti funzioni importanti:

| Metodo | Obbligatorio | Descrizione |
|---|---|---|
| getLogoUrl |  | <ul><li> Questo metodo restituisce l’URL utilizzato come logo del connettore. <li> Per impostazione predefinita, restituisce una stringa vuota che indica che non viene fornito alcun URL del logo a meno che non venga sovrascritto. <br><b> note aggiuntive</b>: <br> <ul><li> Se si specifica sia l&#39;URL del logo che il nome di una classe di logo, l&#39;URL del logo verrà utilizzato per visualizzare il logo nell&#39;interfaccia utente. <li> Se specifichi l’URL del logo tramite le impostazioni di configurazione, sovrascrive l’URL impostato nell’implementazione del metodo. |
| validateConnection | Sì | <ul><li> Utilizzare questo metodo per verificare se il connettore è in grado di stabilire una connessione alla propria origine dati. <li> Accetta un oggetto `ConfigDto` come parametro, contenente le impostazioni di configurazione, ad esempio le credenziali di connessione e gli URL dell&#39;endpoint. <li> Il metodo restituisce true se la convalida (test di connessione) ha esito positivo, indicando che il connettore può connettersi alla propria origine dati. |
| esegui | sì | <ul><li>Utilizzare questo metodo per eseguire una singola query per il connettore, che interagisce con un&#39;origine dati. <li> I connettori che supportano questa operazione gestiscono l’esecuzione della query, analizzano la risposta e, se necessario, la convertono in una stringa JSON. <li> Incapsulare la query da eseguire in questo metodo all&#39;interno di un oggetto `QueryInfoDto`, che contiene dettagli quali la stringa di query e i parametri. <li> Il metodo restituisce una stringa JSON che rappresenta la risposta dell’esecuzione della query. <br><b> note aggiuntive</b>: <li>Le implementazioni di questo metodo variano a seconda del connettore specifico e della sua interazione con l’origine dati. <li> Utilizzare `KonnectException` per gestire eventuali eccezioni o errori che si verificano durante l&#39;esecuzione o la connessione all&#39;origine dati. |
| executeWithLimit | sì | <ul><li> Utilizzare questo metodo per lo stesso scopo di `execute()`, ma con la funzionalità aggiuntiva di applicazione di una query di limitazione, in genere per visualizzare le anteprime nei componenti dell&#39;interfaccia utente. <li> I connettori che supportano questa operazione gestiscono l’esecuzione della query, analizzano la risposta e, se necessario, la convertono in una stringa JSON. <li> Incapsulare la query da eseguire in questo metodo all&#39;interno di un oggetto `QueryInfoDto`, in modo simile al metodo precedente. <br><b> note aggiuntive</b>: <ul><li> `QueryResultDto` è una classe personalizzata o un oggetto trasferimento dati che incapsula il risultato dell&#39;esecuzione della query, inclusi i metadati relativi alla query e al relativo stato di esecuzione. |
| getSampleQuery | | <ul><li>Questo metodo restituisce una stringa di query di esempio che può essere visualizzata nell’interfaccia utente, ad esempio nella finestra di dialogo in cui gli utenti possono inserire o modificare le query. <li>Per impostazione predefinita, restituisce una stringa vuota che indica che non viene fornita alcuna query di esempio, a meno che non venga ignorata. <br><b> note aggiuntive</b>: <ul> <li> Se non si definisce una query di esempio e il metodo restituisce una stringa vuota, nella finestra di dialogo Inserisci query dell&#39;interfaccia utente non verrà visualizzata alcuna query di esempio. |
| getTemplates | | <ul> <li> Questo metodo restituisce un elenco di modelli associati al connettore. <li> Per impostazione predefinita, restituisce un elenco vuoto, indicando che non vengono forniti modelli a meno che non vengano sostituiti. |
| getLogoClassName | | <ul> <li> Questo metodo restituisce il nome della classe come logo del connettore. Per impostazione predefinita, restituisce una stringa vuota che indica che non viene fornito alcun nome di classe logo a meno che non venga sostituito. <br><b> note aggiuntive</b>: <ul><li> Se si specifica sia l&#39;URL del logo che il nome di una classe di logo, l&#39;URL del logo verrà utilizzato per visualizzare il logo nell&#39;interfaccia utente. <li> Se si specifica il nome della classe logo tramite le impostazioni di configurazione, questo sovrascriverà il nome della classe impostato nell&#39;implementazione del metodo. |
| abilitato | sì | <ul><li> Questo metodo controlla se `connector` è abilitato. <li> Per impostazione predefinita, il metodo restituisce false, il che significa che il connettore non è abilitato a meno che non venga sostituito da una classe che implementa questo metodo. |
| getDescription | | <ul><li>Utilizzare questo metodo per restituire una stringa di descrizione che può essere visualizzata nell&#39;interfaccia utente. <li> Per impostazione predefinita, restituisce una stringa vuota, che indica che non viene fornita alcuna descrizione a meno che non venga sovrascritta. |
| getAuthor | | <ul><li> Questo metodo consente di recuperare il nome dell’autore che ha creato o è responsabile del connettore. <li> In genere, aiuta a identificare e riconoscere l’autore o il responsabile della manutenzione del connettore all’interno di un sistema o di un framework. |
| getName | sì | <ul><li>Questo metodo consente di recuperare il nome univoco assegnato a un connettore. <li>Il nome restituito è fondamentale per identificare il connettore all’interno di un contesto di interfaccia utente, soprattutto se le impostazioni di configurazione del connettore non specificano esplicitamente un nome. <li>Questo nome viene utilizzato in vari componenti dell’interfaccia utente per visualizzare o gestire i connettori in modo semplice. |
| getGroup | sì | <ul> <li>Questo metodo consente di recuperare il nome del gruppo associato a un connettore. <li>I nomi dei gruppi vengono in genere utilizzati per organizzare o classificare i connettori in gruppi logici in base alla loro funzionalità, finalità o tipo. <li> Questo consente una gestione e una presentazione più semplici dei connettori all’interno dell’interfaccia utente di configurazione. |
| getDefaultTemplatePath |  | <ul><li> Questo metodo restituisce il percorso predefinito per i modelli associati a questo connettore. <li> Per impostazione predefinita, restituisce una stringa vuota, che indica che non viene impostato alcun percorso predefinito a meno che non venga ignorato. |
| getLogoSvg |  | <ul><li>Utilizzare questo metodo per restituire la rappresentazione SVG del logo del connettore. <li> Per impostazione predefinita, restituisce una stringa vuota che indica che non vengono forniti dati SVG a meno che non vengano sostituiti. |
| getMaxNoRowsForPreviewQuery | | <ul><li>Questo metodo restituisce il numero massimo di righe interrogate o visualizzate nell’anteprima dell’interfaccia utente. <li> Per impostazione predefinita, restituisce il valore di DEFAULT_LIMIT_PREVIEW, una costante che rappresenta il limite predefinito per le righe di anteprima. |
| getConfigClass | sì | <ul><li>Questo metodo fornisce informazioni sulle classi che implementano l&#39;interfaccia Config e sono supportate da questo connettore. <li> Consente all’applicazione o al framework di individuare e lavorare in modo dinamico con configurazioni compatibili con il connettore. |

## Tipi di implementazioni connettore predefinite {#default-connectors}

La libreria *konnect-definitions* include implementazioni di connettori astratti e funzioni predefinite per l&#39;esecuzione di query. Queste implementazioni dei connettori fungono da modelli che possono essere estesi e utilizzati direttamente così com’è. Se è necessaria un’implementazione personalizzata, le relative funzioni possono essere ignorate.

Oltre a implementare i connettori predefiniti, puoi anche implementare una delle seguenti classi astratte predefinite:

- Connettore Rest
- Connettore file
- Connettore GraphQL
- Connettore SQL
- Connettore NoSQL


Se un connettore si inserisce in uno di questi tipi, estendere il connettore alla classe base corrispondente. In caso contrario, creala da zero implementando l’interfaccia del connettore.

## Interfaccia di configurazione {#config-interface}

L&#39;interfaccia `Config` è progettata per configurare un&#39;origine dati con un metodo di autenticazione specifico, che consente di controllare in modo preciso la modalità di creazione della connessione.

L&#39;interfaccia `Config` offre flessibilità per la gestione e l&#39;implementazione dei dettagli di autenticazione. Diverse implementazioni possono offrire diversi modi per autenticare le origini dati. Un connettore utilizza un’istanza Config per eseguire e convalidare le query su un’origine dati, formando un flusso di lavoro completo.
Un connettore utilizza un&#39;istanza `Config` per eseguire e convalidare le query su un&#39;origine dati, formando un flusso di lavoro completo.

Un’implementazione di configurazione definisce il modo in cui viene gestita l’autenticazione per connettersi a un’origine dati. Questa configurazione viene quindi utilizzata da un’implementazione del connettore per interagire con l’origine dati, garantendo che le query vengano eseguite e convalidate correttamente.

Nel complesso, l&#39;interfaccia `Config` è una parte fondamentale del flusso di lavoro per la connessione alle origini dati, in particolare per la configurazione dell&#39;autenticazione.

### Tipi di implementazioni di configurazioni predefinite {#default-config-types}

Esistono tre tipi di implementazioni di configurazione astratta predefinite per l’autenticazione:

- RestConfig
- SqlConfiguration
- NoSqlConfig

Se una configurazione è allineata a uno di questi tipi, può estendere la classe di base corrispondente. In caso contrario, può essere creata da zero implementando l’interfaccia Config.

### Implementazioni di configurazione concrete {#concrete-config-implementation}

La libreria *konnect-definitions* viene fornita con implementazioni predefinite dell&#39;interfaccia di configurazione per alcune configurazioni di autenticazione ampiamente utilizzate. Puoi utilizzare queste configurazioni direttamente nel connettore o definirne di nuove utilizzando l’interfaccia Config. Queste implementazioni includono:

- Configurazione autenticazione chiave API
- Configurazione basata su token di autenticazione di base
- Configurazione autenticazione di base
- Configurazione token Bearer
- Configurazione password nome utente per SQL
- Configurazione di autenticazione della stringa di connessione per NoSQL

### Risorse aggiuntive{#resources}

Experience Manager Guides consente inoltre di fornire risorse personalizzate per logo e modelli insieme all’implementazione. È possibile mantenere queste risorse nella cartella `resources`.
Per renderle utilizzabili dal connettore, è necessario implementare le seguenti funzioni del connettore:


- `getLogoSvg` - Restituisce il logo SVG come stringa.

- `getTemplates` - Restituisce l&#39;elenco dei modelli nel formato specificato.
