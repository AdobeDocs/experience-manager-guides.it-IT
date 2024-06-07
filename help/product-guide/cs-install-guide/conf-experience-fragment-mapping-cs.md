---
title: Configura il mapping basato su JSON tra un argomento e un modello di Frammento di esperienza.
description: Scopri come configurare la mappatura basata su JSON tra un argomento e un modello di Frammento di esperienza.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: f252537d15d7e8f8651dddb0ae635905705e4adf
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Creare una mappatura tra un argomento e un frammento di esperienza

Guide di Adobe Experience Manager fornisce la funzione per creare una mappatura basata su JSON tra un argomento e un modello di Frammento di esperienza. Puoi utilizzare questa mappatura per pubblicare su un frammento di esperienza il contenuto presente in alcuni o tutti gli elementi di un argomento.

1. Per scaricare *experienceFragmentMapping.json*, accedi a Adobe Experience Manager come amministratore.
1. Seleziona il collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare Guide dall&#39;elenco degli strumenti e selezionare **Profili cartella**.
1. Seleziona il riquadro del profilo da configurare. Puoi configurare la mappatura per il profilo globale o per un profilo a livello di cartella. Ad esempio, seleziona la **Profilo globale** affiancare.
1. Seleziona la **Configurazione editor XML** e seleziona la scheda **Modifica** nella parte superiore.
1. Seleziona la **Scarica** per scaricare *experienceFragmentMapping.json*  sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.

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

Experience Manager Guides converte l’argomento completo in HTML che può quindi essere mappato ai componenti core utilizzati nel frammento di esperienza. Ad esempio, il contenuto in una `<p>` può essere mappato per creare un componente testo nel frammento di esperienza.
* `name`: specifica l’elemento HTML. Ad esempio: `<div>`, `<img>`
* `class`: specifica il tag dell’elemento DITA corrispondente all’elemento HTML. Ad esempio: `<p>` `<image>`
* `resourceType`: specifica il tipo di risorsa applicabile al componente utilizzato nel frammento di esperienza. Ad esempio: `wcm/foundation/components/text` è il resourceType per wcm `text` componente.
* `attributeMap`: fornisci ulteriori informazioni al componente, ad esempio se un componente testo deve essere renderizzato come `RichText` o contiene `fileReference` di un componente immagine.




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



Durante la pubblicazione dei frammenti di esperienza dall’editor web, seleziona la `Template` dal menu a discesa nel **Genera frammento esperienza** per visualizzare il mapping disponibile per il modello in **Mappatura** campo. Se non è presente alcuna mappatura personalizzata per un modello, viene elencata la mappatura predefinita. Puoi utilizzare la mappatura predefinita per pubblicare l’intero argomento come frammento di esperienza.

Per ulteriori dettagli, vedi [Pubblicare Frammenti Esperienza](../user-guide/publish-experience-fragment.md).

