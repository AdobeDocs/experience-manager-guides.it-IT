---
title: Configura il mapping basato su JSON tra un argomento e un modello per frammenti di contenuto.
description: Scopri come configurare la mappatura basata su JSON tra un argomento e un modello per frammenti di contenuto.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Creare una mappatura tra un argomento e un frammento di contenuto per Cloud Service

Adobe Experience Manager Guides consente di creare una mappatura basata su JSON tra un argomento e un modello per frammenti di contenuto. Puoi utilizzare la mappatura basata su JSON per pubblicare su un frammento di contenuto il contenuto presente in alcuni o tutti gli elementi di un argomento.

>[!NOTE]
> 
> Se utilizzi le versioni 4.6 o successive, non è necessario creare questa mappatura, puoi trascinare gli elementi dell’argomento nei campi presenti nel modello per frammenti di contenuto.
> Scopri come [pubblicare frammenti di contenuto](../user-guide/publish-content-fragment.md).


1. Per scaricare *contentFragmentMapping.json*, accedi a Adobe Experience Manager come amministratore.
1. Seleziona il collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare Guide dall&#39;elenco degli strumenti e selezionare **Profili cartella**.
1. Selezionare il riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto.
1. Seleziona l&#39;icona **Scarica** per scaricare il file *contentFragmentMapping.json* nel sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.

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

È possibile pubblicare l&#39;intero argomento con la mappatura predefinita. Selezionare il mapping `Full Topic` dal menu a discesa **Genera frammento di contenuto** e inserire il campo &quot;topicData&quot; nel modello per frammenti di contenuto.
