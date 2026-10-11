---
title: Includi attributo @navtitle per impostazione predefinita
description: Scopri come includere @navtitle attributo per impostazione predefinita
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 80784efb-e897-47cc-a10a-4050236b0fad
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 1%
---
# Includi attributo @navtitle per impostazione predefinita {#id2115BC0J0XA}

È possibile aggiungere diversi tipi di file di riferimento in una mappa, ad esempio mappe di argomenti, riferimenti, attività, sottomappe e così via. La maggior parte di questi file supporta l&#39;attributo `@navtitle`. Tuttavia, non molti autori lo usano in modo coerente. Se si desidera imporre l&#39;utilizzo dell&#39;attributo `@navtitle` in tutti i file a cui si fa riferimento in una mappa, è possibile farlo con una semplice configurazione.

Una volta attivato, ogni file di riferimento aggiunto in una mappa otterrà automaticamente l&#39;attributo `@navtitle` aggiunto alle relative proprietà. `@navtitle` otterrà anche il valore dell&#39;elemento `title` del contenuto a cui si fa riferimento.

Nelle schede seguenti vengono fornite istruzioni per includere l&#39;attributo `@navtitle` per impostazione predefinita nelle proprietà dei file di riferimento in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Per scaricare il file di configurazione dell’interfaccia utente, accedi a Adobe Experience Manager come amministratore.
1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto
1. Fai clic sull&#39;icona **Scarica** per scaricare il file ui\_config.json sul sistema locale.
1. Puoi apportare questa modifica a livello globale o a livello di cartella. A seconda della posizione in cui desideri apportare questa modifica, devi scaricare il rispettivo file ui\_config.json. Per ulteriori informazioni sul download del file ui\_config.json, vedere [Configurare e personalizzare XML Web Editor](conf-profiles.md#id2065G300O5Z).

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

>[!TAB On-Premise]

1. Scarica il file ui\_config.json.

   Puoi apportare questa modifica a livello globale o a livello di cartella. A seconda della posizione in cui desideri apportare questa modifica, devi scaricare il rispettivo file ui\_config.json. Per ulteriori informazioni sul download del file ui\_config.json, vedere [Configurare e personalizzare XML Web Editor](conf-profiles.md#id2065G300O5Z).

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

>[!ENDTABS]

**Argomento padre:**[ Personalizza editor](customize-overview.md)
