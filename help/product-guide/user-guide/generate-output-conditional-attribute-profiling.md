---
title: Profilatura attributi condizionale
description: Scopri come creare attributi condizionali nelle guide AEM. Utilizza gli attributi condizionali nella cartella e nei profili globali per condizionare il contenuto.
exl-id: 5ec7666e-df6b-4b0d-b6c2-cdc395fcccc5
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Profilatura attributi condizionale {#id1843I0HN0Y4}

A livello aziendale, è estremamente importante assicurarsi di disporre di un sistema di assegnazione tag standard. I tag o gli attributi condizionali possono essere associati alle risorse digitali nell’archivio, il che consente di pubblicare l’output in base alle condizioni scelte. È ad esempio possibile creare un attributo condizionale per il contenuto di Mac e Windows. Quindi, aggiungi questi attributi al contenuto pertinente nei tuoi argomenti. Al momento della pubblicazione del contenuto, è possibile scegliere se si desidera pubblicare solo il contenuto di Windows o di Mac.

Le guide AEM consentono di creare e associare facilmente attributi condizionali utilizzando gli attributi DITA pertinenti. Puoi definire gli attributi condizionali a livello globale o a livello di cartella. Le condizioni definite a livello globale sono visibili in tutti i progetti e le condizioni specifiche della cartella sono visibili solo nei progetti creati all’interno della cartella specificata. Gli autori dei contenuti possono utilizzare questi attributi condizionali per condizionare il contenuto nei propri argomenti o mappe DITA che creano o utilizzano. Queste condizioni possono quindi essere utilizzate dall’editore per creare predefiniti condizionali. Utilizzando i predefiniti condizionali, l’editore può decidere quale condizione includere ed escludere dall’output pubblicato.

>[!NOTE]
>
> Puoi creare o modificare gli attributi condizionali in un Profilo cartella a cui hai accesso. Se l’amministratore di sistema non ti ha concesso l’accesso a un profilo di cartella, non puoi creare o modificare gli attributi condizionali nel Profilo cartella.

Per definire gli attributi condizionali, effettuare le seguenti operazioni:

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Fai clic sul pulsante **Profili cartella** affiancare e selezionare un profilo cartella.

   >[!NOTE]
   >
   > Non è possibile modificare il profilo globale.

1. Fai clic sul pulsante **Attributi condizionali** e fai clic su **Modifica**.

   Viene visualizzata la tabella Attributi condizionali.

1. Clic **Aggiungi**.

1. Inserisci il **Nome**, **Valore**, e un **Etichetta** per l’attributo.

   Puoi salvare un profilo con solo il nome dell’attributo. Tuttavia, un attributo può essere utilizzato solo quando ha un valore specificato. Se si specificano sia - value che label per un attributo, nell&#39;editor Web verrà comunque visualizzato solo il valore dell&#39;attributo. L’etichetta viene mostrata all’amministratore di pubblicazione al momento della creazione del predefinito condizionale.

   La schermata seguente mostra la definizione per `platform` attributo con valore di `unix` e un’etichetta di `Red Hat Linux`.

   ![](images/add-profile.png){width="800" align="left"}

1. Per aggiungere altri valori per lo stesso attributo, fare clic sul pulsante **+** e immettere un valore e un&#39;etichetta aggiuntivi.

1. Per aggiungere altri attributi, fare clic su **Aggiungi**.

1. Clic **Salva** per salvare le modifiche.


Il `platform` è memorizzato nel sistema. Quando un autore decide di utilizzare il `platform` in un argomento DITA in una cartella, i valori verranno visualizzati nella scheda Proprietà dell&#39;Editor Web.

![](images/properties-tab.png){width="350" align="left"}

**Argomento padre:**[ Generazione di output](generate-output.md)
