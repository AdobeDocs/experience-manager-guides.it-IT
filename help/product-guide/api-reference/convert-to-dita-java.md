---
title: API basate su Java per il flusso di lavoro di conversione
description: Scopri le API basate su Java per il flusso di lavoro di conversione
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 4%

---

# API basate su Java per il flusso di lavoro di conversione {#id175UB30E05Z}

>[!NOTE]
>
> Puoi utilizzare le API basate su Java disponibili in Experience Manager Guides per creare plug-in personalizzati ed estendere flussi di lavoro preconfigurati. Questo articolo verrà archiviato a novembre 2024.
> Visualizza [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) per la documentazione più recente e dettagliata sull&#39;utilizzo dell&#39;API basata su Java.




Le seguenti API basate su Java consentono di convertire i documenti HTML e Word in formato DITA. Queste API sono disponibili sotto forma di bundle. Per utilizzare queste API, devi includere questo bundle nel codice.

**Dettagli bundle**:

- ID gruppo: **com.adobe.fmdita**

- ID artefatto: **api**

- Versione: **3.2**

- Pacchetto: **com.adobe.fmdita.api.conversion**

- Dettagli classe:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  La classe **ConversionUtils** contiene metodi per la conversione di documenti HTML e Word in formato DITA.


## Conversione di documenti HTML

Il metodo `convertHtmlToDita` converte i documenti HTML in formato DITA.

**Sintassi**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sessione JCR valida. |
| `inputFile` | Stringa | Percorso assoluto dei file HTML di origine nell’archivio AEM. |
| `destPath` | Stringa | Percorso assoluto della posizione di destinazione in cui verranno salvati i file DITA convertiti. |
| `createRev` | Booleano | Specificare se creare una revisione dei file \( `true`\) nella destinazione specificata o meno \( `false`\). Questo viene considerato solo quando il percorso di destinazione contiene una versione esistente dei file convertiti. |

**Eccezione**:
Genera `RepositoryException`.

## Convertire documenti di Word

Il metodo ``convertWordToDita`` converte i documenti di Word in formato DITA.

**Sintassi**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `session` | javax.jcr.Session | Una sessione JCR valida. |
| `inputFile` | Stringa | Percorso assoluto dei file Word di origine nell’archivio AEM. |
| `destPath` | Stringa | Percorso assoluto della posizione di destinazione in cui verranno salvati i file DITA convertiti. |
| `style2tagMap` | Stringa | Percorso assoluto del file di mapping degli stili che verrà utilizzato per la conversione. |
| `createRev` | Booleano | Specificare se creare una revisione dei file \( `true`\) nella destinazione specificata o meno \( `false`\). Questo viene considerato solo quando il percorso di destinazione contiene una versione esistente dei file convertiti. |

**Eccezione**:
Genera `RepositoryException`.
