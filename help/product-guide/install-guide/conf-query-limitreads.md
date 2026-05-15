---
title: Configurare il numero di LimitReads per una query
description: Scopri come configurare il numero di LimitReads per una query
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/BwhrVPLcY4zw-pzB2wYGXnzBQHV2eFruoQnHWOE4F88
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 98
ht-degree: 2%

---

# Configurare il numero di LimitReads per una query {#id231RC0HL0ID}

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

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
