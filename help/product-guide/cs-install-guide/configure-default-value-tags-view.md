---
title: Configura il valore predefinito per la vista Tag
description: Scopri come configurare il valore predefinito per la vista Tag
exl-id: 3ab75101-4c23-4e45-bfcf-76c1f5b92c96
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/e-BZ7-itZXflsqHW9-5Vo6ktr9RS73xdIWMZh4BU2MU
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
source-wordcount: 215
ht-degree: 0%

---

# Configura il valore predefinito per la vista Tag {#id223GN0M0NDC}

AEM Guides consente di configurare lo stato predefinito per la visualizzazione Tag nell’editor web, che consente di mantenere la visualizzazione Tag attivata o disattivata per impostazione predefinita per la sessione di un nuovo utente.Per configurare il valore predefinito per la visualizzazione Tag, effettua le seguenti operazioni:

1. Scarica il file di configurazione dell’interfaccia utente accedendo a Adobe Experience Manager come amministratore.
1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti e fare clic su **Profili cartella**.
1. Fai clic sul riquadro **Profilo globale**.
1. Seleziona la scheda **Configurazione editor XML** e fai clic sull&#39;icona **Modifica** in alto.
1. Nella sezione **Configurazione dell&#39;interfaccia utente dell&#39;editor XML**, fare clic sull&#39;icona **Scarica** per scaricare il file `ui_config.json` nel sistema locale.
1. Nel file `ui_config.json`, modificare lo stato di visualizzazione dei tag predefiniti modificando la sezione defaultValues come illustrato di seguito:

```
"defaultValues":
                {
                "tagsView": true
                }
```

1.) Salva il file e caricalo.

>[!NOTE]
>
> La preferenza dell&#39;utente nell&#39;editor Web per attivare/disattivare la visualizzazione Tag ha la precedenza su questo valore predefinito. Pertanto, se un utente abilita la Visualizzazione tag dall’editor web, questa rimane abilitata anche nelle sessioni.

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
