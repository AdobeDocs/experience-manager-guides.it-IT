---
title: Installazione e configurazione
description: Installazione e utilizzo del pacchetto di estensione di AEM Guides
role: User, Admin
exl-id: 0304c8d0-35a8-4712-a9af-36557e3b247f
TQID: https://experienceleague.adobe.com/ngU5TVcI7yva051ZscfGCfBb6vEbtG4cvjoOgplqmoA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 1%

---

# Installazione e utilizzo del pacchetto di estensione di AEM Guides

Le estensioni consentono di personalizzare l’app AEM Guides in base alle esigenze. Questo framework di estensione è supportato con AEM Guides v4.3 e versioni successive (on-prem) e 2310 (cloud).

## Requisiti

Questo pacchetto richiede [git bash](https://github.com/git-guides/install-git) e npm

## Installazione

Il modo più semplice per avviare l’installazione del framework AEM Guides è tramite cli

```bash
npx @adobe/create-guides-extension
```

## Aggiunta del codice di personalizzazione

1. Aggiungere file di codice per ogni componente che si desidera estendere nella directory `src/`. Alcuni file di esempio sono già stati aggiunti per te.
2. Ora nel file `index.ts` che si trova nella directory `src/`:
   - Importa i file `.ts` con le personalizzazioni che desideri aggiungere nella build.
   - Aggiungi le importazioni a `window.extension`
   - Registra `id` del componente personalizzato e importazione corrispondente in `tcx extensions`
   - Fare riferimento all&#39;esempio `/src/index.ts`

## Creazione del codice personalizzato

- Eseguire `npm run build` nella directory radice. Si otterranno 3 file nella directory, `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Output di compilazione](./../imgs/build_output.png)

## Aggiunta della personalizzazione ad AEM

- Vai a `CRXDE` `crx/de/index.jsp#/`
- Nella cartella `apps` creare un nuovo nodo di tipo `cq:ClientLibraryFolder`

![Struttura cartella](./../imgs/crxde_folder_structure.png)

- Nel `properties` del nodo, seleziona `Multi` e aggiungi la seguente proprietà
Nome: `categories`
Tipo: `String []`
Valore: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

>[!NOTE]
>
> Per la penultima interfaccia utente, i valori sarebbero: `apps.fmdita.penultimate.xml_editor.page_overrides` e `apps.fmdita.review_overrides`


![Proprietà cartella](./../imgs/crxde_folder_properties.png)

- Per aggiungere il file js generato, crea un nuovo file, ad esempio `tcx1.js` nel nodo creato sopra. Aggiungere il codice da `dist/guides-extension.umd.cjs` o `dist/guides-extension.js`. Ora crea un nuovo file `js.txt`, qui aggiungiamo il nome del nostro file js, che in questo caso sarebbe:

```t
#base=.
tcx1.js
```

- Per aggiungere il file CSS generato, creare un nuovo file, ad esempio `tcx1.css` nel nodo creato sopra. Aggiungere il codice da `dist/build.css`. Ora crea un nuovo file `css.txt`, qui aggiungiamo il nome del nostro file css, che in questo caso sarebbe:

```t
#base=.
tcx1.css
```

- Esegui `shift + refresh` per caricare l&#39;app con le personalizzazioni.

## Risoluzione di problemi

Verifica che tutti i passaggi precedenti siano stati eseguiti correttamente.
Dopo aver aggiunto il codice a tcx.js, assicurati di eseguire un aggiornamento rapido (MAIUSC+AGGIORNA).
Apri AEM, fai clic con il pulsante destro del mouse e fai clic su `Inspect`
Vai a Origini e cerca il file `[node_name].js` (ad esempio, extensions.js). Eseguire un comando Control / Cmd + D per cercare il file. Se il file `.js` esiste con il codice JS incollato da `dist/guides-extension.umd.cjs` o `dist/guides-extension.js`, l&#39;installazione è completa
