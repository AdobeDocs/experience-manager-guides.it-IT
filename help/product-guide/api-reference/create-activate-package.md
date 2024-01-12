---
title: API REST per la creazione e l’attivazione dei pacchetti
description: Scopri l’API REST per la creazione e l’attivazione dei pacchetti
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# API REST per la creazione e l’attivazione dei pacchetti {#id198CF0260Y4}

La seguente API REST consente di creare e attivare pacchetti CRX.

## Creare e attivare il pacchetto

Metodo POST che crea e attiva il pacchetto CRX.

**URL richiesta**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/activate

**Parametri**: la query della richiesta è costituita dalla stringa di regole JSON. Il tipo di contenuto della richiesta POST deve essere impostato su `application/json; charset=UTF-8`.

**Esempio**: gli esempi seguenti mostrano la chiamata API utilizzando il comando curl:

    &quot;
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate
    &quot;
