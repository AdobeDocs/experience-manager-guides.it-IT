---
sidebar_position: 3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# Personalizzazione dell’app

La nostra app segue una struttura MVC (Model, View, Controller)

## Modello

Il modello definisce i vari attributi e ne memorizza i valori. È possibile accedere ai valori dei vari attributi memorizzati nel modello dal controller utilizzando la sintassi

```typescript
this.model.attributeName
```

Per la personalizzazione nell’app, tutti i nuovi attributi creati verranno aggiunti sotto una mappa nel modello.
Per impostare un nuovo attributo nel modello, verrà utilizzata la seguente sintassi nel controller:

```typescript
this.model.extraProps.set("key", value)
```

Per accedere a un attributo aggiunto al modello verrà utilizzata la sintassi seguente:

```typescript
const value = this.model.extraProps.get("key")
```

## Visualizzazione

La vista definisce l’interfaccia utente dell’app. Utilizziamo i file JSON per definire la visualizzazione dei nostri file. In questo caso, definiamo i componenti, il css (come indicato nell’extraclass dei componenti) ed eseguiamo il rendering dei valori memorizzati nel modello.
Nell’app, ogni visualizzazione è definita utilizzando un JSON. I JSON sono referenziati utilizzando i loro ID univoci chiamati `id`.

## Controller

Il controller viene utilizzato per gestire gli eventi ed elaborare i dati. Il controller viene utilizzato per recuperare e inviare dati dal server, è l’interfaccia tra ciò che viene visualizzato nell’interfaccia utente e memorizzato nel backend.

- Per impostare i valori al momento dell’inizializzazione, utilizziamo `init` funzione.
- Per aggiungere un metodo al controller si utilizza la seguente sintassi:

```typescript
methodName: function(args){
    // functionality
}
```

Il `methodName` qui funge da `key` per fare riferimento al metodo nel JSON (vista) o in altre funzioni

- Per chiamare un metodo nel controller viene utilizzata la sintassi

```typescript
this.next('methodName', args)
```

## Esempio

Ora utilizziamo un semplice esempio per mostrare come questi 3 componenti interagiscono tra loro.
Aggiungeremo un pulsante per cambiare il valore dell’etichetta quando si fa clic su

### Esempio di visualizzazione

Di seguito è definito il JSON per un pulsante che mostra un testo dinamico memorizzato nel modello sotto il nome della variabile `buttonLabel`.
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

in questo caso, `extraProps.buttonLabel` contiene l’etichetta del pulsante

### Esempio di controller

```typescript
  controller: {
    init: function () {
      this.model.extraProps.set("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.model.extraProps.get("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.model.extraProps.set("buttonLabel", buttonLabel)
    }
  }
```

Sotto GIF mostra il codice di cui sopra in azione
![basic_customization](imgs/basic_customisation.gif "Pulsante Personalizzazione di base")
