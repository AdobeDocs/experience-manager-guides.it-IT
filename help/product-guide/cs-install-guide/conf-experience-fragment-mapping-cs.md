---
title: Configura il mapping basato su JSON tra un argomento e un modello di Frammento di esperienza.
description: Scopri come configurare la mappatura basata su JSON tra un argomento e un modello di Frammento di esperienza.
feature: Output Generation
role: Admin
level: Experienced
exl-id: 2b59db60-61b5-4a7e-bbf1-35cab8b89323
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Creare una mappatura tra un argomento e un frammento di esperienza

Adobe Experience Manager Guides fornisce la funzione di creare una mappatura basata su JSON tra un argomento e un modello di Frammento di esperienza. Puoi utilizzare questa mappatura per pubblicare su un frammento di esperienza il contenuto presente in alcuni o tutti gli elementi di un argomento.

1. Per scaricare *experienceFragmentMapping.json*, accedi a Adobe Experience Manager come amministratore.
1. Seleziona il collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare Guide dall&#39;elenco degli strumenti e selezionare **Profili cartella**.
1. Seleziona il riquadro del profilo da configurare. Puoi configurare la mappatura per il profilo globale o per un profilo a livello di cartella. Ad esempio, seleziona la sezione **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto.
1. Seleziona l&#39;icona **Scarica** per scaricare il file *experienceFragmentMapping.json* nel sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.

1. Devi seguire le seguenti convalide:

   1. Deve essere un file JSON
   2. Deve contenere una matrice contenente almeno un oggetto e ogni oggetto deve contenere quanto segue:


      `"template": string `

      `"mapping": array`

      Ogni oggetto di mappatura deve contenere i seguenti elementi:

      `"name": string`

      `"class": string`

      `"resourceType": string`

      `"attributeMap": array`


1. Salva il file e caricalo.

Experience Manager Guides converte l’argomento completo in HTML che può quindi essere mappato ai componenti core utilizzati nel frammento di esperienza. Ad esempio, è possibile mappare il contenuto di un tag `<p>` per creare un componente di testo nel frammento di esperienza.
* `name`: specificare l&#39;elemento HTML. Ad esempio, `<div>`, `<img>`
* `class`: specificare il tag elemento DITA corrispondente all&#39;elemento HTML. Ad esempio, `<p>` `<image>`
* `resourceType`: specificare il tipo di risorsa applicabile per il componente utilizzato nel frammento di esperienza. Ad esempio, `wcm/foundation/components/text` è il resourceType per il componente wcm `text`.
* `attributeMap`: fornire ulteriori informazioni al componente, ad esempio se un componente testo deve essere renderizzato come `RichText` o contiene `fileReference` di un componente immagine.




File di esempio:

```
[
  {
    "template": "default",
    "mapping": [
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  },
  {
    "template": "/conf/we-retail/settings/wcm/templates/experience-fragment-web-variation",
    "mapping": [
      {
        "name": "div",
        "class": "title",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "h1, h2, h3, h4, h5, h6",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "div",
        "class": "p",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "img",
        "class": "image",
        "resourceType": "wcm/foundation/components/image",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "fileReference"
          }
        ]
      },
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  }
]
```



Durante la pubblicazione dei frammenti esperienza dall&#39;editor Web, selezionare `Template` dal menu a discesa nella finestra di dialogo **Genera frammento esperienza** per visualizzare il mapping disponibile per il modello nel campo **Mapping**. Se non è presente alcuna mappatura personalizzata per un modello, viene elencata la mappatura predefinita. Puoi utilizzare la mappatura predefinita per pubblicare l’intero argomento come frammento di esperienza.

Per ulteriori dettagli, visualizza [Frammenti esperienza Publish](../user-guide/publish-experience-fragment.md).
