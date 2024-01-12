---
title: Configurare un connettore origine dati utilizzando gli strumenti
description: Scopri come configurare un connettore di origine dati utilizzando gli strumenti.
exl-id: 2a0ac0a0-b2a9-453e-851b-fb04c8903526
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Configurare un connettore origine dati dall’interfaccia utente

Experience Manager Guides viene fornito con **Origini dati** strumento che consente di configurare connettori predefiniti per le origini dati. È possibile impostare connettori per database JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce e Elasticsearch.

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
   >* Passa il cursore sopra <img src="./assets/info-details.svg" alt= "icona info" width="25"> vicino al campo per visualizzare ulteriori dettagli.
   > * I campi con * sono obbligatori. Ad esempio, puoi immettere i seguenti dettagli per il connettore di Elasticsearch.

   * **Nome**: immetti il nome dell’origine dati.
   * Tipo di autenticazione: seleziona il tipo di autenticazione dall’elenco a discesa. Ad esempio, autenticazione nome utente-password di base
   * **Nome utente**: immetti il nome utente.
   * **Password**: inserisci nome utente e password.
   * **URL**: aggiungi l’URL API.

1. Seleziona **Verifica connessione**. È possibile visualizzare **Verifica connessione** attivato solo dopo l&#39;aggiunta dei dettagli richiesti. Visualizza un messaggio di operazione riuscita se i dettagli della connessione sono corretti. In caso contrario, è possibile visualizzare un messaggio di errore.



1. Seleziona **Salva** nella parte superiore per salvare il connettore.     Visualizza **Salva** dopo aver inserito tutti i dettagli e aver stabilito la connessione.


   Se il connettore viene salvato correttamente, è possibile visualizzare l&#39;origine dati collegata nella pagina.

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
