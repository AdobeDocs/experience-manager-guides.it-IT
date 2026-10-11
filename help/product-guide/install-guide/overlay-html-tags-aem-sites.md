---
title: Sovrapporre i tag HTML nell’output AEM Sites non legacy
description: Configura le impostazioni video e immagine per l’output di AEM Sites in base alla mappatura dei componenti core
feature: Installation
role: Admin
level: Experienced
exl-id: 726420e0-fe52-4334-b72a-8eb8bcae4d6c
TQID: 'https://experienceleague.adobe.com/wWeg9MdnMPXIIQWSjrr5oiQKIqEroCHZY6Oph0wAQ38'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%
---
# Sovrapporre i tag HTML nell’output di AEM Sites

Puoi aggiungere e personalizzare i tag HTML nell’output di AEM Sites generato utilizzando il predefinito di AEM Sites basato sulla mappatura dei componenti core dall’editor web. Per personalizzare i tag di HTML, è possibile sovrapporre il file `config.xml`. Ad esempio, puoi configurare le mappe video e immagine nell’output di AEM Sites.

Per sovrapporre e aggiornare il file `config.xml`, effettuare le seguenti operazioni:

1. Accedi ad AEM e apri la modalità CRXDE Lite.

1. Passa al file di configurazione disponibile nella posizione seguente:

   `/libs/cq/xssprotection/config.xml`

1. Crea un nodo di sovrapposizione della cartella `xssprotection` all&#39;interno del nodo delle app.

1. Passare al file di configurazione disponibile nel nodo `apps`:

   `/apps/fmdita/config/config.xml`

1. Aggiorna i seguenti tag per i video e le immagini. Quindi, salva il file.

Video:

```XML
    <tag name="video" action="validate">
    <attribute name="src">
      <regexp-list>
        <regexp name="anything"/>
      </regexp-list>
    </attribute>
    <attribute name="width">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="height">
       <regexp-list>
          <regexp name="anything"/>
       </regexp-list>
     </attribute>
     <attribute name="data">
       <regexp-list>
         <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="class">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="poster">
      <regexp-list>
        <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="controls">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="source" action="validate">
      <attribute name="src">
        <regexp-list>
           <regexp name="anything"/>
        </regexp-list>
      </attribute>
    </tag>
```

Mappe immagine:

```XML
        <tag name="map" action="validate">
    <attribute    name="name">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <!-- Image & image related tags -->
    <tag name="img" action="validate">
    <attribute name="src" onInvalid="removeTag">
        <regexp-list>
            <regexp name="onsiteURL"/>
            <regexp name="offsiteURL"/>
        </regexp-list>
    </attribute>
    <attribute name="name"/>
    <attribute name="alt"/>
    <attribute name="height"/>
    <attribute name="width"/>
    <attribute name="border"/>
    <attribute name="align"/>
    <attribute name="usemap">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="hspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    <attribute name="vspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="area" action="validate">
    <attribute name="shape">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="coords">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="href">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
   </tag>
```




Ulteriori informazioni sulle best practice di [Sicurezza](https://experienceleague.adobe.com/it/docs/experience-manager-65/content/implementing/developing/introduction/security).
