---
title: Pulsante
description: Pulsante
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 5%

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
