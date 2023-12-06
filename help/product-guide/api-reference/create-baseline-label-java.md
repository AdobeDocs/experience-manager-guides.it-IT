---
title: API basate su Java per lavorare con le linee di base e le etichette
description: Scopri le API basate su Java da utilizzare con le linee di base e le etichette
exl-id: 0e2ba1bb-f5bf-44da-848a-a55385460c83
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 0%

---

# API basate su Java per lavorare con le linee di base e le etichette {#id175UB30E05Z}

Le seguenti API basate su Java consentono di creare una linea di base e aggiungere etichette ai file in una linea di base. Queste API sono disponibili sotto forma di bundle. Per utilizzare queste API, devi includere questo bundle nel codice.

Dettagli bundle:

- ID gruppo: **com.adobe.fmdita**

- ID artefatto: **api**

- Versione: **3,5**

- Pacchetto **com.adobe.fmdita.api.baselines**

- Dettagli classe:

  ```JAVA
  public class BaselineUtils extends Object
  ```

  Il **UtilitàPrevisione** La classe contiene metodi per la creazione di baseline e l&#39;applicazione di etichette ai file in una baseline.


## Creare una baseline

Il metodo di base per la creazione dispone di due versioni: una per la soluzione XML Documentation versione 3.5 e l’altra per le versioni precedenti alla versione 3.5 \ (che include le versioni 3.4, 3.3 e 3.2\). La versione 3.5 dell’API consente la creazione di una linea di base utilizzando un’etichetta, riferimenti diretti e riferimenti indiretti in un file di mappa.

L’altra versione dell’API utilizza la data e l’ora per creare una linea di base. Questa API viene mantenuta per compatibilità con le versioni precedenti dei sistemi che utilizzano la soluzione XML Documentation 3.4, 3.3 o 3.2.

**Sintassi \(per versione 3.5\)**:

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Parametri**: |Nome|Tipo|Descrizione| ----|----|-----------| |`session`|javax.jcr.Session|Sessione JCR valida. La sessione utente deve disporre delle autorizzazioni di lettura e scrittura per la mappa DITA e delle autorizzazioni di lettura per tutti i file di riferimento inclusi nella baseline.| |`sourcePath`|Stringa|Percorso assoluto del file mappa DITA nell&#39;archivio AEM.| |`baselineTitle`|Stringa|Titolo univoco per la linea di base.| |`label`|Stringa|Selezionare la versione di un argomento a cui è applicata l&#39;etichetta specificata.| |`directContext`|LinkedHashMap&lt;string object=&quot;&quot;>|Le configurazioni in base alle quali viene selezionato l’argomento \(contenuto\) direttamente referenziato, per risolvere una versione viene seguito l’ordine indicato nella mappa. <br> Se dopo l&#39;iterazione su tutte le chiavi della mappa non viene trovata alcuna versione, il processo di creazione della linea di base ha esito negativo. <br> Se l&#39;HashMap è vuoto \(invia una mappa vuota e non null per default\), per impostazione predefinita viene popolato come: <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Se si desidera che la creazione della baseline selezioni solo la versione di una determinata etichetta e non riesca in assenza di tale versione, inserire `label` e l’etichetta su cui desideri creare la linea di base.| |`indirectContext`|LinkedHashMap&lt;string object=&quot;&quot;>|Le configurazioni in base alle quali è selezionato l’argomento indirettamente referenziato \(contenuto referenziato\), viene seguito l’ordine indicato nella mappa per risolvere una versione. <br> Se dopo l&#39;iterazione su tutte le chiavi della mappa non viene trovata alcuna versione, il processo di creazione della linea di base ha esito negativo. <br> Se l&#39;HashMap è vuoto \(invia una mappa vuota e non null per default\), per impostazione predefinita viene popolato come: <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Se desideri che sia la versione più recente invece di prelevare automaticamente una versione, sostituisci: <br>`indirectContext.put("pickAutomatically", null);` <br> _con:_ <br>`indirectContext.put("latest", true)`|

