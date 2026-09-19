---
title: Consigli per l’ottimizzazione delle prestazioni per Cloud Service
description: Scopri i consigli per l’ottimizzazione delle prestazioni
feature: Performance Optimization
role: Admin
level: Experienced
exl-id: 6c9684d4-180f-4ccb-bfd6-6c82a8a7b720
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# Consigli per l’ottimizzazione delle prestazioni per Cloud Service {#id213BD0JG0XA}

Per l&#39;ottimizzazione delle prestazioni, considerare i punti seguenti:

- Per ottimizzare il contenuto e l&#39;esperienza di indicizzazione, vedere [Ottimizzare la ricerca e l&#39;indicizzazione dei contenuti](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=it) nella documentazione di AEM.

- Applicazione di patch al file JAR quando si utilizza DITA-OT personalizzato per la pubblicazione. Si tratta di una configurazione obbligatoria, a seconda del caso d’uso. Questa modifica è necessaria solo se si utilizza DITA-OT personalizzato per la pubblicazione dell&#39;output.

  *Configurazione richiesta*: sostituire il file JAR Xerces nel pacchetto DITA-OT personalizzato con quello fornito con OOTB. Il file OOTB `xercesImpl-2.11.0.jar` predefinito è disponibile nel file `/libs/fmdita/dita\_resources/DITA-OT.zip`. Accertarsi di rinominare il file `xercesImpl-2.11.0.jar` in modo che corrisponda al vecchio file Xerces Jar da sostituire. Questa operazione può essere eseguita in fase di esecuzione.

  Questa modifica riduce il tempo di pubblicazione e l&#39;utilizzo della memoria durante la pubblicazione di mappe DITA con un numero elevato di argomenti.
