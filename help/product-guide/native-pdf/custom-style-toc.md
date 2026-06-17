---
title: Funzione di pubblicazione nativa di PDF | Applicare uno stile personalizzato alle voci del sommario e al contenuto dell’argomento
description: Scopri come creare fogli di stile di utilizzo e stili per i contenuti.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/cqknNhuPThhuNTsLZzwnrUzPJguIPs4J-3rX6PVR2V8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: febac97b369bad427f0f650f2cdc69b0ca6c9f69
workflow-type: tm+mt
source-wordcount: 460
ht-degree: 0%

---

# Applicare uno stile personalizzato alle voci del sommario e al contenuto dell’argomento

È possibile applicare stili personalizzati alle voci del sommario, agli argomenti o ai singoli argomenti utilizzando l&#39;attributo `outputclass` sugli elementi di mappa supportati, ad esempio `<topicref>` e `<topichead>`. Per applicare la formattazione personalizzata a un intero argomento, estendere la definizione di stile dell&#39;attributo `outputclass` nel file CSS.

## Personalizzare lo stile di un argomento a cui si fa riferimento tramite `<topicref>`

È possibile applicare un `outputclass` a un elemento `<topicref>` per assegnare uno stile alla voce del sommario, al titolo dell&#39;argomento o al contenuto completo dell&#39;argomento nel PDF generato.

Ad esempio, per identificare un argomento che richiede una revisione, aggiungere un attributo outputclass all&#39;elemento `<topicref>` corrispondente nella mappa DITA e definire gli stili associati nel CSS.

Nell&#39;esempio seguente, all&#39;argomento *Cronologia dei voli* è stato assegnato un attributo `outputclass` con il valore di `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

La classe `new-topic` può essere utilizzata per definire gli stili per:

* Voce principale nel sommario o mini-sommario
* Titolo dell’argomento nel contenuto principale
* L&#39;intero contenuto dell&#39;argomento, incluso il titolo

La seguente definizione CSS modifica il colore del testo per la voce del sommario e il titolo dell’argomento:

```css
.new-topic {
  color:#CC5309
}
```

Questa definizione controlla il colore del testo nel sommario e il titolo dell&#39;argomento. Nell&#39;output di PDF riportato di seguito viene illustrato il diverso colore applicato alla voce del sommario:

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

Anche il titolo dell&#39;argomento viene formattato con lo stesso colore.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Se si desidera che la voce del sommario e il titolo dell&#39;argomento abbiano stili diversi, è possibile definirli separatamente come illustrato di seguito:

```css
...
/*for styling TOC entry */
.new-topic {
  color:#CC3509
}

/* for styling topic's title */
.new-topic.title {
  color:#092ACC
}
...
```

Per applicare gli stili all&#39;intero contenuto dell&#39;argomento, aggiungere il suffisso `-content` al nome della classe. Nell&#39;esempio seguente viene aggiunta una barra di modifica al contenuto dell&#39;argomento:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color:#A609CC;
}
...
```

Utilizzando gli attributi di stile di cui sopra, viene aggiunta una barra di modifica a sinistra dell&#39;argomento *Cronologia del volo*, come illustrato di seguito:

<img src="./assets/pdf-output-topic-content.jpg" width="500">

## Applica stili a `topichead` elementi

È possibile utilizzare l&#39;attributo `outputclass` in un elemento `<topichead>` per applicare stili diversi alla voce del sommario e all&#39;intestazione generata per l&#39;elemento `topichead`.

Ad esempio, se si definiscono i seguenti `topichead` nella mappa DITA:

```xml
<topichead navtitle="Getting Started" outputclass="new-topichead">
    ...
</topichead>
```

La classe `new-topichead` viene applicata alla voce topichead nel sommario e all&#39;intestazione generata per topichead.

Se si desidera applicare uno stile diverso all&#39;intestazione, definire una classe distinta, in modo analogo a come `<topicref>` supporta lo stile separato per la voce del sommario e il titolo dell&#39;argomento:

```css
...
/* Style for the topichead TOC entry */
.new-topichead {
  color: #CC5309;
}

/* Style for the topichead heading */
.new-topichead.title {
  color: #092ACC;
}...
```

Se si desidera applicare uno stile al contenuto associato all&#39;intestazione di argomento, aggiungere il suffisso `- content` al nome della classe:

```css
.new-topichead-content {
    border-left: 2px solid #cccccc;
    padding-left: 8px;
}
```



## Rimuovi righe vuote dal sommario

Se non hai definito il titolo per alcun argomento, nel sommario vengono visualizzate righe vuote per tali argomenti.

Per rimuovere le righe vuote dal sommario e dal sommario mini, aggiungere il seguente stile in `layout.css`:

```css
.toc-body a:empty,
.chaptoc-body a:empty {
    display: none;
} 
```

