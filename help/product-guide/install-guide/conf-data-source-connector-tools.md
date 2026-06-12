---
title: Configurare un connettore origine dati utilizzando gli strumenti
description: Scopri come configurare un connettore di origine dati utilizzando gli strumenti.
exl-id: 2a0ac0a0-b2a9-453e-851b-fb04c8903526
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/VnRmYie1-SA-DFrz46j3xS6GEO6rJG4QAc4M-mNMYYc
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 0%

---

# Configurare un connettore origine dati dall’interfaccia utente

Experience Manager Guides viene fornito con lo strumento **Origini dati** che consente di configurare connettori predefiniti per le origini dati. È possibile impostare connettori per database JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce e Elasticsearch.

Per configurare un connettore, effettuare le seguenti operazioni:

1. Seleziona il collegamento **Adobe Experience Manager** in alto e scegli Strumenti.
1. Selezionare **Guide** dall&#39;elenco degli strumenti.
1. Selezionare il riquadro **Origini dati**. Viene visualizzata la pagina **Origini dati**. È possibile visualizzare le origini dati collegate.

   È possibile passare dalla **Vista elenco** alla **Vista riquadro** per visualizzare le varie origini dati collegate come elenco o come riquadri.

   <img src="./assets/data-sources-create-window.png" alt= "origini dati elencate nella pagina origini dati" width="800">

   *Visualizzare o creare un connettore origine dati.*
1. Fai clic su **Crea**.
1. Selezionare il database per il quale si desidera creare il connettore. Ad esempio, il connettore Elasticsearch.
   >[!NOTE]
   >
   >Vengono elencati tutti i database predefiniti disponibili.

1. Fai clic su **Avanti**.
1. Immettere la configurazione e i dettagli di connessione in base al database.

   >[!TIP]
   >* Passa il cursore sopra <img src="./assets/info-details.svg" alt= "icona info" width="25"> vicino al campo per visualizzare ulteriori dettagli.
   > * I campi con * sono obbligatori. Ad esempio, puoi immettere i seguenti dettagli per il connettore Elasticsearch.

   * **Nome**: immettere il nome dell&#39;origine dati.
   * Tipo di autenticazione: seleziona il tipo di autenticazione dall’elenco a discesa. Ad esempio, autenticazione nome utente-password di base
   * **Nome utente**: immetti il nome utente.
   * **Password**: immetti nome utente e password.
   * **URL**: aggiungi l&#39;URL API.

1. Seleziona **Verifica connessione**. Puoi visualizzare il pulsante **Verifica connessione** abilitato solo dopo aver aggiunto i dettagli richiesti. Visualizza un messaggio di operazione riuscita se i dettagli della connessione sono corretti. In caso contrario, è possibile visualizzare un messaggio di errore.



1. Seleziona **Salva** nella parte superiore per salvare il connettore.     Visualizza il pulsante **Salva** attivato dopo aver compilato tutti i dettagli e aver stabilito la connessione.


   Se il connettore viene salvato correttamente, è possibile visualizzare l&#39;origine dati collegata nella pagina.

## Funzioni disponibili per un connettore

* Consente di passare dalla **Vista elenco** alla **Vista riquadro** per visualizzare le varie origini dati collegate come elenco o sezioni.
* Selezionare la casella di controllo relativa a un singolo connettore. Fare clic su **Seleziona tutto** per selezionare tutti i connettori. È possibile fare clic su **Deseleziona tutto** quando sono selezionati tutti i connettori.

<img src="./assets/data-sources-features.png" alt= "funzioni delle origini dati nella pagina origini dati" width="800">

*Modifica, riconnetti, duplicato o elimina un connettore origine dati.*

Puoi utilizzare le seguenti funzionalità per il connettore nella pagina **Origini dati**:

* **Modifica**: modifica i dettagli di configurazione per il connettore selezionato.

* **Riconnetti**: riconnettiti a un connettore disconnesso.

* **Duplicato**: crea un nuovo connettore duplicato utilizzando il connettore corrente come base. Per impostazione predefinita, il connettore duplicato viene creato con un suffisso (come connectorname_1). Ad esempio, sample-elastic-search_1.
Se esiste un connettore con lo stesso nome, viene visualizzato un errore.

* **Elimina**: elimina il connettore selezionato.


Dopo aver configurato l&#39;origine dati, il connettore viene elencato nel **pannello Origini dati** nell&#39;editor Web. È quindi possibile connettersi all&#39;origine dati e inserire uno snippet di contenuto negli argomenti. Per ulteriori dettagli, visualizzare [Utilizzare i dati dell&#39;origine dati](../user-guide/web-editor-content-snippet.md).

>[!NOTE]
>
>Puoi anche creare connettori personalizzati e utilizzarli con le diverse origini dati. Scopri come [configurare i connettori personalizzati](../knowledge-base/kb-articles/data-source/conf-custom-data-source-connector.md).