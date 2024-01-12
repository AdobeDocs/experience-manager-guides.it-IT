---
title: Installazione e configurazione
description: Installazione e utilizzo del pacchetto di estensione delle guide AEM
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---


# Installazione e utilizzo del pacchetto di estensione delle guide AEM

Le estensioni ti offrono l’opportunità di personalizzare l’app Guide AEM in base alle tue esigenze. Questo framework di estensione è supportato dalle guide AEM v4.3 e versioni successive (on-prem) e 2310 (cloud).

## Requisiti

Questo pacchetto richiede [git bash](https://github.com/git-guides/install-git) e npm

## Installazione

Il modo più semplice per avviare l’installazione del framework delle guide AEM è tramite cli

```bash
npx @adobe/create-guides-extension
```

## Aggiunta del codice di personalizzazione

1. Aggiungi file di codice per ciascun componente che desideri estendere nel `src/` directory. Alcuni file di esempio sono già stati aggiunti per te.
2. Ora nella `index.ts` file che si trova in `src/` directory :
   - Importa `.ts` file con le personalizzazioni che desideri aggiungere nella build.
   - Aggiungi le importazioni a `window.extension`
   - Registrare i `id` e importazione corrispondente a `tcx extensions`
   - Consulta l’esempio `/src/index.ts`

## Creazione del codice personalizzato

- Esegui `npm run build` nella directory principale. Otterrai 3 file nella directory, `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Genera output](./../imgs/build_output.png)

## Aggiunta della personalizzazione all’AEM

- Vai a `CRXDE` `crx/de/index.jsp#/`
- Sotto `apps` cartella, crea un nuovo nodo del tipo `cq:ClientLibraryFolder`

![Struttura delle cartelle](./../imgs/crxde_folder_structure.png)

- In `properties` del nodo, seleziona `Multi` aggiungi la seguente proprietà Name: `categories`
Tipo: `String []`
Valore: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

![Proprietà cartella](./../imgs/crxde_folder_properties.png)

- Per aggiungere il file js generato, crea un nuovo file, ad esempio, `tcx1.js` nel nodo creato in precedenza. Aggiungi il codice da `dist/guides-extension.umd.cjs` o `dist/guides-extension.js`. Ora crea un nuovo file `js.txt`, qui aggiungiamo il nome del nostro file js, che in questo caso sarebbe:

```t
#base=.
tcx1.js
```

- Per aggiungere il file CSS generato, creare un nuovo file, ad esempio `tcx1.css` nel nodo creato in precedenza. Aggiungi il codice da `dist/build.css`. Ora crea un nuovo file `css.txt`, qui aggiungiamo il nome del nostro file css, che in questo caso sarebbe:

```t
#base=.
tcx1.css
```

- Esegui una `shift + refresh` per caricare l’app con le personalizzazioni.

## Risoluzione dei problemi

Verifica che tutti i passaggi precedenti siano stati eseguiti correttamente.
Dopo aver aggiunto il codice a tcx.js, assicurati di eseguire un aggiornamento rapido (MAIUSC+AGGIORNA).
Ora apri AEM, fai clic con il pulsante destro del mouse e fai clic su `Inspect`
Vai a Sorgenti e cerca `[node_name].js` (ad esempio: file extensions.js). Eseguire un comando Control / Cmd + D per cercare il file. Se il `.js` esiste già un file con il codice JS da cui hai incollato `dist/guides-extension.umd.cjs` o `dist/guides-extension.js`, la configurazione è completa
