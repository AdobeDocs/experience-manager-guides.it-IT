---
title: Aggiungere caratteri personalizzati al PDF DITA
description: Ottieni l’integrazione dei font personalizzati per rafforzare l’identità del brand e la coerenza visiva in tutti i contenuti nei PDF DITA nativi.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: 151e3b1c-6340-4ff2-84d4-246bc4b68065
source-git-commit: 9c53ac725618db1164b0ed310a47b258a7224778
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Aggiungere caratteri personalizzati al PDF nativo DITA

## Questo articolo riguarda:

L’aggiunta di font personalizzati per rafforzare l’identità del brand e la coerenza visiva in tutti i contenuti.

Questo processo prevede 3 fasi:

- [Carica il font personalizzato](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Apportare le modifiche necessarie nel foglio di stile dei modelli di PDF](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Incorpora font usati (facoltativo)](#step-3-optional--embed-used-font-in-pdf)

## Passaggio 1: caricare il carattere personalizzato nella cartella delle risorse del modello

![Caricamento font personalizzato e importazione di ](../assets/publishing/custom-font1.png)

## Passaggio 2: apportare le modifiche necessarie nel foglio di stile dei modelli di PDF

![Carattere nel foglio di stile del modello di PDF ](../assets/publishing/custom-font2.png)

## Passaggio 3 (facoltativo): incorporare il tipo di carattere utilizzato in PDF

![Carattere personalizzato incorporato in DITA PDF ](../assets/publishing/custom-font3.png)

## Domande frequenti

### Posso utilizzare Adobe Fonts?

> Sì, vai su fonts.adobe.com e fai clic su &quot;Aggiungi a progetto web&quot;.
> 
> Copia il codice di importazione come `" @import url("https://use.typekit.net/xxxx.css")`;
>
> Incolla nel CSS del contenuto ed esegui le modifiche desiderate nel file CSS.

![Utilizza il tipo di carattere adobe in DITA PDF](../assets/publishing/custom-font4.png)


### Il carattere non è visualizzato in PDF

> Controlla l&#39;ortografia del nome del carattere (errore più comune)
>
> Assicurarsi di incorporare il carattere se i caratteri non sono disponibili nel sistema in cui è aperto PDF

## Per eventuali altre richieste, contatta i rispettivi CSM


## Altre risorse:

- [Come includere il sommario di DITA Bookmap in PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Come includere sommario nella pubblicazione PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Video della sessione di esperti sul PDF nativo](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
