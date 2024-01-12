---
title: Configura il mapping basato su JSON tra un argomento e un modello per frammenti di contenuto.
description: Scopri come configurare la mappatura basata su JSON tra un argomento e un modello per frammenti di contenuto.
exl-id: 21446bcb-e7df-4823-acc3-1fdc7473f0d1
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Creare una mappatura tra un argomento e un frammento di contenuto

Le guide AEM consentono di creare una mappatura basata su JSON tra un argomento e un modello per frammenti di contenuto. Puoi utilizzare questa mappatura per pubblicare su un frammento di contenuto il contenuto presente in alcuni o tutti gli elementi di un argomento.

1. Per scaricare *contentFragmentMapping.json*, accedi a Adobe Experience Manager come amministratore.
1. Seleziona il collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare Guide dall&#39;elenco degli strumenti e selezionare **Profili cartella**.
1. Seleziona la **Profilo globale** affiancare.
1. Seleziona la **Configurazione editor XML** e seleziona la scheda **Modifica** nella parte superiore.
1. Seleziona la **Scarica** per scaricare *contentFragmentMapping.json*  sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.

1. Devi seguire le seguenti convalide:

   1. Deve essere un file JSON
   2. Deve contenere una matrice contenente almeno un oggetto e ogni oggetto deve contenere quanto segue:


      `"name": string `

      `"mapping": array`

      Ogni oggetto di mappatura deve contenere i seguenti elementi:

      `"modelField": string`

      `"xpath": string`

      `"outputType": string`
1. Salva il file e caricalo.

File di esempio:

```
[
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "topicData",
        "xpath": "/topic[1]/body[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Full Topic"
  },
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "heroImage",
        "xpath": "/topic[1]/body[1]/p[1]/image[1]",
        "outputType": "outerHTML"
      },
      {
        "modelField": "dataTable",
        "xpath": "/topic[1]/body[1]/table[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Sample Example with XPath"
  }
]
```

È possibile pubblicare l&#39;intero argomento con la mappatura predefinita. Seleziona la `Full Topic` mappatura dal menu a discesa nella **Pubblica come frammento di contenuto** e avere il campo &quot;topicData&quot; nel modello per frammenti di contenuto.
