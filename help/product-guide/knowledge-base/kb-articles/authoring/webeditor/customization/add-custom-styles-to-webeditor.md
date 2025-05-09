---
title: Aggiungere stili personalizzati all’editor web delle guide
description: Scopri come aggiungere stili personalizzati per modificare l’aspetto dell’editor web Guide.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '261'
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

[utilizza questo collegamento per ulteriori informazioni sul profilo cartella e sulla configurazione del layout del modello CSS](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=it#customize-the-css-template-layout)

Utilizza quanto segue per impostare lo stile precedente nell’editor web:
- Utilizza [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) e caricalo nel profilo cartella che preferisci
- Installa il pacchetto allegato [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) utilizzando Gestione pacchetti AEM per installare le risorse utilizzate nel file CSS precedente

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

Potresti anche essere interessato alla sessione di esperti sulle configurazioni e la personalizzazione dell&#39;editor Web descritta in [Sessione di esperti sull&#39;editor Web](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=it)
