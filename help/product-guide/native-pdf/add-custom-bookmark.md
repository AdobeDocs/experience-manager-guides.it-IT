---
title: Funzione di pubblicazione nativa di PDF | Aggiungi un segnalibro personalizzato nell’output di PDF
description: Scopri come creare fogli di stile di utilizzo e stili per i contenuti.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
feature: Output Generation
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/W971ghc9G1ZE80ccDDAEw99d8Wvc-68AK4ELA1EC2uw'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%
---
# Aggiungere un segnalibro personalizzato nell’output di PDF

In genere, il sommario di una mappa DITA viene replicato come segnalibro nell&#39;output finale di PDF, incluso il titolo **Contents** che apre la pagina del sommario se selezionata. Questo sommario viene creato dai titoli di argomento o di sezione nella mappa DITA.

A volte può essere utile aggiungere un segnalibro personalizzato a un particolare contenuto nell’output di PDF per facilitarne la navigazione. Per ottenere questo risultato, aggiungere un attributo `outputclass` all&#39;elemento e applicare l&#39;attributo seguente:

`bookmark-level: 3`

In questo caso `bookmark-level` è un attributo e il numero `3` è il valore che indica il livello nella gerarchia dei segnalibri in cui viene aggiunto il segnalibro. Nell&#39;esempio seguente, l&#39;argomento di primo livello &quot;Contatti&quot; contiene una tabella, &quot;Elenco contatti&quot;, in cui è stato aggiunto un attributo `outputclass` con il valore di `custom-bookmark`.


<img src="./assets/custom-bookmark-attribute.png" width="500">

Nel file CSS viene aggiunta la seguente definizione della classe `custom-bookmark`:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

Nell&#39;output di PDF, la tabella *Elenco contatti* viene aggiunta al secondo livello nell&#39;elenco dei segnalibri di PDF, come illustrato di seguito:

![](assets/custom-bookmark-in-pdf-output.png) {width="300"}

>[!NOTE]
>
>È necessario scegliere il livello corretto in cui aggiungere il segnalibro personalizzato. Se si specifica un numero inferiore al segnalibro dell&#39;argomento padre, il segnalibro personalizzato assume la posizione del segnalibro padre e tutti gli altri segnalibri vengono visualizzati come figli. Questo può causare una struttura imprevista dei segnalibri.

**Rimozione del titolo del contenuto dai segnalibri di output di PDF**

Se non si desidera includere il titolo **Contents** nell&#39;output di PDF, è possibile rimuoverlo inserendo **Contents** nell&#39;elemento `<p>` anziché nell&#39;elemento `<h1>`.

La procedura dettagliata per rimuovere il titolo Contens dai segnalibri è la seguente:

1. Aprire il modello PDF utilizzato per l&#39;output PDF.
2. Apri la **pagina sommario** in **Layout di pagina**.
La pagina del sommario viene visualizzata a destra.
3. Passare alla modalità **Source** e modificare l&#39;elemento in cui si trova il contenuto da `<h1>` a `<p>`.

Prima della modifica:

```
<h1 class="toc-title">Contents</h1>
```

Dopo la modifica:

```
<p class="toc-title">Contents</p>
```

Salva le modifiche e rigenera l’output.





