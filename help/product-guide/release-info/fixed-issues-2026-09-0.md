---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2026.09.0
description: Scopri le correzioni di bug nella versione 2026.09.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 2123962f8c168928c9b0a1ee1331e5cfd86db319
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 0%

---

# Sono stati risolti i problemi nella versione 2026.09.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2026.09.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, visualizza [Novità della versione 2026.09.0](./whats-new-2026-09-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.09.0](./upgrade-instructions-2026-09-0.md).

## Editor 2.0

- Copiare una tabella dalla modalità Autore e incollarla nella modalità Autore rimuove attributi come `colwidth` e qualsiasi altro attributo definito in `colspec`, causando la perdita delle impostazioni della larghezza delle colonne. (GUIDES-52916)
- Spazio vuoto immesso immediatamente prima dell&#39;eliminazione di un tag in linea nella cella di una tabella `<entry>`. (GUIDES-49144)

## Authoring

Questa sezione descrive i bug corretti in Authoring comuni sia a Editor 1.0 che a Editor 2.0.

- Nelle schermate a bassa risoluzione, la finestra di dialogo Inserisci parola chiave non viene visualizzata quando si inserisce una parola chiave dalla barra degli strumenti, mentre si apre come previsto quando si utilizza l&#39;opzione **Altro**. (GUIDES-48304)
- Il salvataggio di un argomento quando la convalida Schematron è configurata con un file di regole vuoto mostra un messaggio di errore generico e impreciso. (GUIDES-48106)
- Le regole di schema che utilizzano un contesto di nodo di testo non attivano la convalida. (GUIDES-14500)
- L&#39;inserimento di un riferimento incrociato tramite l&#39;opzione **Collegamento Web** aggiunge un collegamento `scope=local` e modifica il valore `href`, anziché inserire un `scope=external` come previsto. (GUIDES-48457)
- Il salvataggio di una mappa di riferimento determina un riferimento interrotto invece di risolverlo nella mappa corretta quando un autore sposta la mappa di riferimento mentre un altro sta aggiungendo contemporaneamente un riferimento a essa in una mappa non salvata. (GUIDES-47467)

## Gestione risorse

- L’API di stato delle risorse non restituisce lo stato corretto per le risorse il cui percorso contiene una virgola. (GUIDES-49065)
- Il filtro per gli elementi DITA nella barra di ricerca dell’amministratore Assets non applica il valore immesso, pertanto i risultati della ricerca non vengono filtrati. (GUIDES-48450)
- L&#39;utility di eliminazione della versione non viene completata in diversi scenari, inclusi alcuni tipi di file, risorse con metadati mancanti e report di grandi dimensioni, anziché completare l&#39;eliminazione e generare un report accurato. (GUIDES-43453)
- La ridenominazione di una risorsa con un nome di file basato su GUID in un GUID diverso tramite l’operazione Sposta nell’interfaccia utente di Assets sostituisce il GUID univoco originale della risorsa con il nuovo GUID. (GUIDES-43006)

## Pubblicazione

- Quando generi un output AEM Sites (con mappatura di componenti compositi) con una linea di base che esegue il targeting di una versione precedente, il contenuto della pagina mostra correttamente tale versione precedente, ma i metadati della pagina mostrano invece la versione corrente. (GUIDES-49325)
- Quando le pagine vengono replicate utilizzando l’attivazione in blocco, le proprietà di tracciamento della replica vengono impostate solo sulla pagina principale e non sulle pagine figlie, rendendo difficile determinare quale contenuto è cambiato dall’ultima replica. (GUIDES-37871)
- Quando il campo **Etichetta** nella finestra di dialogo Crea/Modifica baseline viene attivato per la prima volta, se si incolla o si digita il primo carattere, i suggerimenti di completamento automatico non verranno filtrati correttamente e nel campo verranno visualizzati tutti i suggerimenti anziché i risultati filtrati.(GUIDES-50143)
- Il filtro dei rami genera pagine aggiuntive per gli argomenti indesiderati utilizzati come `keydef` (contrassegnati come `resource-only ="true"` da DITA-OT). (GUIDES-19701)
- La raccolta di mappe abilita l&#39;opzione **Pubblica** per i predefiniti che non sono ancora stati generati. (GUIDES-50510)
- La sezione Cronologia di pubblicazione non visualizza il testo segnaposto quando una raccolta di mappe appena creata non contiene record di pubblicazione. (GUIDES-50366)
- L&#39;applicazione di un profilo colore ICC a un predefinito PDF nativo causa un errore nella generazione dell&#39;output e i colori CMYK non vengono riprodotti correttamente anche quando si utilizza un percorso di profilo diretto. (GUIDES-47137)
- L&#39;impostazione di smarginatura configurata in un predefinito PDF nativo non viene riflessa nell&#39;output generato. (GUIDES-47034)
- Il campo **Testo prima dell&#39;interruzione** per la continuazione della tabella esegue solo il rendering della stringa localizzata e non sostituisce il segnaposto del numero di pagina. (GUIDES-32872)
- L&#39;elenco dei profili ICC visualizza erroneamente i file DITA invece di mostrare solo i file ICC. (GUIDES-25017)
- I commenti bozza non vengono visualizzati nell’output PDF nativo. (GUIDES-47044)
- Un commento bozza inserito all&#39;interno di un elemento `title` viene visualizzato in modo imprevisto nell&#39;output pubblicato. (GUIDES-10686)
- Nel dashboard Mappa, la selezione di un predefinito diverso attiva una chiamata per recuperare i collegamenti tra pari, generando un’elaborazione aggiuntiva. (GUIDES-53703)

