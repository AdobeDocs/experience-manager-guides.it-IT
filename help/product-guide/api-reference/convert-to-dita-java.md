---
title: API basate su Java per il flusso di lavoro di conversione
description: Scopri le API basate su Java per il flusso di lavoro di conversione
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# API basate su Java per il flusso di lavoro di conversione {#id175UB30E05Z}

Le seguenti API basate su Java consentono di convertire i documenti HTML e Word in formato DITA. Queste API sono disponibili sotto forma di bundle. Per utilizzare queste API, devi includere questo bundle nel codice.

**Dettagli bundle**:

- ID gruppo: **com.adobe.fmdita**

- ID artefatto: **api**

- Versione: **3,2**

- Pacchetto **com.adobe.fmdita.api.conversion**

- Dettagli classe:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  Il **ConversionUtils** La classe contiene metodi per la conversione di documenti HTML e Word in formato DITA.


## Conversione di documenti HTML

Il `convertHtmlToDita` metodo converte i documenti HTML in formato DITA.

**Sintassi**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parametri**: |Nome|Tipo|Descrizione| ----|----|-----------| |`session`|javax.jcr.Session|Sessione JCR valida.| |`inputFile`|String|Percorso assoluto dei file HTML di origine nell’archivio AEM.| |`destPath`|Stringa|Percorso assoluto del percorso di destinazione in cui verranno salvati i file DITA convertiti.| |`createRev`|Booleano|Specificare se viene creata una revisione dei file \( `true`\) alla destinazione specificata o meno \( `false`\). Questa opzione viene considerata solo se il percorso di destinazione contiene una versione esistente dei file convertiti.|

**Eccezione**: proiezioni `RepositoryException`.

## Convertire documenti di Word

Il ``convertWordToDita`` converte i documenti di Word in formato DITA.

**Sintassi**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parametri**: |Nome|Tipo|Descrizione| ----|----|-----------| |`session`|javax.jcr.Session|Sessione JCR valida.| |`inputFile`|String|Percorso assoluto dei file Word di origine nell&#39;archivio AEM.| |`destPath`|Stringa|Percorso assoluto del percorso di destinazione in cui verranno salvati i file DITA convertiti.| |`style2tagMap`|String|Percorso assoluto del file di mapping degli stili che verrà utilizzato per la conversione.| |`createRev`|Booleano|Specificare se viene creata una revisione dei file \( `true`\) alla destinazione specificata o meno \( `false`\). Questa opzione viene considerata solo se il percorso di destinazione contiene una versione esistente dei file convertiti.|

**Eccezione**: proiezioni `RepositoryException`.
