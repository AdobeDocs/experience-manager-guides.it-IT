---
title: Pubblicazione del sommario tramite NativePDF
description: Pubblicazione del sommario e di altri elenchi di libri per la mappa di libri dita tramite NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
TQID: https://experienceleague.adobe.com/GyB4TpCF64rEGNgHVPKq4fUCBQsJjqh4jWA0CJC4A-0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 322
ht-degree: 0%

---

# Generare il sommario di Bookmap nella pubblicazione in PDF

## Configurare la mappa dei libri

Includi l&#39;elemento `<toc>`:
All&#39;interno dell&#39;elemento `<frontmatter>` della mappa del libro, individua l&#39;elemento `<booklists>`.  Nidificare un elemento `<toc>` all&#39;interno di `<booklists>` in questo modo:

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

La specifica DITA consente di inserire il sommario e gli elenchi di libri anche nella sezione `<backmatter>`.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Struttura di esempio di bookmap con sommario, elenco di figure e elenco di tabelle in primo piano e elenco di indici in secondo piano.

```
<bookmap>
  <title>My Bookmap Title </title>
  <frontmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <tablelist/>
    </booklists>
  </frontmatter>

  <chapter href="chapter1.ditamap">
  <chapter href="chapter2.ditamap">
  </chapter>

  <backmatter>
    <booklists>
      <indexlist/>
    </booklists>
  </backmatter>
</bookmap>
```

Il sommario e gli elenchi dei libri vengono generati automaticamente in base alla struttura definita nella mappa dei libri.

Una volta configurata la bookmap, utilizza il PDF nativo per generare l’output PDF. Elabora la struttura e i riferimenti della mappa del libro, inclusi il sommario e gli elenchi dei libri.

## Progettazione del sommario e relativo ordine in PDF

La funzionalità PDF nativa offre un metodo pratico per personalizzare il layout e la progettazione del sommario.

È possibile controllare la progettazione tramite layout di pagina separato per sommario e stili tramite layout.css.

L&#39;ordine del sommario e di altri elenchi di libri in PDF si basa solo sulla struttura della mappa di libri.

![sommario](../assets/publishing/toc.png)


## Domande frequenti

### Come includere il sommario di un Ditamap in un PDF

Le diagrammi non dispongono direttamente di un sommario (sommario), come accade invece per le mappe. Tuttavia, le mappe svolgono un ruolo cruciale nella definizione della struttura del contenuto e contribuiscono indirettamente al processo di generazione del sommario.

Se si pubblica Ditamap, Native PDF offre la funzionalità per generare automaticamente sommario ed elenco libri. È possibile abilitare/disabilitare la generazione di sommario in corrispondenza di ditamap dalle impostazioni di Native PDF.

![Abilita Disabilita sommario](../assets/publishing/pageorder.png)

## Risorse aggiuntive :

- [Documentazione del layout della pagina di progettazione nativa di PDF](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Sessione Expert preregistrata sulle funzionalità di base native di PDF](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Pubblica sul [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) della community AEM Guides per qualsiasi domanda.



