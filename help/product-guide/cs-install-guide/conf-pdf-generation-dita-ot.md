---
title: Configurare la generazione di PDF con argomento singolo
description: Scopri come configurare la generazione di PDF per un singolo argomento
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/DinL1ZwovhmP61iQOQkW6XR-ALahlONxOU4e5UXpSGY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 0%

---

# Configurare la generazione di PDF con argomento singolo {#id22ADC70M0XA}

Con AEM Guides, puoi generare il PDF di singoli argomenti o di un intero file di mappa. È possibile pubblicare gli argomenti in formato PDF utilizzando il metodo nativo PDF o DITA-OT. Utilizza il metodo PDF nativo per generare un output PDF ricco di funzioni basato sugli standard W3C CSS3 e CSS paged media. È possibile utilizzare il metodo DITA-OT per generare un output PDF per una mappa dal dashboard delle mappe.

>[!NOTE]
>
> PDF nativo è il metodo predefinito per generare un PDF nella versione corrente di AEM Guides.

Per abilitare la generazione precedente di PDF tramite DITA-OT dalla modalità di anteprima dell&#39;argomento, effettuare le seguenti operazioni:

1. Accedi a Adobe Experience Manager come amministratore e scarica il file di configurazione dell’interfaccia utente.

1. Per farlo, fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto
1. Fai clic sull&#39;icona **Scarica** per scaricare il file ui\_config.json sul sistema locale. Puoi quindi apportare modifiche al file e caricarlo allo stesso modo.
1. Nel file `ui_config.json`, trovare la seguente configurazione:

   ```
   {
                           "component": "button",
                           "variant": "action",
                           "quiet": true,
                           "icon": "filePDF",
                           "title": "Download as PDF",
                           "on-click": "EDITOR_SAVE_AS_PDF"
                           }
   ```

   e sostituirlo con

   ```
   {
                           "component": "button",
                           "icon": "filePDF",
                           "variant": "action",
                           "quiet": true, "title": "Export as PDF",
                           "on-click": "DOWNLOAD_TOPIC_PDF",
                           "show" : ["@isPreviewMode", "@isXmlMode"]
                           }
   ```

1. Salva il file e caricalo.

Dopo aver eseguito i passaggi indicati sopra, se si sceglie lo stesso profilo di cartella da Preferenze utente nell’editor web, verrà visualizzata l’opzione per la generazione di PDF nella modalità di anteprima di un argomento.

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
