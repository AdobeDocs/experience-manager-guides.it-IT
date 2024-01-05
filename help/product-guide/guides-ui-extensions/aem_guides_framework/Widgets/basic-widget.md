---
title: Widget
description: Informazioni sui widget
source-git-commit: f9a72e44fe1a3d90180ff728189a24ea9c7b1b1a
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 0%

---


# Widget

È possibile combinare più componenti di base, come descritto nella sezione Componenti, per creare un widget.
I widget possono essere utilizzati per creare un nuovo componente &quot;più complesso&quot; o per strutturare gli elementi di un componente.

Approfondiamo il concetto di widget!

Inizieremo creando un semplice widget per visualizzare un elenco di lingue.

```js title="basicWidget.js"
const widgetJSON =  {
    "component": "div", 
    "id": "widget_languages", 
    "items": [ // adding components to the widget
        {
            "component": "div",
            "items": [
                {
                    "component": "icon",
                    "icon": "info"
                },
                {
                    "component": "label",
                    "label": "List of some languages"
                }
            ]
        },
        {
            "component": "list",
            "data": "@languages"
        }
    ]
},
```

Qui, `@languages` è un array definito nel modello di `widget_languages` come: [&quot;Inglese&quot;, &quot;Francese&quot;, &quot;Hindi&quot;, &quot;Spagnolo&quot;, &quot;Urdu&quot;]

Il widget di base sottoposto a rendering sarà simile al seguente:

![basic_widget](imgs/basic_widget.png "Widget di base")
