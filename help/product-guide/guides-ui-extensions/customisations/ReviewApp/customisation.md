---
title: Personalizzazione
description: Personalizzazione dell’app di revisione
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
source-git-commit: 492f72768e0de74a91eb7acc9db8264e21bfc810
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Personalizzazione dell’app di revisione

Per facilitare la personalizzazione dell’app di revisione abbiamo fornito alcuni hook elencati e spiegati di seguito:

## Revisione-Commento

- id: `review_comment`
- hook: `this.next('updateExtraProps')`:

Come discusso [qui](../../aem_guides_framework/basic-customisation.md), qualsiasi nuovo attributo aggiunto durante la personalizzazione va sotto `this.model.extraProps`. Il metodo `updateExtraProps` consente di aggiungere attributi a un commento di revisione, gestendo l&#39;aggiornamento e l&#39;archiviazione dell&#39;attributo aggiunto anche sul server.

### Esempio di utilizzo

Si supponga, ad esempio, di voler aggiungere i campi `commentRationale` e `severity` ai commenti.
Aggiorniamo `commentRationale` a &quot;Questa è una frase importante&quot;. e `severity` a &quot;CRITICAL&quot;.
Questa operazione può essere eseguita utilizzando la sintassi:

```typescript
  this.next('updateExtraProps', {
    'commentRationale': 'This is an important sentence.',
    'severity': 'CRITICAL'
  })
```

Il frammento di codice sopra riportato gestirà l’aggiornamento e il salvataggio dei valori. È possibile eseguire il rendering dei valori salvati nell’interfaccia utente definendo la vista.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Pannello Revisione in linea

- id: `inline_review_panel`

1. hook: `onNewCommentEvent`
L&#39;hook `onNewCommentEvent` consente di generare un evento o di chiamare un metodo su un nuovo commento o su un nuovo evento di risposta.
Gli argomenti ricevuti in `onNewCommentEvent` includono:
   - eventi: l’evento di commento/risposta inviato.
   - newComment: booleano
Se l&#39;evento inviato è un nuovo evento di commento, ad esempio `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: booleano
Se l’evento inviato era un nuovo evento di risposta.

2. hook: `sendExtraProps`

Questo hook è utile se desideri estendere un `event` e inviare `extraProps` dal pannello di revisione in linea. Di seguito viene illustrato l&#39;utilizzo di questi due hook.

### Esempio di pannello Revisione in linea

Si supponga di voler inviare un oggetto extraProp, `userInfo`, ogni volta che viene inviato un nuovo commento o una nuova risposta. Ora questo verrà fatto tramite il pannello di revisione in linea, tuttavia non abbiamo il riferimento al commentId del commento appena generato, quindi per ottenere questo possiamo scrivere il seguente codice.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.getValue('currTopicIndex') || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

Nel frammento di codice precedente, stiamo verificando se l’evento inviato è un nuovo commento o una nuova risposta. In caso di un nuovo commento o risposta, verrà chiamato il metodo `setUserInfo`

```typescript
    const getUserInfo = (userId) => {
      return $.ajax({
        url: '/bin/dxml/xmleditor/userinfo',
        data: {
          username: userId,
        },
        success: (data) => {
          return data
        }
      })
    }

    setUserInfo(event) {
      getUserInfo(event.user).done(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const data = {... event, extraProps}
        this.next(
          'sendExtraProps',
          data
        )
      })
    },
```

Con il metodo precedente, estendiamo l’evento per inviare extraProp che includono nome dell’utente, e-mail, titolo, ecc. Estendendo l’evento in questo modo, gli extraProp vengono inviati con il commentId corretto, garantendo che siano allegati al commento corretto.

L&#39;hook `updateExtraProps` chiama intrinsecamente l&#39;hook `sendExtraProps`, quindi quando utilizzare cosa?

`updateExtraProps` viene utilizzato nel controller `review_comment`, che ha già il `id` del commento e pertanto è sufficiente menzionare `extraProps.`

`inline_review_panel` non ha tuttavia accesso all&#39;ID del commento, pertanto in qualsiasi momento sia necessario inviare un evento dal pannello di revisione in linea, `sendExtraProps` sarà utile.