## Traduzione

- Quando si avvia una traduzione utilizzando un progetto XLIFF, viene creato un progetto vuoto che non passa mai a uno stato in corso. (GUIDES-51759)
- Lo spostamento del contenuto da una cartella di lingua a un’altra mediante l’operazione di spostamento delle risorse impedisce agli autori di selezionare tale contenuto per la traduzione nel pannello Traduzione. (GUIDES-49386)
- L&#39;invio di risorse per la traduzione tramite l&#39;opzione **Aggiungi al progetto di traduzione esistente** durante l&#39;elaborazione di un&#39;altra richiesta di traduzione (creazione di un nuovo progetto o richiesta *Aggiungi a esistente*) per lo stesso progetto genera un conflitto. (GUIDES-49354)

## Riferimento

- La selezione della baseline salvata di un predefinito non viene visualizzata correttamente come *Nessuna baseline* dopo l&#39;eliminazione della baseline o durante la creazione di una baseline dinamica. (GUIDES-52690)

## Rivedere

- Il caricamento dell&#39;elenco delle attività richiede un po&#39; di tempo quando si apre il pannello Revisione o si applica un filtro progetto. (GUIDES-48893)

## Rapporti

- La generazione del report Collegamenti interrotti per una mappa con un numero elevato di argomenti fa sì che l&#39;interfaccia del report rimanga bloccata nel **messaggio di recupero dei dettagli dei collegamenti interrotti** per un tempo indefinito, causando la mancata risposta del browser e l&#39;arresto anomalo del browser. (GUIDES-37845)

## Contenuto di apprendimento

- Quando si crea un nuovo argomento di apprendimento utilizzando un HTML o un modello di apprendimento con un’intestazione personalizzata, il titolo dell’argomento non viene visualizzato nell’intestazione personalizzata. (GUIDES-52343)
- La percentuale di precisione calcolata per un quiz del corso differisce leggermente dal valore previsto. (GUIDES-52346)
- Per un corso, quando si tenta di svolgere un quiz, i punteggi ottenuti differiscono leggermente dal punteggio calcolato previsto. (GUIDES-52345)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2026.09.0:

- La modifica dello stato di un documento di un argomento già bloccato aggiorna l&#39;intero documento. (GUIDES-53905)
- Quando si utilizza la funzione Anteprima con baseline, le richieste di anteprima hanno un timeout per le mappe di grandi dimensioni (più di 10.000 argomenti) o per le mappe con un numero elevato di `keydefs` (ad esempio, 100 `keydefs` e 3.500 argomenti). (GUIDES-54147)
- Per i server di database, quando una mappa contenente un `keydef` senza un `href` viene visualizzata in anteprima con l&#39;opzione Anteprima utilizzando la linea di base abilitata, `keydef` non viene risolto. (GUIDES-53878)
- Le aree sensibili configurate in una risorsa mappa immagine non sono interattive in modalità Anteprima, impedendo agli autori di convalidare i collegamenti dei punti attivi prima della pubblicazione. (GUIDES-53398)<br>**Soluzione**: inserire l&#39;immagine da convertire in una mappa immagine, selezionare **Modifica mappa immagine** dal menu di scelta rapida e configurare i collegamenti dei punti attivi.
- Quando si sposta una mappa con una linea di base esistente in una cartella diversa mentre la mappa è aperta, l&#39;opzione **Anteprima con linea di base** rimane selezionata in modalità Anteprima, ma la linea di base non viene più visualizzata nell&#39;elenco a discesa. (GUIDES-54284)<br>**Soluzione**: è possibile chiudere e riaprire la mappa per risolvere il problema.
- In un ambiente AEM Cloud Service appena configurato (AEM as a Cloud Service SDK), il tentativo di creare un file mappa o argomento genera un errore *Impossibile creare il file* oppure *Errore durante il recupero della regola DTD*. (GUIDES-53904)<br>**Soluzione**: è possibile riavviare l&#39;ambiente AEM Cloud Service.
- Quando due autori lavorano contemporaneamente sullo stesso argomento, il blocco di un argomento che è stato aperto per un certo periodo di tempo da un autore non aggiorna le proprietà dei metadati come il numero di versione, le etichette, lo stato del documento, i tag e altri, anche dopo che sono stati modificati dall’altro autore, causando la continua visualizzazione di valori obsoleti. (GUIDES-54810)<br>**Soluzione**: chiudere e riaprire l&#39;argomento per aggiornare i metadati e visualizzare i valori più recenti.