---
title: Escludere dalla traduzione i paragrafi di un argomento
description: Escludere i paragrafi di un argomento dalla traduzione
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
TQID: https://experienceleague.adobe.com/IAY5PLpWlHEpMygjmHI-BqS75-VqAU5x1o9mdiu4Aac
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 0%

---

# Escludere i paragrafi di un argomento dalla traduzione

Il modo più semplice è utilizzare translation=no attribute.

+ Gli autori possono inserire l&#39;attributo aggiuntivo come **translation=no** nei paragrafi che non desiderano tradurre. Il fornitore di traduzione deve essere informato e può eseguire la configurazione alla sua fine per ignorare il testo con questo attributo.
+ La traduzione automatica OOTB (con connettore di traduzione Microsoft di prova) presenta lo stesso comportamento.
+ Test con Microsoft Translation : se definisci l&#39;attributo **translate=no** a livello di paragrafo, il paragrafo completo non viene tradotto. Questo attributo può essere definito in qualsiasi elemento e il contenuto all’interno di tale elemento non verrà tradotto.


Ecco alcune schermate che lo spiegano ulteriormente:

**Contenuto Source**

![Contenuto Source](assets/source-content.jpg)

**Contenuto tradotto in spagnolo**

![Contenuto tradotto in spagnolo](assets/trans-content.jpg)
