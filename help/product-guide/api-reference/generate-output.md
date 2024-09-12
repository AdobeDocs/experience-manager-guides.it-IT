---
title: API basata su Java per lavorare con la generazione di output
description: Scopri l’API basata su Java per lavorare con la generazione dell’output
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
source-git-commit: ee4eb829ebe215315b05cd1f376e934c02a73b1e
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# API basata su Java per lavorare con la generazione di output {#id175UB30E05Z}

>[!NOTE]
>
> Puoi utilizzare le API basate su Java disponibili in Experience Manager Guides per creare plug-in personalizzati ed estendere flussi di lavoro preconfigurati. Questo articolo verrà archiviato a novembre 2024.
> Visualizza [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) per la documentazione più recente e dettagliata sull&#39;utilizzo dell&#39;API basata su Java.

La seguente API basata su Java consente di generare l&#39;output per una mappa DITA. Questa API è disponibile sotto forma di bundle. Per utilizzare queste API, devi includere questo bundle nel codice.

Dettagli bundle:

- ID gruppo: **com.adobe.fmdita**

- ID artefatto: **api**

- Versione: **3.4**

- Pacchetto: ****com.adobe.fmdita.api.map****

- Dettagli classe:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  La classe **`PublishUtils`** contiene un metodo per generare l&#39;output per uno o più predefiniti di output.


## Genera output

Il metodo ``generateOutput`` genera l&#39;output per un file di mappa DITA utilizzando i predefiniti di output specificati.

**Sintassi**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sessione JCR valida. |
| ``sourcePath`` | Stringa | Percorso \(nel repository AEM\) del file di mapping DITA per il quale deve essere generato l&#39;output. |
| ``outputName`` | Stringa | Nome del predefinito di output\(s\) da utilizzare per generare l&#39;output. È possibile specificare più predefiniti di output utilizzando un delimitatore pipe \(&quot;\|&quot;\), ad esempio `aemsite\|pdfoutput`. |

**Eccezione**:
Genera ``javax.jcr.RepositoryException``, `java.io.IOException` e `java.lang.Exception`.
