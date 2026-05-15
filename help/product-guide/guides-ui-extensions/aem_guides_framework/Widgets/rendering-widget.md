---
title: Widget di rendering
description: Funzionamento del rendering nei widget JUI
role: User, Admin
exl-id: 381cc7b9-c957-40be-9db4-8347eefe2fa7
TQID: https://experienceleague.adobe.com/-VznRFHuyxLqumy55MssEvPMMHIIt2BelCe7C6zBqR8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 86
ht-degree: 0%

---

# Widget di rendering

È possibile eseguire il rendering di un widget facendo riferimento ad esso utilizzando il relativo `id`

Per eseguire il rendering del widget `widget_languages` in qualsiasi punto dell&#39;app, è possibile utilizzare la sintassi semplice:

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

`@files` è un elenco di oggetti file contenenti campi

```typescript
- fileName: string
- contributors: Array<String>
```
