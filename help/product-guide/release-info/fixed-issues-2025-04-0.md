---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2025.04.0
description: Scopri le correzioni di bug nella versione 2025.04.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: ad3e95b5-4903-4387-8e4d-c4b9ba77fee2
TQID: https://experienceleague.adobe.com/v7tg4-eP4JVt9bR0S4Ld4lWb0YbdlT-uJc7PrXPT4Wg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 764
ht-degree: 6%

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


## Rivedere

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
- Si verifica un errore dell&#39;applicazione quando più argomenti di una mappa vengono modificati e quindi chiusi utilizzando l&#39;opzione **Chiudi tutto**, con l&#39;impostazione **Chiedi conferma salvataggio versione alla chiusura** abilitata.(27931)

Adobe ha identificato il seguente problema noto con una soluzione alternativa:

+++Nell’output di AEM Sites, le immagini si interrompono quando la linea di base non viene applicata durante la pubblicazione. (28043)
***Soluzione alternativa:*** Puoi pubblicare tali risorse dalla **interfaccia utente di Assets**, dopo di che il collegamento diventerà operativo.
+++
