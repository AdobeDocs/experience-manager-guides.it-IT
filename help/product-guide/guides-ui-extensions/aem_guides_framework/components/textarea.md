---
title: Area testo
description: Area testo
role: User, Admin
exl-id: 4c576acc-fa6a-4c41-9b92-443ba51dc8ee
source-git-commit: 08d379acc98dac425f1c84b0ac2226b0e34f6d8b
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 3%

---

# Campo di testo e area di testo

Per prendere il testo come input, usiamo i componenti, il campo di testo e l’area di testo.
Il componente area di testo in JUI rappresenta un html `<textarea/>`.

```js title="textArea.js"
const textAreaJSON =  {
    "component": "textarea", //tells the component name
    "id": "input_name", // can be used to give a unique identifier to a component
    "data": "@name", // the variable storing the inputted text
    "on-keyup": {
        "name": "submitName",
        "eventArgs": {
            "keys": [
            "ENTER"
            ]
        }
    },
},
```

`on-keyup` è la sintassi per richiamare i comandi nei controller.
Verrà generato un textArea in cui premendo INVIO verrà chiamato l&#39;evento `submitName`

L’area di testo di cui è stato eseguito il rendering sarà simile alla seguente:

![area di testo](./imgs/text_area.png "Area di testo")
