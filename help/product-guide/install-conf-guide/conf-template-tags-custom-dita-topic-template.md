---
title: Configura modello di argomento DITA personalizzato
description: Scopri come configurare un modello di argomento DITA personalizzato
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '488'
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

1. [Creare un modello di authoring personalizzato](conf-profiles.md#id1917D0EG0HJ)

1. Aggiungi un modello personalizzato al profilo globale o a livello di cartella come descritto nella sezione [Configurare i modelli di authoring](conf-profiles.md#id1889D0IL0Y4)


## Configura percorso cartella modello DITA personalizzato {#id191LCF0095Z}

AEM Guides consente di configurare una cartella in cui memorizzare la mappa DITA e i modelli personalizzati. Per impostazione predefinita, i file modello vengono memorizzati nella seguente cartella in DAM:

`/content/dam/dita-templates/`

Per gestire i file degli argomenti e dei modelli di mapping, sono disponibili cartelle dedicate in cui sono memorizzati gli argomenti e i modelli di mapping. Per impostazione predefinita, tutti i modelli di argomento sono archiviati in `/content/dam/dita-templates/topics`

cartella. Tutti i modelli di mappa sono archiviati nella cartella `/content/dam/dita-templates/maps`.

In qualità di amministratore, puoi scegliere di creare modelli di mappe o argomenti personalizzati nella cartella predefinita o di creare una cartella personalizzata in cui memorizzare i modelli personalizzati. Se prevedi di utilizzare la cartella predefinita, puoi saltare questo processo.

Le schede seguenti forniscono istruzioni per configurare il percorso della cartella del modello DITA personalizzato in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornire i dettagli \(property\) seguenti per configurare una cartella per i modelli di argomento DITA personalizzati:

>[!IMPORTANT]
>
> Puoi saltare questo processo se desideri utilizzare la cartella predefinita per memorizzare i modelli personalizzati.

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Specifica un percorso in cui memorizzare i modelli personalizzati.<br> Se il percorso specificato esiste in DAM, tutti i modelli di mapping e argomenti predefiniti vengono copiati in tale cartella. Se il percorso non esiste, la cartella viene creata con tutti i modelli predefiniti per mappe e argomenti. |

>[!TAB On-Premise]

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


>[!ENDTABS]


**Argomento padre:**[ Configura modelli di argomento e mappa](conf-template-tags.md)
