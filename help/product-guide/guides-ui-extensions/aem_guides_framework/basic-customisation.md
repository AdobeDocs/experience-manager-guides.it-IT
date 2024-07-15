---
title: Personalizzazione dell’app
description: Personalizzazione dell’app
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Personalizzazione dell’app

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
    init: function (context) {
      context.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

Sotto GIF mostra il codice di cui sopra in azione
![personalizzazione di base](imgs/basic_customisation.gif "Pulsante Personalizzazione di base")
