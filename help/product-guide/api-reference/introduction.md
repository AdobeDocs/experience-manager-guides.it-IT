---
title: Introduzione
description: Introduzione alla guida di riferimento API per le guide AEM
role: Developer
feature: Introduction
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
source-git-commit: 26d0b3fd6b6d34fb2a86417179c8be672d40ad86
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---

# Introduzione {#id1761C0007W7}

Guide di Adobe Experience Manager \(in seguito denominate *Guide AEM*\) è una soluzione aziendale end-to-end che consente a Adobe Experience Manager \(AEM\) di disporre delle funzionalità della soluzione di gestione dei contenuti dei componenti \(CCMS\) per la creazione e la distribuzione di contenuti basati su DITA. I clienti possono accedere ai flussi di lavoro delle guide AEM a livello di programmazione utilizzando le API delle guide AEM per integrarle con altre applicazioni aziendali. Queste API possono essere utilizzate anche dai partner Adobi per migliorare la proposta di valore delle guide AEM estendendone le funzionalità o integrandole con altre applicazioni o servizi.

## API delle guide AEM

Le API delle guide dell’AEM sono disponibili in due formati: HTTP e Java. Queste API espongono le funzioni chiave delle guide AEM agli sviluppatori di applicazioni. Utilizzando queste funzioni, gli sviluppatori possono creare i propri plug-in per estendere i flussi di lavoro preconfigurati. Le API sono disponibili per la gestione degli output per il contenuto DITA, l&#39;utilizzo delle mappe DITA, l&#39;aggiunta di attributi condizionali ai profili a livello di cartella e la conversione di documenti HTML e Words in formato DITA.

## Installazione dei JAR nell’archivio Apache Maven locale {#install-jar-local}

Per poter utilizzare i file JAR esposti dalle guide AEM, devi installarli nell’archivio Apache Maven locale. Per installare i JAR nel percorso dell’archivio Maven, effettua le seguenti operazioni:

1. Estrai il contenuto del file \(.zip\) del pacchetto Guide AEM sul sistema locale.

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

4. \(*Facoltativo*\) Installa la dipendenza nell’archivio del progetto Maven locale. Per farlo, crea una cartella nel progetto Maven ed esegui il comando `mvn install` comando fornito nel passaggio precedente con il seguente parametro aggiuntivo:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   Quindi, per esporre la cartella dell’archivio locale del progetto al processo di build Maven, aggiungi una `repository` nel file pom.xml padre come illustrato di seguito:

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
   > Nel seguente snippet di codice, X.x deve essere sostituito con il numero di versione effettivo e il nome del file JAR dell’API. Queste informazioni sono identiche a quelle fornite nel passaggio 3 della [processo di installazione](#install-jar-local).

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

1. Per utilizzare il file JAR dell’API di servizio in un progetto, configura l’archivio Maven pubblico delle guide AEM nel file pom.xml.
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
   > Utilizza la stessa versione del JAR API del pacchetto Guide AEM installato sul server.

4. Configura la dipendenza Maven come mostrato di seguito:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


Una volta aggiunto il file JAR dell’API di servizio come dipendenza dal progetto nel file pom.xml del progetto, puoi creare e utilizzare le API Java delle guide AEM nel progetto.

## Utilizzo di API JAR dall’archivio centrale Maven per guide AEM as a Cloud Service

Per le guide AEM as a Cloud Service, il file JAR dell’API è stato distribuito in Maven Central. Puoi utilizzare il file JAR dell’API senza alcuna configurazione.

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

## Risorse aggiuntive

Di seguito è riportato un elenco di altre utili risorse delle Guide dell’AEM, disponibili sul sito [Informazioni e supporto](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) pagina:

- Guida utente
- Guida all’installazione e alla configurazione
- Guida rapida
- [Pagina Archiviazione della Guida](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(accedere alla documentazione sulle versioni precedenti\)
