---
title: Altre funzioni negli editor di mappe
description: Scopri alcune funzioni comuni nell’Editor mappa. Scopri come risolvere i riferimenti chiave nell’editor mappa.
exl-id: f0e7a402-ac12-4c63-9d7f-92567ee29a39
feature: Authoring, Map Editor
role: User
source-git-commit: 594e348fc1188e66cf2f4648702ed2b17f1f8f33
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---

# Funzioni aggiuntive nell’editor mappa {#id1942D0T0HUI}

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

**Argomento padre:**[ Introduzione all&#39;editor mappe](map-editor.md)
