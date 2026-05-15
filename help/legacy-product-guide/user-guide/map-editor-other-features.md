---
title: Altre funzioni negli editor di mappe
description: Scopri alcune funzioni comuni negli Editor mappe di base e avanzati. Scopri come risolvere i riferimenti chiave nell’editor mappa.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: d6e00884-e17c-499e-9568-0807a75051ad
TQID: https://experienceleague.adobe.com/tAzYI5Pxc6SkzgksjL3mFAQHY01YtejwTrU6vHW5vMc
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 467
ht-degree: 0%

---

# Altre funzioni negli editor di mappe {#id1942D0T0HUI}

Alcune funzioni comuni negli Editor mappe di base e avanzati sono:

## Risolvi riferimenti chiave {#id176GD01H05Z}

Un riferimento a una chiave di contenuto DITA o `conkeyref` è un meccanismo per inserire una parte di contenuto da un argomento a un altro. Questo meccanismo utilizza la chiave per individuare il contenuto da riutilizzare, anziché il meccanismo di riferimento diretto ai contenuti. Per ulteriori informazioni sui riferimenti diretti e indiretti in DITA, vedere *Indirizzi DITA* nelle specifiche del linguaggio OASIS DITA.

Se all&#39;argomento DITA sono associati riferimenti chiave, è necessario risolverli prima di visualizzare in anteprima, modificare o rivedere un argomento.

I riferimenti chiave vengono risolti in base alla mappa principale impostata nel seguente ordine di priorità:

1. Preferenze utente
1. Pannello Vista mappa
1. Profilo cartella

La mappa principale selezionata in Preferenze utente ha la precedenza più alta per risolvere i riferimenti chiave, seguita dal pannello Vista mappa e dalla mappa principale Profilo cartella. Pertanto, se nelle Preferenze utente non è impostata alcuna mappa, viene utilizzata la mappa aperta nel pannello Vista mappa. Se nel pannello Vista mappa non è aperta alcuna mappa, per risolvere i riferimenti chiave viene utilizzata la mappa impostata nei Profili cartella.

I riferimenti chiave possono essere memorizzati all&#39;interno di un file mappa DITA o di un file DITA separato. In AEM Guides, puoi specificare i riferimenti chiave a livello di progetto o di sessione. Se per la sessione utente è già definita una mappa radice, questa viene utilizzata per risolvere le chiavi. Altrimenti, viene utilizzata la mappa principale predefinita per quella cartella. Se non è configurata una mappa principale predefinita, all’utente vengono evidenziati i riferimenti chiave mancanti.

Esistono diversi modi per risolvere i riferimenti chiave in un argomento DITA definendo la mappa DITA da utilizzare nelle posizioni seguenti:

**Proprietà progetto** - È possibile definire una mappa radice per la risoluzione dei riferimenti chiave durante la creazione di un progetto nella sezione Proprietà progetto.

Questa mappa principale sarà applicabile a tutte le risorse (cartelle e sottocartelle) associate a quel progetto. Per il contenuto a cui si fa riferimento in più progetti, viene mantenuto un elenco alfabetico di progetti e viene utilizzata la mappa principale predefinita associata al primo progetto. È inoltre possibile scegliere la mappa DITA da utilizzare dall&#39;elenco per la risoluzione dei riferimenti chiave.

**Anteprima argomento** - Nella modalità di anteprima argomento, fare clic sull&#39;icona Risoluzione chiave nella barra degli strumenti e selezionare il file DITA da utilizzare per i riferimenti chiave.

**Visualizzazione modifica argomento** - Fare clic sull&#39;icona Risoluzione chiave durante la modifica di un argomento DITA e selezionare il file DITA da utilizzare per la risoluzione dei riferimenti chiave.

**Argomento padre:**[ Utilizzare l&#39;editor mappe](map-editor.md)
