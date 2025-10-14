---
title: Includi attributo @navtitle per impostazione predefinita
description: Scopri come includere @navtitle attributo per impostazione predefinita
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: a3c7973868549c72e868c05a3fc6ca8bdce9bce3
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 0%

---

# Includi attributo @navtitle per impostazione predefinita {#id2115BC0J0XA}

È possibile aggiungere diversi tipi di file di riferimento in una mappa, ad esempio mappe di argomenti, riferimenti, attività, sottomappe e così via. La maggior parte di questi file supporta l&#39;attributo `@navtitle`. Tuttavia, non molti autori lo usano in modo coerente. Se si desidera imporre l&#39;utilizzo dell&#39;attributo `@navtitle` in tutti i file a cui si fa riferimento in una mappa, è possibile farlo con una semplice configurazione.

Una volta attivato, ogni file di riferimento aggiunto in una mappa otterrà automaticamente l&#39;attributo `@navtitle` aggiunto alle relative proprietà. `@navtitle` otterrà anche il valore dell&#39;elemento `title` del contenuto a cui si fa riferimento.

Per includere l&#39;attributo `@navtitle` per impostazione predefinita nelle proprietà dei file di riferimento, eseguire la procedura seguente:

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto
1. Fai clic sull&#39;icona **Scarica** per scaricare il file ui\_config.json sul sistema locale.
1. Puoi apportare questa modifica a livello globale o a livello di cartella. A seconda della posizione in cui desideri apportare questa modifica, devi scaricare il rispettivo file ui\_config.json. Per ulteriori informazioni sul download del file ui\_config.json, vedere [Configurare e personalizzare XML Web Editor](conf-folder-level.md#id2065G300O5Z).

1. Cercare la definizione `ditaAttributes`.

   La definizione predefinita di `ditaAttributes` è:

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Modifica il parametro `required` come mostrato di seguito:

   ```
   "required": {"navtitle": true}
   ```

   Se è impostato su `true`, il pulsante **Aggiorna attributo titolo navigazione** è attivato per essere visualizzato nella barra degli strumenti dell&#39;editor. Se impostato su `false` o lasciato vuoto, il pulsante rimane nascosto nell&#39;editor.
1. Salva il file.

1. Carica il file nel profilo corrispondente \(Global o Folder\).


Con questa configurazione, ogni file di riferimento aggiunto a una mappa conterrà l&#39;attributo `@navtitle` per impostazione predefinita.



**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
