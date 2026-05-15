---
title: Aggiungere stili personalizzati all’editor web delle guide
description: Scopri come aggiungere stili personalizzati per modificare l’aspetto dell’editor web Guide.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/uQc8TTz7dHxbN6-zbin-esQevLoJR-IMR1hchrwEs8M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 300
ht-degree: 0%

---

# Aggiungere stili personalizzati all’editor web delle guide

Questo articolo illustra come aggiungere stili personalizzati per modificare l’aspetto predefinito dell’editor web.

Ciò comporta le seguenti fasi:
- Aggiunta di stili personalizzati tramite la configurazione dell’editor XML del profilo della cartella
- Scelta del rispettivo profilo di cartella nell’editor web e verifica delle modifiche


## Implementazione con un esempio

Comprendiamo questo con un esempio in cui vogliamo mostrare la breve descrizione e il titolo come blocco separato con alcuni aspetti di stile nell’editor.

![Anteprima dell&#39;editor Web con stili personalizzati](../../../assets/authoring/webeditor-customstyles-preview.png)


## Implementazione di


### Aggiunta di CSS personalizzati al profilo della cartella

Utilizza i profili cartella per controllare *css_layout.css* nella scheda &quot;Configurazione editor XML&quot; e aggiungere i CSS con stili personalizzati

[usa questo collegamento per ulteriori informazioni sul profilo cartella e sulla configurazione del layout del modello CSS](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en#customize-the-css-template-layout)

Utilizza quanto segue per impostare lo stile precedente nell’editor web:
- Utilizza [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) e caricalo nel profilo cartella che preferisci
- Installa il pacchetto allegato [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) utilizzando Gestione pacchetti di AEM per installare le risorse utilizzate nel file CSS precedente

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### Test

- Apri editor web
- In Preferenze utente, scegli il profilo di cartella in cui hai aggiunto gli stili personalizzati. Se l’hai aggiunto al profilo globale, probabilmente lo stai già utilizzando.
- Apri un argomento e noterai che l’area di modifica deve avere un’interfaccia utente personalizzata

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## Riferimenti

Potresti anche essere interessato alla sessione di esperti sulle configurazioni e la personalizzazione dell&#39;editor Web descritta in [Sessione di esperti sull&#39;editor Web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=en)
