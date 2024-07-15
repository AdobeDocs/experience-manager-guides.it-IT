---
title: Funzionalità nativa di PDF Publish | Aggiungere un segnalibro personalizzato nell’output di PDF
description: Scopri come creare fogli di stile di utilizzo e stili per i contenuti.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Aggiungere un segnalibro personalizzato nell’output di PDF

In genere, il sommario di una mappa DITA viene replicato come segnalibro nell&#39;output finale di PDF. Questo sommario viene creato dai titoli di argomento o di sezione nella mappa DITA. A volte può essere utile aggiungere un segnalibro personalizzato a un particolare contenuto nell’output PDF per facilitarne la navigazione. Per ottenere questo risultato, aggiungere un attributo `outputclass` all&#39;elemento e applicare l&#39;attributo seguente:

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

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">

>[!NOTE]
>
>È necessario scegliere il livello corretto in cui aggiungere il segnalibro personalizzato. Se si specifica un numero inferiore al segnalibro dell&#39;argomento padre, il segnalibro personalizzato assume la posizione del segnalibro padre e tutti gli altri segnalibri vengono visualizzati come figli. Questo può causare una struttura imprevista dei segnalibri.
