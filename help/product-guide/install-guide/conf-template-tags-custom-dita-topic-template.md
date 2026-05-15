---
title: Configura modello di argomento DITA personalizzato
description: Scopri come configurare un modello di argomento DITA personalizzato
exl-id: a9b2c479-7bf6-4c62-addd-fdfe74dc1f69
feature: Template Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/YGsNmqPAjBHtBEa-o53tns-h1DLRkTZNIq3PNbG8LNw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 365
ht-degree: 2%

---

# Configura modello di argomento DITA personalizzato {#id16A7G0O02TD}

AEM Guides viene fornito con i seguenti modelli di argomenti DITA:

- Argomento

- Attività

- Concetto

- Riferimento

- Glossario

- Risoluzione di problemi

- Vuoto


È possibile utilizzare uno qualsiasi di questi modelli per creare modelli di argomenti in base ai requisiti di creazione. Il modello DITA vuoto non contiene alcuna struttura o elemento come gli altri modelli. È possibile utilizzare il modello vuoto come base, se il modello è altamente personalizzato e non è basato su alcun modello di argomento DITA regolare.

Per personalizzare il modello di argomento DITA e utilizzarlo per l&#39;authoring, è necessario eseguire le tre attività principali seguenti:

1. *\(Facoltativo\)* [Configura percorso cartella modello DITA personalizzato](#id191LCF0095Z)

1. [Creare un modello di authoring personalizzato](conf-folder-level.md#id1917D0EG0HJ)

1. Aggiungi un modello personalizzato al profilo globale o a livello di cartella come descritto nella sezione [Configurare i modelli di authoring](conf-folder-level.md#id1889D0IL0Y4)


## Configura percorso cartella modello DITA personalizzato {#id191LCF0095Z}

AEM Guides consente di configurare una cartella in cui memorizzare la mappa DITA e i modelli personalizzati. Per impostazione predefinita, i file modello vengono memorizzati nella seguente cartella in DAM:

`/content/dam/dita-templates/`

Per gestire i file degli argomenti e dei modelli di mapping, sono disponibili cartelle dedicate in cui sono memorizzati gli argomenti e i modelli di mapping. Per impostazione predefinita, tutti i modelli di argomento sono archiviati in `/content/dam/dita-templates/topics`

cartella. Tutti i modelli di mappa sono archiviati nella cartella `/content/dam/dita-templates/maps`.

In qualità di amministratore, puoi scegliere di creare modelli di mappe o argomenti personalizzati nella cartella predefinita o di creare una cartella personalizzata in cui memorizzare i modelli personalizzati. Se prevedi di utilizzare la cartella predefinita, puoi saltare questo processo.

Per configurare una cartella per i modelli di argomento DITA personalizzati, effettuare le seguenti operazioni:

>[!IMPORTANT]
>
> Puoi saltare questo processo se desideri utilizzare la cartella predefinita per memorizzare i modelli personalizzati.

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle *com.adobe.fmdita.config.ConfigManager*.

1. Nella proprietà **Posizione modelli**, specificare un percorso in cui memorizzare i modelli personalizzati.

1. Fai clic su **Salva**.


Se il percorso specificato esiste in DAM, tutti i modelli di mappa e argomenti predefiniti vengono copiati in tale cartella. Se il percorso non esiste, la cartella viene creata con tutti i modelli predefiniti per mappe e argomenti.

**Argomento padre:**[ Configura modelli di argomento e mappa](conf-template-tags.md)
