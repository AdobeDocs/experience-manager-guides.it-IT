---
title: Configurare un connettore origine dati utilizzando gli strumenti
description: Scopri come configurare un connettore di origine dati utilizzando gli strumenti.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 873542cb2e8e1b7e80e0ecc113cae4f603b18592
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 0%

---

# Configurare un connettore origine dati dall’interfaccia utente

Experience Manager Guides viene fornito con **Origini dati** strumento che consente di configurare connettori predefiniti per le origini dati. È possibile impostare i connettori client JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch e REST generico.


Oltre a questi connettori predefiniti, Experience Manager Guides fornisce i connettori per le origini dati Salsify, Akeneo e ADO (Microsoft Azure DevOps Boards). Puoi scaricare e installare questi connettori open-source dall&#39; [Archivio centrale Maven](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides). Gli utenti possono quindi configurare questi connettori.
Scopri come [installare un connettore open source](#install-open-source-connector).



Puoi anche connetterti a file di dati JSON utilizzando un connettore per file. Carica il file JSON dal computer o sfoglia le risorse Adobe Experience Manager. Quindi, crea snippet di contenuto o argomenti utilizzando i generatori.

Per configurare un connettore, effettuare le seguenti operazioni:

1. Seleziona la **Adobe Experience Manager** nella parte superiore e scegliere Strumenti.
1. Seleziona **Guide** dall&#39;elenco degli strumenti.
1. Seleziona la **Origini dati** affiancare. Il **Origini dati** viene visualizzata. È possibile visualizzare le origini dati collegate.

   È possibile alternare tra **Vista a elenco** o **Vista affiancata** per visualizzare le varie origini dati collegate come un elenco o come sezioni.

   <img src="./assets/data-sources-create-window.png" alt= "origini dati elencate nella pagina origini dati" width="800">

   *Visualizzare o creare un connettore origine dati.*
1. Fai clic su **Crea**.
1. Selezionare il database per il quale si desidera creare il connettore. Ad esempio, il connettore di Elasticsearch.
   >[!NOTE]
   >
   >Vengono elencati tutti i database predefiniti disponibili.

1. Fai clic su **Avanti**.
1. Immettere la configurazione e i dettagli di connessione in base al database.

   >[!TIP]
   >
   >* Passa il cursore sopra <img src="./assets/info-details.svg" alt= "icona info" width="25"> vicino al campo per visualizzare ulteriori dettagli.
   > * I campi con * sono obbligatori. Ad esempio, puoi immettere i seguenti dettagli per il connettore di Elasticsearch.

   * **Nome**: immetti il nome dell’origine dati.
   * **Tipo di autenticazione**: seleziona il tipo di autenticazione dal menu a discesa. Ad esempio, autenticazione nome utente-password di base
   * **Nome utente**: immetti il nome utente.
   * **Password**: inserisci nome utente e password.
   * **URL**: aggiungi l’URL API.


1. Seleziona la **Escludi modelli di fabbrica** opzione per escludere i modelli di fabbrica dall&#39;utilizzo per la generazione di argomenti e snippet. Non verranno visualizzati sotto **Modello di mappatura dati** menu a discesa nella  **Aggiungi generatore frammenti di contenuto** o **Aggiungi generatore di argomenti** .


1. Seleziona **Verifica connessione**. È possibile visualizzare **Verifica connessione** attivato solo dopo l&#39;aggiunta dei dettagli richiesti. Visualizza un messaggio di operazione riuscita se i dettagli della connessione sono corretti. In caso contrario, è possibile visualizzare un messaggio di errore.



1. Seleziona **Salva** nella parte superiore per salvare il connettore.     Visualizza **Salva** dopo aver inserito tutti i dettagli e aver stabilito la connessione.


   Se il connettore viene salvato correttamente, è possibile visualizzare l&#39;origine dati collegata nella pagina.

**Connessione a più risorse**

È possibile aggiungere o utilizzare più risorse in base a URL diversi per alcuni connettori, come ad esempio Generic REST Client, Salsify, Akeneo e Microsoft Azure DevOps Boards (ADO). Quindi, connettiti con loro per creare snippet di contenuto o argomenti utilizzando i generatori per loro.

Per creare una risorsa, effettua le seguenti operazioni:

1. Seleziona ![icona aggiungi](assets/Add_icon.svg) nel **Sezione risorse URL** per aggiungere una risorsa per ogni URL.
1. Configura tutti i dettagli in **Aggiungi risorsa** .
1. Clic **Aggiungi**.
1. È possibile modificare ![icona modifica](assets/edit_pencil_icon.svg) o eliminare ![eliminare](assets/Delete_icon.svg) la risorsa dall’elenco delle risorse URL.

1. È inoltre possibile utilizzare le risorse predefinite disponibili per origini dati quali Salsify, Akeneo e Microsoft ADO. Disattiva le opzioni per la risorsa da non configurare per un’origine dati.

Questo consente di recuperare rapidamente i dati da una qualsiasi delle risorse per una particolare origine dati in un singolo frammento di contenuto o argomento.



## Installare un connettore open source{#install-open-source-connector}

Per pubblicare una dipendenza presente sul [Archivio centrale Maven](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) ai Cloud Service, devi includere e incorporare la dipendenza per un connettore open-source.

1. Aggiungere la dipendenza in `all/pom.xml`  nel codice del progetto Git di cloud manager. Ad esempio, puoi aggiungere la seguente dipendenza per il connettore dell’origine dati delle bacheche DevOps di Microsoft Azure.


   ```
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <version>1.0.0</version>
       <type>jar</type>
   </dependency> 
   ```

1. Incorpora la dipendenza aggiunta.

       &quot;
       &lt;embedded>
       &lt;groupid>com.adobe.aem.addon.guides&lt;/groupid>
       &lt;artifactid>konnect-azure-devops&lt;/artifactid>
       &lt;type>barattolo&lt;/type>
       &lt;target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install&lt;/target>
       &lt;/embedded>
       &quot;
   
1. Esegui la pipeline per applicare le modifiche nei Cloud Service.
Il connettore è installato nell’ambiente.


## Funzioni disponibili per un connettore

* Passa da **Vista a elenco** o **Vista affiancata**  per visualizzare le varie origini dati collegate come un elenco o come sezioni.
* Selezionare la casella di controllo relativa a un singolo connettore. Clic **Seleziona tutto** per selezionare tutti i connettori. Puoi fare clic su **Deseleziona tutto** quando sono selezionati tutti i connettori.

<img src="./assets/data-sources-features.png" alt= "funzioni delle origini dati nella pagina origini dati" width="800">

*Modifica, riconnetti, duplicato o elimina un connettore origine dati.*

È possibile utilizzare le seguenti funzioni per il connettore sul **Origini dati** pagina:

* **Modifica**: modifica i dettagli di configurazione per il connettore selezionato.

* **Riconnetti**: riconnetti a un connettore disconnesso.

* **Duplica**: crea un nuovo connettore duplicato utilizzando il connettore corrente come base. Per impostazione predefinita, il connettore duplicato viene creato con un suffisso (come connectorname_1). Ad esempio, sample-elastic-search_1.
Se esiste un connettore con lo stesso nome, viene visualizzato un errore.

* **Elimina**: elimina il connettore selezionato.


Dopo aver configurato l’origine dati, il connettore viene elencato in **Pannello Origini dati** nell&#39;editor Web. È quindi possibile connettersi all&#39;origine dati e inserire uno snippet di contenuto negli argomenti. Per ulteriori dettagli, vedi [Inserire uno snippet di contenuto dall&#39;origine dati](../user-guide/web-editor-content-snippet.md).
