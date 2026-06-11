---
title: Configurare un connettore Git in AEM Guides
description: Scopri come configurare un Git in Experience Manager Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 5f626c210e74c6d11e2441f719cfbfeb33bf55c5
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# Creare e configurare il connettore Git dall’interfaccia utente

Utilizza lo strumento Origini dati in Experience Manager Guides per creare e configurare un connettore Git dall’interfaccia utente. Dopo aver configurato correttamente il connettore, puoi utilizzarlo per importare il contenuto da un archivio Git in Experience Manager Guides.


1. Seleziona il collegamento **Adobe Experience Manager** in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti.
1. Selezionare il riquadro **Origini dati**. Viene visualizzata la pagina **Origini dati**.
1. Seleziona **Crea**.
1. Dall&#39;elenco dei connettori di origine dati, selezionare **GitHub**.

   ![](assets/github-connector-tile.png){width="600"}

1. Seleziona **Avanti**.
1. Immetti la configurazione e i dettagli di connessione.

   ![](assets/conf-git-connector.png){width="600"}

   >[!TIP]
   >
   >* Passa il cursore sopra <img src="./assets/info-details.svg" alt= "icona info" width="25"> vicino al campo per visualizzare ulteriori dettagli.
   >* I campi con * sono obbligatori. Ad esempio, puoi immettere i seguenti dettagli per il connettore Elasticsearch.

   * **Nome**: immettere il nome dell&#39;origine dati.
   * **Percorso directory principale di AEM di destinazione**: immetti il percorso nell&#39;archivio AEM in cui deve essere archiviato il contenuto importato da Git.
   * **Filtro tipo file (inclusione)**: specificare i tipi di file da includere durante l&#39;importazione.
   * **Percorso escluso (regex)**: specificare i pattern di percorso da escludere dall&#39;importazione.
   * **Tipo di autenticazione**: selezionare il tipo di autenticazione dall&#39;elenco a discesa. Attualmente, **Personal Access Token (PAT)** è l&#39;unico metodo di autenticazione supportato. Immetti il PAT durante la configurazione del connettore per autenticare e accedere all’archivio Git.
   * **URL archivio**: immettere l&#39;URL archivio Git da cui importare il contenuto.
   * **Ramo**: immettere il ramo da utilizzare per l&#39;importazione del contenuto.

1. Verifica la connessione. Il pulsante **Verifica connessione** è attivato solo dopo aver immesso i dettagli richiesti. Se i dettagli della connessione sono corretti, viene visualizzato un messaggio di operazione riuscita. In caso contrario, viene visualizzato un messaggio di errore.

   ![](assets/git-connector-test-connection.png){width="600"}

1. Seleziona **Salva** nella parte superiore per salvare il connettore.

   Il pulsante Salva viene attivato solo dopo l&#39;immissione di tutti i dettagli richiesti e la connessione ha esito positivo. Se il connettore è stato salvato correttamente, è possibile visualizzare il connettore Github configurato nella pagina **Origini dati**.

   ![](assets/git-connector-connected.png){width="600"}

