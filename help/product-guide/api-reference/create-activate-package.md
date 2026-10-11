---
title: API REST per la creazione e l’attivazione dei pacchetti
description: Scopri l’API REST per la creazione e l’attivazione dei pacchetti
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/cJUVS3QdzVhnZjFF7uoHfpOSBefgm5W2jh-kWM1PvmE'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: fc9467a9-8572-4512-95c7-e18f4488202b
    internal-label: REST API Packages
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '181'
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
