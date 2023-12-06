---
sidebar_position: 4
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 2%

---


# Icona

Per visualizzare un’icona utilizziamo il componente, icona.
Il componente area di testo in JUI rappresenta un html `<icon/>`.

Icone disponibili all’indirizzo [Adobe di icone di spettro](https://spectrum.adobe.com/page/icons/) sono compatibili con la nostra app.

```js title="icon.js"
const iconJSON =  {
    "component": "icon", //tells the component name
    "icon": "info", // name of the icon to be used
    "size": "S", // size of the icon
    "title": "Information" // tooltip corresponding to the icon.
},
```

è inoltre possibile aggiungere icone ai pulsanti.

L’icona di cui è stato eseguito il rendering sarà simile alla seguente:

![icona](./imgs/info_icon.png "Icona")
