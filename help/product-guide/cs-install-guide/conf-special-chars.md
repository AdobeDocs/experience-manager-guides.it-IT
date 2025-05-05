---
title: Configurare i caratteri speciali consentiti
description: Scopri come configurare i caratteri speciali consentiti
exl-id: 7ff4305f-71bb-4155-b8e5-911cea6f0ad9
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Configurare i caratteri speciali consentiti {#id20CIL600035}

L’editor web consente di inserire caratteri speciali pronti all’uso. Tuttavia, è possibile personalizzare l&#39;elenco dei caratteri speciali che gli autori possono inserire nei propri documenti. Se personalizzi l’elenco dei caratteri speciali, questo sovrascrive il set predefinito di caratteri speciali. Solo i caratteri speciali aggiunti nella configurazione vengono resi disponibili agli autori.

Per sovrascrivere l’elenco predefinito di caratteri speciali, effettua le seguenti operazioni:

1. Crea il file `symbols.json` nel percorso seguente nell&#39;archivio Git di Cloud Manager:

   ```
   /apps/fmdita/xmleditor/
   ```

1. Aggiungere la definizione del carattere speciale nel file `symbols.json` come:

   ```
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


La struttura del file `symbols.json` è illustrata di seguito:

- `"label": "Arrows"`: specifica la categoria dei caratteri speciali. Nel frammento è definita una categoria con il nome `"Arrows"`.
- `"items"`: definisce la raccolta di caratteri speciali nella categoria.
- `"name": "←", "title": "Left Arrow"`: definizione del carattere speciale. Inizia con l&#39;etichetta `"name"`, che non deve essere modificata. Il nome è seguito dal carattere speciale. `"title"` è il nome o il titolo del carattere speciale visualizzato come descrizione comando per il carattere speciale.

  All’interno di una categoria è possibile definire più definizioni di caratteri speciali.


**Argomento padre:**&#x200B;[ Personalizza editor Web](conf-web-editor.md)
