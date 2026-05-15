---
title: Supporto di Schematron nell’editor web
description: Utilizzo di Schematron nell’editor web
exl-id: 3e61432f-d81e-446e-b0ad-560f5b9fa91a
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/gF-ylj-r-PDXduhUU-60-hiJ4UaYEdsCYTaCIyUiT0s
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 0%

---

# Controllo della qualità dei contenuti nell’editor web

Questo articolo offre una panoramica delle possibilità di convalida nell’editor web di AEM Guides.
Per progettazione, l&#39;editor Web sfrutta l&#39;impostazione dello schema DITA nel sistema per imporre agli utenti di creare contenuto compatibile con DITA. In questo modo, tutto il contenuto memorizzato nel sistema è strutturato, riutilizzabile e valido.

Oltre al supporto per le regole DITA, Web-editor supporta anche la convalida del contenuto in base alle regole &quot;*Schematron*&quot;.

&quot;*Schematron*&quot; fa riferimento a un linguaggio di convalida basato su regole utilizzato per definire test per un file XML. Potete importare i file Schematron e modificarli nell&#39;Editor Web. Utilizzando un file &quot;Schematron&quot; è possibile definire determinate regole e quindi convalidarle per un argomento DITA o una mappa. Le regole di schema possono garantire la coerenza della struttura XML imponendo restrizioni definite come regole. Tali restrizioni sono dettate dalle PMI proprietarie della qualità e della coerenza dei contenuti.

NOTA: l&#39;editor Web supporta ISO Schematron.


## Conoscenza del funzionamento di &quot;Schematron&quot; nell’editor web

### Configurazione delle regole di Schematron

Consulta la sezione &quot;Supporto per i file Schematron&quot; nella [Guida utente](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=148)


### Applica regole di convalida al salvataggio dei file

Le impostazioni dell’editor web consentono agli utenti avanzati di impostare regole/file Schematron che verranno eseguiti ogni volta che un utente aggiorna il contenuto. Per ulteriori dettagli fare riferimento alla sezione &quot;Convalida&quot; nella [Guida utente](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=58)

![Imposta regole da impostazioni editor Web](../../../assets/authoring/schematron-editorsettings-validation-tab.png)


### È possibile eseguire la convalida manualmente?

Sì, come autore/utente durante la creazione di contenuti puoi utilizzare il pannello Schematron nell’editor web per caricare un file schematron ed eseguire convalide sul file aperto nell’editor.

Affinché ciò funzioni, l&#39;amministratore del profilo di cartella deve consentire a tutti gli utenti di aggiungere file Schemtron nel pannello Convalida. Vedi le impostazioni dell’editor (schermata data sopra)

![Scegli il file di schema](../../../assets/authoring/schematron-rightpanel-validation-addsch.png)
![Esegui convalida](../../../assets/authoring/schematron-rightpanel-validation-runsch.png)


### Regole supportate

La versione corrente di AEM Guides supporta la convalida utilizzando solo le regole basate su &quot;Asserzioni&quot;. (vedi [risorsa vs report](https://schematron.com/document/205.html))
Eventuali regole basate su &quot;Rapporti&quot; non sono ancora supportate.


### Esempi e ulteriori informazioni sulle regole di Schematron

#### Casi d’uso di esempio

- Controlla se un collegamento è esterno e se ha ambito &quot;esterno&quot;

  ```
  <sch:pattern>
      <sch:rule context="xref[contains(@href, 'http') or contains(@href, 'https')]">
          <sch:assert test="@scope = 'external' and @format = 'html'">
              All external xref links must be with scope='external' and format='html'
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- Controlla se c&#39;è almeno un &quot;topicref&quot; in una mappa o almeno un &quot;li&quot; sotto un &quot;ul&quot;

  ```
  <sch:pattern>
      <sch:rule context="map">
          <sch:assert test="count(topicref) > 0">
              There should be atleast one topicref in map
          </sch:assert>
      </sch:rule>
  
      <sch:rule context="ul">
          <sch:assert test="count(li) > 1" >
              A list must have more than one item.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- L’elemento &quot;indexterm&quot; deve essere sempre presente in un &quot;prologo&quot;

  ```
  <sch:pattern>
      <sch:rule context="*[contains(@class, ' topic/indexterm ')]">
          <sch:assert test="ancestor::node()/local-name() = 'prolog'">
              The indexterm element should be in a prolog.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

#### Risorse

- Nozioni di base su [Schematron](https://da2022.xatapult.com/#what-is-schematron)
- Ulteriori informazioni sulle [regole di asserzione in Schematron](https://www.xml.com/pub/a/2003/11/12/schematron.html#Assertions)
- [File di schema di esempio](../../../assets/authoring/sample_schematron.sch)
