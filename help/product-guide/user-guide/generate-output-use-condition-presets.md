---
title: Utilizzare i predefiniti per le condizioni
description: Conoscere l’uso delle condizioni preimpostate nelle guide AEM. Scopri come creare, modificare, copiare ed eliminare i predefiniti per le condizioni in AEM.
exl-id: f6865a34-abdd-4d23-b903-0211bebd13b7
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 1%

---

# Utilizzare i predefiniti per le condizioni {#id1825FL004PN}

È possibile definire gli attributi negli argomenti DITA e utilizzare il predefinito di condizione per specificare cosa accade con l&#39;attributo nell&#39;output finale. Ad esempio, puoi aggiungere nel contenuto attributi come versione 1.0 e versione 2.0 e utilizzare un predefinito di condizione per includere la versione 1.0 per la versione 1.0 ed escludere la versione 2.0. Allo stesso modo, è possibile aggiungere al contenuto attributi come OS Windows e OS Linux e quindi includere o escludere il contenuto rilevante per l&#39;output finale in base al sistema operativo.

Puoi creare i predefiniti per le condizioni in due modi:

* Dall&#39;editor Web: consente di creare e gestire i predefiniti di condizione per una mappa DITA dall&#39;editor Web.
* Dal dashboard delle mappe: consente di creare e gestire i predefiniti per le condizioni di una mappa DITA dal dashboard delle mappe.


## Predefiniti di condizione dall’editor web

Guide di Experience Manager consente di gestire i predefiniti di condizione dall’editor Web e di utilizzarli all’interno dei predefiniti di output per generare l’output finale.
Puoi creare e visualizzare i predefiniti per le condizioni, visualizzare gli attributi e gestire le azioni per la mappa corrente dalla **Predefiniti condizione** nell&#39;editor Web.

<img src="images//manage-condtions-presets.png" alt= "Predefiniti condizione nell’editor web" width="800" border="1px">



### Creare un predefinito di condizione

Il **Predefiniti condizione** visualizza informazioni dettagliate sui predefiniti per le condizioni, ad esempio gli attributi, i valori e le azioni.
Per creare un predefinito per le condizioni degli argomenti, effettua le seguenti operazioni:

1. In **Archivio** aprire il file mappa DITA in Vista mappa.
1. Seleziona la **Gestisci** scheda.
1. Seleziona **Predefiniti condizione** a sinistra. Viene visualizzato l&#39;elenco dei predefiniti di condizioni definiti per la mappa DITA.
1. Seleziona l’icona + accanto a **Predefiniti condizione** per aprire **Nuovo predefinito condizione** .
1. Immettete un nome univoco per il predefinito.

   >[!NOTE]
   >
   > Viene visualizzato un errore se il campo del nome è vuoto o se si immette un carattere non valido o un nome uguale a un predefinito di condizione esistente. È possibile utilizzare un trattino &quot;-&quot; o il carattere di sottolineatura &quot;_&quot; come separatore.

1. Seleziona **Crea**.
Il nuovo predefinito di condizione viene aggiunto all’elenco.
1. Fai doppio clic su un predefinito di condizione per visualizzare gli attributi e le azioni.
Il **Attributi** Il pannello mostra tutti gli attributi aggiunti a qualsiasi riferimento presente nella mappa. Il pannello a destra mostra solo le condizioni aggiunte ai predefiniti condizione.
1. Per aggiungere gli attributi, effettuate una delle seguenti operazioni:
   * Seleziona uno o più attributi per aggiungere tutti i valori al relativo predefinito di condizione. Ad esempio, puoi selezionare `platform` per aggiungere tutti i relativi valori.
   * Seleziona uno o più valori di attributo per aggiungerli al predefinito di condizione. Ad esempio, puoi selezionare `Unix` e `Win` valori dell’attributo platform
   * Selezionate una coppia di attributi e valori e trascinatela nel pannello centrale. Ad esempio, puoi selezionare `Unix` valore dell’attributo platform e trascinarlo.
   * **Seleziona tutto** per aggiungere tutti gli attributi e i relativi valori al predefinito di condizione.
Per impostazione predefinita, l&#39;azione per un attributo è `Include`.

1. Seleziona **Aggiungi**. Puoi ripetere questo passaggio per aggiungere altri attributi. Gli attributi aggiunti vengono spostati dal pannello centrale a quello di destra.
1. Seleziona Rimuovi nella barra delle azioni in alto per rimuovere gli attributi selezionati nel pannello di destra.
1. (Facoltativo) Se necessario, puoi sovrascrivere l’azione applicata agli attributi.
Effettua una delle operazioni seguenti:
   * Per qualsiasi attributo, seleziona una delle azioni seguenti dal menu a discesa Azione.
      * Includi
      * Escludi
      * Passthrough
      * Flag
   * Seleziona più righe di attributi dal pannello di destra e scegli un’azione dalla barra delle azioni in alto. Ad esempio, puoi selezionare Escludi azione per gli attributi selezionati.
