---
title: Includi attributo @navtitle per impostazione predefinita
description: Scopri come includere @navtitle attributo per impostazione predefinita
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Includi attributo @navtitle per impostazione predefinita {#id2115BC0J0XA}

È possibile aggiungere diversi tipi di file di riferimento in una mappa, ad esempio mappe di argomenti, riferimenti, attività, sottomappe e così via. La maggior parte di questi file supporta `@navtitle` attributo. Tuttavia, non molti autori lo usano in modo coerente. Se desideri imporre l’utilizzo di `@navtitle` in tutti i file a cui si fa riferimento in una mappa, è possibile farlo con una semplice configurazione.

Una volta attivato, ogni file di riferimento aggiunto in una mappa otterrà automaticamente il `@navtitle` alle relative proprietà. Il `@navtitle` otterrà anche il valore di `title` del contenuto a cui si fa riferimento.

Da includere `@navtitle` per impostazione predefinita, nelle proprietà dei file di riferimento, effettuare le seguenti operazioni:

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Seleziona **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul pulsante **Profilo globale** affiancare.
1. Seleziona la **Configurazione editor XML** e fai clic su **Modifica** icona in alto
1. Fai clic su **Scarica** per scaricare il file ui\_config.json sul sistema locale.
1. Puoi apportare questa modifica a livello globale o a livello di cartella. A seconda della posizione in cui desideri apportare questa modifica, devi scaricare il rispettivo file ui\_config.json. Per ulteriori informazioni sul download del file ui\_config.json, vedi [Configurazione e personalizzazione dell&#39;editor Web XML](conf-folder-level.md#id2065G300O5Z).

1. Cerca `ditaAttributes` definizione.

   La definizione predefinita di `ditaAttributes` è:

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Modificare il `required` parametro come:

   ```
   "required": {"navtitle": true}
   ```

1. Salva il file.

1. Carica il file nel profilo corrispondente \(Global o Folder\).


Con questa configurazione, ogni file di riferimento aggiunto a una mappa conterrà `@navtitle` per impostazione predefinita.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
