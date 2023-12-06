---
title: Funzione di pubblicazione nativa di PDF | Usa stili personalizzati nelle note a piè di pagina
description: Scopri come applicare lo stile ai numeri nelle note a piè di pagina.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 0%

---

# Applica stili nota a piè di pagina


Le note a piè di pagina sono note posizionate nella parte inferiore di una pagina che commentano o citano un riferimento per una parte designata del testo.

Ogni nota a piè di pagina ha un contrassegno nella parte inferiore della pagina, che in genere è un numero o un simbolo come un asterisco. All’interno del contenuto principale, lo stesso marcatore di nota a piè di pagina viene visualizzato come chiamata di nota a piè di pagina ed è indicato dallo stesso numero o simbolo di un apice.




## Modificare gli stili delle chiamate e dei marcatori delle note a piè di pagina

Potete modificare gli stili delle chiamate e dei marcatori delle note a piè di pagina e gestirne l&#39;aspetto nell&#39;output di PDF. Questi stili consentono di identificare rapidamente le note a piè di pagina nel documento.


**Esempio 1**:

Utilizza l’esempio dato per aggiungere una parentesi prima e dopo la chiamata e il marcatore della nota a piè di pagina:

* Aggiungi il prefisso &quot;(&quot; e il suffisso &quot;)&quot; utilizzando l’attributo content nel `footnote-call` stile, che aggiunge le parentesi quadre attorno al numero della nota a piè di pagina nel contenuto dell&#39;argomento.
* Aggiungi il prefisso &quot;(&quot; e il suffisso &quot;)&quot; utilizzando l’attributo content nel `footnote-marker` che aggiungerà le parentesi quadre attorno al numero della nota a piè di pagina nella parte inferiore della pagina.

```css
...
.fn::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.fn::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```



<img src="./assets/pdf-output-footer-numbers.png" alt="Piè di pagina nell’output di PDF" width="500" border="2px">

*Aggiungete parentesi quadre attorno alla chiamata della nota a piè di pagina e al contrassegno della nota.*

**Esempio 2**:

È inoltre possibile contrassegnare la chiamata e l&#39;indicatore della nota a piè di pagina con un asterisco o un carattere greco inferiore invece di un numero.


```css
.fn::footnote-call {
 content: counter(footnote, asterisks);
}
.fn::footnote-marker {
 content: counter(footnote, asterisks) " ";
}
```

Nell’output, puoi visualizzare un elemento simile a:

<img src="./assets/footnote-number-2.png" alt="Piè di pagina nell’output di PDF" width="500" border="2px">

*Aggiungere un asterisco a una chiamata e a un indicatore di nota a piè di pagina.*

## Nascondere una chiamata nota a piè di pagina

È inoltre possibile applicare uno stile alle chiamate delle note a piè di pagina con attributi specifici. Ad esempio, utilizzare lo stile seguente per nascondere una nota a piè di pagina con gli ID: La chiamata della nota a piè di pagina è nascosta nel contenuto principale, ma il contrassegno della nota a piè di pagina viene visualizzato nella parte inferiore della pagina.

```css
.fn[id]::footnote-call {
		display: none;
                        }
```

## Formattare l&#39;area delle note a piè di pagina

L&#39;area delle note a piè di pagina è l&#39;area in cui vengono inserite tutte le note a piè di pagina, in genere nella parte inferiore della pagina. È possibile formattare l&#39;area delle note a piè di pagina utilizzando i layout di pagina o gli stili CSS.


### Layout di pagina

È possibile utilizzare le proprietà di pagina per i layout di pagina per applicare uno stile all&#39;area delle note a piè di pagina nelle diverse sezioni di un documento PDF. Ad esempio, potete specificare i margini e le proprietà di riempimento dell&#39;area delle note a piè di pagina di un capitolo. È inoltre possibile modificare il lato del bordo, lo stile, il colore, la larghezza e il raggio.

Scopri come [utilizzare le proprietà di pagina di un layout di pagina](./design-page-layout.md#page-props-page-layout).

### Stili CSS

Potete applicare stili e formattare l&#39;area delle note a piè di pagina in un documento PDF. È ad esempio possibile modificare la lunghezza, lo stile, il colore e la larghezza del bordo.

```css
	@page {
	  @footnote {
   		border-top-style: solid;
   		border-top-color: #FF0000;
   		border-top-width: 3px;
 		        }
	      }
```

## Riavvia la numerazione delle note a piè di pagina

Per impostazione predefinita, le note a piè di pagina vengono numerate continuamente in un documento. Tuttavia, è possibile utilizzare i layout di pagina o gli stili CSS per riavviare la numerazione delle note a piè di pagina.


### Layout di pagina

È possibile specificare un numero nei layout di pagina per riavviare la numerazione delle note a piè di pagina nelle diverse sezioni di un documento PDF. Ad esempio, seleziona un numero dal campo **Riavvia numerazione da** nel pannello Proprietà pagina per riavviare la numerazione delle note a piè di pagina per ciascun capitolo.

### Stili CSS

Usate lo stile seguente per reimpostare la numerazione delle note a piè di pagina in ogni pagina dell&#39;output di PDF:

```css
@page
{
counter-reset: footnote
}
```

Pertanto, le note a piè di pagina di ogni pagina ripartiscono da 1.

## Visualizza note a piè di pagina in linea

In genere, ogni nota a piè di pagina viene visualizzata come un blocco o inizia su una nuova riga. Ma puoi anche metterli uno accanto all&#39;altro o in fila.

```css
.fn{
  	display: inline;
              }
```

## Applicare stili ai rimandi delle note a piè di pagina

Potete anche fare riferimento incrociato a una nota a piè di pagina e fare riferimento più volte alla stessa nota nell&#39;output di PDF. Ciò consente di fare riferimento più volte alla stessa citazione o nota dettagliata nel documento senza creare una nuova nota a piè di pagina.

La schermata seguente mostra ad esempio come la stessa nota a piè di pagina viene usata come riferimento incrociato per tutte le città nell’output di PDF.
<img width="550" alt="riferimenti alle note a piè di pagina in un pdf" src="./assets/link-footnotes.png" border="2px">

*Inserite il rimando a una nota a piè di pagina.*





Utilizzando gli stili CSS, potete anche formattare i riferimenti incrociati alle note a piè di pagina. Ad esempio, potete modificare il colore di sfondo dei riferimenti incrociati.

```css
    .xref-fn{
	background-color: red;
	}
```



