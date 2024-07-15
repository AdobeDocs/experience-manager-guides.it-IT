---
title: Icona
description: Icona
role: User, Admin
exl-id: 5ba41c77-7329-49fc-bce5-02682261ea8e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 6%

---

# Icona

Per visualizzare un’icona utilizziamo il componente, icona.
Il componente area di testo in JUI rappresenta un html `<icon/>`.

Le icone disponibili all&#39;indirizzo [Icone Adobe dello spettro](https://spectrum.adobe.com/page/icons/) sono compatibili con la nostra app.

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
