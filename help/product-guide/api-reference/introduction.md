---
title: Introduzione
description: Introduzione alla guida di riferimento API per AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/dNO8nZusaPCor506Q-2drrcJGf68mx-Hxo4uaT-cDtM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f3645292-50bd-4f4a-ac6a-29dcecdf8abe
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 656
ht-degree: 0%

---

# Introduzione {#id1761C0007W7}

Adobe Experience Manager Guides \(in seguito denominato *AEM Guides*\) è una soluzione aziendale end-to-end che consente a Adobe Experience Manager \(AEM\) di disporre delle funzionalità della soluzione di gestione dei contenuti dei componenti \(CCMS\) per la creazione e la distribuzione di contenuti basati su DITA. I clienti possono accedere ai flussi di lavoro di AEM Guides a livello di programmazione utilizzando le API di AEM Guides per integrarlo con altre applicazioni aziendali. Queste API possono essere utilizzate anche dai partner Adobe per migliorare la value proposition di AEM Guides estendendone le funzionalità o integrandola con altre applicazioni o servizi.

## API di AEM Guides

Le API di AEM Guides sono disponibili in due formati:

- [API basate su Java](#java-based-apis)
- [API basate su REST](#rest-based-apis)

Queste API espongono le funzioni chiave di AEM Guides agli sviluppatori di applicazioni. Utilizzando queste funzioni, gli sviluppatori possono creare i propri plug-in per estendere i flussi di lavoro preconfigurati. Le API sono disponibili per la gestione degli output per il contenuto DITA, l&#39;utilizzo delle mappe DITA, l&#39;aggiunta di attributi condizionali ai profili a livello di cartella e la conversione di documenti HTML e Words in formato DITA.


### API basate su Java

Puoi utilizzare le API basate su Java disponibili in Experience Manager Guides per creare plug-in personalizzati ed estendere flussi di lavoro preconfigurati.

**Configura SDK dall&#39;archivio centrale Maven per AEM Guides as a Cloud Service**

>[!INFO]
>
>Visualizza [![javadoc](./images/javadoc-cs-icon.svg)](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) per la documentazione più recente e dettagliata sull&#39;utilizzo dell&#39;API basata su Java per Experience Manager Guides as a Cloud Service.

Per configurare e utilizzare i file JAR dell&#39;API di servizio dall&#39;archivio Maven nei progetti, aggiungi l&#39;API SDK come dipendenza dal progetto nel file `pom.xml` del progetto, come illustrato di seguito.

```XML
<dependency>
<groupId>com.adobe.aem</groupId>
<artifactId>aem-dox-sdk-api</artifactId>
<version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Assicurati di utilizzare la stessa versione del JAR API del pacchetto AEM Guides installato sul server.

**Configura e utilizza l&#39;API JAR dall&#39;archivio centrale Maven (on-premise)**

>[!INFO]
>
>Visualizza [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) per la documentazione più recente e dettagliata sull&#39;utilizzo dell&#39;API basata su Java per la configurazione on-premise di Experience Manager Guides.

Per configurare e utilizzare i file JAR delle API di servizio per le distribuzioni on-premise, aggiungi il file JAR delle API di servizio come dipendenza dal progetto nel file `pom.xml` del progetto, come illustrato di seguito:

```XML
<dependency>
<groupId>com.adobe.aem</groupId>
<artifactId>aem-guides-sdk-api</artifactId>
<version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Assicurati di utilizzare la stessa versione del JAR API del pacchetto AEM Guides installato sul server.


**Configura e utilizza l&#39;API JAR dall&#39;archivio Maven pubblico di AEM Guides (on-premise)**

>[!NOTE]
>
> L’archivio Maven pubblico di AEM Guides diventerà obsoleto dopo la versione 5.3.0 di Experience Manager Guides. Il file JAR dell’API sarà successivamente disponibile solo nell’archivio centrale Maven.

Per utilizzare i JAR dell’API di servizio dall’archivio Maven pubblico, effettua le seguenti operazioni:

1. Configura l&#39;archivio Maven pubblico di AEM Guides nel file `pom.xml` o `settings.xml` come mostrato di seguito:

   ```XML
   <repository>
       <id>fmdita-public</id>
       <name>fmdita-public</name>
       <url>https://repo.aem-guides.com/repository/fmdita-public</url>
    </repository>
   ```

1. Una volta configurato l&#39;archivio, aggiungere il file JAR dell&#39;API di servizio come dipendenza dal progetto nel file `pom.xml` del progetto.

   ```XML
   <dependency>
       <groupId>com.adobe.fmdita</groupId>
       <artifactId>api</artifactId>
       <version>${RELEASE}</version>
   </dependency>
   ```

   >[!NOTE]
   >
   > Utilizza la stessa versione del JAR API del pacchetto AEM Guides installato sul server.

Una volta aggiunto il file JAR dell&#39;API di servizio come dipendenza del progetto nel file `pom.xml` del progetto, puoi generare e utilizzare le API Java di AEM Guides nel progetto.


### API basate su REST

Experience Manager Guides fornisce un set completo di API basate su REST che consentono agli sviluppatori di accedere e interagire con le funzionalità di base tramite HTTP.

Queste API sono ideali per:

- Integrazione di Experience Manager Guides con altri sistemi aziendali
- Automazione dei flussi di lavoro di pubblicazione e revisione
- Creazione di applicazioni ed estensioni personalizzate

Per informazioni dettagliate sull&#39;utilizzo delle API, sui parametri e sulle richieste di esempio, consulta gli argomenti pertinenti nella sezione **Riferimento API** della documentazione di Experience Manager Guides.

## Risorse aggiuntive

Di seguito è riportato un elenco di altre utili risorse di AEM Guides, disponibili nella pagina [Informazioni e supporto](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html):

- Guida utente
- Guida all’installazione e alla configurazione
- Guida rapida
- [Pagina di archiviazione della Guida](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(accedere alla documentazione delle versioni precedenti\)
