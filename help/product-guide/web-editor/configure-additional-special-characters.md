---
title: Configurare caratteri speciali aggiuntivi nella barra degli strumenti dell’editor
description: Scopri come configurare caratteri speciali aggiuntivi nell’editor di AEM Guides.
feature: Web Editor
role: User
exl-id: 0fbc05a5-a6b0-4f6b-bbc4-8fca03581d90
TQID: https://experienceleague.adobe.com/7InE1R4lpkq7cQ6xptqVIyjG4b-2i9klObtxf2y7Cw8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 0%

---

# Come configurare caratteri speciali aggiuntivi nella barra degli strumenti dell’editor per On-Premise

Nella barra degli strumenti dell’editor web è disponibile un’opzione di scelta rapida che consente all’autore di inserire già i caratteri speciali.
Lo stesso può essere visto nella schermata seguente:

![Caratteri speciali](assets/special-chars.png)


L’elenco dei caratteri è configurabile qui. Per aggiungere altri caratteri, effettua le seguenti operazioni:

+ Accedi ad AEM e apri la modalità CRXDE Lite.

+ Crea il file symbols.json nella posizione seguente: &#39;/apps/fmdita/xmleditor/&#39; (puoi copiare il file predefinito da - posizione &#39;/libs/fmdita/clientlibs/clientlibs/xmleditor/symbols.json&#39;)

+ Aggiungi la definizione del carattere speciale nel file symbols.json come:

```
{
      "label": "Logical Symbols",
      "items": [
        {
          "name": "≥",
          "title": "Greater-Than or Equal To"
        },
        {
          "name": "≤",
          "title": "Smaller-Than or Equal To"
        }
      ]
}
```

La struttura del file symbols.json è spiegata di seguito:

+ &quot;label&quot;: &quot;Logical Symbols&quot;: specifica la categoria dei caratteri speciali. Nel frammento è definita una categoria denominata &quot;Simbolo logico&quot;.

+ &quot;items&quot; (elementi): definisce la raccolta di caratteri speciali nella categoria.

+ &quot;name&quot;: &quot;≥&quot;, &quot;title&quot;: &quot;Greater-Than or Equal To&quot;: questa è la definizione del carattere speciale. Inizia con l&#39;etichetta &quot;name&quot;, che non deve essere modificata. Il nome è seguito dal carattere speciale. Il &quot;titolo&quot; è il nome o il titolo del carattere speciale che viene visualizzato come descrizione comando del carattere speciale.

All’interno di una categoria è possibile definire più definizioni di caratteri speciali.

Verrà aggiunta un’altra categoria nella finestra di dialogo dei caratteri speciali:

![Categoria di simboli speciali](assets/special-char-category.png)

![Inserisci carattere speciale](assets/insert-special-char.png)

>[!MORELIKETHIS]
>
>+ [Guida all&#39;installazione e alla configurazione](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-6/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)
