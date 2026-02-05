---
title: Distribuzione dell’indicizzazione personalizzata
description: Scopri come personalizzare il contenuto dell’indice
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 9a4f0391c464d69ea65ecfdaac6ecdcb17d1a3da
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 3%

---

# Distribuzione dell’indice personalizzato per la funzione Trova e sostituisci (visualizzazione Source)

## Panoramica

Questa guida fornisce istruzioni dettagliate per la distribuzione dell&#39;indice personalizzato `guidesAssetLucene‑1‑custom‑1` in Adobe Experience Manager (AEM) as a Cloud Service. Anche se la funzione standard Trova e sostituisci nella vista Autore funziona senza questo indice, l’indice personalizzato è necessario in modo specifico per abilitare Trova e sostituisci nella vista Source. La vista Trova e sostituisci (Source) consente di cercare non solo il contenuto visibile creato, ma anche la struttura XML sottostante, inclusi elementi, tag e valori di attributi.

## Prerequisiti

Prima di procedere con la distribuzione dell’indice, assicurati di disporre di:

- **Ambiente AEM as a Cloud Service** con AEM Guides installato
- **Accesso alla base di codice del progetto** (archivio Git)
- **Accesso a Cloud Manager** con autorizzazioni di distribuzione

## Definizione dell’indice

Per abilitare la funzione Trova e sostituisci (visualizzazione Source), è necessario distribuire un indice personalizzato denominato **`guidesAssetLucene-1-custom-1`** nell&#39;ambiente AEM Cloud Service.

### Nome indice

```
guidesAssetLucene-1-custom-1
```

### Definizione indice (.content.xml)

Crea la seguente definizione di indice nel progetto in:

`ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:dam="http://www.day.com/dam/1.0"
          xmlns:nt="http://www.jcp.org/jcr/nt/1.0" xmlns:oak="http://jackrabbit.apache.org/oak/ns/1.0"
          xmlns:rep="internal"
          jcr:mixinTypes="[rep:AccessControllable]"
          jcr:primaryType="oak:QueryIndexDefinition"
          async="[async,nrt]"
          compatVersion="{Long}2"
          evaluatePathRestrictions="{Boolean}true"
          includedPaths="[/content/dam]"
          selectionPolicy="tag"
          tags="[ditaSearch]"
          type="lucene">

    <aggregates jcr:primaryType="nt:unstructured">
        <dam:Asset jcr:primaryType="nt:unstructured">
            <include0
                    jcr:primaryType="nt:unstructured"
                    path="jcr:content/renditions/original/jcr:content"
                    relativeNode="{Boolean}true"/>
        </dam:Asset>
    </aggregates>

    <analyzers jcr:primaryType="nt:unstructured">
        <default jcr:primaryType="nt:unstructured">
            <tokenizer
                    jcr:primaryType="nt:unstructured"
                    name="Whitespace"/>
        </default>
    </analyzers>

    <indexRules jcr:primaryType="nt:unstructured">
        <dam:Asset
                jcr:primaryType="nt:unstructured"
                indexNodeName="{Boolean}true">
            <properties jcr:primaryType="nt:unstructured">
                <cqTags
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/cq:tags"
                        nodeScopeIndex="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        useInSpellcheck="{Boolean}true"
                        useInSuggest="{Boolean}true"/>
                <jcrLastModified
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/jcr:lastModified"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <jcrCreated
                        jcr:primaryType="nt:unstructured"
                        name="jcr:created"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <guidesParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesParentMaps"
                        propertyIndex="{Boolean}true"/>
                <guidesDirectParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesDirectParentMaps"
                        propertyIndex="{Boolean}true"/>
                <ditaClass
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dita_class"
                        propertyIndex="{Boolean}true"/>
                <nodeNameLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(fn:name())"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"/>
                <cqDriveLock
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/cq:driveLock"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <docState
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/docstate"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <jcrPath
                        jcr:primaryType="nt:unstructured"
                        function="fn:path()"
                        ordered="{Boolean}true"/>
                <dcTitleLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(jcr:first(jcr:content/metadata/@dc:title))"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <dcTitle
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dc:title"
                        propertyIndex="{Boolean}true"/>
            </properties>
        </dam:Asset>
    </indexRules>

    <tika jcr:primaryType="nt:unstructured">
        <mimeTypes jcr:primaryType="nt:unstructured">
            <application jcr:primaryType="nt:unstructured">
                <xml
                        jcr:primaryType="nt:unstructured"
                        mappedType="application/dita+xml"/>
            </application>
            <text jcr:primaryType="nt:unstructured">
                <markdown
                        jcr:primaryType="nt:unstructured"
                        mappedType="text/markdown+source"/>
            </text>
        </mimeTypes>
    </tika>
</jcr:root>
```

## Passaggi della distribuzione

Per istruzioni dettagliate sulla distribuzione di indici personalizzati in AEM as a Cloud Service, visualizzare [Ricerca e indicizzazione dei contenuti - AEM as a Cloud Service](https://experienceleague.adobe.com/it/docs/experience-manager-cloud-service/content/operations/indexing).

### Punti importanti per questo indice

Quando segui la guida alla distribuzione, utilizza le seguenti specifiche per l’indice Find and replace:

- **Nome indice**: `guidesAssetLucene-1-custom-1`
- **Tipo di indice**: indice completamente personalizzato (non personalizzazione dell&#39;indice OOTB)
- **Posizione**: `ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`
- **Proprietà pacchetto richieste**:
   - `noIntermediateSaves=true`
   - `allowIndexDefinitions=true`

## Reindicizzazione

La reindicizzazione viene gestita **automaticamente** da AEM as a Cloud Service quando distribuisci l&#39;indice tramite la pipeline CI/CD di Cloud Manager.

L’indicizzazione viene in genere gestita automaticamente. Tuttavia, se i vecchi dati rimangono non ricercabili anche dopo la distribuzione corretta e il completamento del processo di indicizzazione, è necessario eseguire una reindicizzazione manuale dell’indice una volta.

### Cosa aspettarsi

- Il processo di indicizzazione verrà avviato automaticamente dopo la distribuzione.
- Puoi monitorare l’avanzamento nella pagina della build di Cloud Manager.
- L’ambiente rimane completamente operativo durante l’indicizzazione.

## Verifica

Dopo il completamento della distribuzione e dell’indicizzazione, verifica che l’indice funzioni correttamente.

### Verifica distribuzione indice

Nell’ambiente di sviluppo (se CRXDE Lite è disponibile):

1. Accedi a `/oak:index/guidesAssetLucene-1-custom-1`.
2. Verifica che esista il nodo con la configurazione prevista.

### Verificare la funzionalità Trova e sostituisci

La verifica principale consiste nel testare la funzione:

1. Apri AEM Guides.
2. Passa a **Strumenti** > **Guide** > **Trova e sostituisci nell&#39;archivio**.
3. Configurare una ricerca di testo nei file DITA o Markdown.
4. Verifica che i risultati della ricerca vengano restituiti correttamente.
5. Testare la funzionalità di sostituzione in un file di test.

## Risorse aggiuntive

- [Documentazione sull&#39;indicizzazione di AEM as a Cloud Service](https://experienceleague.adobe.com/it/docs/experience-manager-cloud-service/content/operations/indexing)
- [Guida all&#39;indicizzazione di Apache Jackrabbit Oak](https://jackrabbit.apache.org/oak/docs/query/indexing.html)
- [Documentazione di AEM Guides](https://experienceleague.adobe.com/it/docs/experience-manager-guides)
- [Documentazione di Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager)
