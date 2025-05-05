---
title: Recommendations per l'ottimizzazione delle prestazioni
description: Scopri Recommendations per l’ottimizzazione delle prestazioni
exl-id: b2a836a0-de82-4d89-aae3-43276997da74
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: b28b7d96cce69f677b0bcf891b94d7ac84eb1eb0
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Recommendations per l&#39;ottimizzazione delle prestazioni {#id213BD0JG0XA}

## Configura archivio dati \(Obbligatorio\)

**Qual è la modifica?**
Impostare la proprietà `minRecordLength` su un valore di `100` nella configurazione `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.` Per ulteriori informazioni sull&#39;archivio date del file e sull&#39;archivio dati S3, vedere l&#39;articolo [Configurazione degli archivi nodi e degli archivi dati in AEM 6](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html).

>[!NOTE]
>
> Per l’archivio dati S3, il costo per la gestione dei contenuti in tale archivio dipende anche dal numero di richieste. Pertanto, quando si esegue questa impostazione con S3, è necessario considerare anche il costo di configurazione per richiesta e la dimensione della cache.

**Quando configurare?**
Dopo la configurazione iniziale, ma prima della migrazione di qualsiasi contenuto. È necessario eseguire questa modifica anche su un sistema esistente, in modo che tutti i nuovi contenuti vengano memorizzati nell’archivio dati anziché in quello dei segmenti.

**Risultato di questa modifica**
I file DITA vengono salvati nell&#39;archivio dati anziché nell&#39;archivio segmenti. In questo modo la dimensione dell’archivio segmenti viene mantenuta al di sotto dei limiti consigliati, il che migliora la reattività del sistema.

## Aggiorna indice Lucene \(obbligatorio\)

**Qual è la modifica?**
Escludi /var/dxml da oak:index/lucene.

>[!NOTE]
>
> AEM Guides non utilizza mai gli indici Lucene per cercare contenuti nel nodo /var/dxml.

**Quando configurare?**
Se si sta apportando questa modifica su un nuovo sistema prima di eseguire la migrazione del contenuto, è necessario aggiornare solo oak:index/lucene. In caso contrario, su un sistema esistente in cui il contenuto è già stato migrato, quindi dopo aver apportato la modifica in oak:index/lucene, ricompilare gli indici per Lucene \(*il completamento potrebbe richiedere alcune ore*\).

**Risultato di questa modifica**
Questa modifica impedisce al nodo /var/dxml di essere indicizzato e memorizzato nell’archivio segmenti.

## Ottimizzazione della memoria Java \(Obbligatorio\)

**Qual è la modifica?**
I parametri di avvio della JVM devono essere accuratamente regolati in base all&#39;infrastruttura e alle dimensioni del disco. È consigliabile consultare il supporto Adobe per ottenere assistenza per accedere alla configurazione ideale. Tuttavia, puoi provare autonomamente le seguenti configurazioni:

: imposta la dimensione heap JVM su un minimo di 1/4 della memoria totale disponibile. Utilizzare il parametro `-Xmx<size>` per impostare la dimensione della memoria heap. Impostare il valore per -`Xms` uguale a `-Xmx`.

- Abilitare `-XX:+HeapDumpOnOutOfMemoryError` e impostare il percorso per `-XX:HeapDumpPath=</path/to/folder` `>`.

- Abilita registro Java GC come:

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

- In generale, per Java 11, utilizzare G1GC \(`-XX:+UseG1GC`\) e per Java 8 utilizzare CMS \(-`XX:+UseConcMarkSweepGC`\).

- Utilizzare `-XX:NewRatio` per controllare le dimensioni della memoria di nuova generazione. Il valore predefinito è 2, il che significa che 1/3 della memoria è utilizzato per le generazioni giovani. Poiché ci sono molti oggetti che vengono creati e distrutti rapidamente, l&#39;utilizzo di un valore pari a 1 allocerà 1/2 della memoria alle giovani generazioni.

: controlla il numero di oggetti da promuovere alla vecchia generazione utilizzando `-XX:MaxTenuringThreshold`. Utilizza il valore 15 \(default\) per ritardare la promozione degli oggetti alla vecchia generazione.

**Quando configurare?**
Se si apporta questa modifica su un sistema esistente, è necessario riavviare il sistema. In caso di una nuova installazione, questa modifica deve essere apportata nello script iniziale \(.bat o .sh\) prima dell&#39;avvio del sistema.

**Risultato di questa modifica**
Ciò consente di ottenere dimensioni heap ottimali e un’esecuzione regolamentata di GC.

## Minificazione della libreria client nell’istanza di authoring \(Facoltativo\)

**Qual è la modifica?**
Le librerie client devono essere impostate per minimizzare nelle istanze di authoring. In questo modo il numero di byte da scaricare per l&#39;esplorazione del sistema da posizioni diverse è ridotto. Per apportare questa modifica, impostare la configurazione in **HTML Library Manager** dalla console Felix.

**Quando configurare?**
Questa operazione può essere eseguita in fase di esecuzione tramite la console Felix o tramite la distribuzione del codice.

**Risultato di questa modifica**
Questa modifica migliora il tempo di caricamento delle pagine nell’istanza di authoring, poiché viene trasferito un numero inferiore di byte per il caricamento delle librerie client.

## Configura i thread di pubblicazione simultanea \(Obbligatorio, a seconda del caso d’uso\)

**Qual è la modifica?**
Questa modifica è necessaria se si utilizza DITA-OT per pubblicare l&#39;output ed è anche definito un numero di thread di pubblicazione simultanei.

Per impostazione predefinita, AEM Guides imposta i thread di pubblicazione sul numero di CPU+1. Tuttavia, si consiglia di impostare questo valore su metà \(1/2\) o un terzo \(1/3\) del numero totale di CPU. Per eseguire questa operazione, impostare la proprietà **Dimensione pool di generazione** nella configurazione `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` in base alle raccomandazioni.

**Quando configurare?**
Questa operazione può essere eseguita in fase di esecuzione tramite la console Felix o tramite la distribuzione del codice.

**Risultato di questa modifica**
Questa modifica assicura che in un’istanza di authoring in esecuzione tutte le risorse non siano allocate per le operazioni di pubblicazione. In questo modo le risorse di sistema sono disponibili anche per gli autori, il che si traduce in una migliore esperienza d&#39;uso.

## Configura la dimensione batch dei nodi per la generazione dell’output del sito AEM \(Obbligatorio, a seconda del caso d’uso\)

**qual è la modifica?**
Questa modifica è necessaria se si sta generando l’output di AEM Sites.

Impostare la proprietà **Limita pagine del sito AEM nell&#39;heap** in `com.adobe.fmdita.config.ConfigManager` su un numero in base alla configurazione del sistema. Questa proprietà definisce la dimensione batch dei nodi di cui eseguire il commit quando vengono generate le pagine del sito. Ad esempio, in un sistema con un numero maggiore di CPU e dimensioni heap, è possibile aumentare il valore predefinito da `500` a un numero maggiore. Per ottenere un valore ottimale per questa proprietà, devi eseguire il test con il valore modificato.

**Quando configurare?**
Questa operazione può essere eseguita in fase di esecuzione tramite la console Felix o tramite la distribuzione del codice.

**Risultato di questa modifica**
Un numero maggiore di **Limita pagine del sito AEM nella proprietà Heap** ottimizza il processo di generazione dell&#39;output del sito AEM.


**Argomento padre:**&#x200B;[ Scarica e installa](download-install.md)
