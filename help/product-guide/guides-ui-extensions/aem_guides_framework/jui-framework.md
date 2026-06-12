---
title: Framework Jui
description: Informazioni su Jui Framework
role: User, Admin
exl-id: c193cf90-5916-4d8c-88f1-be5014beca1c
TQID: https://experienceleague.adobe.com/AQFEy2bHTDHXq6QH8KTBOEzUvtA3Hf2ojhxvD0dsI7o
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 1%

---

# Framework Jui

Prima di scoprire come scrivere estensioni, comprenderemo l’architettura del framework.
In modo da poterla estendere efficacemente.

## Introduzione

JUI è un framework MVC che si aggiunge ai componenti React e Adobe React Spectrum. JUI è l’interfaccia utente JSON. È costituito da più archivi Git.

JUI-Core è la libreria di base con tutta la logica necessaria per convertire la configurazione JSON in componenti react funzionanti e collegarla a un’istanza della classe di controller rilevante.
La libreria JUI-React-Spectrum dispone di widget wrapper dei componenti Adobe React Spectrum

## Progettazione Core JUI

### Progettazione interfaccia utente MVC

![Flusso MVC JUI](./imgs/jui-mvc-flow.png)

### Widget

- Ha un ID univoco.
- Dispone di un singolo file JSON per la visualizzazione.
- Può avere un controller proprio o condiviso.
- Può utilizzare un modello padre o un nuovo modello.
- Può contenere elementi dell’interfaccia utente (componenti React)
- Può avere altri widget
- L&#39;app è un widget

![Widget JUI](./imgs/jui-widget.png)

### Elemento

- È un componente HTML/React.
- Non ha alcun modello, il suo usa il modello di widget principale.

### Gestore di Evento

- Successivo(eventOpts)
   - Per attivare un evento con alcune opzioni
- Subscribe(callback)
   - Ricevi la notifica che l’evento è stato attivato con la configurazione

### Modello app/globale

- Successivo (nuovo valore)
   - Per pubblicare un nuovo valore
- Subscribe(callback)
   - Per ricevere una notifica per il valore modificato
   - Prima volta che ottieni un valore obsoleto
- GetValue()
   - Per ottenere il valore corrente

### Controller

- Deve essere esteso dalla classe Controller
- API
- CreaModello
   - Per creare un modello separato di widget figlio
- InitEventHandler
   - Per creare un gestore di eventi separato per il widget figlio
- RegisterCommands
   - Per registrare eventi locali, principali o dell’app
- Next(eventName, eventHandler)
   - Per attivare l&#39;evento del gestore eventi widget figlio, del gestore eventi widget padre o del gestore eventi app
- Subscribe(callback, eventHandler)
- SubscribeAppModel(callback)

### Progettazione app di esempio

![App di esempio](./imgs/jui-sample-app.png)
