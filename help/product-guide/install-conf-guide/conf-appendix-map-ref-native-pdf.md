---
title: Configurare il rendering dell'appendice per i riferimenti di mappa nell'output PDF nativo
description: Scopri come configurare Experience Manager Guides per il rendering degli argomenti aggiunti in una mappa secondaria all’interno di un’appendice come contenuto dell’appendice nell’output PDF nativo.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 63ae0f947d50646bed34cd815db6b9fb585fc015
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%
---

# Configurare il rendering dell&#39;appendice per i riferimenti di mappa nell&#39;output PDF nativo

Nell&#39;output PDF nativo, gli argomenti a cui viene fatto riferimento in una mappa secondaria all&#39;interno di un elemento `<appendix>` possono essere rappresentati come capitoli anziché come appendici. Per impostazione predefinita, Experience Manager Guides classifica i riferimenti di mappa per nome di elemento e tali informazioni vengono perse una volta che le mappe vengono appiattite durante l’elaborazione.

Utilizzare questa impostazione per classificare i riferimenti di mappa utilizzando l&#39;attributo `class` generato da DITA-OT. Gli argomenti in una sottomappa dell’appendice vengono quindi rappresentati come appendici.

>[!NOTE]
>
>Questa impostazione consente di modificare la classificazione dei riferimenti di mappa. Per impostazione predefinita, è disabilitata. Abilitare questa opzione solo se il contenuto inserisce gli argomenti in una mappa secondaria all&#39;interno di un `<appendix>` e li visualizzi come capitoli nell&#39;output PDF nativo.

## Quando utilizzare questa configurazione

Prendi in considerazione il seguente esempio di mappa del libro:

- Un elemento `<appendix>` fa riferimento direttamente agli argomenti. Questi argomenti vengono visualizzati come appendici nel PDF generato.

  ```XML
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix href="topics/appendix-reference-tables.dita">
    </appendix>
    <appendix href="topics/appendix-troubleshooting.dita">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>`
  ```

- Un altro elemento `<appendix>` fa riferimento a una mappa secondaria e questa fa riferimento ad argomenti utilizzando `<topicref>`.

  ```xml
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix format="ditamap" href="submap-for-appendix.ditamap" type="map">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>
  ```

  La submap-for-appendix:

  ```xml
  <map id="GUID-cc306264-825c-455e-89db-d27af9197a2f">
    <title>submap-for-appendix</title>
    <topicref href="topics/appendix-reference-tables.dita" type="reference">
    </topicref>
    <topicref href="topics/appendix-troubleshooting.dita" type="topic">
    </topicref>
  </map>
  ```

Senza questa configurazione, gli argomenti della prima appendice vengono rappresentati come appendici, ma gli argomenti della sottomappa vengono rappresentati come capitoli. Vengono pubblicati solo gli argomenti; la mappa secondaria stessa viene utilizzata per la gerarchia e non viene visualizzata nell’output.

## Configurare l’impostazione

Di seguito sono riportate le istruzioni per configurare questa impostazione:

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](../install-conf-guide/download-install-config-override.md) per creare il file di configurazione.

2. Nel file di configurazione, fornisci i seguenti dettagli (proprietà):

   | PID | Chiave proprietà | Valore proprietà |
   | --------------------------------------- | -------------------------------- | ----------------------------- |
   | `com.adobe.fmdita.config.ConfigManager` | `guides.publish.config` | {USE_DITA_OT_GENERATED_CLASS&quot;: false} |

3. Impostare il valore su `true` per abilitare l&#39;impostazione e distribuire la configurazione utilizzando Cloud Manager.