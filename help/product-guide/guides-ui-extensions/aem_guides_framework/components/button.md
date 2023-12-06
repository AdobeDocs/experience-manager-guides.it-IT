---
sidebar_position: 1
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 1%

---


# Pulsante

Per visualizzare un pulsante utilizziamo il componente, pulsante.
Il componente pulsante in JUI rappresenta un html `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Verrà prodotto un pulsante con l&#39;etichetta `Yes, login`. Le altre proprietà includono, ma non sono limitate a, variante, etichetta, clic con il mouse.
> **_NOTA:_**  Il `on-<events>` è la sintassi per richiamare i comandi nei controller.

Il pulsante con rendering sarà simile al seguente:

![pulsante](imgs/yes_login_button.png "Pulsante")
