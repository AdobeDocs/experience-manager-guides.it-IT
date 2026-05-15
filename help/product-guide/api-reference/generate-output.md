---
title: API basata su Java per lavorare con la generazione di output
description: Scopri l’API basata su Java per lavorare con la generazione dell’output
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/i5mTM1VtBg3QFUa-sBmF2pH8BITRn9j-efw2dr8VwCU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: a3bd6397-2eb2-4908-a61c-226e26855dcaid: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2: id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 225
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
| ``sourcePath`` | Stringa | Percorso \(nel repository AEM\) del file mappa DITA per il quale deve essere generato l&#39;output. |
| ``outputName`` | Stringa | Nome del predefinito di output\(s\) da utilizzare per generare l&#39;output. È possibile specificare più predefiniti di output utilizzando un delimitatore pipe \(&quot;\|&quot;\), ad esempio `aemsite\|pdfoutput`. |

**Eccezione**:
Genera ``javax.jcr.RepositoryException``, `java.io.IOException` e `java.lang.Exception`.
