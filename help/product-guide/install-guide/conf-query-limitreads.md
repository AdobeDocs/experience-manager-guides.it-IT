---
title: Configurare il numero di LimitReads per una query
description: Scopri come configurare il numero di LimitReads per una query
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 2%

---

# Configurare il numero di LimitReads per una query {#id231RC0HL0ID}

Per aumentare il numero di nodi che una query può leggere alla volta, eseguire la procedura seguente:

1. Apri la pagina JMX della console web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Cerca e fai clic su **ImpostazioniMotoreQuery**.

1. Modifica il valore dell’attributo per **LimitReads** attributo.

1. Fai clic su **Salva**.


Quando si aumenta il valore di questo attributo, è possibile generare il report per mappe DITA più grandi.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
