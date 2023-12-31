---
title: Barra degli strumenti e barra degli argomenti
description: Personalizzazione della barra superiore e della barra degli strumenti
source-git-commit: 5962414dfc065543b946cac1468a5f62013073cf
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---


# Personalizzazione della barra superiore e della barra degli strumenti

Per personalizzare `topbar` e `toolbar`, utilizzeremo gli id: `topbar` o `toolbar`e seguire la stessa visualizzazione, ovvero la stessa struttura di controller.

Di seguito è riportato un banale esempio di personalizzazione della barra degli strumenti. In questo caso, è stata rimossa la `Insert Numbered List` e ha sostituito il `Insert Paragraph` con un nostro componente utilizzando un gestore al clic personalizzato.

```js title = toolbar_customisation.js
const toolbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                {
                    "component": "button",
                    "icon": "textParagraph",
                    "variant": "action",
                    "quiet": true,
                    "title": "Insert Paragraph",
                    "on-click": "INSERT_P"
                },

                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {

        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
