---
title: Configura il mapping basato su JSON tra un argomento e un modello per frammenti di contenuto.
description: Scopri come configurare la mappatura basata su JSON tra un argomento e un modello per frammenti di contenuto.
exl-id: 438e2964-b9c7-462a-a68c-8031bd97911c
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/w1XQiP79ta2-huLRGIdevylhP7VCYvmmOQVpQgI7w4w
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 275
ht-degree: 0%

---

# Creare una mappatura tra un argomento e un frammento di contenuto



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
