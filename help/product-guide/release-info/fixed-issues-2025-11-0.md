---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2025.11.0
description: Scopri le correzioni di bug nella versione 2025.11.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: d9a46a009477b1110208a509d4ad8c0616139661
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 3%

---

# Sono stati risolti i problemi nella versione 2025.11.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2025.11.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2025.11.0](whats-new-2025-11-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.11.0](upgrade-instructions-2025-11-0.md).

## Authoring

- Se a un file DITAVAL viene aggiunto un elemento `prop` vuoto senza attributi o valori, non è possibile aggiungere ulteriori elementi `prop`. (GUIDES-33597)
- Dopo l&#39;aggiornamento di Experience Manager Guides alla versione 2025.08.0, l&#39;opzione per abilitare o disabilitare la scheda personalizzata **Acrolinx** non viene più visualizzata in **Impostazioni Workspace**. (GUIDES-35261)
- I CSS personalizzati applicati a un profilo a livello di cartella per argomenti o mappe vengono ripristinati allo stile predefinito nella modalità Anteprima dopo l’aggiornamento del browser. (GUIDES-31098)
- Le operazioni **Annulla** e **Ripristina** non funzionano come previsto nella visualizzazione Source dell&#39;editor per i file DITA. (GUIDE-24914, GUIDE-25034)
- Quando si fa riferimento a una mappa DITA in un argomento utilizzando l&#39;elemento `Xref`, viene visualizzato il nome file della mappa di riferimento anziché il titolo della mappa. (GUIDES-21759)
- Quando si aggiungono più file Schematron per la convalida tramite il pannello di destra dell&#39;interfaccia dell&#39;editor, viene visualizzato un errore **I file Schematron non esistono o contengono errori** anche se i file aggiunti sono validi e non contengono errori. (GUIDES-33731)
- Le equazioni di MathML grandi o complesse non vengono visualizzate nell’editor. (GUIDES-29095)

## Gestione risorse

- Quando ricarichi un’immagine modificata tramite l’interfaccia utente di Experience Manager Guides, la rappresentazione originale dell’immagine viene aggiornata ma il contenuto DITA associato continua a visualizzare la versione precedente dell’immagine. (GUIDES-33693)
- Quando si tenta di spostare due o più cartelle dal percorso di origine a un percorso diverso (utilizzando lo strumento Spostamento in blocco), l’operazione non riesce se i nomi delle cartelle iniziano con la stessa stringa (ad esempio, Product e ProductImages). (GUIDES-29096)
- L&#39;eliminazione di una risorsa ricercata dall&#39;interfaccia utente di Omnisearch Assets ignora la finestra di avviso **Forza eliminazione** ed elimina direttamente la risorsa, anche quando vi si fa riferimento nel contenuto DITA esistente. (GUIDES-17232)

## Pubblicazione

- Quando si pubblica una mappa DITA utilizzando la linea di base su AEM Sites (con mappatura di componenti legacy), vengono pubblicati anche gli elementi mappa con l&#39;attributo `processing-role = resource-only`. (GUIDES-37649)
- In alcuni casi, la proprietà `jcr:content/fmUuidOfSource` risulta mancante nelle pagine di output di AEM Sites (con mappatura dei componenti legacy), pertanto le nuove pagine di contenuto create non sono individuabili.
- Il filtro dei contenuti tramite filtri DITAVal e predefiniti condizionali non funziona per la pubblicazione Salesforce. (GUIDES-33515)
- Impossibile creare un predefinito PDF nativo per una mappa se nella gerarchia del contenuto è presente una cartella con lo stesso nome. (GUIDES-33012)
- Quando l&#39;output del PDF nativo viene generato utilizzando una linea di base dinamica, il termine **PDFProject** viene visualizzato come titolo del PDF invece del titolo effettivo della mappa. (GUIDES-31102)
- La generazione dell&#39;output PDF nativo con alcuni valori di attributo `print` nei riferimenti argomento non funziona come previsto. (GUIDES-31101)
- Quando una cartella contenente mappe DITA viene spostata utilizzando l&#39;interfaccia utente di Assets o l&#39;opzione **Spostamento in blocco**, le raccolte di mappe esistenti e le raccolte di attivazione in blocco che fanno riferimento a tali mappe non vengono caricate. (GUIDES-28355)
- Quando sposti una cartella contenente una mappa con predefiniti di condizione, le condizioni non vengono applicate nell’output generato dopo lo spostamento. (GUIDES-28352)
- Quando si genera l&#39;output di AEM Sites utilizzando la mappatura dei componenti legacy, gli argomenti che utilizzano l&#39;attributo `copy-to` vengono pubblicati con il nome dell&#39;argomento `copy-from` invece del nome impostato nell&#39;attributo `copy-to`. (GUIDES-22155)
- L&#39;attivazione di una o più mappe DITA dal **dashboard di pubblicazione in blocco** genera registri di dimensioni eccessive. (GUIDES-20746)

## Platform

- I registri di errori generati durante il caricamento di una risorsa tramite l’interfaccia utente di Assets o la creazione di un nuovo file dall’interfaccia dell’editor utilizzano erroneamente il termine `predecessor` invece di `successor` nel messaggio del registro. (GUIDES-35607)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2025.11.0:

- La creazione di un argomento duplicato utilizzando l&#39;attributo `copy-to` e il riferimento a esso con l&#39;attributo `scope=peer` causa problemi di reindirizzamento nell&#39;output di AEM Sites, dove i collegamenti vengono reindirizzati da AEM Sites (con mappatura di componenti compositi) ad AEM Sites (con mappatura di componenti legacy) e viceversa. (GUIDES-37656)











