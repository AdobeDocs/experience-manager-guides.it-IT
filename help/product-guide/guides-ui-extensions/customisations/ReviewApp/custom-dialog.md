---
title: Finestra di dialogo personalizzata
description: Aggiungere una finestra di dialogo personalizzata
role: User, Admin
exl-id: 00ea7f6f-1130-433f-b557-c2ea552b17c7
TQID: https://experienceleague.adobe.com/rKpSp3cAlzjL6ZBOAEAbmtP3FX0oAYOl962lkFSO0eo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 124
ht-degree: 0%

---

# Aggiunta di una finestra di dialogo personalizzata

Per dare un’occhiata all’aggiunta di una finestra di dialogo personalizzata nell’app di revisione, effettua le seguenti operazioni:

## Esempio di utilizzo

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
  controller:{

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
```


## Chiamata di una finestra di dialogo personalizzata

Questo esempio descrive le informazioni relative alla modalità di aggiunta di un pulsante per aprire una finestra di dialogo personalizzata.
Consideriamo il pannello `review_comment` per questo. L’estensione completa è disponibile qui:
[Commento revisione](../../examples/review_app_examples/review_comment.ts)

```typescript
const reviewComment = {
  id: 'review_comment',
  view: {
    items: [
      ...
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
    ...

    sendAcceptWithModificationProps(args) {
      this.next('updateExtraProps', args)
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

    ...
  }
}
```

## Come passare gli argomenti a una finestra di dialogo personalizzata

Qui puoi vedere che `args` viene passato con l&#39;ID della finestra di dialogo e che noi trasmettiamo un onSuccess con questo per gestire un callback in caso di evento di successo.
Possiamo passare `onCancel` anche se vogliamo fornire alcuni callback personalizzati al clic di annullamento e gestirli all&#39;interno dell&#39;evento di annullamento nella finestra di dialogo.
