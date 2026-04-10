---
title: Configurare i caratteri speciali consentiti
description: Scopri come configurare i caratteri speciali consentiti
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# Configurare i caratteri speciali consentiti {#id20CIL600035}

L’editor web consente di inserire caratteri speciali pronti all’uso. Tuttavia, è possibile personalizzare l&#39;elenco dei caratteri speciali che gli autori possono inserire nei propri documenti. Se personalizzi l’elenco dei caratteri speciali, questo sovrascrive il set predefinito di caratteri speciali. Solo i caratteri speciali aggiunti nella configurazione vengono resi disponibili agli autori.

Le schede seguenti forniscono istruzioni per sovrascrivere l’elenco predefinito di caratteri speciali in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

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

>[!TAB On-Premise]

1. Accedi ad AEM e apri la modalità CRXDE Lite.

1. creare il file `symbols.json` nel percorso seguente:

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Aggiungere la definizione del carattere speciale nel file `symbols.json` come:

   ```json
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

>[!ENDTABS]

**Argomento padre:**[ Personalizza editor Web](customize-overview.md)
