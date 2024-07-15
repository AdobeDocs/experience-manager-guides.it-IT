---
title: API basate su Java per l'utilizzo delle mappe DITA
description: Scopri le API basate su Java per lavorare con le mappe DITA
exl-id: bd91fc90-75f8-487c-99d1-2637e9cf9924
feature: Java-Based API Dita Map
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 0%

---

# API basate su Java per l&#39;utilizzo delle mappe DITA {#id175UB30E05Z}

Le seguenti API basate su Java consentono di lavorare con le mappe DITA in AEM Guides. Queste API sono disponibili sotto forma di bundle. Per utilizzare queste API, devi includere questo bundle nel codice.

Dettagli bundle:

- ID gruppo: **com.adobe.fmdita**

- ID artefatto: **api**

- Versione: **3.2**

- Pacchetto: **com.adobe.fmdita.api.map**

- Dettagli classe:

  ```JAVA
  public class MapUtilities extends Object
  ```

  La classe MapUtilities contiene metodi per recuperare informazioni sui metadati da un file di mapping DITA.


## Scarica mappa DITA con dipendenti

Il metodo `zipMapWithDependents` crea un file .zip contenente una mappa DITA insieme a tutti i relativi dipendenti, ad esempio argomenti di riferimento, mappe secondarie, immagini e DTD. Il file .zip della mappa DITA viene creato in base a una determinata linea di base.

Consente inoltre di mantenere la stessa struttura \(cartelle principali e secondarie\) o di creare una struttura di file flat all’interno di una singola cartella per tutti i file dipendenti.

>[!IMPORTANT]
>
> L’API genera un’eccezione e non riesce a creare un file .zip se manca uno qualsiasi dei file dipendenti.

**Sintassi**:

```JAVA
public static void zipMapWithDependents(Session session, 
                     String sourcePath, 
                     String baseline, 
                     OutputStream outputStream,
                     boolean flatFS) 
                     throws RepositoryException, IOException
```

