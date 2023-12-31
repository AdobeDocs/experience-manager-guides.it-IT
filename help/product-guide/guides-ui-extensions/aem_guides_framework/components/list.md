---
title: Elenco
description: Elenco
source-git-commit: dfd4c898d3c093bfee1a8a6efff4e395efd20c60
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
