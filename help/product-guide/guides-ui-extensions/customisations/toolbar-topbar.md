---
title: Barra degli strumenti e barra degli argomenti
description: Personalizzazione della barra superiore e della barra degli strumenti
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: e1d6123991ddd8d25f76ee03befeb95f020a9834
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# Personalizzazione della barra superiore e della barra degli strumenti

Per personalizzare `topbar` e `toolbar`, è possibile utilizzare gli ID `topbar` o `toolbar` e seguire la stessa visualizzazione, la stessa struttura del controller.

>[!NOTE]
>
>A partire dalla versione 2502 di Experience Manager Guides, l&#39;ID **barra degli strumenti** è stato rinominato **barra degli strumenti dell&#39;editor**. Se utilizzi le versioni precedenti, puoi personalizzare la barra degli strumenti utilizzando l&#39;ID **barra degli strumenti**. Ora non disponiamo di alcun ID come **topbar** e abbiamo una **editor_tab_bar**.

Di seguito è riportato un banale esempio di personalizzazione della barra degli strumenti. In questo caso, il pulsante `Insert Numbered List` è stato rimosso e sostituito dal pulsante `Insert Paragraph` con un componente personalizzato che utilizza un gestore di clic personalizzato.

>[!TIP]
>
>Poiché **editor_toolbar** è progettato per eseguire il rendering dei pulsanti, l&#39;aggiunta di widget potrebbe interrompere il CSS e la reattività. Si consiglia di includere solo pulsanti o componenti di base, ad esempio un&#39;etichetta.

Per accedere alle funzionalità esposte sotto l&#39;oggetto `proxy`, è necessario accedervi utilizzando `this.getValue`, ad esempio per recuperare un valore.

Per AEM Guides versione 2502 e versioni successive, puoi fare riferimento all’esempio seguente per la personalizzazione della barra degli strumenti.

```js title = toolbar_customization.js
const toolbarExtend = {
    id: "editor_toolbar",
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
                "component": "button",
                "icon": "textParagraph",
                "variant": "action",
                "quiet": true,
                "title": "Insert Paragraph",
                "on-click": "INSERT_P",
                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                "component": "button",
                "icon": "fileHTML",
                "variant": "action",
                "quiet": true,
                "title": "URL Link Customization",
                "on-click": "openExternalLinkDialog",
                target: {
                key: "title", value: "Insert Bulleted List",
                viewState: VIEW_STATE.REPLACE
                }
            }
        ]
    },
    controller: {
        init: function() {
            console.log(this.getValue("canUndo"))
            this.subscribeAppEvent({
              key: "editor.preview_rendered",
              next: async function (e) {
                console.log(this.getValue("canUndo"))
              }.bind(this)
            })
        },
        INSERT_P(){
            this.appEventHandlerNext("AUTHOR_INSERT_ELEMENT",  "p" )
        },
        openExternalLinkDialog() {
            this.appEventHandlerNext("AUTHOR_INSERT_ELEMENT",
                {
                args: "<xref href='' scope='external' format = 'dita' ></xref>", activeTabId: "conkey_reference"
                }
            )
        }
    }
}
```


Una volta personalizzato, l’output finale può essere visualizzato come segue:

![editor_toolbar](imgs/editor_toolbar.png)

Consulta l’esempio seguente per personalizzare la barra degli strumenti nella versione 4.6.x di AEM Guides e nella versione precedente.

```js title = toolbar_customization.js
const topbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Element",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Bulleted List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                "component": "button",
                "extraclass": "insert-multimedia",
                "icon": "more",
                "variant": "action",
                "quiet": true,
                "holdAffordance": true,
                "title": "More Insert Options",
                "elementID": "toolbar_insert",
                "on-click": {
                    "name": "APP_SHOW_OPTIONS_POPOVER",
                    "args":{
                        "target": "toolbar_insert",
                        "extraclass": "new_options_buttons",
                        "items": [
                            {
                                "component": "button",
                                "icon": "add",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Element",
                                "on-click": "AUTHOR_SHOW_INSERT_ELEMENT_UI"
                            },
                            {
                                "component": "button",
                                "icon": "textParagraph",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Paragraph",
                                "on-click": "INSERT_P"
                            },
                            {
                                "component": "button",
                                "icon": "textNumbered",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Numbered List",
                                "on-click": "AUTHOR_INSERT_REMOVE_NUMBERED_LIST"
                            },
                            {
                                "component": "button",
                                "icon": "textBulleted",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Bulleted List",
                                "on-click": "AUTHOR_INSERT_REMOVE_BULLETED_LIST"
                            },
                            {
                                "component": "button",
                                "icon": "table",
                                "variant": "action",
                                "quiet": true,
                                "title": "Insert Table",
                                "on-click": "AUTHOR_INSERT_ELEMENT",
                            }
                        ]
                    },
                },
                target: {
                    key:"title",value: "Insert Table",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {
        init() {
            console.log(this.proxy.getValue('canUndo'))
            this.proxy.subscribeAppEvent({
                key: "editor.preview_rendered",
                next: async function (e) {
                    console.log(this.proxy.getValue('canUndo'))
                }.bind(this)
            })
        },
        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```

Una volta personalizzato, l’output finale può essere visualizzato come segue:

![barra degli strumenti](imgs/toolbar.png)


In un altro esempio, viene creato un pulsante personalizzato della barra degli strumenti che consente di passare direttamente alle opzioni secondarie desiderate di **Riferimento incrociato**, ad esempio E-mail, Riferimento file, Weblink e così via.


```js title = toolbar_customisation.js
const toolbarExtend = {
    id: "editor_toolbar",
    view: {
        items: [
            
                {
                    "component": "button",
                    "icon": "fileHTML",
                    "variant": "action",
                    "quiet": true,
                    "title": "External URL Link",
                    "on-click": "openExternalLinkDialogP",
            
                target: {
                    key:"title",value: "Insert Bulleted List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            }
        ]
    },
    controller: {
        openExternalLinkDialog() {
            tcx.eventHandler.next ("AUTHOR_INSERT_ELEMENT")
            t{
          args:"<xref href='' scope='external' format = 'dita' ></xref>",activeTabId:"conkey_reference"
        }
    }
  }
}
```

In questo caso, `activeTabId` è l&#39;enum per la selezione della scheda corretta. Per impostazione predefinita, selezionando la scheda Riferimento incrociato si apre `file_link`. È possibile modificare i valori `activeTabId` in `content_reference`, `conkey_reference`, `key_reference`, `file_link`, `web_link` e ` email_link` in base al requisito.
