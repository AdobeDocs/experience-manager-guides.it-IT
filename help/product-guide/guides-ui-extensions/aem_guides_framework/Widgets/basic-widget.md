---
title: Widget
description: Informazioni sui widget
role: User, Admin
exl-id: 96e960df-d595-4d58-8ad4-27057f857bac
TQID: https://experienceleague.adobe.com/SssVShlzFB3kjQCV-cNAOZVYb0TYSQ1CjtWoax2Q-LU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 86
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

`@languages` è un array definito nel modello di `widget_languages` come: [&quot;Inglese&quot;, &quot;Francese&quot;, &quot;Hindi&quot;, &quot;Spagnolo&quot;, &quot;Urdu&quot;]

Il widget di base sottoposto a rendering sarà simile al seguente:

![widget_base](imgs/basic_widget.png "widget di base")
