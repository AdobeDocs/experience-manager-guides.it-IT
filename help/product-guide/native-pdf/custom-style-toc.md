---
title: Funzionalità nativa di PDF Publish | Applicare uno stile personalizzato alle voci del sommario e al contenuto dell’argomento
description: Scopri come creare fogli di stile di utilizzo e stili per i contenuti.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: db4c823e592e249e1d828a7071fc0848a5e68c0f
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Applicare uno stile personalizzato alle voci del sommario e al contenuto dell’argomento

Talvolta, potrebbe essere utile applicare uno stile personalizzato alle voci del sommario o a un particolare argomento. A tale scopo è possibile associare un attributo `outputclass` all&#39;elemento `<topicref>` nella mappa DITA. Inoltre, nel caso in cui desideri applicare un formato personalizzato a un intero argomento, ciò può essere ottenuto anche estendendo la definizione di stile dell’attributo nel CSS.

Prendiamo ad esempio un nuovo argomento che si desidera inviare per la revisione. Per identificare facilmente l&#39;argomento aggiornato, è necessario aggiungere un attributo `outputclass` all&#39;elemento `<topicref>` nella mappa DITA e quindi definire uno stile personalizzato per lo stesso elemento nel CSS.

Nell&#39;esempio seguente, all&#39;argomento *Cronologia dei voli* è stato assegnato un attributo `outputclass` con il valore di `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

La definizione di classe di `new-topic` in un CSS può consentire di definire lo stile per i seguenti elementi:
* Voce principale nel sommario o mini-sommario
* Titolo dell’argomento nel contenuto principale
* L&#39;intero contenuto dell&#39;argomento, incluso il titolo

Vediamo come ciascuno di questi scenari può essere definito nel CSS. Nella seguente definizione CSS della classe `new-topic`, il colore del testo è stato modificato.

```css
…
.new-topic {
  color: #CC5309
}
…
```

Questa definizione controlla il colore del testo nel sommario e il titolo dell&#39;argomento. Nell&#39;output PDF riportato di seguito viene illustrato il diverso colore applicato alla voce del sommario:

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

Anche il titolo dell&#39;argomento viene formattato con lo stesso colore.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Se si desidera che la voce del sommario e il titolo dell&#39;argomento abbiano stili diversi, è possibile definirli separatamente come illustrato di seguito:

```css
...
/*for styling TOC entry */
.new-topic {
  color: #CC3509
}

/* for styling topic's title */
.new-topic.title {
  color: #092ACC
}
...
```

Infine, puoi anche applicare stili all’intero contenuto all’interno dell’argomento. Per questo, devi aggiungere un suffisso &quot;`-content`&quot; al nome della classe. Nell&#39;esempio seguente è stata aggiunta una barra di modifica all&#39;intero contenuto dell&#39;argomento:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

Utilizzando gli attributi di stile di cui sopra, viene aggiunta una barra di modifica a sinistra dell&#39;argomento *Cronologia del volo*, come illustrato di seguito:

<img src="./assets/pdf-output-topic-content.jpg" width="500">

## Rimuovi righe vuote dal sommario

Se non hai definito il titolo per alcun argomento, nel sommario vengono visualizzate righe vuote per tali argomenti.

Per rimuovere le righe vuote dal sommario e dal sommario mini, aggiungere il seguente stile in `layout.css`:

```css
.toc-body a:empty,
.chaptoc-body a:empty {
    display: none;
} 
```

