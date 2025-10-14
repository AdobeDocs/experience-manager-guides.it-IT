---
title: Altre funzioni nell’Editor mappa
description: Scopri alcune funzioni comuni nell’Editor mappa. Scopri come risolvere i riferimenti chiave nell’Editor mappa.
exl-id: f0e7a402-ac12-4c63-9d7f-92567ee29a39
feature: Authoring, Map Editor
role: User
source-git-commit: 41c6e4edb470038c4934c01f1c28539f1e4d4f86
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 0%

---

# Funzioni aggiuntive nell’Editor mappa {#id1942D0T0HUI}

Alcune funzioni comuni nell’Editor mappa sono:

## Risolvi riferimenti chiave {#id176GD01H05Z}

Un riferimento a una chiave di contenuto DITA o `conkeyref` è un meccanismo per inserire una parte di contenuto da un argomento a un altro. Questo meccanismo utilizza la chiave per individuare il contenuto da riutilizzare, anziché il meccanismo di riferimento diretto ai contenuti. Per ulteriori informazioni sui riferimenti diretti e indiretti in DITA, visualizzare *Indirizzi DITA* in Specifiche lingua OASIS DITA.

Se all&#39;argomento DITA sono associati riferimenti chiave, è necessario risolverli prima di visualizzare in anteprima, modificare o rivedere un argomento.

I riferimenti chiave vengono risolti in base alla mappa principale impostata nel seguente ordine di priorità:

1. Preferenze utente
1. Pannello Vista mappa
1. Profilo cartella

La mappa principale selezionata in Preferenze utente ha la precedenza più alta per risolvere i riferimenti chiave, seguita dal pannello Vista mappa e dalla mappa principale Profilo cartella. Pertanto, se nelle Preferenze utente non è impostata alcuna mappa, viene utilizzata la mappa aperta nel pannello Vista mappa. Se nel pannello Vista mappa non è aperta alcuna mappa, per risolvere i riferimenti chiave viene utilizzata la mappa impostata nei Profili cartella.

I riferimenti chiave possono essere memorizzati all&#39;interno di un file mappa DITA o di un file DITA separato. In Experience Manager Guides, puoi specificare i riferimenti chiave a livello di progetto o di sessione. Se per la sessione utente è già definita una mappa radice, questa viene utilizzata per risolvere le chiavi. Altrimenti, viene utilizzata la mappa principale predefinita per quella cartella. Se non è configurata una mappa principale predefinita, all’utente vengono evidenziati i riferimenti chiave mancanti.

Esistono diversi modi per risolvere i riferimenti chiave in un argomento DITA definendo la mappa DITA da utilizzare nelle posizioni seguenti:

**Proprietà progetto** - È possibile definire una mappa radice per la risoluzione dei riferimenti chiave durante la creazione di un progetto nella sezione Proprietà progetto.

Questa mappa principale sarà applicabile a tutte le risorse (cartelle e sottocartelle) associate a quel progetto. Per il contenuto a cui si fa riferimento in più progetti, viene mantenuto un elenco alfabetico di progetti e viene utilizzata la mappa principale predefinita associata al primo progetto. È inoltre possibile scegliere la mappa DITA da utilizzare dall&#39;elenco per la risoluzione dei riferimenti chiave.

**Anteprima argomento** - Nella modalità di anteprima argomento, selezionare l&#39;icona Risoluzione chiave nella barra degli strumenti e selezionare il file DITA da utilizzare per i riferimenti chiave.

**Visualizzazione modifica argomento** - Selezionare l&#39;icona Risoluzione chiave durante la modifica di un argomento DITA e selezionare il file DITA da utilizzare per la risoluzione dei riferimenti chiave.

## Aggiungi riferimenti di navigazione

L&#39;elemento `navref` viene utilizzato all&#39;interno di una mappa DITA per includere i riferimenti di spostamento da un&#39;altra mappa DITA. Questo consente agli autori di riutilizzare la struttura di navigazione, ad esempio menu o collegamenti condivisi, senza unire nell’output il contenuto effettivo della mappa di riferimento.

>[!NOTE]
>
> L&#39;elemento `navref` è destinato esclusivamente alla navigazione all&#39;interno della struttura della mappa. Non contribuisce all&#39;output delle mappe DITA generato ed è escluso dall&#39;elaborazione e dalla visualizzazione in visualizzazione Mappa, Report, Linea di base, Traduzione e Anteprima.

Per aggiungere riferimenti di navigazione a una mappa, effettuare le seguenti operazioni:

1. Aprire il file di mapping DITA in cui si desidera aggiungere un riferimento di spostamento.

   Il file di mappa viene aperto nell&#39;Editor mappa.
1. Passare alla vista Autore e posizionare il cursore in una posizione valida per un riferimento di navigazione.
1. Selezionare l&#39;opzione **Elemento** nella barra degli strumenti.
1. Nella finestra di dialogo **Inserisci elemento**, seleziona **navref**.

   ![](./images/select-navref-element.png)
1. Viene visualizzata la finestra di dialogo **Seleziona percorso**. Seleziona un file di mappa da includere come riferimento di navigazione nella mappa e scegli **Seleziona**.

Nella posizione specificata viene aggiunto un riferimento di navigazione del file di mappa selezionato. Inoltre, il titolo della mappa a cui si fa riferimento viene visualizzato sia nella vista Creazione che nella vista Layout.

![](./images/navref-added-author-view.png)

*Visualizzazione autore*

![](./images/navref-added-layout-view.png)

*Visualizzazione Layout*


**Argomento padre:**&#x200B;[&#x200B; Introduzione all&#39;editor mappe](map-editor.md)
