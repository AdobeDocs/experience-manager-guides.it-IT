---
title: Escludere dalla traduzione i paragrafi di un argomento
description: Escludere i paragrafi di un argomento dalla traduzione
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '148'
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
