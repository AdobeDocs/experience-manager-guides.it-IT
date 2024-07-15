---
title: Configurare la generazione di PDF con argomento singolo
description: Scopri come configurare la generazione di PDF per un singolo argomento
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Configurare la generazione di PDF con argomento singolo {#id22ADC70M0XA}

Con AEM Guides, puoi generare le PDF di singoli argomenti o di un intero file di mappa. È possibile pubblicare gli argomenti in formato PDF utilizzando il metodo nativo PDF o DITA-OT. Utilizza il metodo PDF nativo per generare un output PDF ricco di funzioni basato sugli standard W3C CSS3 e CSS paged media. È possibile utilizzare il metodo DITA-OT per generare un output PDF per una mappa dal dashboard delle mappe.

>[!NOTE]
>
> Native PDF è il metodo predefinito per generare un PDF nella versione corrente di AEM Guides.

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

Dopo aver eseguito i passaggi indicati sopra, se si sceglie lo stesso profilo di cartella da Preferenze utente nell’editor Web, verrà visualizzata l’opzione per la generazione di PDF nella modalità di anteprima di un argomento.

**Argomento padre:**[ Personalizza editor Web](conf-web-editor.md)
