---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2025.04.0
description: Scopri le correzioni di bug nella versione 2025.04.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 9a943a26a22b64035b61c72c47268a0de2c23b7f
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 3%

---

# Sono stati risolti i problemi nella versione 2025.04.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2025.04.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2025.04.0](whats-new-2025-04-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.04.0](upgrade-instructions-2025-04-0.md).

## Authoring

- Impossibile caricare la casella di inserimento dei caratteri speciali nell’editor per le impostazioni internazionali tedesche. (24537)
- I commenti e le etichette aggiunti durante il salvataggio di una nuova versione di un file DITAVAL non vengono salvati nella cronologia delle versioni con la nuova versione. (24076)
- I riferimenti in uscita e in entrata in **Proprietà file** nel pannello di destra non vengono aggiornati correttamente quando si passa da un file di mappa all&#39;altro. Questo problema si verifica in modo specifico quando i file di mappa contengono un numero elevato di riferimenti. (23344)
- Il filtro dell&#39;archivio non mantiene l&#39;ordine dei filtri personalizzati definiti in `ui_config.json`. (21193)
- L&#39;eliminazione di più righe di testo in un elemento `codeblock` crea uno spazio vuoto che non può essere rimosso dalla visualizzazione Autore. (20672)
- Non è possibile generare nuovi ID per gli elementi quando questi vengono aggiunti tramite snippet o creati tramite modelli, anche quando l&#39;opzione **genera automaticamente ID** è abilitata in `XMLEditorConfig`. (21734)
- La creazione di una nuova risorsa DITA dai modelli DITA copia le proprietà di replica dai modelli DITA corrispondenti. (25145)
- Impossibile accedere alle proprietà del file dal pannello dell’archivio se il nome della cartella principale include il carattere &quot;&amp;&quot;. (25762)
- La chiusura di un file di argomento consente di salvarlo come nuova versione, anche quando l&#39;argomento è bloccato. Questo problema si verifica in modo specifico quando l&#39;opzione **Richiedi nuova versione alla chiusura** è abilitata in `XMLEditorConfig`. (23875)
- La larghezza massima corrente del pannello dell’archivio nasconde i titoli degli argomenti e delle mappe quando la gerarchia dei contenuti è profondamente nidificata. (27751)

## Pubblicazione

- Nell’output legacy di AEM Sites, i collegamenti di sezione all’interno di argomenti nidificati di una mappa non vengono risolti correttamente se impostati manualmente in modalità Source o se il contenuto viene importato da un’origine esterna. Invece di passare alla sezione desiderata, vengono reindirizzati all’argomento principale che contiene l’argomento nidificato. (26103)
- Se l&#39;attributo `scope=external` non è presente nei collegamenti esterni in un argomento DITA, la pubblicazione di HTML5 non riesce senza indicare i file in cui l&#39;attributo non è presente nei log degli errori, in particolare quando il microservizio è abilitato. (25969)
- Impossibile incorporare collegamenti video in PDF nativo anche quando l&#39;opzione **Incorpora file multimediali** è abilitata nel predefinito PDF. (9989)
- Impossibile passare le proprietà dei metadati per mappare le pagine di destinazione generate con la nuova pubblicazione AEM Sites. (27288)

## Gestione

- Lo stato del documento della copia di lavoro di un argomento viene visualizzato rispetto a tutte le versioni di tale argomento nell&#39;interfaccia utente Traduzione e baseline. (20674)


## Rivedi

- L’aggiornamento dei dettagli di un’attività di revisione nel dashboard Revisione non conferma se l’aggiornamento è stato eseguito correttamente o meno. (8051)

## Traduzione

- Le traduzioni inviate tramite Experience Manager Guides non includono le risorse associate, pertanto il pulsante **Avvia** per il processo di traduzione non sarà più disponibile per gli utenti.

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2025.04.0:

- Il conteggio dei riferimenti nell’interfaccia utente della baseline non viene aggiornato in seguito alla modifica della baseline. Si aggiorna solo quando le modifiche vengono salvate. (28015)
- Quando nell&#39;editor sono aperte più schede, l&#39;esecuzione di un&#39;operazione **Annulla** nella visualizzazione **Source** di un file ripristina l&#39;ultima modifica, ma passa anche alla scheda aperta in precedenza. (27891)
- L&#39;opzione **Controllo ortografia di AEM** viene visualizzata nell&#39;elenco a discesa **Menu** anche quando l&#39;opzione **Controllo ortografia del browser** è abilitata nelle impostazioni dell&#39;editor. (27993)
- Quando modifichi un&#39;immagine nell&#39;interfaccia utente di Assets e la salvi, viene creata e visualizzata una versione aggiuntiva nel pannello **Cronologia versioni**. (28001)
- Quando si incolla nuovo contenuto in una nuova riga all&#39;interno di un elemento `codeblock`, viene inserita automaticamente una riga vuota.(27842)
- Il passaggio da un predefinito all&#39;altro che utilizza la stessa linea di base disattiva il pulsante **Salva** per il predefinito corrente. (28025)
- Un argomento all&#39;interno di una mappa DITA non viene pubblicato nell&#39;output di AEM Sites quando viene utilizzato sia come `keydef` che come `topicref` all&#39;interno delle relative mappe secondarie. (22269)
- Nell’output di AEM Sites, le immagini si interrompono quando la linea di base non viene applicata durante la pubblicazione. (28043)
- Si verifica un errore dell&#39;applicazione quando più argomenti di una mappa vengono modificati e quindi chiusi utilizzando l&#39;opzione **Chiudi tutto**, con l&#39;impostazione **Chiedi al salvataggio della versione alla chiusura** abilitata.(27931)







