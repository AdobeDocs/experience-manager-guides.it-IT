---
title: Barra degli strumenti e barra degli argomenti
description: Personalizzazione della barra superiore e della barra degli strumenti
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: 4f41609368b64415993b93be27162b069e7b2e32
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# Personalizzazione della barra superiore e della barra degli strumenti

Per personalizzare `topbar` e `toolbar`, verranno utilizzati gli ID `topbar` o `toolbar` e verrà seguita la stessa visualizzazione, la stessa struttura del controller.

Di seguito è riportato un banale esempio di personalizzazione della barra degli strumenti. In questo caso, il pulsante `Insert Numbered List` è stato rimosso e sostituito dal pulsante `Insert Paragraph` con un componente personalizzato che utilizza un gestore di clic personalizzato.

Per accedere alla funzionalità esposta in `proxy` oggetto, dovremo accedervi utilizzando `this.proxy.getValue`, diciamo per recuperare un valore.

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
        init: function() {
            console.log(this.proxy.getValue("canUndo"))
            this.proxy.subscribeAppEvent({
              key: "editor.preview_rendered",
              next: async function (e) {
                console.log(this.proxy.getValue("canUndo"))
              }.bind(this)
            })
        },
        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
