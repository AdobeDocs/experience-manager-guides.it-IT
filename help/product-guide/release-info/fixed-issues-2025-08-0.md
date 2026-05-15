---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2025.08.0
description: Scopri le correzioni di bug nella versione 2025.08.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 05fe0e2c-ec65-4aec-a543-9b9a75c82f2c
TQID: https://experienceleague.adobe.com/7J25vfpTwwPyT3-qNF6-LLbPra8EePs5XaKqkAjEk5I
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 713
ht-degree: 6%

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

- Copiare una cartella con un numero elevato di risorse dall’interfaccia utente di Assets causa un timeout API. L&#39;operazione continua a essere eseguita nel backend e viene completata dopo un certo periodo di tempo, ma nell&#39;interfaccia utente non viene visualizzato alcun messaggio di esito positivo o negativo o di notifica. (GUIDES-30900)
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
