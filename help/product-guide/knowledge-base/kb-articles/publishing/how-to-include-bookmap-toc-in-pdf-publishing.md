---
title: Pubblicazione del sommario tramite NativePDF
description: Pubblicazione del sommario e di altri elenchi di libri per la mappa di libri dita tramite NativePDF
feature: Native PDF Output
role: User, Admin
source-git-commit: 6ccaef5d35d492fe8dbe0f8b52af8d11258f3d2a
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Generare il sommario di Bookmap nella pubblicazione PDF

## Configurare la mappa dei libri

Includi `<toc>`  elemento: all’interno della mappa `<frontmatter>`, individuare il `<booklists>` elemento.  Nidifica a `<toc>` elemento all&#39;interno di `<booklists>` così:

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

La specifica DITA consente di inserire il sommario e gli elenchi di libri all&#39;interno del `<backmatter>` sezione.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Il sommario e gli elenchi dei libri vengono generati automaticamente in base alla struttura definita nella mappa dei libri.

Una volta configurata la bookmap, utilizza Native PDF per generare l’output di PDF. Elabora la struttura e i riferimenti della mappa del libro, inclusi il sommario e gli elenchi dei libri.

## Progettazione del sommario e relativo ordine in PDF

La funzionalità PDF nativa offre un metodo pratico per personalizzare il layout e la progettazione del sommario.

È possibile controllare la progettazione tramite layout di pagina separato per sommario e stili tramite layout.css.

L&#39;ordine del sommario e di altri elenchi di libri in PDF si basa solo sulla struttura di bookmap.

![sommario](../assets/publishing/toc.png)


## Domande frequenti

- ### Come includere il sommario di un Ditamap in un PDF

Le diagrammi non dispongono direttamente di un sommario (sommario), come accade invece per le mappe. Tuttavia, le mappe svolgono un ruolo cruciale nella definizione della struttura del contenuto e contribuiscono indirettamente al processo di generazione del sommario.

Se si pubblica Ditamap, Native PDF offre la funzionalità per generare automaticamente sommario ed elenco libri . È possibile abilitare/disabilitare la generazione di sommario in corrispondenza di ditamap dalle impostazioni di Native PDF.

![Abilita Disabilita sommario](../assets/publishing/pageorder.png)

## Risorse aggiuntive :

- [Documentazione del layout della pagina di progettazione nativa di PDF](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Sessione Expert preregistrata sulle funzionalità di base di PDF native](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Pubblica le tue domande nella community delle guide AEM [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) per qualsiasi query.

