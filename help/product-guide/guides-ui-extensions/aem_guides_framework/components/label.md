---
title: Etichetta
description: Etichetta
role: User, Admin
exl-id: aceefb08-3198-4c3a-90ec-ac1cdde28582
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%

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
