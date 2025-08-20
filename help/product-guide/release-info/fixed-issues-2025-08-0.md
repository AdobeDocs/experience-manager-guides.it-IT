---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides, versione 2025.08.0
description: Scopri le correzioni di bug nella versione 2025.08.0 di Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 5abe5c153d8cedc7b555d6ca82709557cc38d28f
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 3%

---

# Sono stati risolti i problemi nella versione 2025.08.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2025.08.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2025.08.0](whats-new-2025-08-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2025.08.0](upgrade-instructions-2025-08-0.md).

## Authoring

- I file **CSS** e **Layout di pagina** nei modelli PDF nativi presentano un comportamento di blocco dei file incoerente, che consente di apportare modifiche anche quando i file sono bloccati. (GUIDES-26688)
- L’aggiornamento della pagina dopo l’aggiunta di pulsanti personalizzati al pannello sinistro crea schede duplicate. (GUIDES-30899)
- Quando si aggiunge contenuto XML contenente parentesi angolari (ad esempio &lt;/ o />) all&#39;interno di un elemento `code block` in un argomento, l&#39;elemento blocco di codice appare vuoto nell&#39;output finale. (GUIDES-31007)
- I valori delle variabili globali `canCheckIn` e `canCheckOut` non vengono impostati correttamente quando un file viene estratto e archiviato dalla barra degli strumenti dell&#39;editor.(GUIDES-29890)
- Quando si apre una mappa DITA con la shell unificata attivata, l&#39;editor viene aggiornato in modo intermittente.(GUIDES-26919)
- Quando una mappa DITA è selezionata nella vista Mappa, il conteggio delle selezioni non viene visualizzato correttamente in un primo momento perché i nodi figlio della mappa non sono selezionati. Il conteggio corretto delle selezioni e l’inclusione di tutti i nodi figlio si riflettono solo sulla selezione successiva. (GUIDES-25663)
- I file Markdown non vengono recuperati quando si esegue una ricerca nel pannello Archivio utilizzando il filtro **Argomento DITA**. Inoltre, **Trova e sostituisci** non funziona per i file Markdown e il contenuto correlato. (GUIDES-27133)
- Impossibile personalizzare il menu a discesa **Menu** della barra degli strumenti dell&#39;editor utilizzando il framework delle estensioni. Di conseguenza, non è possibile nascondere o visualizzare i pulsanti esistenti o aggiungere nuovi pulsanti nel menu a discesa. (GUIDES-28748)

## Gestione risorse

- Copiare una cartella con un numero elevato di risorse dall’interfaccia utente di Assets causa un timeout API. L’operazione continua a essere eseguita nel backend e viene completata dopo un certo periodo di tempo, ma nell’interfaccia utente non viene visualizzato alcun messaggio di esito positivo o negativo o di notifica. (GUIDES-30900)
- L’operazione di copia e incolla eseguita su una cartella nell’interfaccia utente di Assets non riesce a causa di errori di post-elaborazione. (GUIDES-30840)
- L’operazione di copia e incolla non riesce per le cartelle contenenti risorse composte (risorse con risorse secondarie) nell’interfaccia utente di Assets. (28107)
- Le cartelle con un numero elevato di risorse non vengono caricate correttamente nel repository. (GUIDES-32500)
- I nomi dei nodi delle cartelle non vengono visualizzati correttamente al posto dei titoli delle cartelle nell’editor. (GUIDES-32402)
- Si verifica un errore durante il caricamento di risorse con caratteri non supportati o non consentiti nei nomi dei file. (GUIDES-28845)

## Pubblicazione

- Nell’output del PDF nativo, l’elenco degli indici (LOI) viene visualizzato in ordine non alfabetico e i termini degli indici nidificati non vengono raggruppati correttamente, rendendo difficile la navigazione nell’indice. (GUIDES-29090)
- L&#39;elenco a discesa **Modello per pagina mappa** e **Modello per pagina argomento** nella pagina predefinita di output di mappatura dei componenti di AEM Sites appare vuoto se il percorso di destinazione contiene una variabile con due punti. (GUIDES-28119)
- Quando una mappa DITA contiene diversi tipi di riferimenti ad argomenti quali Concetto, Riferimento o Attività e viene unita utilizzando l&#39;attributo `chunk=to-content` per generare output a pagina singola in AEM Sites con mappatura dei componenti, il contenuto non viene pubblicato correttamente a causa di errori di pubblicazione. (GUIDES-28118)

## Riferimento

- Copiando una mappa DITA dall&#39;interfaccia utente di Assets, anche la Baseline associata viene copiata nella nuova mappa. (GUIDES-11227)

## Home page

- La home page diventa vuota se uno dei file elencati nel widget **File recenti** è basato su un modello il cui modello di origine non include una miniatura. (GUIDES-31506)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2025.08.0:

- Quando un file aperto nell&#39;editor viene rinominato o spostato, il passaggio tra le modalità (ad esempio **Autore**, **Anteprima** e altre) aggiorna il contenuto nell&#39;area di modifica ma non evidenzia visivamente la modalità attiva nell&#39;angolo in basso a destra. (GUIDES-32719) <br> **Soluzione**: aggiorna la pagina per risolvere il problema.
- Le immagini con spazi nei nomi dei file non vengono visualizzate nell’output quando vengono contrassegnate utilizzando gli attributi condizionali. (GUIDES-33858)
- Nel pannello **Proprietà contenuto**, il campo Attributi si chiude automaticamente quando si tenta di aggiornare un riferimento dalla finestra di dialogo **Aggiorna collegamento**, impedendo l&#39;aggiornamento del collegamento. (GUIDES-17767)



