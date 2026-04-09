---
title: Note sulla versione | Corretti problemi in Adobe Experience Manager Guides, versione 2026.03.0
description: Scopri le correzioni di bug nella versione 2026.03.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 6eca85f5-d7d3-4486-8b32-8af3a6cce4ee
hidefromtoc: true
source-git-commit: 22ea3fe3ccb974fe3795299f7815e7aae78d41e7
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 3%

---

# Sono stati risolti i problemi nella versione 2026.03.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2026.03.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2026.03.0](whats-new-2026-03-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.03.0](upgrade-instructions-2026-03-0.md).

## Authoring

- Quando si modifica un file Schematron (`*.sch`) e si utilizza la funzione Trova e sostituisci, il pannello Trova e sostituisci appare parzialmente fuori schermo nella parte inferiore, impedendo l&#39;accesso ai relativi campi e controlli di input. (GUIDES-38412)

## Pubblicazione

- Quando lo stesso argomento viene riutilizzato in più mappe con diversi predefiniti condizionali, la pubblicazione della mappa più recente in Salesforce sovrascrive il contenuto dell’argomento, causando la visualizzazione di dati errati agli utenti delle mappe pubblicate in precedenza. (GUIDES-37806)
- Quando si pubblica un PDF nativo per una mappa che include un&#39;elaborazione condizionale o alcune mappe nidificate, l&#39;elemento `dc:title` definito nella mappa non viene visualizzato nella copertina di PDF, causando la perdita del titolo della copertina. (GUIDES-37733)
- La generazione dell&#39;output del sito AEM (mediante la mappatura di componenti compositi) per una mappa non riesce e genera un errore quando la variabile `map_title` è presente nel percorso di output. (GUIDES-36968)
- Quando nel predefinito di output Native PDF viene specificato un percorso di output con una barra finale, l’interfaccia utente aggiunge automaticamente una barra finale aggiuntiva, creando un percorso con doppia barra che in alcuni scenari causa il mancato caricamento di PDF. (GUIDES-34932)
- Quando si pubblicano pagine AEM Sites generate da contenuti DITA tramite Pubblicazione rapida o Gestisci pubblicazione, le risorse DITA associate vengono pubblicate in modo non intenzionale. (GUIDES-27967)
- Quando si pubblica una mappa in AEM Sites (utilizzando il mapping di componenti legacy), i riferimenti incrociati (`xrefs`) con `scope = peer` che eseguono il targeting dei sottoelementi di un argomento (come i paragrafi) in una mappa diversa non vengono risolti nell&#39;ID elemento specifico, ma solo nell&#39;argomento principale, causando il caricamento della pagina all&#39;inizio dell&#39;argomento anziché lo scorrimento alla sezione desiderata. (GUIDES-21802)


## Traduzione

- Quando un&#39;immagine inizialmente gestita come risorsa specifica per la lingua con una versione specifica (ad esempio, in `/en/`) viene spostata in una cartella globale con una versione aggiornata e viene eseguita l&#39;esportazione della linea di base, la nuova linea di base continua a fare riferimento a versioni obsolete specifiche per la lingua dell&#39;immagine, causando un&#39;esportazione della linea di base non riuscita. (GUIDES-39394)
- Durante l&#39;elaborazione dei progetti di traduzione creati all&#39;esterno di Experience Manager Guides, vengono generati più messaggi di registro di errore che indicano che la proprietà *`fmTarget`non è stata trovata*. (GUIDES-37804)

## Riferimento

- Durante la creazione di una linea di base dinamica, a volte l’editor non risponde a causa di più richieste API simultanee, causando l’arresto di tutte le altre operazioni. (GUIDES-39054)

## Rivedere

- Quando si assegna un utente a un’attività di revisione, il menu a discesa elenca tutti gli utenti anziché solo quelli associati ai progetti selezionati, generando opzioni utente non valide. (GUIDES-37781)

## Rapporti

- Quando si apre un report per una mappa, si verifica un ritardo nel caricamento del pannello Filtri (GUIDES-39385)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 2026.03.0:

- Viene caricata una schermata vuota durante la creazione di un predefinito ServiceNow Knowledge Base duplicato. (GUIDES-42732)
- L’API per il recupero dello stato del documento restituisce una risposta null per alcuni file, causando la visualizzazione di stati del documento non corretti nell’interfaccia utente. (GUIDES-42561)
- Le personalizzazioni dell’interfaccia utente basate sui nomi delle schede nel dashboard Mappa non vengono applicate. (GUIDES-42285)
- Quando un file viene aperto sia nell&#39;Editor che nel pannello Ricerca, l&#39;eliminazione dal pannello Esplora risorse rimuove il file e aggiorna l&#39;elenco Esplora risorse, ma l&#39;aggiornamento della pagina continua a visualizzare il file nel pannello Ricerca. (GUIDES-41935)
- Durante l&#39;aggiornamento di un&#39;attività di revisione attiva, se un argomento che fa già parte della revisione viene rimosso e quindi aggiunto di nuovo senza fare clic su **Aggiorna**, le informazioni del revisore nella scheda Revisori andranno perse.   (GUIDES-38774)
- Se si seleziona un argomento in modalità Anteprima, non viene evidenziato nella vista Mappa se l&#39;argomento si trova all&#39;interno di tag di mappa segnalibro (frontmatter, capitolo, parte o backmatter) o parte di contenuto ciclico. (GUIDES-42416)
- Nell&#39;interfaccia utente di Assets, il pulsante **Sposta** non viene attivato al primo tentativo quando sono selezionati più di 2 file o cartelle. (GUIDES-42721) <br> **Soluzione**: dopo aver selezionato più di due file o cartelle, attendere alcuni secondi prima di selezionare la cartella di destinazione.
- Quando si passa a **Preferenze utente** dall&#39;editor e si aggiorna la mappa principale mentre la modalità Anteprima è aperta nell&#39;editor, l&#39;anteprima della mappa viene caricata come una schermata vuota quando si torna all&#39;editor. (GUIDES-42412) <br> **Soluzione**: l&#39;aggiornamento dell&#39;anteprima utilizzando l&#39;icona **Aggiorna** disponibile in modalità Anteprima risolve il problema.
- La ridenominazione di un modello esistente non aggiorna il nome nel pannello **Modelli di output** fino a quando la pagina non viene aggiornata manualmente. (GUIDES-42528)<br> **Soluzione**: aggiorna il browser per visualizzare il nome del modello aggiornato nel pannello Modelli di output.
