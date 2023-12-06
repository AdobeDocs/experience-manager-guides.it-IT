---
title: Configura modello di argomento DITA personalizzato
description: Scopri come configurare un modello di argomento DITA personalizzato
exl-id: a9b2c479-7bf6-4c62-addd-fdfe74dc1f69
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# Configura modello di argomento DITA personalizzato {#id16A7G0O02TD}

Le guide AEM sono disponibili con i seguenti modelli di argomenti DITA:

- Argomento

- Attività

- Concetto

- Riferimento

- Glossario

- Risoluzione dei problemi

- Vuoto


È possibile utilizzare uno qualsiasi di questi modelli per creare modelli di argomenti in base ai requisiti di creazione. Il modello DITA vuoto non contiene alcuna struttura o elemento come gli altri modelli. È possibile utilizzare il modello vuoto come base, se il modello è altamente personalizzato e non è basato su alcun modello di argomento DITA regolare.

Per personalizzare il modello di argomento DITA e utilizzarlo per l&#39;authoring, è necessario eseguire le tre attività principali seguenti:

1. *\(Facoltativo\)* [Configura percorso cartella modello DITA personalizzato](#id191LCF0095Z)

1. [Creare un modello di authoring personalizzato](conf-folder-level.md#id1917D0EG0HJ)

1. Aggiungere un modello personalizzato al profilo globale o a livello di cartella come descritto nella [Configurare i modelli di authoring](conf-folder-level.md#id1889D0IL0Y4) sezione


## Configura percorso cartella modello DITA personalizzato {#id191LCF0095Z}

Le guide AEM consentono di configurare una cartella in cui memorizzare la mappa DITA e i modelli personalizzati. Per impostazione predefinita, i file modello vengono memorizzati nella seguente cartella in DAM:

`/content/dam/dita-templates/`

Per gestire i file degli argomenti e dei modelli di mapping, sono disponibili cartelle dedicate in cui sono memorizzati gli argomenti e i modelli di mapping. Per impostazione predefinita, tutti i modelli di argomento sono memorizzati nel `/content/dam/dita-templates/topics`

cartella. Tutti i modelli di mappa sono memorizzati nel `/content/dam/dita-templates/maps` cartella.

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

1. Cerca e fai clic su *com.adobe.fmdita.config.ConfigManager* pacchetto.

1. In **Posizione modelli** , specificare un percorso in cui memorizzare i modelli personalizzati.

1. Fai clic su **Salva**.


Se il percorso specificato esiste in DAM, tutti i modelli di mappa e argomenti predefiniti vengono copiati in tale cartella. Se il percorso non esiste, la cartella viene creata con tutti i modelli predefiniti per mappe e argomenti.

**Argomento padre:**[ Configurare modelli di argomenti e mappe](conf-template-tags.md)
