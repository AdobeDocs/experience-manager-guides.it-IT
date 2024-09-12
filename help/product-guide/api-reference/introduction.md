---
title: Introduzione
description: Introduzione alla guida di riferimento API per AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: 9024b552fd470344ba7b0068a147c37084ae0d13
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%

---

# Introduzione {#id1761C0007W7}

Adobe Experience Manager Guides \(in seguito denominato *AEM Guides*\) è una soluzione aziendale end-to-end che consente a Adobe Experience Manager \(AEM\) di disporre delle funzionalità della soluzione di gestione dei contenuti dei componenti \(CCMS\) per la creazione e la distribuzione di contenuti basati su DITA. I clienti possono accedere ai flussi di lavoro di AEM Guides a livello di programmazione utilizzando le API di AEM Guides per integrarlo con altre applicazioni aziendali. Queste API possono essere utilizzate anche dai partner Adobe per migliorare la proposta di valore di AEM Guides estendendone le funzionalità o integrandola con altre applicazioni o servizi.

## API di AEM Guides

Le API di AEM Guides sono disponibili in due formati: HTTP e Java. Queste API espongono le funzioni chiave di AEM Guides agli sviluppatori di applicazioni. Utilizzando queste funzioni, gli sviluppatori possono creare i propri plug-in per estendere i flussi di lavoro preconfigurati. Le API sono disponibili per la gestione degli output per il contenuto DITA, l&#39;utilizzo delle mappe DITA, l&#39;aggiunta di attributi condizionali ai profili a livello di cartella e la conversione di documenti HTML e Words in formato DITA.

## Installazione dei JAR nell’archivio Apache Maven locale {#install-jar-local}

Per poter utilizzare i file JAR esposti da AEM Guides, devi installarli nell’archivio Apache Maven locale. Per installare i JAR nel percorso dell’archivio Maven, effettua le seguenti operazioni:

1. Estrai il contenuto del file del pacchetto AEM Guides \(.zip\) sul sistema locale.

2. Al prompt dei comandi passare alla cartella seguente nel percorso del contenuto estratto:

   ```
   \jcr_root\libs\fmdita\osgi-bundles\install
   ```

3. Esegui il seguente comando per installare il bundle API nell’archivio Maven locale:

   ```
   mvn install:install-file -Dfile=api-X.x.jar -DgroupId=com.adobe.fmdita -DartifactId=api -Dversion=X.x -Dpackaging=jar**
   ```

   >[!NOTE]
   >
   > Nel comando precedente, X.x deve essere sostituito con il numero di versione effettivo nei parametri Dfile e Dversion.

4. \(*Facoltativo*\) Installa la dipendenza nell’archivio del progetto Maven locale. Per ottenere questo risultato, crea una cartella nel progetto Maven ed esegui il comando `mvn install` fornito nel passaggio precedente con il seguente parametro aggiuntivo:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   Quindi, per esporre la cartella dell’archivio locale del progetto al processo di compilazione Maven, aggiungi un elemento `repository` nel file pom.xml padre come mostrato di seguito:

   ```XML
   <repositories>
      <repository>
         <id>project-repository</id>
         <url>file://${project.basedir}/repository</url>
      </repository>
   </repositories>
   ```


Questo processo installa i JAR API nell’archivio Maven locale.

## Utilizzo del JAR dell’API di servizio in un progetto Maven

Dopo aver installato i JAR API nell’archivio Maven locale, esegui i seguenti passaggi per utilizzare i JAR nei progetti:

1. Aggiungi il file JAR alla base di codice e esegui il commit nell’archivio della base di codice in una cartella, ad esempio &quot;dependencies&quot;. Il nome della cartella dipende dalla gerarchia della base di codice.

