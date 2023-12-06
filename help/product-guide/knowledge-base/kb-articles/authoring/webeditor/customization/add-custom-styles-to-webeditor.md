---
title: Aggiungere stili personalizzati all’editor web delle guide
description: Scopri come aggiungere stili personalizzati per modificare l’aspetto dell’editor web Guide.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# Aggiungere stili personalizzati all’editor web delle guide

Questo articolo illustra come aggiungere stili personalizzati per modificare l’aspetto predefinito dell’editor web.

Ciò comporta le seguenti fasi:
- Aggiunta di stili personalizzati tramite la configurazione dell’editor XML del profilo della cartella
- Scelta del rispettivo profilo di cartella nell’editor web e verifica delle modifiche


## Implementazione con un esempio

Comprendiamo questo con un esempio in cui vogliamo mostrare la breve descrizione e il titolo come blocco separato con alcuni aspetti di stile nell’editor.

![Anteprima dell’editor web con stili personalizzati](../../../assets/authoring/webeditor-customstyles-preview.png)


## Implementazione di


### Aggiunta di CSS personalizzati al profilo della cartella

Utilizza i profili cartella per controllare *css_layout.css* nella scheda &quot;XML Editor Configuration&quot; (Configurazione editor XML) e aggiungi i CSS con stili personalizzati

[usa questo collegamento per ulteriori informazioni sul profilo cartella e sulla configurazione del layout del modello CSS](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en#customize-the-css-template-layout)

Utilizza quanto segue per impostare lo stile precedente nell’editor web:

- Utilizzare [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) e caricarlo nel profilo di cartella desiderato
- Installare il pacchetto allegato [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) utilizzo di Gestione pacchetti AEM per installare le risorse utilizzate nel file CSS sopra riportato

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

Potresti anche essere interessato alla sessione di esperti sulle configurazioni e la personalizzazione dell’editor web descritta in [Sessione di esperti sull’editor web](/help/product-guide/knowledge-base/expert-sessions/webbased-authoring-jan2023.md)
