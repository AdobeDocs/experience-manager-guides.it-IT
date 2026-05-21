---
title: Esempi
description: Elenco di esempi di personalizzazione
exl-id: 40cdc703-7a78-4979-a7b5-1158558d4868
TQID: https://experienceleague.adobe.com/Fgry-byLX0-N5gxaBk2TiN9QyzSPTXLepzGiQ4w1hSU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 18a1e586774da61e19055f8e4eb68a507192205c
workflow-type: tm+mt
source-wordcount: 563
ht-degree: 0%

---

# Esempi

In questo pacchetto sono stati inoltre forniti alcuni esempi di personalizzazione (disponibili all&#39;indirizzo `guides_extension/src`). Segue una breve descrizione per ciascuno di essi.

1. **Menu di scelta rapida**: in questo esempio è stato personalizzato il menu di scelta rapida `file_options` per rimuovere le opzioni `Delete` e `Edit` e sostituire l&#39;opzione `Duplicate` con un&#39;opzione `Download`. Scarica l&#39;esempio di codice per [Context Menu](./examples/file_options.ts).

```typescript
enum VIEW_STATE {
  APPEND = 'append',
  PREPEND = 'prepend',
  REPLACE = 'replace',
}

const loadDitaFile = (filePath, uuid) =>{
  return $.ajax({
    type: 'POST',
    url: '/bin/referencelistener',
    data: {
        operation: 'getdita',
        path: filePath,
        type: uuid ? 'UUID' : 'PATH',
        cache: false,
    },
  })
}

const fileOptions = {
  id: "file_options",
  contextMenuWidget: "repository_panel",
  view: {
    items: [
      {
        component: "div",
        target: {
          key: "displayName", value: "Delete",
          viewState: VIEW_STATE.REPLACE
        }
      },
      {
        component: "div",
        target: {
          key: "displayName", value: "Edit",
          viewState: VIEW_STATE.REPLACE
        }
      },
      {
        "displayName": "Download",
        "data": {
          "eventid": "downloadFile"
        },
        "icon": "downloadFromCloud",
        "class": "menu-separator",
        target: {
          key: "displayName", value: "Duplicate",
          viewState: VIEW_STATE.REPLACE
        }
      },
    ]
  },

  controller: {
    downloadFile() {
      const path = this.getValue('selectedItems')[0].path
      loadDitaFile(path, true).then((file) => {
        function download_file(name, contents) {
          const mime_type = "text/plain";

          const blob = new Blob([contents], { type: mime_type });

          const dlink = document.createElement('a');
          dlink.download = name;
          dlink.href = window.URL.createObjectURL(blob);
          dlink.onclick = function () {
            // revokeObjectURL needs a delay to work properly
            const that = this;
            setTimeout(function () {
              window.URL.revokeObjectURL(that.href);
            }, 1500);
          };

          dlink.click();
          dlink.remove();
        }
        download_file(path, file.xml)

      });
    }
  }
}

export default fileOptions
```

1. **Pannello sinistro**: in questo esempio `left tab panel` è stato personalizzato per avere un altro`tab` denominato &quot;TEST EXTENSION&quot; e un `tab panel` corrispondente con etichetta: `Test Tab Panel`.
Scarica l&#39;esempio di codice per il [pannello sinistro](./examples/left_panel_container.ts).

```typescript
const tabLeftPanel = {
    "id": "left_panel_container",
    "tabView": {
        "id": "left_panel_container",
        "tabs": [
            {
                "component": "tab",
                "id": "new_tab_extension",
                "extraclass": "collection-panel-tab",
                "showClass": "@visibleTabs.collection_panel",
                "on-click": "tabClick",
                "icon": "collection",
                "title": "TEST EXTENSION",
                "label": "TEST EXTENSION",
                "prevTabID": "condition_panel"
            },
        ],
        "tabPanels":
            [
                {
                    "component": "tabPanel",
                    "tabId": "new_tab_extension",
                    "showClass": "@visibleTabs.citation_panel",
                    "items": [
                        {
                            "id": "annotation_toolbox"
                        }
                    ],
                },
            ]
    }
}
export default tabLeftPanel
```

1. **Pannello a destra**: in questo esempio `right tab panel` è stato personalizzato per avere un altro `tab` denominato &quot;TEST EXTENSION&quot; e un `tab panel` corrispondente con etichetta: `New Tab Panel`. Scarica l&#39;esempio di codice per il [pannello destro](./examples/right_panel_container.ts).

```typescript
const rightPanel = {
    "id": "right_panel_container",
    "tabView": {
        "id": "right_panel_container_tab",
        "tabs": [
            {
                "component": "tab",
                "id": "new_tab_extension",
                "on-click": "tabClick",
                "icon": "collection",
                "title": "TEST EXTENSION",
            },
        ],
        "tabPanels":
            [
                {
                    "component": "tabPanel",
                    "tabId": "new_tab_extension",
                    "items": [
                        {
                            "component": "label",
                            "label": "New Tab Label",
                        }
                    ],
                },
            ]
    }
}
export default rightPanel
```

1. **Pannello archivio**: scarica l&#39;esempio di codice per [Pannello archivio](./examples/repository_panel.ts).

```typescript
export enum VIEW_STATE2 {
  APPEND = 'append',
  PREPEND = 'prepend',
  REPLACE = 'replace',
}

export default {
  class: "flex bg-red-100 bg-green-200 bg-green-300 mr-4",
  id: 'repository_panel',
  view: {
    className: '',
    items: [
      {
        target: {
          key: "id",
          value: 'respository-'
          ,
        },
        component: 'widget',
        id: 'loading_shimmer',
        viewState: VIEW_STATE2.REPLACE,
        index: 2,
      },
      {
        component: 'button',
        label: 'Close',
        'on-click': 'cancel',
        variant: 'secondary',
        quiet: true,
        index: 20,
      },
      {
        label: "@testLabel",
        component: "label"
      }
    ],
  },
  controller: {
    init: function() {
      console.log('subject: ', this.subject)      
      this.subscribe({
        key: 'rename',
        next: () => { console.log('rename using extension') }
      })
      console.log('Logging view config ', this.viewConfig)
      this.next(this.viewConfig.items[1].searchModeChangedEvent, { searchMode: true })
      this.subscribeAppEvent({
        key: 'app.active_document_changed',
        next: () => { console.log('active doc changed subs') }
      })
      this.subscribeAppModel('app.mode',
        () => { console.log('app mode subs') }
      )
      this.subscribeParentEvent({
        key: 'tabChange',
        next: () => { console.log('tab change subs') }
      })
      this.parentEventHandlerNext('tabChange', {
        data: 'map_panel'
      })
      this.appModelNext('app.mode', 'author')
      this.appEventHandlerNext('app.active_document_changed', 'active doc changed')
    },
    cancel: function (args) {
      this.setValue('testLabel', 'testlabel2')
    },
  },
  model: {
    deps: ['testLabel'],
  },
}   
```


1. **Barra degli strumenti**: in questo esempio sono stati sostituiti i pulsanti `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` con un singolo pulsante `More Insert Options` contenente tutti questi pulsanti. Scarica l&#39;esempio di codice per [Toolbar](./examples/toolbar.ts).

```typescript
import { VIEW_STATE } from "./review_app_examples/review_comment"

const topbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key: "title", value: "Insert Element",
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                component: "div",
                target: {
                    key: "title", value: "Insert Paragraph",
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                component: "div",
                target: {
                    key: "title", value: "Insert Numbered List",
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                component: "div",
                target: {
                    key: "title", value: "Insert Bulleted List",
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
                    "args": {
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
                    key: "title", value: "Insert Table",
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {
        init() {
            console.log(this.proxy.getValue("canUndo"))
            this.proxy.subscribeAppEvent({
              key: "editor.preview_rendered",
              next: async function (e) {
                console.log(this.proxy.getValue("canUndo"))
              }.bind(this)
            })
        },
        INSERT_P() {
            this.next("AUTHOR_INSERT_ELEMENT", "p")
        }
    }
}

export default topbarExtend
```

1. **Pulsante Gestisci nel pannello Metadati**: in questo esempio, il pulsante **Gestisci** (che si trova nel pannello Metadati nella pagina Rapporti) è stato personalizzato in modo da essere disabilitato quando i file selezionati sono in modalità di sola lettura. In questo modo è possibile evitare la modifica accidentale di metadati su file non destinati alla modifica. Scarica l&#39;esempio di codice per il pulsante [Gestisci nel pannello Metadati](./examples/metadata_report_manage_button.ts).

```typescript
const mapConsoleActionBar = {
  id: "map_console_action_bar",
  view: {
    items: [
      {
        "key": "manageTags",
        "component": "button",
        "title": "Manage",
        "on-click": "reports.manage_report",
        "label": "Manage",
        "icon": "s2AppGear",
        "type": "secondary",
        "variant": "action",
        "quiet": true,
        "show": "@showManageTags",
        "disabled": "$$extensionMap.overrideShowManageTags",
        target: {
          key: "title", value: "Manage",
          viewState: 'replace'
        }
      },
      {

        "key": "selectAll",
        "component": "button",
        "title": "@selectAllTitle",
        "on-click": "SELECT_ALL",
        "label": "@selectAllTitle",
        "variant": "action",
        "extraclass": "select-all-button",
        "quiet": true,
        "show": "@showSelectAllButton",
        "hide": "$$extensionMap.overrideShowManageTags",
        target: {
          key: "key", value: "selectAll",
          viewState: 'replace'
        }
      },
    ]
  }
}

function getAutoCheckoutConfigFromAppModel() {
  const config = tcx.model.getValue(tcx.model.KEYS.EDITOR_CHECKOUT_CONFIG)
  return config === true || config === 'true'
}

const bulkMetadataEditorController = {
  id: "bulkmetadata_report_view",
  controller: {
    rowSelectionChanged() {
      const selectedItems = this.getValue('selectedItems');
      let areReadOnlyFilesSelected = false;
      let autoCheckoutConfig = getAutoCheckoutConfigFromAppModel();

      for (let idx = 0; idx < selectedItems.length; idx++) {
        const item = selectedItems[idx].obj;
        const isLocked = Boolean(item.isCheckedOut);

        if (autoCheckoutConfig && !isLocked) {
          areReadOnlyFilesSelected = true;
          break;
        }
      }

      this.setExtensionAppState('overrideShowManageTags', areReadOnlyFilesSelected);
    }
  }
}

export {
  mapConsoleActionBar,
  bulkMetadataEditorController
}
```

## Rivedi esempi di app

1. **Casella degli strumenti Annotazione**: in questo esempio è stato aggiunto un altro pulsante alla casella degli strumenti Annotazione che apre l&#39;argomento di revisione corrente in AEM. Scarica l&#39;esempio di codice per [Annotation Toolbox](./examples/review_app_examples/annotation_extension.ts).

```typescript
import { VIEW_STATE } from './review_comment'

export default {
  id: 'annotation_toolbox',
  view: {
    items: [
      {
        component: 'button',
        icon: 'linkOut',
        title: 'openTopicInAEM',
        'on-click': 'openTopicInAEM',
        target: {
          key: 'value',
          value: 'addcomment',
          viewState: VIEW_STATE.APPEND
        },
      },
    ],
  },
  controller: {
    openTopicInAEM: function (args) {
      const topicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC)
      const { allTopics = {} } = tcx.model.getValue(tcx.model.KEYS.REVIEW_DATA) || {}
      tcx.appGet('util').openInAEM(allTopics[topicIndex])
    },
  },
}
```

1. **Commento revisione**: in questo esempio è stato aggiunto che il nome utente è stato sostituito con le informazioni utente (ovvero il nome completo e il titolo del commento), è stato aggiunto un ID commento univoco, un&#39;icona mailTo e sono stati aggiunti campi di input per indicare la gravità e la motivazione del commento.
È stato aggiunto anche un pulsante `accept with modification` ai commenti sul lato XMLEditor che apre una finestra di dialogo. Scarica l&#39;esempio di codice per [Commento revisione](./examples/review_app_examples/review_comment.ts).

```typescript
export enum VIEW_STATE {
  APPEND = 'append',
  PREPEND = 'prepend',
  REPLACE = 'replace',
}

const reviewComment = {
  id: 'review_comment',
  view: {
    items: [
      {
        component: 'label',
        label: '@extraProps.commentUniqId',
        extraclass: 'commentUniqId',
        target: {
          key: 'extraclass',
          value: 'user-image',
          viewState: VIEW_STATE.PREPEND,
        },
      },
      {
        component: 'div',
        extraclass: 'user-info',
        items: [
          {
            component: 'label',
            "label": "@extraProps.userInfo",
            "extraclass": "reviewer-name",
          },
          {
            component: 'button',
            icon: 'email',
            extraclass: 'mailto-icon',
            "on-click": "openMailTo"
          }
        ],
        target: {
          key: 'extraclass',
          value: 'reviewer-name',
          viewState: VIEW_STATE.REPLACE,
        },
      },
      {
        component: 'div',
        extraclass: 'comment-details',
        items:
          [
            {
              component: 'div',
              extraclass: 'comment-type-text',
              items:
                [
                  {
                    component: 'label',
                    label: 'Comment Type: ',
                    "extraclass": "severity-label",
                  },
                  {
                    component: 'label',
                    label: '@extraProps.severity'
                  }
                ],
            },
            {
              component: 'div',
              extraclass: 'comment-rationale',
              items:
                [
                  {
                    component: 'label',
                    label: 'Comment Rationale: ',
                    extraclass: 'comment-rationale-label'
                  },
                  {
                    component: 'label',
                    label: '@extraProps.commentRationale'
                  }
                ],
            },
          ],
        target: {
          key: 'id',
          value: 'attachment_tiles',
          viewState: VIEW_STATE.PREPEND,
        },
      },
      {
        component: 'div',
        items: [
          {
            component: 'div',
            extraclass: 'edit-comment-type',
            items: [
              {
                component: 'label',
                "label": "Comment Type",
              },
              {
                "component": "comboBox",
                "data": "@extraProps.labels",
                "extraclass": "severity-combobox",
                "multiple": false,
                "placeholder": "",
                'value': "@extraProps.severity",
                "on-change": "changeSeverity",
                "on-keyup": { "name": "changeSeverity", "eventArgs": { "keys": ["ENTER"] } },
              },
            ],
          },
          {
            component: "div",
            extraclass: 'edit-comment-rationale',
            items: [
              {
                component: 'label',
                label: 'Comment Rationale'
              },
              {
                component: "textarea",
                extraclass: "edit-textfield",
                "id": "edit_comment_rationale",
                "data": "@extraProps.commentRationale",
                "on-keyup": {
                  "name": "submitEditComment",
                  "eventArgs": {
                    "keys": [
                      "ENTER"
                    ]
                  }
                },
                "stopKeyPropagation": true
              },
            ],
          },
        ],
        target: {
          key: 'class',
          value: 'comment-block',
          viewState: VIEW_STATE.APPEND,
        },
      },
      {
        component: "button",
        "icon": "MultipleAdd",
        "variant": "action",
        "quiet": true,
        "extraclass": "hover-item",
        "title": "Accept with Modifications",
        "on-click": "acceptWithModification",
        target: {
          key: 'title',
          value: 'Reject comment',
          viewState: VIEW_STATE.APPEND,
        },
      }
    ],
  },

  controller: {
    init: function () {
      const reqComment = tcx.commentStore.getComment(this.getValue('commentId'))
      this.setValue('extraProps', reqComment.extraProps)
      this.setValue("labels", ['None', 'CRITICAL', 'MAJOR', 'SUBSTANTATIVE', 'ADMINISTRATIVE'])
    },

    sendAcceptWithModificationProps(args) {
      this.next('updateExtraProps', args)
    },

    changeSeverity: function (args) {
      this.setValue("severity", args.data)
      this.next('updateExtraProps',
        { 'severity': this.getValue("severity") }
      )
    },

    changeCommentRationale: function () {
      this.next('updateExtraProps',
        { 'commentRationale': this.getValue("commentRationale") }
      )
    },

    submitEditComment({ domEvent }: { domEvent?: KeyboardEvent } = {}) {
      if (domEvent?.key === 'Enter') {
        this.setValue('commentRationale', _.trim(this.getValue('commentRationale')))
      }
      if (this.getValue("originalCommentRationale") !== this.getValue("commentRationale")) {
        this.setValue("originalCommentRationale", this.getValue("commentRationale"))
        this.next('changeCommentRationale')
      }
    },

    openMailTo() {
      const mailToLink = `mailto:${this.getValue("userEmail")}`
      tcx.util.openLink(mailToLink)
    },

    acceptWithModification() {
      tcx.eventHandler.next(tcx.eventHandler.KEYS.APP_SHOW_DIALOG,
        {
          id: 'accept_with_modification_dialog',
          args: {
            onSuccess: (extraProps) => this.next('sendAcceptWithModificationProps', extraProps),
          }
        })
    }
  }
}

export default reviewComment
```

1. **Risposta al commento**: in questo esempio è stato aggiunto che il nome utente è stato sostituito con le informazioni utente, ovvero il nome completo e il titolo del commento, e che è stata aggiunta un&#39;icona mailTo nell&#39;intestazione del commento. Scarica l&#39;esempio di codice per [Comment Reply](./examples/review_app_examples/comment_reply.ts).

```typescript
import { VIEW_STATE } from "./review_comment"

const commentReply = {
  id: 'comment_reply',
  view: {
    items: [
      {
        component: 'div',
        extraclass: 'user-info',
        items: [
          {
            component: 'label',
            label: "@extraProps.userInfo",
            "extraclass": "user-name",
          },
          {
            component: 'button',
            icon: 'email',
            extraclass: 'mailto-icon',
            "on-click": "openMailTo"
          }
        ],

        target: {
          key: 'extraclass',
          value: 'user-name',
          viewState: VIEW_STATE.REPLACE,
        },
      },
    ],
  },
  model: {
    deps: [],
  },
  controller: {
    init: function () {
      const reqComment = tcx.commentStore.getComment(this.getValue('commentId'))
      const reqReply = reqComment.findReply(this.getValue('replyId'))
      this.setValue('extraProps', reqReply.extraProps)
    },

    openMailTo(){
      const mailToLink = `mailto:${this.getValue("userEmail")}`
      tcx.util.openLink(mailToLink)
    }
  }
}

export default commentReply
```

1. **Riquadro revisioni in linea**: in questo file viene calcolato e assegnato l&#39;ID commento univoco, indicato negli esempi `Review Comment` e `Comment Reply`.
   - Il metodo `setCommentId` imposta l&#39;ID univoco di ogni commento in base al numero di commenti.

   - `setUserInfo` imposta il valore di userInfo, utilizzando il nome completo e il titolo per ogni commento.

   - `onNewCommentEvent` assicura che il metodo `setUserInfo` venga chiamato per ogni nuovo commento o risposta.

   - La funzione `updatedProcessComments` viene eseguita per ogni nuovo evento di commento e assicura che `setCommentId` venga chiamato se si riceve un nuovo evento di commento.

Scarica l&#39;esempio di codice per [Inline Review Panel](./examples/review_app_examples/inline_review_panel.ts).

```typescript
export const updatedProcessComments = function (data, topicIndex) {
  const newCommentEvents = ["highlight", "strikethrough", "addcomment", "insertext"]
  _.each(data, (event: any) => {
    const identify = _.findIndex(newCommentEvents, eventType => eventType === event.eventType)
    if (identify !== -1) {
      this.next('setCommentId', { event, topicIndex })
    }
  })
}

const inline_extend = {
  id: 'inline_review_panel',
  model: {
    deps: ['commentCount'],
  },
  controller: {
    init: function () {
      this.setValue("commentCount", {})
      tcx.model.subscribeVal(tcx.model.KEYS.REVIEW_DATA, (reviewData) => {
        for (let topicId of reviewData.topicsinReview) {
          topicId = topicId.toString()
          tcx.commentStore.onProcessEvent(topicId, (events) => updatedProcessComments.call(this, events, topicId))
        }
      })
    },

    onNewCommentEvent(args) {
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.getValue('currTopicIndex') || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },

    setUserInfo(event) {
      tcx.api?.getUserInfo(event.user).subscribe(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const name = `${extraProps.userFirstName} ${extraProps.userLastName}, ${extraProps.userJobTitle}`
        if (_.trim(name) === ',') {
          extraProps.userInfo = userData.displayName
        }
        else {
          extraProps.userInfo = name
        }
        const data = { ...event, extraProps }
        this.next(
          'sendExtraProps',
          data
        )
      })
    },

    setCommentId({ event, topicIndex }) {
      const processingComments = this.getValue('processingComments')
      const modelComment = _.find(processingComments, { commentId: event.commentId })
      const reqComment = tcx.commentStore.getComment(event.commentId)
      const commentCount = this.getValue('commentCount')
      if (_.has(this.getValue('commentCount'), topicIndex)) {
        commentCount[topicIndex] += 1
        this.setValue("commentCount", commentCount)
      }
      else {
        commentCount[topicIndex] = 1
      }
      if (reqComment) {
        this.setValue("commentCount", commentCount)
        const commentUniqId = `${Number(topicIndex) + 1}.${commentCount[topicIndex]}`
        reqComment.extraProps.set("commentUniqId", commentUniqId)
        modelComment?.extraProps?.set("commentUniqId", commentUniqId)
      }
    },
  },
}

export default inline_extend  
```


1. **Pannello Revisione argomenti**: questo file estende **Il pannello Revisione in linea** (come illustrato in precedenza) in modo che le personalizzazioni aggiunte funzionino anche sul lato app Revisione. Scarica l&#39;esempio di codice per il [pannello Revisioni argomenti](./examples/review_app_examples/topic_reviews.ts).

```typescript
import inline_extend from './inline_review_panel';
import { updatedProcessComments } from './inline_review_panel';

const topic_reviews_extend = {
  id: 'topic_reviews',
  model: {
    deps: [],
  },
  controller: {
    ...inline_extend.controller,
    init: function () {
      this.setValue("commentCount", {})
      tcx.model.subscribeVal(tcx.model.KEYS.REVIEW_DATA, (reviewData) => {
        for (let topicId of reviewData.topicsinReview) {
          topicId = topicId.toString()
          tcx.commentStore.onProcessEvent(topicId, (events) => updatedProcessComments.call(this, events, topicId))
        }
      })
    },

  },
}

export default topic_reviews_extend
```

1. **Accetta con finestra di dialogo per modifica**: questo è un esempio di aggiunta di nuovi widget all&#39;app. È stata creata una nuova finestra di dialogo con due campi di testo di input: `Revised Text` e `Adjudicator Comment Rationale`. Scarica l&#39;esempio di codice per [Accept with Modification Dialog](./examples/review_app_examples/accept_with_modification_dialog.ts).

```typescript
const acceptWithModification = {
  id: 'accept_with_modification_dialog',
  view: {
    component: "dialog",
    "header": {
      "items": [
        {
          component: 'label',
          extraclass: "header",
          label: 'Accept With Modifications',
        }
      ]
    },
    content: {
      items: [
        {
          component: 'div',
          "extraclass": "revised-text",
          items: [
            {
              component: 'label',
              label: 'Revised Text (Required)',
              extraclass: 'revised-text-label'
            },
            {
              component: "textarea",
              "extraclass": "revised-text-textarea",
              "data": "@extraProps.revisedText",
              "stopKeyPropagation": true,
            }
          ]
        },
        {
          component: 'div',
          "extraclass": "adjudication-rationale",
          items: [
            {
              component: 'label',
              label: 'Adjudicator Comment Rationale (Required)',
              extraclass: 'adjudication-rationale-label'
            },
            {
              component: "textarea",
              extraclass: "adjudication-rationale-textarea",
              "data": "@extraProps.adjudicationRationale",
              "on-keyup": {
                "name": "",
                "eventArgs": {
                  "keys": [
                    "ENTER"
                  ]
                }
              },
              "stopKeyPropagation": true
            }
          ]
        },
      ],
    },
    footer: {
      "items": [
        {
          "component": "button",
          "label": "Cancel",
          "on-click": "handleClose",
          "variant": "secondary"
        },
        {
          "component": "button",
          "label": "Submit",
          "variant": "cta",
          "on-click": "submitAcceptWithModification"
        }
      ]
    }
  },
  model: {
    deps: [],
  },
  controller: {
    init: function () {
    },

    submitAcceptWithModification: function () {
      const extraProps = {
        'revisedText': this.getValue("revisedText"),
        'adjudicationRationale': this.getValue("adjudicationRationale"),
      }
      this.args.onSuccess(extraProps)
      this.next('handleClose')
    },

    handleClose() {
      tcx.eventHandler.next(tcx.eventHandler.KEYS.APP_HIDE_DIALOG, { id: 'accept_with_modification_dialog' })
    }
  }
}

export default acceptWithModification
```

1. **Salva revisione**: questo è un esempio di come aggiornare una finestra di dialogo esistente. Aggiungiamo un pulsante per la pubblicazione in questo. È consentita la modifica del contenuto della finestra di dialogo. Fare riferimento al relativo json qui: [`save_revision`](./jsons/dialogs/save_revision.json). Scarica l&#39;esempio di codice per [Salva revisione](./examples/save_revision.ts).

```typescript
enum VIEW_STATE {
    APPEND = 'append',
    PREPEND = 'prepend',
    REPLACE = 'replace',
}

const saveRevision = {
    id: 'save_revision',
    view: {
        items: [
            {
                component: "button",
                label: 'publish',
                target: {
                    key: 'label',
                    value: 'Save',
                    viewState: VIEW_STATE.APPEND
                }
            }
        ]
    }
}

export default saveRevision
```


![Accetta con finestra di dialogo per modifica](./imgs/accept_with_modification_dialogue.png)

Ecco il pannello di revisione prima e dopo la personalizzazione:

![Pannello di revisione;](./imgs/review_panel.png)
![Accetta con finestra di dialogo per modifica](./imgs/customised_review_panel.png)
