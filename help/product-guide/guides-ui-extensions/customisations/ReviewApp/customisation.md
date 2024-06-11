---
title: Personalizzazione
description: Personalizzazione dell’app di revisione
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Personalizzazione dell’app di revisione

Per facilitare la personalizzazione dell’app di revisione abbiamo fornito alcuni hook elencati e spiegati di seguito:

## Revisione-Commento

- id: `review_comment`
- gancio: `this.updateExtraProps`:

Come discusso [qui](../../aem_guides_framework/basic-customisation.md), qualsiasi nuovo attributo aggiunto durante la personalizzazione va sotto `this.model.extraProps`. Il metodo `updateExtraProps` consente di aggiungere attributi a un commento di revisione, gestendo l’aggiornamento e l’archiviazione dell’attributo aggiunto anche sul server.

### Esempio di utilizzo

Ad esempio, se desideri aggiungere dei campi `commentRationale` e `severity` ai tuoi commenti.
Aggiorniamo il `commentRationale` to &quot;Questa è una frase importante&quot;. e `severity` &quot;CRITICAL&quot;.
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

1. gancio: `onNewCommentEvent`
Il gancio `onNewCommentEvent` consente di generare un evento o chiamare un metodo su un nuovo evento di commento o risposta.
Gli argomenti ricevuti nel `onNewCommentEvent` include:
   - eventi: l’evento di commento/risposta inviato.
   - newComment: booleano Se l’evento inviato era un nuovo evento di commento, ovvero `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: booleano Se l’evento inviato era un nuovo evento di risposta.

2. gancio: `sendExtraProps`

Questo gancio è utile se desideri estendere un `event` e invia `extraProps` dal pannello di revisione in linea. Di seguito viene illustrato l&#39;utilizzo di questi due hook.

### Esempio di pannello Revisione in linea

Di&#39; che vogliamo inviare un extraProp, `userInfo`, ogni volta che viene inviato un nuovo commento o una nuova risposta. Ora questo verrà fatto tramite il pannello di revisione in linea, tuttavia non abbiamo il riferimento al commentId del commento appena generato, quindi per ottenere questo possiamo scrivere il seguente codice.

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

Nel frammento di codice precedente, stiamo verificando se l’evento inviato è un nuovo commento o una nuova risposta. In caso di un nuovo commento o risposta, chiamiamo il metodo `setUserInfo`

```typescript
    setUserInfo(event) {
      this.loader?.getUserInfo(event.user).subscribe(userData => {
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

Il gancio `updateExtraProps` richiama intrinsecamente l’hook `sendExtraProps`quindi quando utilizzare cosa?

Utilizziamo `updateExtraProps` nel `review_comment` controller, che ha già la proprietà `id` e quindi è sufficiente menzionare il `extraProps.`

Il `inline_review_panel` tuttavia, non ha accesso all’id del commento; pertanto, ogni volta che devi inviare un evento dal pannello di revisione in linea, il `sendExtraProps` sarà utile.
