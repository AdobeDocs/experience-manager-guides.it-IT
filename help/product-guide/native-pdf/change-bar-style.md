---
title: Funzionalità nativa di PDF Publish | Utilizzare gli stili delle barre di modifica personalizzati
description: Scopri come applicare gli stili sulle barre di modifica.
exl-id: a81ec56c-ccbb-4599-a696-8edef7a73cdd
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Utilizzare gli stili delle barre di modifica personalizzati

Una barra delle modifiche è una linea verticale che identifica visivamente il contenuto nuovo o rivisto. AEM Guides consente di visualizzare una barra di modifica a sinistra del contenuto modificato all’interno di argomenti e anche gli argomenti modificati nel sommario dell’output PDF.

Per ulteriori dettagli sulla visualizzazione della barra delle modifiche, vedere l&#39;impostazione *Crea PDF con barra di modifica tra versioni pubblicate* in [Output di Publish PDF](../web-editor/native-pdf-web-editor.md).

## Contenuto modificato negli argomenti

La barra delle modifiche viene visualizzata a sinistra del contenuto negli argomenti inseriti, modificati o eliminati.

È possibile modificare i seguenti stili per visualizzare il contenuto modificato e tra con le barre di modifica.


>[!NOTE]
>
>Questi stili fanno parte del file `layout.css` e possono essere modificati in base alle esigenze.

È ad esempio possibile utilizzare l&#39;attributo color nello stile `.inserted-block` per definire la modalità di visualizzazione del contenuto inserito nell&#39;output PDF pubblicato.


```css
...
.inserted-block { 
  color: #2ECC40; 
  display: inline; 
  -ro-comment-content: " "; 
  -ro-comment-style: underline; 
  -ro-comment-title: "Inserted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

Analogamente, è possibile utilizzare lo stile `.deleted-block` per definire la modalità di visualizzazione del contenuto eliminato nell&#39;output PDF pubblicato.

```css
...
.deleted-block { 
  display: inline; 
  color: #FF6961; 
  text-decoration: line-through; 
  -ro-comment-content: " "; 
  -ro-comment-style: strikeout; 
  -ro-comment-title: "Deleted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

È possibile utilizzare lo stile `.inserted-change-bar` e `.deleted-change-bar` per modificare l&#39;aspetto delle barre di modifica visualizzate a sinistra del contenuto aggiornato.

Ad esempio, è possibile utilizzare l&#39;attributo `-ro-change-bar-color` nello stile `.inserted-change-bar` per visualizzare la barra delle modifiche inserita in verde. È inoltre possibile utilizzare l&#39;attributo `-ro-change-bar-color` nello stile `.deleted-change-bar` per visualizzare la barra delle modifiche eliminata in rosso.

```css
...
.inserted-change-bar { 
  -ro-change-bar-color: #2ECC40; 
} 

.deleted-change-bar { 
  -ro-change-bar-color: #FF6961; 
  } 
...
```

<img src="./assets/changed-bar-content.png" alt="Contenuto dell’argomento barra modificato" width="500">

## Argomento modificato nel sommario

È inoltre possibile aggiungere una barra di modifica a sinistra degli argomenti modificati nel sommario dell&#39;output di PDF. È possibile utilizzare l&#39;attributo `-ro-change-bar-color` nello stile `.changed-topic` per aggiungere una barra di modifica con il colore desiderato per gli argomenti aggiornati nell&#39;elenco sommario.

Ad esempio, è possibile aggiungere una barra di modifica di colore verde.

```css
...
.changed-topic { 
 -ro-change-bar-color: #2ECC40; 
}  
...
```


Questa mostra una barra di modifica verde rispetto a tutti gli argomenti nel sommario in cui sono stati eseguiti alcuni aggiornamenti. Puoi fare clic sull’argomento modificato nel sommario e visualizzare le modifiche dettagliate.

<img src="./assets/changed-bar-TOC.png" alt="Sommario a barre modificato" width="500">