**Restituisce**: nome della linea di base, che è il nome del nodo della linea di base nell’archivio JCR. Il titolo della baseline appena creata verrà visualizzato all&#39;utente nella pagina Baseline della mappa DITA.

**Eccezione**: proiezioni ``ItemExistExceptiom`` se esiste già una baseline con lo stesso titolo.

**Sintassi \(per le versioni 3.4, 3.3 e 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Parametri**: |Nome|Tipo|Descrizione| ----|----|-----------| |`session`|javax.jcr.Session|Sessione JCR valida. La sessione utente deve disporre delle autorizzazioni di lettura e scrittura per la mappa DITA e delle autorizzazioni di lettura per tutti i file di riferimento inclusi nella baseline.| |``sourcePath``|Stringa|Percorso assoluto del file mappa DITA nell&#39;archivio AEM.| |`baselineTitle`|Stringa|Titolo univoco per la linea di base.| |`versionDate`|Data|La previsione viene creata utilizzando le versioni degli argomenti\(a cui si fa riferimento direttamente dalla mappa DITA\) come in questa data. Specifica la data in `d-MM-yyyy H:mm` formato.|

**Restituisce**: nome della linea di base, che è il nome del nodo della linea di base nell’archivio JCR. Il titolo della baseline appena creata verrà visualizzato all&#39;utente nella pagina Baseline della mappa DITA.

**Eccezione**: proiezioni ``RepositoryException.``

## Applica etichette

Il ``applyLabel`` Il metodo applica una o più etichette ai file di una baseline.

**Sintassi**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Parametri**: |Nome|Tipo|Descrizione| ----|----|-----------| |`session`|javax.jcr.Session|Sessione JCR valida.| |`sourcePath`|Stringa|Percorso assoluto del file mappa DITA nell&#39;archivio AEM.| |``baselineName``|String|Nome del nodo della linea di base a cui deve essere applicata l&#39;etichetta. Per ottenere il nome del nodo della baseline, è possibile utilizzare [\#id185NFF0085Z](#id185NFF0085Z) o controllare il nodo delle baseline della mappa DITA in CRXDE.<br> **Nota:** L&#39;etichetta viene applicata alla versione dei file a cui viene fatto riferimento direttamente dal file mappa nella linea di base.| |`label`|Stringa|Etichetta applicata ai file nella baseline. Assicurati che l’etichetta non contenga i seguenti caratteri: &amp;sol; &amp;virgola; &amp;colon; &amp;virgola; &amp;lbrack; &amp;virgola; &amp;rbrack; &amp;virgola; &amp;vert; &amp;virgola; &amp;ast; <br> Se si desidera impostare più etichette, separarle con una virgola, ad esempio Label1, Label2.|

**Eccezione**: proiezioni `RepositoryException`.

## Elimina etichette

Il ``deleteLabel`` metodo elimina una o più etichette dai file di una baseline.

**Sintassi**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Parametri**: |Nome|Tipo|Descrizione| ----|----|-----------| |`session`|javax.jcr.Session|Sessione JCR valida.| |`sourcePath`|Stringa|Percorso assoluto del file mappa DITA nell&#39;archivio AEM.| |`baselineName`|String|Nome della linea di base da cui eliminare l&#39;etichetta. <br> **Nota:** L&#39;etichetta viene eliminata dalla versione dei file a cui viene fatto riferimento direttamente dal file di mappa nella linea di base.| |`label`|Stringa|Etichetta da eliminare dai file nella linea di base. <br> Se si desidera eliminare più etichette, separarle con una virgola, ad esempio Label1, Label2.|

**Restituisce**: mappa con *chiave:valore* coppia di `path:deletedlabels` per tutti i file nella baseline.

**Eccezione**: proiezioni ``RepositoryException`, `VersionException`, `Exception``.
