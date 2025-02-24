---
title: Utilizzare i predefiniti per le condizioni
description: Conoscere l’utilizzo dei predefiniti per le condizioni in AEM Guides. Scopri come creare, modificare, copiare ed eliminare i predefiniti per le condizioni in AEM.
exl-id: f6865a34-abdd-4d23-b903-0211bebd13b7
feature: Publishing
role: User
source-git-commit: f6ff978305d9a1587366acbe96d274408bf457f4
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 1%

---

# Utilizzare i predefiniti per le condizioni {#id1825FL004PN}

È possibile definire gli attributi negli argomenti DITA e utilizzare il predefinito di condizione per specificare cosa accade con l&#39;attributo nell&#39;output finale. Ad esempio, puoi aggiungere nel contenuto attributi come versione 1.0 e versione 2.0 e utilizzare un predefinito di condizione per includere la versione 1.0 per la versione 1.0 ed escludere la versione 2.0. Allo stesso modo, è possibile aggiungere al contenuto attributi come OS Windows e OS Linux e quindi includere o escludere il contenuto rilevante per l&#39;output finale in base al sistema operativo.

Puoi creare i predefiniti per le condizioni in due modi:

- [Dalla console Mappa](#condition-presets-from-the-map-console)
- [Dal dashboard Mappa](#condition-presets-from-the-map-dashboard)


## Predefiniti per le condizioni dalla console delle mappe

Experience Manager Guides consente di creare e gestire i predefiniti di condizione dalla console Mappa e di utilizzarli all&#39;interno dei **Predefiniti di output** per generare l&#39;output condizionale finale.

<img src="images/manage-condtions-presets.png" alt= "Predefiniti condizione nel console delle mappe" width="800" border="1px">

### Creare un predefinito di condizione

La visualizzazione **Predefiniti condizione** fornisce informazioni dettagliate sui predefiniti condizione, ad esempio gli attributi, i valori e le azioni.

Per creare un predefinito per le condizioni degli argomenti, effettua le seguenti operazioni:

1. [Aprire il file mappa DITA nella console Mappa](./open-files-map-console.md).
1. Passa a **Predefiniti condizione** a sinistra. Viene visualizzato l&#39;elenco dei predefiniti di condizioni definiti per la mappa DITA.
1. Seleziona l&#39;icona + accanto a **Predefiniti condizione** per aprire la finestra di dialogo **Nuovo predefinito condizione**.
1. Immettete un nome univoco per il predefinito.

   >[!NOTE]
   >
   > Viene visualizzato un errore se il campo del nome è vuoto o se si immette un carattere non valido o un nome uguale a un predefinito di condizione esistente. È possibile utilizzare un trattino &quot;-&quot; o il carattere di sottolineatura &quot;_&quot; come separatore.

1. Seleziona **Crea**.

   Il nuovo predefinito di condizione viene aggiunto all’elenco.
1. Seleziona il predefinito di condizione per visualizzare gli attributi e le azioni.

   Il pannello **Attributi** mostra tutti gli attributi aggiunti a qualsiasi riferimento presente nella mappa. Il pannello a destra mostra solo le condizioni aggiunte ai predefiniti condizione.
1. Per aggiungere gli attributi, effettuate una delle seguenti operazioni:
   - Seleziona uno o più attributi per aggiungere tutti i valori al relativo predefinito di condizione. Ad esempio, è possibile selezionare l&#39;attributo `platform` per aggiungerne tutti i valori.
   - Seleziona uno o più valori di attributo per aggiungerli al predefinito di condizione. Ad esempio, puoi selezionare i valori `Unix` e `Win` dell&#39;attributo platform
   - Selezionate una coppia di attributi e valori e trascinatela nel pannello centrale. Ad esempio, è possibile selezionare il valore `Unix` dell&#39;attributo platform e trascinarlo.
   - **Seleziona tutto** per aggiungere tutti gli attributi e i relativi valori al predefinito di condizione. Per impostazione predefinita, l&#39;azione per un attributo è `Include`.

1. Seleziona **Aggiungi**. Puoi ripetere questo passaggio per aggiungere altri attributi. Gli attributi aggiunti vengono spostati dal pannello centrale a quello di destra.
1. Seleziona **Rimuovi** dalla barra delle azioni in alto per rimuovere gli attributi selezionati nel pannello di destra.
1. (Facoltativo) Se necessario, puoi sovrascrivere l’azione applicata agli attributi.

   Effettuare una delle seguenti operazioni:
Per qualsiasi attributo, seleziona una delle azioni seguenti dal menu a discesa Azione o dalla barra degli strumenti.

   - Includi
   - Escludi
   - Passthrough
   - Flag

   Seleziona più righe di attributi dal pannello di destra e scegli un’azione dalla barra delle azioni in alto. Ad esempio, puoi selezionare l&#39;azione **Escludi** per gli attributi selezionati.
1. Seleziona **Salva** per salvare il predefinito di condizione.

   >[!NOTE]
   >
   > Se selezionate un altro predefinito o chiudete il predefinito senza salvarlo, viene visualizzato un avviso.

Dopo aver creato un predefinito di condizione, questo viene visualizzato nel menu a discesa **Predefiniti di condizione** dei **Predefiniti di output**. Ulteriori informazioni su come [pubblicare l&#39;output di PDF](../web-editor/native-pdf-web-editor.md).

### Rinominare un predefinito di condizione

Per rinominare un predefinito di condizione, effettua le seguenti operazioni:

1. Passa il puntatore del mouse su un predefinito di condizione dal pannello **Predefiniti di condizione**.
1. Selezionare **Rinomina** dal menu Opzioni per aprire la finestra di dialogo **Rinomina predefinito di condizione**.
1. Modifica il nome del predefinito di condizione.
1. Selezionare **Rinomina**.

### Duplicare un predefinito di condizione

Per duplicare un predefinito di condizione, effettua le seguenti operazioni:

1. Passa il puntatore del mouse su un predefinito di condizione dal pannello **Predefiniti di condizione**.
1. Seleziona **Duplica** dal menu Opzioni per aprire la finestra di dialogo **Predefinito condizione duplicato**.

   >[!NOTE]
   >
   > Il nome predefinito è `<selected condition preset name>_1`. Puoi modificare il nome in base alle tue esigenze.

1. Seleziona **Duplica**.

### Elimina predefinito condizione

Per eliminare i predefiniti di condizione, effettua le seguenti operazioni:

1. Passa il puntatore del mouse su un predefinito di condizione dal pannello **Predefiniti di condizione**.
1. Selezionare **Elimina** dal menu Opzioni per aprire la finestra di dialogo **Elimina predefinito di condizione**.
1. Seleziona **Elimina**.



## Predefiniti condizione dal dashboard Mappa


### Creare un predefinito di condizione

Per creare un predefinito di condizione, effettua le seguenti operazioni:

1. Selezionare la scheda **Predefiniti condizione** nel dashboard delle mappe DITA.
1. Seleziona **Crea**.
1. Immettere un nome per il predefinito in **Condizione nome**.
1. Selezionare una delle azioni predefinite seguenti dall&#39;elenco a discesa **Imposta azione predefinita su**:

   - Includi
   - Escludi
   - Passthrough
   - Contrassegno
L’azione è impostata come azione predefinita per tutti gli attributi, a prescindere dal fatto che vengano aggiunti o meno al predefinito della condizione.

   Ad esempio, nel documento sono presenti 15 attributi di condizione, quattro dei quali sono stati inclusi nel predefinito di condizione. Se selezioni **escludi** come azione predefinita, viene applicato a tutti e 15 gli attributi.

1. Per aggiungere gli attributi, effettuate una delle seguenti operazioni:
   - Seleziona **Aggiungi** a un attributo del predefinito di condizione. Puoi ripetere questo passaggio per aggiungere altri attributi.
   - Seleziona **Aggiungi tutti** per aggiungere tutti gli attributi al predefinito di condizione.
1. \(Facoltativo\) Se necessario, è possibile sostituire l&#39;azione predefinita applicata agli attributi nel passaggio 4. Effettua una delle seguenti operazioni:
   - Selezionare più attributi, scegliere un&#39;azione tra **Imposta l&#39;azione per le condizioni selezionate su** e selezionare **Applica**.
   - Selezionare un&#39;azione per un attributo dal menu a discesa **Azione**.
1. Seleziona **Salva**.

### Modificare un predefinito di condizione

È possibile apportare modifiche a un predefinito di condizione esistente per modificare le azioni applicate agli attributi nel predefinito di condizione. Per modificare un predefinito di condizione, effettua le seguenti operazioni:

1. Selezionare la scheda **Predefiniti condizione** nella console delle mappe DITA.
1. Selezionare il pulsante **Modifica**.
1. Apporta le modifiche necessarie per tutti gli attributi nel predefinito di condizione.
1. Seleziona **Salva**.

### Creare una copia di un predefinito di condizione

È possibile creare una copia di un predefinito di condizione e quindi modificarlo in base alle proprie esigenze. Per creare una copia di un predefinito di condizione, effettua le seguenti operazioni:

1. Selezionare la scheda **Predefiniti condizione** nella console delle mappe DITA.
1. Seleziona il pulsante **Duplica**.

   >[!NOTE]
   >
   > Il nome predefinito è `<selected condition preset name>_Duplicate`

   Puoi modificare il nome in base alle tue esigenze.

1. \(Facoltativo\) Apportare le modifiche necessarie per tutti gli attributi nel predefinito di condizione.
1. Seleziona **Salva**.

### Elimina predefinito condizione

È possibile eliminare uno o più predefiniti di condizione dalla scheda **Predefinito condizione** della console delle mappe DITA. Per eliminare i predefiniti di condizione, effettua le seguenti operazioni:

1. Selezionare la scheda **Predefiniti condizione** nella console delle mappe DITA.
1. Seleziona il predefinito di condizione\(s\) da eliminare.
1. Selezionare il pulsante **Rimuovi**.
1. Seleziona **Rimuovi** per confermare l&#39;azione.

**Argomento padre:**[ Generazione output](generate-output.md)
