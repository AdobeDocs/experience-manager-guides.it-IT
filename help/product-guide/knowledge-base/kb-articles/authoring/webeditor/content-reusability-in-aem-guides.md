---
title: Riutilizzo di contenuti DITA nelle guide AEM
description: Questo breve articolo spiega come le guide AEM e DITA consentono di risparmiare tempo e fatica quando si utilizza la riutilizzabilità dei contenuti
role: User, Admin
source-git-commit: 6ff99d32dd7a30c1104a79da4f223defe109f190
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# Riutilizzabilità dei contenuti nelle guide AEM

Adobe Le guide all’AEM sfruttano i punti di forza di DITA per fornire un’interfaccia intuitiva per il riutilizzo dei contenuti.

## Riutilizzabilità tramite riferimenti argomento (topicref)



Supponiamo che tu sia un&#39;azienda di produzione e che abbia argomenti generici sulle precauzioni di sicurezza o sulle tecniche per la risoluzione dei problemi.

Questi possono essere indicati e adattati in specifici manuali d&#39;uso per ciascun modello di macchina, riducendo la ridondanza e garantendo che le informazioni di sicurezza principali rimangano coerenti.

```
<map id="user_manual_model 100" title="ABC Model 100 User Manual ">


<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
</map>
```


Analogamente per il modello 200

```
<map id="user_manual_model 200" title="ABC Model 200 User Manual ">

<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
  
</map>
```

## Riutilizzabilità utilizzando riferimento contenuto (conref e conkeyref)

L’attributo riferimento contenuto (conref) ti consente di collegare ad altre parti del contenuto. In questo modo si favorisce il riutilizzo e si riduce la ridondanza.

Ad esempio:

Supponiamo che tu sia un&#39;azienda finanziaria e abbia un argomento generico per KYC che contiene procedure KYC per singoli utenti, aziende e così via.

Desideri riutilizzare i singoli frammenti KYC per gli argomenti &quot;Salvataggio account&quot; e &quot;Account demat&quot;.

```
<section id="kyc_requirements_saving_account">
  <title>Know Your Customer (KYC) Requirements</title>
  <p>To comply with regulations and ensure customer identification, all individual applicants for savings  accounts must fulfill the KYC requirements as outlined below</p>
  <p conref=kyc_procedures.dita#individual_kyc></p>
</section>
```

Qui `conref=kyc_procedures.dita#indvidual_kyc` kyc_procedures.dita è l’identificatore del file e #individual_kyc è l’identificatore del frammento.

Kyc_procedure.dita continua a essere l&#39;unica fonte singola di informazioni. Se sono presenti modifiche al processo KYC come richiesto dalle normative, è sufficiente aggiornare un argomento e tali modifiche vengono automaticamente riportate in tutti gli argomenti che vi fanno riferimento.

Utilizzando le guide AEM, i suoi due clic

Passaggio 1: fare clic su Inserisci contenuto riutilizzabile
![barra strumenti](../../assets/publishing/content-reusability_image1.png)

<br>

Passaggio 2: seleziona il file e il frammento che devono essere riutilizzati.
![conref](../../assets/publishing/content-reusability_image2.png)

Simile a &quot;conref&quot;, puoi utilizzare anche &quot;conkeyref&quot; dove invece di fornire un percorso di contenuto, puoi fare riferimento al contenuto tramite i tasti.

Esempio di codice:

```
<section conkeyref="kyc_procedure/individual_kyc_procedure" id="individual_kyc_procedure"></section>
```

La definizione della chiave è simile alla seguente:

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2020.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Chiave - &quot;Kyc_procedure&quot; continuerà ad essere l&#39;unica fonte di informazioni. Se vengono apportate modifiche al processo KYC come richiesto dalle normative, è sufficiente aggiornare un percorso argomento con un nuovo percorso argomento, che verrà automaticamente riportato in tutti gli argomenti che vi fanno riferimento.

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2024.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

In questo caso il percorso dell&#39;argomento viene modificato da &quot;kyc_procedure_2020.dita&quot; a &quot;kyc_procedure_2024.dita&quot; a causa di recenti modifiche alle normative.

Utilizzando le guide AEM, i suoi due clic

Passaggio 1: fare clic su Inserisci contenuto riutilizzabile
![barra strumenti](../../assets/publishing/content-reusability_image1.png)

Passaggio 2: seleziona la mappa principale (opzionale), la chiave e il frammento da riutilizzare.
![conkeyref](../../assets/publishing/content-reusability_image3.png)

La mappa principale qui è stata selezionata automaticamente perché era già aperta nella vista mappa


### Riutilizzare i contenuti con un solo clic nelle guide AEM

Le guide AEM offrono la funzionalità &quot;Contenuti riutilizzabili&quot; per aggiungere riferimenti ai contenuti con un solo clic.

Passaggio 1: aggiungere un argomento generico al contenuto riutilizzabile

![Aggiungi contenuto riutilizzabile](../../assets/publishing/content-reusability_image4.png)

Passaggio 2: una volta aggiunto, trascina e rilascia il frammento che desideri riutilizzare negli argomenti di destinazione.

![Aggiungi GIF di contenuto riutilizzabile](../../assets/publishing/content-reusability_image5.gif)



## Domande frequenti

- ### Non viene visualizzato tutto il contenuto dopo la selezione del file o della chiave nella finestra di dialogo Riutilizza contenuto

È necessario assegnare gli ID ai frammenti (elementi Dita ) che si desidera riutilizzare in altri argomenti

- ## Le chiavi non vengono visualizzate nella finestra di dialogo Riutilizza contenuto

Assicurati di aver aperto la mappa principale/mappa principale nella vista mappa che ha una definizione di chiave oppure aggiungi manualmente il percorso della mappa principale nella stessa finestra di dialogo.


<br>


Post sulla community dei guide dell’AEM [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) per qualsiasi query.

