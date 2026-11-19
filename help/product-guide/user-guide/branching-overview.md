---
title: Diramazione in AEM Guides | ADOBE EXPERIENCE MANAGER GUIDES
description: Scopri come creare e gestire i rami di una mappa DITA in AEM Guides per supportare l’authoring parallelo, la pubblicazione indipendente e l’unione delle modifiche alla documentazione.
TQID: https://experienceleague.adobe.com/pg9zeEg8m3NeDbN-j945SqPbaMX0GgBmuquAsQcrjOM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: 6359bacca2ef4114a81049d9792214f3439de364
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 0%
---
# Panoramica

>[!NOTE]
>
> La funzione di ramificazione e unione è introdotta nella versione 2026.11.0 di Experience Manager Guides as a Cloud Service ed è disabilitata per impostazione predefinita. Per abilitare la funzione per il tuo ambiente, contatta il team Customer Success.

La creazione di rami in Adobe Experience Manager Guides consente di creare e gestire più rami del ramo **principale** affinché una mappa DITA funzioni in parallelo su diverse versioni della documentazione. Ogni ramo consente agli autori di gestire le modifiche al contenuto in modo indipendente, senza influire sul contenuto corrispondente in altri rami.

Con la creazione di diramazioni, più team possono lavorare contemporaneamente su diverse versioni, funzioni o correzioni associate alla stessa mappa DITA. È possibile unire le modifiche da un ramo al ramo predefinito (`main`) quando gli aggiornamenti sono pronti.

## Funzionamento della diramazione

È possibile creare un ramo da **main** o da qualsiasi ramo esistente di una mappa DITA. Dopo aver creato un ramo, puoi passare ad esso e iniziare a modificare la mappa e il relativo contenuto. Puoi anche pubblicare il contenuto dal ramo selezionato o unire le modifiche in `main` quando è pronto.

Si consideri, ad esempio, una mappa DITA denominata `install-the-lift.ditamap` che contiene istruzioni di installazione per un prodotto. Il tuo team di documentazione può creare due rami di questa mappa da `main`:

- **Versione 1:** Il team A mantiene le istruzioni di installazione esistenti e le correzioni degli indirizzi.
- **Versione 2:** Il team B sviluppa le istruzioni di installazione per le nuove funzionalità.

Entrambi i team possono lavorare in modo indipendente sui rispettivi rami della mappa senza influire sulle modifiche reciproche.

>[!NOTE]
>
>Viene creato un ramo in base a una mappa DITA. Puoi anche aggiungere e modificare argomenti a cui la mappa non fa riferimento nel ramo selezionato. Per ulteriori informazioni, visualizzare [Apri o modifica argomenti esterni alla mappa corrente](./create-manage-branch.md#open-or-edit-topics-outside-the-current-map-context).

Quando si crea un ramo di una mappa DITA, Experience Manager Guides non copia automaticamente gli argomenti di riferimento della mappa nel nuovo ramo. Gli argomenti non modificati vengono letti dal ramo di origine o dal ramo predefinito (principale). Un argomento viene copiato nel nuovo ramo solo quando lo si modifica e lo si salva in tale ramo.

>[!NOTE]
>
> Il controllo delle versioni degli argomenti continua a funzionare con la diramazione. È possibile creare e gestire versioni di argomenti in un ramo selezionato di una mappa DITA. Ogni ramo mantiene la propria cronologia delle versioni, indipendentemente dagli altri rami.

## Vantaggi chiave

L’utilizzo di una filiale in Experience Manager Guides offre i seguenti vantaggi:

- **Modifica isolata:** apporta modifiche all&#39;interno di un ramo mappa selezionato senza influire sul contenuto corrispondente in altri rami.
- **Authoring parallelo:** consente a più team di lavorare simultaneamente su diverse versioni, funzionalità o correzioni all&#39;interno dei rispettivi rami di mappa.
- **Pubblicazione indipendente:** Pubblica la documentazione da singoli rami di mappa senza attendere il completamento delle modifiche in altri rami.
- **Unione controllata:** unire le modifiche da un ramo mappa al ramo predefinito (`main`), con la possibilità di esaminare e risolvere i conflitti.

## Branching e linee di base

>[!NOTE]
>
> Le linee di base e le diramazioni si escludono a vicenda. Quando la diramazione è abilitata, la funzionalità di base diventa non disponibile. Tuttavia, le linee di base esistenti rimangono intatte e non vengono eliminate. Se la diramazione viene disattivata in un secondo momento, le linee di base esistenti diventano nuovamente disponibili per l&#39;uso.

Una **baseline** identifica una combinazione specifica di versioni di argomenti per una mappa DITA, consentendo di generare l&#39;output utilizzando le versioni selezionate.

Un **branch** fornisce un ambiente di modifica separato per una mappa DITA e il relativo contenuto, consentendo agli autori di apportare modifiche senza influire su altri rami della stessa mappa.

| Linee di base | Diramazione |
|---|---|
| Selezionare versioni specifiche degli argomenti in una mappa DITA. | Creare rami separati di una mappa DITA per gestire le modifiche in modo indipendente. |
| Utilizzato per pubblicare combinazioni specifiche di versioni di argomenti. | Utilizzato per sviluppare e pubblicare diverse versioni in parallelo. |
| Non fornire contesti di modifica isolati. | Supporto di operazioni di modifica e unione isolate. |

## Funzionalità future

Le funzionalità seguenti sono attualmente supportate solo nel ramo predefinito (`main`) e sono previste per essere supportate in altri rami di una mappa DITA nelle versioni future di Experience Manager Guides:

- Ricerca
- Trova e sostituisci
- Rivedere i flussi di lavoro

