---
title: Configura il valore predefinito per la vista Tag
description: Scopri come configurare il valore predefinito per la vista Tag
exl-id: 52214459-74b8-47ec-982b-6176145348a8
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Configura il valore predefinito per la vista Tag {#id223GN0M0NDC}

AEM Guides consente di configurare lo stato predefinito per la visualizzazione Tag nell’editor web, per mantenere la visualizzazione Tag attivata o disattivata per impostazione predefinita per la sessione di un nuovo utente.Per configurare il valore predefinito per la visualizzazione Tag, effettua le seguenti operazioni:

1. Scarica il file di configurazione dell’interfaccia utente accedendo a Adobe Experience Manager come amministratore.
1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto.
1. Nella sezione **Configurazione dell&#39;interfaccia utente dell&#39;editor XML**, fare clic sull&#39;icona **Scarica** per scaricare il file `ui_config.json` nel sistema locale.
1. Nel file `ui_config.json`, modificare lo stato di visualizzazione dei tag predefiniti modificando la sezione defaultValues come illustrato di seguito:

   ```json
   "defaultValues":
                   {
                   "tagsView": true
                   }
   ```

1. Salva il file e caricalo.

>[!NOTE]
>
> La preferenza dell&#39;utente nell&#39;editor Web per attivare/disattivare la visualizzazione Tag ha la precedenza su questo valore predefinito. Pertanto, se un utente abilita la Visualizzazione tag dall’editor web, questa rimane abilitata anche nelle sessioni.

**Argomento padre:**&#x200B;[ Personalizza editor Web](conf-web-editor.md)
