---
title: Consigli per l’ottimizzazione delle prestazioni
description: Scopri i consigli per l’ottimizzazione delle prestazioni
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
feature: Performance Optimization
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/vh0hogZNMjKrCL12WdKVuwF2qXdzy64KxIhhB-K4esA'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
    internal-label: Administration and security
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
    internal-label: Performance optimization
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
    internal-label: User administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 5%
---
# Consigli per l’ottimizzazione delle prestazioni {#id213BD0JG0XA}

Per l&#39;ottimizzazione delle prestazioni, considerare i punti seguenti:

- Per ottimizzare il contenuto e l&#39;esperienza di indicizzazione, vedere [Ottimizzare la ricerca e l&#39;indicizzazione dei contenuti](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=it) nella documentazione di AEM.

- Applicazione di patch al file JAR quando si utilizza DITA-OT personalizzato per la pubblicazione. Si tratta di una configurazione obbligatoria, a seconda del caso d’uso. Questa modifica è necessaria solo se si utilizza DITA-OT personalizzato per la pubblicazione dell&#39;output.

  *Configurazione richiesta*: sostituire il file JAR Xerces nel pacchetto DITA-OT personalizzato con quello fornito con OOTB. Il file xercesImpl-2.11.0.jar OOTB predefinito è disponibile nel file /libs/fmdita/dita\_resources/DITA-OT.zip. Accertati di rinominare il file xercesImpl-2.11.0.jar in modo che corrisponda al vecchio file Xerces Jar che viene sostituito. Questa operazione può essere eseguita in fase di esecuzione.

  Questa modifica riduce il tempo di pubblicazione e l&#39;utilizzo della memoria durante la pubblicazione di mappe DITA con un numero elevato di argomenti.


**Argomento padre:**[ Scarica e installa](download-install.md)
