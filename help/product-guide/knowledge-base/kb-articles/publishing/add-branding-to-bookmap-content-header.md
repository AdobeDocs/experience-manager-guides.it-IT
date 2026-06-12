---
title: Aggiungere il marchio Enterprise alla prima pagina di un PDF DITA
description: Ottieni il marchio dell’azienda integrando la pagina di copertina e la pagina del capitolo, garantendo che l’identità dell’azienda sia chiaramente visualizzata nella parte superiore del contenuto.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: ab452529-3c7f-4057-a0f6-212b9f52a99d
TQID: https://experienceleague.adobe.com/6CGRK2QWFZ6nIXmIAQZy3lX7t4KYP2-HeyqlVW2-7eE
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
source-wordcount: 422
ht-degree: 0%

---

# Aggiungere il marchio Enterprise alla prima pagina di un PDF DITA

## Questo articolo riguarda:

Ottenere il marchio Enterprise unendo perfettamente la pagina FrontCover con la pagina del capitolo, assicurando che l&#39;identità dell&#39;azienda venga visualizzata in primo piano nel contenuto.

- [Configura il contenuto](#set-up-your-content)
- [Apporta le modifiche necessarie nel modello PDF](#create-necessary-changes-in-pdf-template)

**Prima:**

![Prima di correggere il branding: schermata che mostra il layout PDF prebranded](../assets/publishing/branding-image1.png)
<br>
<br>

**Dopo:**

![Dopo aver corretto il branding: schermata che mostra il layout del PDF post-branding](../assets/publishing/branding-image2.png)

## Configura il contenuto

Per pubblicare il contenuto in formato PDF, è necessario creare una mappa digitale o una mappa.

Esempio di struttura Bookmap:

```
<bookmap>
  <title>My Bookmap Title </title>
  <frontmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <tablelist/>
    </booklists>
  </frontmatter>

  <chapter href="chapter1.ditamap">
  <chapter href="chapter2.ditamap">
  </chapter>

  <backmatter>
    <booklists>
      <indexlist/>
    </booklists>
  </backmatter>
</bookmap>
```

Esempio di struttura Ditamap:

```
<map title="My map Title">

  <topicref href="topic1.dita" >
  </topicref>
  <topicref href="topic2.dita">
  </topicref>
  
</map>
```

Il FrontCover di PDF viene generato automaticamente se Bookmap contiene `<frontmatter>`.


## Apporta le modifiche necessarie nel modello PDF

In questa sezione verrà configurato il modello. Per iniziare, puoi utilizzare o duplicare il modello Hi-tech.

### Configura il modello:

- Vai al modello di PDF nativo.
- Passare al layout di pagina di FrontCover e modificarlo.
- Aggiungere qui l&#39;immagine di branding in `data-region="content"`.
- Se necessario, aggiungi altre modifiche necessarie nel modello di capitolo.
- Ora segui i passaggi riportati di seguito in base al tuo contenuto.


#### Se utilizzi Ditamap per la generazione di PDF:

Quando si pubblica un DITAMAP, il PDF nativo fornisce la funzionalità per generare automaticamente una pagina FrontCover. L&#39;opzione per abilitare o disabilitare la generazione di pagine di FrontCover può essere configurata nel modello PDF nativo.

Per unire:
- Passa alle impostazioni del modello PDF nativo —> Ordine di layout pagina
- È ora possibile unire FrontCover alla pagina successiva, ad esempio Capitolo e argomenti.
  ![Unione di FrontCover con il capitolo: schermata che mostra le impostazioni del modello PDF nativo](../assets/publishing/branding-image3.png)
- Salva il modello, seleziona questo modello per il predefinito e pubblica.


#### Se utilizzi Bookmap per la generazione di PDF

Nel caso di un Bookmap, la sequenza dell&#39;ordine di layout della pagina è controllata dalla struttura del Bookmap anziché dall&#39;ordine del modello.

Per ottenere questo risultato per Bookmap , utilizzeremo la funzione JavaScript di NativePDF.

- Aggiungi sotto JavaScript nella cartella delle risorse del modello

```
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onAfterPagination(function () {
        var frontMatterWrappers = document.querySelectorAll('.rh-front-matter-wrapper');

        frontMatterWrappers.forEach(function(wrapper) {
            var contentDiv = wrapper.querySelector('div[data-region="content"]');
            var chapterBody = document.querySelector('.chapter-body');

            if (contentDiv && chapterBody) {
                chapterBody.insertBefore(contentDiv, chapterBody.firstChild);
            }

            wrapper.remove();
        });
    });
});
```

- Includi questo JavaScript nel modello del capitolo.
  ![Includi JavaScript nel modello di capitolo: schermata che mostra la voce nel modello di PDF di layout pagina](../assets/publishing/branding-image4.png)

- Abilita JavaScript dall’opzione predefinita
  ![Abilita impostazione predefinita JavaScript: schermata che mostra l&#39;impostazione predefinita per abilitare JavaScript](../assets/publishing/branding-image5.png)

- Pubblica!

## Allegati :

- [Scarica il pacchetto modello PDF di esempio per visualizzare le modifiche applicate.](../assets/publishing/NativePDF_DemoTemplate.zip)
- [Scarica il pacchetto di esempio del predefinito PDF per visualizzare le modifiche applicate.](../assets/publishing/Preset_Package.zip)


## Altre risorse:

- [Come includere il sommario di DITA Bookmap in PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Video di sessione degli esperti sul PDF nativo](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
