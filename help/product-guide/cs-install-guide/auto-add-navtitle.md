---
title: Includi attributo @navtitle per impostazione predefinita
description: Scopri come includere @navtitle attributo per impostazione predefinita
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/h8rkQYPX4uJRWTdJKIHmdGrzbCIh--HtTrhsQ5QeuL8
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
source-wordcount: 326
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
