---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides 5.2.0 Service Pack 3
description: Scopri le correzioni di bug nella versione 5.2.0 Service Pack 3 di Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: a3144f0078b2073289043befacc5e2358b9c0e02
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%
---
# Sono stati risolti i problemi nella versione 5.2.0 Service Pack 3 (novembre 2026)

Questo articolo descrive i bug corretti in varie aree della versione 5.2.0 Service Pack 3 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 5.2.0 Service Pack 3](upgrade-instructions-5-2-0-sp3.md).

## Editor 2.0

- Copiare una tabella dalla modalità Autore e incollarla nella modalità Autore rimuove attributi come `colwidth` e qualsiasi altro attributo definito in `colspec`, causando la perdita delle impostazioni della larghezza delle colonne. (GUIDES-52916)
- Quando si incolla una tabella da Microsoft Word, vengono create le celle della riga di intestazione, ma il loro contenuto viene perso. (GUIDES-49847)
- Quando il codice viene incollato in un elemento `codeblock`, da Microsoft Word o da editor di testo simili, utilizzando la combinazione di tasti Ctrl+V, le interruzioni di riga e gli spazi iniziali vengono persi e il codice viene appiattito in un&#39;unica riga. (GUIDES-33247)

## Gestione risorse

- L’API di stato delle risorse non restituisce lo stato corretto per le risorse il cui percorso contiene una virgola. (GUIDES-49065)

## Pubblicazione

- Quando si pubblica una mappa DITA con `processing-role=resource-only` elementi in AEM Sites (con mappatura dei componenti legacy), vengono generate pagine del sito orfane per tali elementi in scenari aggiuntivi, ad esempio elementi `topicgroup` e configurazioni di contenuto specifiche. (GUIDES-37650)
- Il filtro dei rami genera pagine aggiuntive per gli argomenti indesiderati utilizzati come `keydef` (contrassegnati come `resource-only ="true"` da DITA-OT). (GUIDES-19701)
- Nel dashboard Mappa, la selezione di un predefinito diverso attiva una chiamata per recuperare i collegamenti tra pari, generando un’elaborazione aggiuntiva. (GUIDES-53703)
- Nell&#39;output PDF nativo, i riferimenti ad argomenti contrassegnati con l&#39;attributo `toc="no"` sono ancora inclusi nel sommario, creando un sommario lungo e disordinato. (GUIDES-20156)
- In alcuni casi, quando una mappa DITA completa viene generata e pubblicata in AEM Sites utilizzando una linea di base dinamica, alcuni argomenti vengono pubblicati con versioni precedenti o non approvate anziché con le versioni approvate correnti. (GUIDES-55646)
- Durante l&#39;elaborazione di un numero elevato di risorse, `PurgePresetExecutionDataJob` a volte rileva un `RuntimeNodeTraversalException` non gestito, causando il blocco del processo in un ciclo infinito e la generazione di registri eccessivi. (GUIDES-53897)
- Nell&#39;output PDF nativo, l&#39;attributo `outputclass` impostato su un elemento `topichead` o `topicgroup` non viene applicato o riportato alla sezione PDF risultante. (GUIDES-22950)
- In alcuni casi, durante la pubblicazione con il motore di PDF nativo v1, l&#39;ordine di lettura del contenuto con accessibilità `settingsenabled` non è corretto. I numeri di pagina dei piè di pagina vengono letti prima del contenuto principale e non alla fine.(GUIDES-27790)


## Traduzione

- L’applicazione di una linea di base a una mappa con molte risorse ritarda il caricamento del rapporto di traduzione per la lingua selezionata, talvolta causando un timeout della richiesta prima del rendering del rapporto. (GUIDES-45508)
- I gruppi di lingue nella scheda Traduzione in Impostazioni Workspace non vengono mantenuti quando la cartella della lingua selezionata utilizza un codice locale sillabato (ad esempio, `da-DK`) invece di un formato di sottolineatura (`da_dk`). (GUIDES-37843)
- Quando si avvia una traduzione utilizzando un progetto XLIFF, viene creato un progetto vuoto che non passa mai a uno stato in corso. (GUIDES-51759)
- L&#39;impostazione `propagateVersionLabel` nel profilo della cartella globale viene reimpostata in modo intermittente su `false` quando un utente con il solo ruolo Collaboratore accede all&#39;editor. (GUIDES-51870)

## Riferimento

- La selezione della baseline salvata di un predefinito non viene visualizzata correttamente come *Nessuna baseline* dopo l&#39;eliminazione della baseline o durante la creazione di una baseline dinamica. (GUIDES-52690)
- In alcuni casi, le linee di base dinamiche rimangono bloccate nello stato di elaborazione dopo una ricostruzione non riuscita, causando l’utilizzo di versioni obsolete di argomenti e mappe senza visualizzare alcun errore nella generazione di esportazioni e output. (GUIDES-56739)

## Rivedere

- Negli scenari che coinvolgono un numero elevato di attività di revisione, l’apertura del pannello Revisione o l’applicazione di un filtro di progetto richiede più tempo del previsto per caricare l’elenco delle attività. (GUIDES-48893)
- Il riquadro dei contenuti nell’interfaccia utente Revisione visualizza una barra di scorrimento orizzontale su determinate risoluzioni dello schermo, inclusa la risoluzione consigliata di 1600 px, che causa la visualizzazione dei commenti di revisione quando il contenuto si estende oltre la larghezza del riquadro. (GUIDES-44082)

## Platform

- Le interfacce Sposta API, Rinomina API e Assets impediscono di rinominare una risorsa DITA con un nome di file basato su GUID in un nome di file leggibile. È ora possibile rinominare Assets con nomi di file leggibili dall&#39;utente, tuttavia non è ancora consentito rinominare un nome di file basato su GUID con un altro nome di file basato su GUID. (GUIDE-43006, GUIDE-59684)
- Quando una risorsa non DITA, come un’immagine, migrata da una configurazione non UUID a una configurazione UUID viene ripristinata o diramata in un’altra versione, il relativo UUID cambia. I riferimenti esistenti alla risorsa non vengono più risolti e l’immagine appare interrotta negli argomenti che vi fanno riferimento. (GUIDES-58414)
- L&#39;installazione di Experience Manager Guides Service Pack rimuove gli strumenti esterni installati in precedenza, ad esempio ACS Commons, dalla sezione **Strumenti** di AEM. (GUIDES-60365)

## Problemi noti

Adobe ha identificato i seguenti problemi noti per la versione 5.2.0 Service Pack 3:

- Dopo aver installato il service pack, la convalida Schematron potrebbe non riuscire con un&#39;eccezione `NoClassDefFoundError` e non è possibile salvare gli argomenti nell&#39;editor. (GUIDES-60062)<br>**Soluzione alternativa:** Aggiornare il bundle `com.adobe.fmdita.schematron-wrapper` dalla console Web di AEM (`/system/console/bundles`).