1. Seleziona **Salva** per salvare il predefinito di condizione.

   >[!NOTE]
   >
   > Se selezionate un altro predefinito o chiudete il predefinito senza salvarlo, viene visualizzato un avviso.

Una volta creato un predefinito di condizione, questo viene visualizzato nella sezione **Predefiniti condizione** menu a discesa dei predefiniti di output. Ulteriori informazioni su come [Pubblica output PDF](../web-editor/native-pdf-web-editor.md).

### Rinominare un predefinito di condizione

Per rinominare un predefinito di condizione, effettua le seguenti operazioni:

1. Passa il puntatore del mouse su un predefinito di condizione dalla **Predefiniti condizione** pannello.
1. Seleziona **Rinomina** dal menu Opzioni per aprire **Rinomina predefinito condizione** .
1. Modifica il nome del predefinito di condizione.
1. Clic **Rinomina**.

### Duplicare un predefinito di condizione

Per duplicare un predefinito di condizione, effettua le seguenti operazioni:

1. Passa il puntatore del mouse su un predefinito di condizione dalla **Predefiniti condizione** pannello.
1. Seleziona **Duplica** dal menu Opzioni per aprire **Predefinito condizione duplicato** .
   >[!NOTE]
   >
   > Il nome predefinito è `<selected condition preset name>_1`. Puoi modificare il nome in base alle tue esigenze.

1. Clic **Duplica**.

### Elimina predefinito condizione

Per eliminare i predefiniti di condizione, effettua le seguenti operazioni:

1. Passa il puntatore del mouse su un predefinito di condizione dalla **Predefiniti condizione** pannello.
1. Seleziona **Elimina** dal menu Opzioni per aprire **Elimina predefinito condizione** .
1. Fai clic su **Elimina**.



## Predefiniti condizione dal dashboard delle mappe


### Creare un predefinito di condizione

Per creare un predefinito di condizione, effettua le seguenti operazioni:

1. Seleziona **Predefiniti condizione** nella console delle mappe DITA.
1. Clic **Crea** pulsante.
1. Immettete un nome per il predefinito in **Condizione nome**.
1. Seleziona una delle seguenti azioni predefinite da **Imposta azione predefinita su** elenco a discesa:

   * Includi
   * Escludi
   * Passthrough
   * Flag L’azione è impostata come azione predefinita per tutti gli attributi, a prescindere che vengano aggiunti o meno al predefinito della condizione.

   Ad esempio, nel documento sono presenti 15 attributi di condizione, quattro dei quali sono stati inclusi nel predefinito di condizione. Se si seleziona **escludi** come azione predefinita, viene applicata a tutti e 15 gli attributi.

1. Per aggiungere gli attributi, effettuate una delle seguenti operazioni:
   * Clic **Aggiungi** a un attributo del predefinito di condizione. Puoi ripetere questo passaggio per aggiungere altri attributi.
   * Clic **Aggiungi tutto** per aggiungere tutti gli attributi al predefinito di condizione.
1. \(Facoltativo\) Se necessario, è possibile sostituire l&#39;azione predefinita applicata agli attributi nel passaggio 4. Effettua una delle operazioni seguenti:
   * Seleziona più attributi, scegli un’azione da **Imposta l&#39;azione per le condizioni selezionate su** e fai clic su **Applica**.
   * Selezionare un&#39;azione per un attributo da **Azione** a discesa.
1. Fai clic su **Salva**.

### Modificare un predefinito di condizione

È possibile apportare modifiche a un predefinito di condizione esistente per modificare le azioni applicate agli attributi nel predefinito di condizione. Per modificare un predefinito di condizione, effettua le seguenti operazioni:

1. Seleziona **Predefiniti condizione** nella console delle mappe DITA.
1. Clic **Modifica** pulsante.
1. Apporta le modifiche necessarie per tutti gli attributi nel predefinito di condizione.
1. Fai clic su **Salva**.

### Creare una copia di un predefinito di condizione

È possibile creare una copia di un predefinito di condizione e quindi modificarlo in base alle proprie esigenze. Per creare una copia di un predefinito di condizione, effettua le seguenti operazioni:

1. Seleziona **Predefiniti condizione** nella console delle mappe DITA.
1. Clic **Duplica** pulsante.

   >[!NOTE]
   >
   > Il nome predefinito è `<selected condition preset name>_Duplicate`

   Puoi modificare il nome in base alle tue esigenze.

1. \(Facoltativo\) Apportare le modifiche necessarie per tutti gli attributi nel predefinito di condizione.
1. Fai clic su **Salva**.

### Elimina predefinito condizione

È possibile eliminare uno o più predefiniti di condizione dal **Predefinito condizione** della console delle mappe DITA. Per eliminare i predefiniti di condizione, effettua le seguenti operazioni:

1. Seleziona **Predefiniti condizione** nella console delle mappe DITA.
1. Seleziona il predefinito di condizione\(s\) da eliminare.
1. Clic **Rimuovi** pulsante.
1. Clic **Rimuovi** per confermare l’azione.

**Argomento padre:**[ Generazione di output](generate-output.md)
