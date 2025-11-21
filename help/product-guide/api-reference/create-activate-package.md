---
title: API REST per la creazione e l’attivazione dei pacchetti
description: Scopri l’API REST per la creazione e l’attivazione dei pacchetti
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# API REST per la creazione e l’attivazione dei pacchetti {#id198CF0260Y4}

La seguente API REST consente di creare e attivare pacchetti CRX.

## Creare e attivare il pacchetto

Un metodo POST che crea e attiva il pacchetto CRX.

**URL richiesta**:
http://*&lt;server-guide-aem\>*: *&lt;numero-porta\>*/bin/fmdita/activate

**Parametri**:
La query della richiesta è costituita dalla stringa delle regole JSON. Il tipo di contenuto della richiesta POST deve essere `application/json; charset=UTF-8`.

**Esempio**:
L’esempio seguente mostra la chiamata API utilizzando il comando curl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Parametro facoltativo**

`activationTarget`

**Valori validi**

`preview` o `publish` per Cloud Service e `publish` per il software locale

- Per Cloud Service, se il parametro contiene un valore non valido, l’attivazione del pacchetto non riesce.

- Per il software locale, se il parametro contiene un valore non valido, l&#39;errore viene registrato e la pubblicazione viene eseguita utilizzando il valore predefinito `publish`.

Se non si definisce il parametro opzionale `activationTarget`, verrà attivato utilizzando l&#39;agente di pubblicazione predefinito sia per Cloud Service che per il software locale.



L’esempio seguente mostra la chiamata API utilizzando il comando curl con il parametro opzionale:


```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate?activationTarget=`<validActivationTargetValue>`
```
