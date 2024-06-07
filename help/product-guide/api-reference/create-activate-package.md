---
title: API REST per la creazione e l'attivazione di pacchetti
description: Scopri informazioni sull'API REST per la creazione e l'attivazione di pacchetti
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: b95a64ca2e8ebffebec3d8ff8704f76f7faceca2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# API REST per la creazione e l&#39;attivazione di pacchetti {#id198CF0260Y4}

La seguente API REST permette di creare e attivare pacchetti CRX.

## Crea e attiva il pacchetto

Un metodo POST che crea e attiva il pacchetto CRX.

**Richiesta URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/activate&lt;/port-number\>&lt;/aem-guides-server\>

**Parametri**:
La query richiesta è costituita dalla stringa delle regole JSON. Il tipo di contenuto del richiesta POST deve essere impostato su `application/json; charset=UTF-8`.

**Esempio**:
L&#39;esempio seguente mostra la chiamata API utilizzando il comando curl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Parametro facoltativo**

`activationTarget`

**Valori validi**

`preview` oppure `publish` per Cloud Service e `publish` per software on-premise

- Ad Cloud Service, se il parametro contiene un valore non valido, l&#39;attivazione del pacchetto non riesce.

- Per il software locale, se il parametro contiene un valore non valido, l&#39;errore viene registrato e la pubblicazione viene eseguita utilizzando il valore predefinito, `publish`.

Se non si definisce il parametro facoltativo, `activationTarget`, viene attivato utilizzando l&#39;agente pubblicare predefinito sia per il software Cloud Service che per il software locale.



L&#39;esempio seguente mostra la chiamata API utilizzando il comando curl con parametro opzionale:


    &#39;&#39;&#39;XML
    
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: applicazione/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate?activationTarget=&#39;&lt;validActivationTargetValue>&#39;&#39;
    &#39;
&lt;/validActivationTargetValue>&lt;/*port-number*>&lt;/*aem-guides-server*>&lt;/*password*>&lt;/*username*>&#39;