---
title: Funzione di pubblicazione nativa di PDF | Aggiungi un segnalibro personalizzato nell’output di PDF
description: Scopri come creare fogli di stile di utilizzo e stili per i contenuti.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Aggiungere un segnalibro personalizzato nell’output di PDF

In genere, il sommario di una mappa DITA viene replicato come segnalibro nell&#39;output finale di PDF. Questo sommario viene creato dai titoli di argomento o di sezione nella mappa DITA. A volte può essere utile aggiungere un segnalibro personalizzato a un particolare contenuto nell’output PDF per facilitarne la navigazione. A questo scopo è possibile aggiungere una `outputclass` sull&#39;elemento e applicando il seguente attributo:

`bookmark-level: 3`

Ecco, il `bookmark-level` è un attributo e un numero `3` è il valore che indica il livello nella gerarchia dei segnalibri in cui viene aggiunto il segnalibro. Nell’esempio seguente, l’argomento di primo livello &quot;Contatti&quot; presenta una tabella, &quot;Elenco contatti&quot;, in cui è stata aggiunta una sezione `outputclass` attributo con il valore di `custom-bookmark`.


<img src="./assets/custom-bookmark-attribute.png" width="500">

La seguente definizione di `custom-bookmark` viene aggiunta nel file CSS:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

Nell’output di PDF, il *Elenco contatti* la tabella viene aggiunta al secondo livello dell&#39;elenco dei segnalibri di PDF, come illustrato di seguito:

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">

>[!NOTE]
>
>È necessario scegliere il livello corretto in cui aggiungere il segnalibro personalizzato. Se si specifica un numero inferiore al segnalibro dell&#39;argomento padre, il segnalibro personalizzato assume la posizione del segnalibro padre e tutti gli altri segnalibri vengono visualizzati come figli. Questo può causare una struttura imprevista dei segnalibri.
