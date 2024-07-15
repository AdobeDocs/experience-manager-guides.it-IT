---
title: Introduzione all’archivio delle estensioni
description: Struttura della directory dei pacchetti di estensione di AEM Guides
role: User, Admin
exl-id: 99a00b3e-a5c9-41d8-a73d-8690d587277e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Struttura della directory dei pacchetti di estensione di AEM Guides

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
├── dist
│   ├── guides-extension.js
│   ├── guides-extension.umd.cjs
│   ├── build.css
├── node_modules
├── package.json
├── package-lock.json 
└── .gitignore
└── buildCSS.mjs // for creating tailwind classes
└── vite.config.js // config for specifying TS and javascript build options
└── taliwind.config.js // config for tailwind we can add custom config for a design system here
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```

## /src

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
```

La directory di origine conterrà i file typescript o javascript dell’estensione. Il file index.ts è il punto di ingresso dell&#39;estensione. Puoi importare tutti i componenti qui ed esportarli come un singolo oggetto. Questo oggetto verrà utilizzato dall’estensione per eseguire il rendering dei componenti.

### /dist

Questa è la directory di build finale. Contiene il file JS e CSS finale, che deve essere copiato nell&#39;AEM

```test
├── dist
│   ├── gudies-extension.js // you can either choose es module (this one) or .cjs(other one) file
│   ├── gudies-extension.umd.cjs
│   ├── build.css // this is your tailwind css output
```

## /jsons

Questa directory contiene i JSON per le varie viste. Puoi utilizzare questi JSON per identificare le destinazioni e personalizzare la visualizzazione.

```text
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```
