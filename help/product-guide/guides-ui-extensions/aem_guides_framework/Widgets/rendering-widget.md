---
title: Widget di rendering
description: Funzionamento del rendering nei widget JUI
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Widget di rendering

È possibile eseguire il rendering di un widget facendo riferimento a esso utilizzando il relativo `id`

Per eseguire il rendering del widget `widget_languages` ovunque nell’app puoi utilizzare la sintassi semplice:

```json
{
    "component": "widget",
    "id": "widget_languages"
}
```

I widget possono essere utilizzati anche per eseguire il rendering di elementi complessi, ad esempio per eseguire il rendering dell’elenco dei collaboratori di ciascun file.
In questo caso, il widget può essere costruito come:

```js title="fileContributorsWidget.js"
const widgetJSON =  {
    component: "div", 
    id: "file_contributors", 
    items: [ // adding components to the widget
        {
            component: "div",
            items: [
                {
                    component: "icon",
                    icon: "file"
                },
                {
                    component: "label",
                    label: "@fileName"
                }
            ]
        },
        {
            component: "list",
            data: "@contributors",
            itemConfig: {
                component: "label"
            }
        }
    ]
},
```

Ora, per eseguire il rendering di un elenco di collaboratori per ciascun file, scriviamo l’elenco come:

```js title="fileContributorsList.js"
const listJSON = {
    component: "list"
    data: "@files"
    itemConfig: {
        component: "widget",
        id: "file_contributors"
    }
}
```

Qui `@files` è un elenco di oggetti file contenenti campi

```typescript
- fileName: string
- contributors: Array<String>
```
