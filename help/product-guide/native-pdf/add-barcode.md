---
title: Funzione di pubblicazione nativa di PDF | Aggiungi codice a barre
description: Scopri come aggiungere codici a barre.
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Aggiungere un codice a barre all&#39;output PDF

I codici a barre sono utili per includere informazioni che possono essere facilmente elaborate dalle macchine. Allo stesso modo, i codici QR vengono utilizzati per i collegamenti che i lettori possono aprire con i propri dispositivi mobili.

Questo tutorial ti aiuta ad aggiungere codici a barre sopra ogni pagina nell’output di PDF.

## Passaggi per generare un codice a barre

Per generare un codice a barre, effettuare le seguenti operazioni:

### Aggiungere un ID risorsa alla mappa DITA

Aggiungere un elemento ID risorsa alla mappa DITA. L’ID risorsa funge da input principale per generare il codice a barre.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<map id="GUID-3c330691-4dac-4020-904a-d2d6246aeeb1-en">
  <title>Barcode Sample</title>
  <topicmeta>
    <resourceid id="7a5bda1c-b1db-4fd8-8763-a731e2e8abba">
    </resourceid>
  </topicmeta>
  <topicref href="GUID-139f6c64-bea3-4f17-8b22-ee131557e249-en.dita" type="topic">
  </topicref>
</map>  
```

Puoi anche modificare l’ID risorsa nella modalità Authoring.

<img src="./assets/barcode-map.png" alt="Output di esempio con codice a barre" width="700" border="2px solid blue">


### Aggiungi un segnaposto per codice a barre nell’intestazione del modello

Modifica il `Common.plt` file in **Base** modello per aggiungere un codice a barre dopo il titolo del progetto.

```html
...
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
...
```


### Aggiornare il CSS del modello per eseguire il rendering di un valore di codice a barre

Modifica il `content.css` per eseguire il rendering di un codice a barre durante la generazione di PDF. Sono supportati vari tipi di codice a barre come &quot;qrcode&quot; e &quot;pdf417&quot;.  Per ulteriori dettagli, consulta [Tipi di codice a barre](#barcode-types).



```css
...
.barcode {
  -ro-replacedelement: barcode;
  -ro-barcode-type: code128;
}
...
```

Dopo aver eseguito i passaggi precedenti, puoi generare l’output PDF con un codice a barre.

La schermata seguente mostra un codice a barre di esempio in un output PDF.

<img src="./assets/barcode-output-sample.png" alt="Output di esempio con codice a barre" width="700">


## Tipi di codice a barre {#barcode-types}

| Tipo | Attributo CSS | Attributi aggiuntivi |
| ------------------------------- | ----------------------- | -------------------------- |
| Codice QR | qrcode |                            |
| PDF 417 | pdf417 |                            |
| DataMatrix | data-matrix |                            |
| Codice Aztec | codice azteco |                            |
| Matrice griglia | griglia a matrice |                            |
| Maxicode | modalità maxicode 4 |                            |
| Micro QR | microqr |                            |
| Codice uno | code-one |                            |
| Blocco codice F | codablockf |                            |
| GS1 Databar Limited | databar-limited |                            |
| Databar GS1 omnidirezionale | databar omnidirezionale |                            |
| EAN-13 | ean-13 |                            |
| GS1-128 (EAN-128) | code128 | -codifica ro-barcode-encoding: gs1; |
| ITF-14 | itf14 |                            |
| UPC-A | upc-a |                            |
| Codice 128 | code128 |                            |
| Interfoliazione 2 di 5 | code2of5 interleaved |                            |
| POSTNET | postnet |                            |
| Codice postale olandese | kixcode |                            |
| Post Corea | korea-post |                            |
| Codice postale Deutsche Post | dp-leitcode |                            |
| Post Australia | auspost |                            |
| Logmars | logmars |                            |
| Codice Farmacologico | codice farmacologico |                            |
| USPS OneCode (posta intelligente) | usps-onecode |                            |


