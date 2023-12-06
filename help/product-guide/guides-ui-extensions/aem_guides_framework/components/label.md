---
sidebar_position: 2
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 2%

---


# Etichetta

Per visualizzare qualsiasi testo o stringa, utilizziamo il componente, etichetta.
Il componente etichetta in JUI rappresenta un html `<label/>`.

Di seguito è riportato un esempio per aggiungere un’etichetta statica

```js title="staticLabel.js"
const staticLabelJSON =  {
    "component": "label", //tells the component name
    "label": "This is an example label", // the string to be displayed
}
```

Sotto JSON viene visualizzata una stringa dinamica:

```js title="dynamicLabel.js"
const labelJSON =  {
    "component": "label", //tells the component name
    "label": "@name", // the variable storing the text to be displayed
},
```

L’etichetta di cui è stato eseguito il rendering sarà simile alla seguente:

![etichetta](./imgs/label.png "Etichetta")