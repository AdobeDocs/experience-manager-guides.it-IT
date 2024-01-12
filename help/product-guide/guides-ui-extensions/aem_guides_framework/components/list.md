---
title: Elenco
description: Elenco
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
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

In genere itemConfig è un `widget`. Per ulteriori informazioni sui widget, visita [Widget](../Widgets/basic-widget.md)

L’elenco renderizzato sarà simile al seguente:

![list](./imgs/list.png "Elenco")