**Parametri**:
|Nome|Tipo|Descrizione|
----|----|-----------|
|`session`|javax.jcr.Session|Sessione JCR valida.|
|`sourcePath`|Stringa|Percorso \(nell&#39;archivio AEM\) del file mappa DITA da scaricare.|
|`outputStream`|java.io.OutputStream|Flusso in cui scrivere il file ZIP.|
|`baseline`|Stringa|Titolo della linea di base utilizzata per recuperare il contenuto con versione. <br> **Nota:** il valore fa distinzione tra maiuscole e minuscole.|
|flatFS|Boolean|\(Facoltativo\) Se impostato su true, nel file ZIP viene restituita una struttura di file flat. Ad esempio, se la mappa DITA fa riferimento a contenuto in più cartelle, tutti i file di riferimento vengono estratti in un&#39;unica cartella. Nel caso vi siano file con lo stesso nome, tali file vengono rinominati aggiungendo un suffisso numerico. Tutti i riferimenti \(in mappa DITA e argomenti\) vengono gestiti automaticamente, in quanto vengono aggiornati in base alla nuova posizione dei file nella struttura di cartelle flat. Se impostato su false, la struttura delle cartelle viene mantenuta invariata nel file ZIP. Se la mappa DITA fa riferimento a file provenienti da più posizioni, anche tutte queste posizioni vengono create nel file ZIP. Quando si ripristina il file ZIP, viene creata la struttura di cartelle esatta nel percorso di destinazione. <br> Il valore predefinito per questo parametro è false.|

**Restituisce**:
Il contenuto del file ZIP è scritto in `outputStream`.

**Eccezione**:
Genera ``javax.jcr.RepositoryException``, `java.io.IOException`.

## Scarica mappa DITA con i dipendenti \(Asincrono\)

In alternativa, è possibile scaricare una mappa DITA con dipendenti in modalità asincrona. Questo approccio è più utile per le mappe DITA più grandi.

Il metodo `zipMapWithDependents` crea un file .zip contenente una mappa DITA insieme a tutti i relativi dipendenti, ad esempio argomenti di riferimento, mappe secondarie, immagini e DTD. Il file .zip della mappa DITA viene creato in base a una determinata linea di base.

Consente inoltre di mantenere la stessa struttura \(cartelle principali e secondarie\) o di creare una struttura di file flat all’interno di una singola cartella per tutti i file dipendenti.

>[!NOTE]
>
> Questo nodo viene eliminato automaticamente dopo un certo periodo di tempo in base alla configurazione output.history.purgetime, se definita, oppure 5 giorni come impostazione predefinita.

**Sintassi**:

```JAVA
public static CompletableFuture<Node> zipMapWithDependencies(Session session,
                     String sourcePath, 
                     String baseline, 
                     boolean flatFS) 
```

**Parametri**:
|Nome|Tipo|Descrizione|
----|----|-----------|
|`session`|javax.jcr.Session|Sessione JCR valida.|
|`sourcePath`|Stringa|Percorso \(nell&#39;archivio AEM\) del file mappa DITA da scaricare.|
|`baseline`|Stringa|Titolo della linea di base utilizzata per recuperare il contenuto con versione. <br> **Nota:** il valore fa distinzione tra maiuscole e minuscole.|
|flatFS|Boolean|\(Facoltativo\) Se impostato su true, nel file ZIP viene restituita una struttura di file flat. Ad esempio, se la mappa DITA fa riferimento a contenuto in più cartelle, tutti i file di riferimento vengono estratti in un&#39;unica cartella. Nel caso vi siano file con lo stesso nome, tali file vengono rinominati aggiungendo un suffisso numerico. Tutti i riferimenti \(in mappa DITA e argomenti\) vengono gestiti automaticamente, in quanto vengono aggiornati in base alla nuova posizione dei file nella struttura di cartelle flat. Se impostato su false, la struttura delle cartelle viene mantenuta invariata nel file ZIP. Se la mappa DITA fa riferimento a file provenienti da più posizioni, anche tutte queste posizioni vengono create nel file ZIP. Quando si ripristina il file ZIP, viene creata la struttura di cartelle esatta nel percorso di destinazione.<br> Il valore predefinito per questo parametro è false.|

**Restituisce**:
Il nodo del file zip è racchiuso nella classe `CompletableFuture`. L&#39;utente può continuare a gestirlo in modo asincrono e può utilizzare il metodo `.get()` del futuro per bloccare il thread quando il nodo è necessario. Il valore restituito può inoltre terminare con un errore e può essere gestito con il metodo `.exceptionally()`.

## Ottieni un elenco di linee di base

Il metodo ``getBaselineList`` recupera un elenco di tutte le baseline esistenti per una determinata mappa DITA.

**Sintassi**:

```JAVA
public static List<HashMap<String,String>> getBaselineList( 
                  javax.jcr.Session session, 
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parametri**:
|Nome|Tipo|Descrizione|
----|----|-----------|
|`session`|javax.jcr.Session|Sessione JCR valida.|
|`sourcePath`|Stringa|Percorso \(nell&#39;archivio AEM\) del file mappa DITA per il quale devono essere recuperate le informazioni della baseline.|

**Restituisce**:
Elenco di `HashMap` oggetti. Ogni oggetto `HashMap` rappresenta una baseline e contiene il nome e il titolo della baseline.

**Eccezione**:
Genera ``javax.jcr.RepositoryException``.

## Ottenere un elenco di predefiniti condizionali

Il metodo ``getConditionalPresetList`` recupera un elenco di tutti i predefiniti condizionali esistenti per una determinata mappa DITA.

**Sintassi**:

```JAVA
public static List<HashMap<String,String>> getConditionalPresetList (
                  javax.jcr.Session session,
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parametri**:
|Nome|Tipo|Descrizione|
----|----|-----------|
|`session`|javax.jcr.Session|Sessione JCR valida.|
|`sourcePath`|Stringa|Percorso \(nell&#39;archivio AEM\) del file mappa DITA per il quale devono essere recuperate le informazioni sul predefinito condizionale.|

**Restituisce**:
Elenco di `HashMap` oggetti. Ogni oggetto `HashMap` rappresenta un predefinito condizionale e contiene il nome e il titolo del predefinito condizionale.

**Eccezione**:
Genera ``javax.jcr.RepositoryException``.

## Ottenere le informazioni del file DITAVAL per un predefinito condizionale

Il metodo ``getDitavalFromConditionalPreset`` recupera il percorso del file DITAVAL corrispondente a un predefinito condizionale per una data mappa DITA.

**Sintassi**:

```JAVA
public static String getDitavalFromConditionalPreset
    (Session session,
    String sourcePath, 
    String cpName) throws RepositoryException
```

**Parametri**:
|Nome|Tipo|Descrizione|
----|----|-----------|
|`session`|javax.jcr.Session|Sessione JCR valida.|
|`sourcePath`|Stringa|Percorso \(nell&#39;archivio AEM\) del file mappa DITA per il quale deve essere recuperato il file DITAVAL.|
|`cpName`|Stringa|Nome del predefinito condizionale nella mappa DITA per il quale deve essere recuperato il file DITAVAL.|

**Restituisce**:
Percorso del file DITAVAL corrispondente al predefinito condizionale definito nel file di mappa DITA.

## Ottenere tutte le dipendenze per un nodo

Il metodo ``getAllDependencies`` restituisce tutte le dipendenze di un determinato nodo.

**Sintassi**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Parametri**:
|Nome|Tipo|Descrizione|
----|----|-----------|
|`rootNode`|javax.jcr.Node|Il nodo principale per il quale devono essere recuperate tutte le dipendenze.|

**Restituisce**:
Elenco di nodi contenente tutte le dipendenze del nodo principale.
