---
title: Elenco
description: Elenco
role: User, Admin
exl-id: 333b5e24-efba-4a51-8f68-83b5d1d7daec
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 5%

---

# Elenco

Per visualizzare un elenco, utilizziamo l’elenco dei componenti.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@languages", // an array of list items
},
```

In questo caso, il linguaggio è un semplice array di stringhe. `languages = ["English", "Hindi", "French"]`
Se desideri eseguire il rendering di un elenco di oggetti, possiamo specificare la struttura utilizzando la configurazione dell’elemento.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@projects", // an array of list items
    "itemConfig": { // used to define the structure of the list items.
    "component": "widget",
    "id": "checkbox_label"
    }
},
```

In genere itemConfig è un `widget`. Per ulteriori informazioni sui widget, vai a [Widget](../Widgets/basic-widget.md)

L’elenco renderizzato sarà simile al seguente:

![elenco](./imgs/list.png "Elenco")
