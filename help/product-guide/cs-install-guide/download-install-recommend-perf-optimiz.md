---
title: Recommendations per l'ottimizzazione delle prestazioni
description: Scopri Recommendations per l’ottimizzazione delle prestazioni
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Recommendations per l&#39;ottimizzazione delle prestazioni {#id213BD0JG0XA}

Per l&#39;ottimizzazione delle prestazioni, considerare i punti seguenti:

- Per ottimizzare il contenuto e l’esperienza di indicizzazione, consulta [Ottimizzare la ricerca e l’indicizzazione dei contenuti](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=it) nella documentazione AEM.

- Applicazione di patch al file JAR quando si utilizza DITA-OT personalizzato per la pubblicazione. Si tratta di una configurazione obbligatoria, a seconda del caso d’uso. Questa modifica è necessaria solo se si utilizza DITA-OT personalizzato per la pubblicazione dell&#39;output.

  *Configurazione richiesta*: sostituisci il file JAR Xerces nel pacchetto DITA-OT personalizzato con quello fornito con OOTB. Il file xercesImpl-2.11.0.jar OOTB predefinito è disponibile nel file /libs/fmdita/dita\_resources/DITA-OT.zip. Accertati di rinominare il file xercesImpl-2.11.0.jar in modo che corrisponda al vecchio file Xerces Jar che viene sostituito. Questa operazione può essere eseguita in fase di esecuzione.

  Questa modifica riduce il tempo di pubblicazione e l&#39;utilizzo della memoria durante la pubblicazione di mappe DITA con un numero elevato di argomenti.


**Argomento padre:**[ Scarica e installa](download-install.md)
