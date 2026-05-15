---
title: Aggiungere caratteri personalizzati al PDF DITA
description: Ottieni l’integrazione dei font personalizzati per rafforzare l’identità del brand e la coerenza visiva in tutti i contenuti nei PDF DITA nativi.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: 151e3b1c-6340-4ff2-84d4-246bc4b68065
TQID: https://experienceleague.adobe.com/xqr9eYA2XTcyXL8X4aS-Wu2-FmU8-aCWDpb-L2BBFqI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 223
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

![Caricamento font personalizzato e importazione di &#x200B;](../assets/publishing/custom-font1.png)

## Passaggio 2: apportare le modifiche necessarie nel foglio di stile dei modelli di PDF

![Carattere nel foglio di stile del modello di PDF &#x200B;](../assets/publishing/custom-font2.png)

## Passaggio 3 (facoltativo): incorporare il tipo di carattere utilizzato in PDF

![Carattere personalizzato incorporato in DITA PDF &#x200B;](../assets/publishing/custom-font3.png)

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
