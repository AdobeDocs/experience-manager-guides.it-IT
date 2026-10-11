---
title: Consigli per l’ottimizzazione delle prestazioni per Cloud Service
description: Scopri i consigli per l’ottimizzazione delle prestazioni
feature: Performance Optimization
role: Admin
level: Experienced
exl-id: 6c9684d4-180f-4ccb-bfd6-6c82a8a7b720
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
    internal-label: Performance optimization
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
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