2. Configura i file pom.xml del progetto come segue:

   File pom.xml del progetto padre:

   >[!IMPORTANT]
   >
   > Nel seguente snippet di codice, X.x deve essere sostituito con il numero di versione effettivo e il nome del file JAR dell’API. Queste informazioni saranno le stesse fornite nel passaggio 3 del [processo di installazione](#install-jar-local).

   ```XML
   <plugin>
   
       <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
       <version>2.5.2</version>
   
       <configuration>
   
               <groupId>com.adobe.fmdita</groupId>
   
               <artifactId>api</artifactId>
   
               <version>X.x</version>
   
               <file>${basedir}/dependencies/fmdita/api-X.x.jar</file>
   
               <packaging>jar</packaging>
   
               <generatePom>true</generatePom>
   
       </configuration>
   
       <executions>
   
           <execution>
   
               <id>inst_fmdita</id>
   
                   <goals>
   
                       <goal>install-file</goal>
   
                   </goals>
   
                   <phase>clean</phase>
   
           </execution>
   
       </executions>
   </plugin>
   ```

   File pom.xml del modulo secondario:

   ```XML
   <plugin>
      <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
      <configuration>
   
         <groupId>com.adobe.fmdita</groupId>
   
         <artifactId>api</artifactId>
   
         <version>3.6</version>
   
         <file>${basedir}/../dependencies/fmdita/api-3.6.jar</file>
   
         <packaging>jar</packaging>
   
         <generatePom>true</generatePom>
   
      </configuration>
   
      <executions>
   
         <execution>
   
            <id>inst_fmdita</id>
   
            <goals>
   
               <goal>install-file</goal>
   
            </goals>
   
            <phase>clean</phase>
   
         </execution>
   
      </executions>
   
   </plugin>
   ```


## Configurare e utilizzare il servizio API JAR dall’archivio Maven pubblico

Per configurare e utilizzare i JAR dell’API del servizio dall’archivio Maven pubblico nei progetti, effettua le seguenti operazioni:

1. Per utilizzare il file JAR dell’API di servizio in un progetto, configura l’archivio Maven pubblico di AEM Guides nel file pom.xml.
2. Configura l’archivio Maven pubblico nel file settings.xml di Maven come segue:

   ```XML
   <repository>
      <id>fmdita-public</id>
      <name>fmdita-public</name>
      <url>https://repo.aem-guides.com/repository/fmdita-public</url>
   </repository>
   ```

3. Una volta configurato l’archivio, aggiungi il JAR dell’API del servizio come dipendenza dal progetto nel file pom.xml del progetto.

   >[!NOTE]
   >
   > Utilizza la stessa versione del JAR API del pacchetto AEM Guides installato sul server.

4. Configura la dipendenza Maven come mostrato di seguito:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


Una volta aggiunto il file JAR dell’API di servizio come dipendenza dal progetto nel file pom.xml del progetto, puoi creare e utilizzare le API Java di AEM Guides nel progetto.

## Utilizzo di API JAR dall’archivio centrale Maven per AEM Guides as a Cloud Service

Per AEM Guides as a Cloud Service, il file JAR dell’API è stato distribuito a Maven Central. Puoi utilizzare il file JAR dell’API senza alcuna configurazione.

>[!NOTE]
>
> La convenzione di denominazione del file jar dell’API è stata aggiornata in base alla convenzione di denominazione dei componenti aggiuntivi per cloud.

Per utilizzare il file JAR API, devi aggiungere la dipendenza al pom.xml del progetto come mostrato di seguito:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-guides-sdk-api</artifactId>
   <version>2022.5</version>
</dependency>
```

>[!NOTE]
>
> Poiché i pacchetti all’interno del JAR API sono ancora gli stessi, non è necessaria alcuna modifica del codice per utilizzare questo JAR API nei progetti cloud esistenti.

### API basate su Java

Puoi utilizzare le API basate su Java disponibili in Experience Manager Guides per creare plug-in personalizzati ed estendere flussi di lavoro preconfigurati. Visualizza [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) per la documentazione più recente e dettagliata sull&#39;utilizzo dell&#39;API basata su Java.



## Risorse aggiuntive

Di seguito è riportato un elenco di altre utili risorse di AEM Guides, disponibili nella pagina [Informazioni e supporto](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html):

- Guida utente
- Guida all’installazione e alla configurazione
- Guida rapida
- [Pagina di archiviazione della Guida](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(accedere alla documentazione delle versioni precedenti\)
