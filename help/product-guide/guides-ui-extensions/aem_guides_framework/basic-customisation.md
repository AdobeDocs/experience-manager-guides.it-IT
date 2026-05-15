---
title: Personalizzazione dell’app
description: Personalizzazione dell’app
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
TQID: https://experienceleague.adobe.com/7DiEcUTAvp4rT3Fy9pIv4-zaHKwswjokjlaBgx8Pbyo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 0%

---

# Personalizzazione dell’app

## Funzionalità esposte nel framework dell’estensione

È stato esposto un set di funzioni e getter in un `proxy` che possono essere utilizzati per accedere ai dati, configurare ed attivare gli eventi. Di seguito è riportato un elenco e le modalità di accesso.

```typescript
interface EventData {
  key?: string,
  keys?: string[]
  view?: any,
  next?: any,
  error?: any,
  completed?: any,
  id?: any
}

* getValue(key)
* setValue(key, value)
* subject // getter
* subscribe(opts: EventData)
* subscribeAppEvent(opts: EventData)
* subscribeAppModel(key, next)
* subscribeParentEvent(opts: EventData)
* parentEventHandlerNext(eventName: string, opts: any)
* appModelNext(eventName:string, opts) 
* appEventHandlerNext(eventName:string, opts)
* next(eventName:string, opts, eventHandler?)
* viewConfig //getter
* args //getter
```

La nostra app segue una struttura MVC (Model, View, Controller)

## Modello

Il modello definisce i vari attributi e ne memorizza i valori. È possibile accedere ai valori dei vari attributi memorizzati nel modello dal controller utilizzando la sintassi

```typescript
this.getValue('attributeName')
```

Per la personalizzazione nell’app, tutti i nuovi attributi creati verranno aggiunti sotto una mappa nel modello.
Per impostare un nuovo attributo nel modello, verrà utilizzata la seguente sintassi nel controller:

```typescript
// If a key is not already in model then it will be added to extraProps
this.setValue('key', value)
```

Per accedere a un attributo aggiunto al modello verrà utilizzata la sintassi seguente:

```typescript
const value = this.getValue("key")
```

## Visualizzazione

La vista definisce l’interfaccia utente dell’app. Utilizziamo i file JSON per definire la visualizzazione dei nostri file. In questo caso, definiamo i componenti, il css (come indicato nell’extraclass dei componenti) ed eseguiamo il rendering dei valori memorizzati nel modello.
Nell’app, ogni visualizzazione è definita utilizzando un JSON. Viene fatto riferimento ai JSON utilizzando i loro ID univoci denominati `id`.

## Controller

Il controller viene utilizzato per gestire gli eventi ed elaborare i dati. Il controller viene utilizzato per recuperare e inviare dati dal server, è l’interfaccia tra ciò che viene visualizzato nell’interfaccia utente e memorizzato nel backend.

- Per impostare i valori all&#39;inizializzazione, si utilizza la funzione `init`.
- Per aggiungere un metodo al controller si utilizza la seguente sintassi:

```typescript
methodName: function(args){
    // functionality
}
```

`methodName` funge da `key` per fare riferimento al metodo nel JSON (visualizzazione) o in altre funzioni

- Per chiamare un metodo nel controller viene utilizzata la sintassi

```typescript
this.next('methodName', args)
```

## Esempio

Ora utilizziamo un semplice esempio per mostrare come questi 3 componenti interagiscono tra loro.
Aggiungeremo un pulsante per cambiare il valore dell’etichetta quando si fa clic su

### Esempio di visualizzazione

Di seguito viene definito il JSON per un pulsante che mostra un testo dinamico memorizzato nel modello con il nome della variabile `buttonLabel`.
In questo esempio, facendo clic sul pulsante ne cambia l’etichetta.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Esempio di modello

in questo caso, `extraProps.buttonLabel` contiene l&#39;etichetta del pulsante

### Esempio di controller

```typescript
  controller: {
    init: function () {
      this.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

Sotto GIF mostra il codice di cui sopra in azione
![personalizzazione di base](imgs/basic_customisation.gif "Pulsante Personalizzazione di base")


### Esempio di configurazione della visualizzazione

In questo caso, l&#39;evento della modalità di ricerca verrà aperto utilizzando `viewConfig` e verrà attivato un evento per aggiornarlo

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        console.log('Logging view config ', this.viewConfig)
        this.next(this.viewConfig.items[1].searchModeChangedEvent, { searchMode: true })
      }
    }
  }
```

### Esempio di abbonamento

In questo caso, quando si fa clic sull’opzione Rinomina file, viene aggiunta la sottoscrizione al registro della console al momento della ridenominazione

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribe({
          key: 'rename',
          next: () => { console.log('rename using extension') }
        })
      }
    }
  }
```

### Esempio di evento &quot;Subscribe app&quot;

In questo caso, l’accesso al documento attivo viene console modificato (modifica delle schede nell’interfaccia utente dell’editor)

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppEvent({
          key: 'app.active_document_changed',
          next: () => { console.log('Extension: active document changed') }
        })
      }
    }
  }
```

### Esempio di eventi del modello di app Subscribe

Esempio per la sottoscrizione di eventi del modello di app come `app.mode`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppModel('app.mode',
          () => { console.log('app mode subs') }
        )
      }
    }
  }
```

### Esempio di eventi del controller padre

In questo viene aggiunta la sottoscrizione all&#39;evento `tabChange` che è un evento del controller `left_panel_container` che agisce
come controller padre per `repository_panel`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeParentEvent({
          key: 'tabChange',
          next: () => { console.log('tab change subs') }
        })
        this.parentEventHandlerNext('tabChange', {
          data: 'map_panel'
        )
      }
    }
  }
```

### Modello app e controller app successivo

Possono essere attivati direttamente conoscendo l’evento corretto da attivare e i relativi dati

```typescript
  { 
    id: 'file_options', 
    controller: {
      init: function () {
        this.appModelNext('app.mode', 'author')
        this.appEventHandlerNext('app.active_document_changed', 'active doc changed')   
      }
    }
  } 
```
