---
title: Includi attributo @navtitle per impostazione predefinita
description: Scopri come includere @navtitle attributo per impostazione predefinita
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/bwVOZrkVrn6QPq7BoUttFvnFAzdLIL6--JGCoHYkA0o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 1%

---

# Includi attributo @navtitle per impostazione predefinita {#id2115BC0J0XA}

È possibile aggiungere diversi tipi di file di riferimento in una mappa, ad esempio mappe di argomenti, riferimenti, attività, sottomappe e così via. La maggior parte di questi file supporta l&#39;attributo `@navtitle`. Tuttavia, non molti autori lo usano in modo coerente. Se si desidera imporre l&#39;utilizzo dell&#39;attributo `@navtitle` in tutti i file a cui si fa riferimento in una mappa, è possibile farlo con una semplice configurazione.

Una volta attivato, ogni file di riferimento aggiunto in una mappa otterrà automaticamente l&#39;attributo `@navtitle` aggiunto alle relative proprietà. `@navtitle` otterrà anche il valore dell&#39;elemento `title` del contenuto a cui si fa riferimento.

Per includere l&#39;attributo `@navtitle` per impostazione predefinita nelle proprietà dei file di riferimento, eseguire la procedura seguente:

1. Scarica il file ui\_config.json.

   Puoi apportare questa modifica a livello globale o a livello di cartella. A seconda della posizione in cui desideri apportare questa modifica, devi scaricare il rispettivo file ui\_config.json. Per ulteriori informazioni sul download del file ui\_config.json, vedere [Configurare e personalizzare XML Web Editor](conf-folder-level.md#id2065G300O5Z).

1. Cercare la definizione `ditaAttributes`.

   La definizione predefinita di `ditaAttributes` è:

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Modifica il parametro `required` come:

   ```json
   "required": {"navtitle": true}
   ```

1. Salva il file.

1. Carica il file nel profilo corrispondente \(Global o Folder\).


Con questa configurazione, ogni file di riferimento aggiunto a una mappa conterrà l&#39;attributo `@navtitle` per impostazione predefinita.
