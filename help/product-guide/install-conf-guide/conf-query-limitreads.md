---
title: Configurare il numero di LimitReads per una query
description: Scopri come configurare il numero di LimitReads per una query
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 53748636-f3d1-4b3b-a772-2730b78741cb
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 2%

---

# Configurare il numero di LimitReads per una query per On-Premise

Per aumentare il numero di nodi che una query può leggere alla volta, eseguire la procedura seguente:

1. Apri la pagina JMX della console web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Cerca e fai clic su **QueryEngineSettings**.

1. Modifica il valore dell&#39;attributo **LimitReads**.

1. Fai clic su **Salva**.


Quando si aumenta il valore di questo attributo, è possibile generare il report per mappe DITA più grandi.

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor](customize-overview.md)
