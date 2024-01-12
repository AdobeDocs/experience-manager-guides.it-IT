---
title: Includi attributo @navtitle per impostazione predefinita
description: Scopri come includere @navtitle attributo per impostazione predefinita
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 1%

---

# Includi attributo @navtitle per impostazione predefinita {#id2115BC0J0XA}

È possibile aggiungere diversi tipi di file di riferimento in una mappa, ad esempio mappe di argomenti, riferimenti, attività, sottomappe e così via. La maggior parte di questi file supporta `@navtitle` attributo. Tuttavia, non molti autori lo usano in modo coerente. Se desideri imporre l’utilizzo di `@navtitle` in tutti i file a cui si fa riferimento in una mappa, è possibile farlo con una semplice configurazione.

Una volta attivato, ogni file di riferimento aggiunto in una mappa otterrà automaticamente il `@navtitle` alle relative proprietà. Il `@navtitle` otterrà anche il valore di `title` del contenuto a cui si fa riferimento.

Da includere `@navtitle` per impostazione predefinita, nelle proprietà dei file di riferimento, effettuare le seguenti operazioni:

1. Scarica il file ui\_config.json.

   Puoi apportare questa modifica a livello globale o a livello di cartella. A seconda della posizione in cui desideri apportare questa modifica, devi scaricare il rispettivo file ui\_config.json. Per ulteriori informazioni sul download del file ui\_config.json, vedi [Configurazione e personalizzazione dell&#39;editor Web XML](conf-folder-level.md#id2065G300O5Z).

1. Cerca `ditaAttributes` definizione.

   La definizione predefinita di `ditaAttributes` è:

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Modificare il `required` parametro come:

   ```json
   "required": {"navtitle": true}
   ```

1. Salva il file.

1. Carica il file nel profilo corrispondente \(Global o Folder\).


Con questa configurazione, ogni file di riferimento aggiunto a una mappa conterrà `@navtitle` per impostazione predefinita.
