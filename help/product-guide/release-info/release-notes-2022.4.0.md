---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di aprile 2022
description: Versione di aprile di Adobe Experience Manager Guides as a Cloud Service
exl-id: c735ba24-a803-454b-8723-57dacf90061b
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---

# Versione di aprile di Adobe Experience Manager Guides as a Cloud Service

## Effettua l’aggiornamento alla versione di aprile

Aggiorna il tuo attuale [!DNL Adobe Experience Manager Guides] as a Cloud Service (in seguito denominato *[!DNL AEM Guides]as a Cloud Service*) eseguendo i seguenti passaggi:
1. Consulta il codice Git del Cloud Service e passa al ramo configurato nella pipeline dei Cloud Service corrispondente all’ambiente da aggiornare.
1. Aggiorna `<dox.version>` proprietà in `/dox/dox.installer/pom.xml` file del codice Git dei tuoi Cloud Service in 2022.4.133.
1. Esegui il commit delle modifiche ed esegui la pipeline dei Cloud Service per l’aggiornamento alla versione di aprile di [!DNL AEM Guides] as a Cloud Service.

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate da [!DNL AEM Guides] Versione as a Cloud Service di aprile 2022.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Non compatibile | Aggiornamento 2020 4 e versioni successive |
| | |


### Connettore ossigeno

| Versione cloud delle guide AEM | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac |
| --- | --- | --- |
| 2022.4.0 | 2.5.6. | 2.5.6. |
|  |  |  |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

## Nuove funzioni e miglioramenti

Nell’editor web sono stati aggiunti molti miglioramenti e nuove funzioni:

### Risoluzione chiave migliorata

Un riferimento a una chiave di contenuto DITA inserisce una parte di contenuto da un argomento in un altro. Utilizza una chiave per individuare il contenuto. È necessario risolvere i riferimenti chiave associati a un argomento DITA. La mappa principale selezionata ha la precedenza più alta per risolvere i riferimenti chiave.

![finestra di dialogo preferenze utente](assets/user-preferences.png)

Ora i riferimenti chiave vengono risolti in base alla mappa principale impostata nel seguente ordine di priorità:

1. Preferenze utente
1. Pannello Vista mappa
1. Profilo cartella

Per ulteriori dettagli, consulta *Risolvi riferimenti chiave* nella Guida utente.

### Aggiungi un pannello personalizzato nel pannello a sinistra

Ora è possibile aggiungere un pannello personalizzato nel pannello sinistro dell’Editor web. Puoi utilizzare un pannello personalizzato per vari scopi, ad esempio per fornire assistenza o eseguire il test di un progetto. Se è stato configurato un pannello personalizzato, viene visualizzato anche nell’elenco dei pannelli all’interno di **Impostazioni editor**. È possibile attivare o disattivare l&#39;opzione per mostrare o nascondere il pannello personalizzato.

### Possibilità di modificare lo stato del documento degli argomenti in una mappa DITA

Ora è possibile modificare facilmente lo stato del documento degli argomenti selezionati all&#39;interno di una mappa DITA. È inoltre possibile aprire e modificare le proprietà degli argomenti selezionati in una mappa DITA dal **Altre opzioni** nella parte inferiore del pannello Vista mappa.

![proprietà argomento selezionate](assets/map-view-properties.png)

### Informazioni sulla versione visualizzate in modalità Anteprima

L’editor web consente di gestire le versioni. È inoltre possibile visualizzare la versione dell&#39;argomento attivo o della mappa DITA nell&#39;angolo superiore destro della scheda File dell&#39;argomento nella modalità Anteprima di un argomento.

![anteprima versione](assets/preview-version.png)

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

* Le nuove etichette non vengono riportate automaticamente nel menu a discesa Aggiungi/Rimuovi etichetta, ma è necessario un aggiornamento della linea di base. (9249)
* Impossibile modificare il titolo della baseline se una baseline viene creata in base ai criteri delle etichette. (9171)
* Il processo di pubblicazione che utilizza una baseline si blocca in stato di &quot;attesa&quot; se lo stato della baseline diventa &quot;non riuscito&quot;. (9194)
* La rimozione delle etichette sui riferimenti diretti comporta anche la rimozione delle etichette dai riferimenti indiretti. (9257)
* La ricerca durante la digitazione causa richieste di ricerca indesiderate nella vista Archivio. 9307
* Si verificano dei problemi quando nel titolo della scheda viene utilizzata una parola chiave. (9318)
* La linea di base non riesce quando si aggiunge un’etichetta con spazi. (9362)
* L&#39;output del sito AEM non visualizza correttamente l&#39;elemento glossusage. (8936)
* Si verifica un errore della console all’apertura di **Output** nell&#39;editor Web. (8715)
* Il messaggio di errore visualizzato quando si pubblica un tipo di record manuale tramite Salesforce non è intuitivo. (8952)
* L’impostazione Convalida con attributi condizione non viene aperta immediatamente, ma l’utente deve riaprire il file per visualizzare le convalide. 9300
* I metadati non possono essere rimossi dopo la pubblicazione di una mappa DITA con i metadati.  (9178)
* Il pannello Traduzione è visibile anche all&#39;apertura della mappa DITA nell&#39;Editor mappa. (9053)
* La DTD personalizzata definita dall&#39;utente non ha la precedenza sulla DTD DITA standard incorporata in DITA-OT. (9104)
* Nella funzione Native PDF, il caricamento nei modelli non riesce per i file non DITA e non di immagine. 9070
* Il meccanismo di autorizzazione esegue due query invece di una, in alcuni scenari specializzati. (9221)
* La pubblicazione dell&#39;output del sito AEM non riesce se si utilizza una DTD personalizzata. (9243)
* La nota a piè di pagina &quot;Use-by-reference&quot; non scorre fino alla sezione della nota a piè di pagina nell&#39;output del sito AEM. (9234)

## Problemi noti

L’Adobe ha identificato il seguente problema noto in [!DNL AEM Guides] Versione as a Cloud Service di aprile.

* L&#39;editor Web non segnala un errore quando due o più baseline vengono create con lo stesso nome ma presentano differenze di spazio o maiuscole/minuscole. Ad esempio, &quot;adobe&quot; e &quot;Adobe&quot; o &quot;Adobe&quot;.
* Il connettore dell’ossigeno si blocca in modo intermittente durante l’esecuzione di frequenti accessi, disconnessione o commutazione tra diversi tipi di autenticazione.
