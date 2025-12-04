---
title: Gestire un corso in Product Training and Learning
description: Scopri le varie funzioni presenti in Experience Manager Guides che ti consentono di gestire il corso in modo efficiente.
feature: Authoring
role: User
exl-id: 0f480d08-2f8a-494e-ab56-4965e5eeb960
source-git-commit: 0171f7b798686a0a16942e98133001a4c05bb76b
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 0%

---

# Gestire il corso

Dopo aver creato un corso, questo si apre nel pannello Gestione corsi. Puoi bloccare il corso e apportare tutte le modifiche necessarie a livello di corso. Nelle sezioni seguenti vengono illustrate le opzioni disponibili per la modifica del corso.

## Aggiungi nuovo contenuto

Per aggiungere nuovi contenuti al corso, effettua le seguenti operazioni:

1. Selezionare il menu **Opzioni** > **Aggiungi nuovo**.

   ![](assets/learning-course-content.png)
2. Seleziona il tipo di contenuto da creare. Opzioni disponibili:
   - **Panoramica**: il primo argomento del corso che fornisce una rapida introduzione a ciò che il corso copre.
   - **Argomento**: il materiale principale di un corso è costituito da pezzi brevi e mirati come passaggi, esempi o spiegazioni che insegnano una competenza o un&#39;idea specifica. Per ulteriori dettagli, visualizzare [Crea e personalizza argomento](./create-content.md).
   - **Riepilogo**: revisione rapida alla fine di un capitolo del corso che ricorda agli Allievi i punti chiave che hanno appena appreso.
   - **Quiz**: una serie di domande utilizzate per verificare se qualcuno comprende bene ciò che ha imparato. Per ulteriori dettagli, visualizzare [Crea e gestisci quiz](./create-quiz.md).
   - **Banca domande**: un insieme condiviso di domande riutilizzabili che possono essere utilizzate per creare quiz in modo rapido e coerente. Per ulteriori dettagli, visualizzare [Banca domande](./create-qb.md).
   - **Gruppo**: un gruppo di apprendimento consente di organizzare in un ordine logico argomenti correlati come capitoli, argomenti e altri moduli, creando una gerarchia chiara che semplifica la gestione e il riutilizzo dei materiali di formazione.
3. Seleziona **Crea**.

Il contenuto selezionato viene creato e aggiunto al corso. Per una panoramica video, visualizza [Aggiungi nuovo contenuto a un corso](https://video.tv.adobe.com/v/3469537/aem-guides-learning-content?quality=12&learn=on) ![](assets/Smock_VideoCheckedOut_18_N.svg).

## Aggiungi contenuto esistente

Puoi aggiungere al corso contenuto esistente dal tuo archivio dei contenuti. Per aggiungere contenuto esistente, effettua le seguenti operazioni:

1. Seleziona il menu **Opzioni** > **Aggiungi esistente**.
2. Seleziona il tipo di contenuto del corso che desideri creare.
3. Nella finestra di dialogo **Seleziona percorso**, passa alla posizione del contenuto e seleziona il contenuto di apprendimento desiderato.

   ![](assets/add-existing-learning-content.png)
4. Scegli **Seleziona**.

Il contenuto del corso selezionato viene aggiunto al corso dall’archivio.

>[!NOTE]
>
>È inoltre possibile utilizzare l&#39;opzione **Aggiungi file esistente** > **File (solo risorsa zip)** per includere un file zip che viene decompresso e integrato nella struttura di cartelle dell&#39;output SCORM finale. Questo consente di semplificare la creazione di pacchetti di risorse durante la pubblicazione del corso.

Per una panoramica video, visualizza [Aggiungi contenuto esistente a un corso](https://video.tv.adobe.com/v/3469537/aem-guides-learning-content?quality=12&learn=on) ![](assets/Smock_VideoCheckedOut_18_N.svg).

## Rimuovi contenuto

È possibile rimuovere qualsiasi argomento dal corso selezionando il menu **Opzioni** per l&#39;argomento specifico e quindi selezionando **Rimuovi voce** come illustrato di seguito.

![](assets/remove-learning-content.png)

Per una panoramica video, visualizza [Rimuovi contenuto dal corso](https://video.tv.adobe.com/v/3475210/learning-content-aem-guides) ![](assets/Smock_VideoCheckedOut_18_N.svg).


## Creare versioni del corso

Puoi controllare il controllo delle versioni del corso selezionando il menu **Opzioni** > **Controllo delle versioni**.

![](assets/course-versioning.png)

Per il controllo delle versioni di un corso sono disponibili le seguenti opzioni:

- **Salva come nuova versione**: salva il corso con un nuovo numero di versione.
- **Cronologia versioni**: visualizza l&#39;anteprima della versione corrente e consente di confrontarla con le altre versioni disponibili per il corso.
- **Etichetta versione**: consente di specificare etichette in formato testo libero o di utilizzare un set di etichette predefinite.

## Impostazioni di visualizzazione: Mostra

L&#39;opzione **Mostra** determina la modalità di visualizzazione degli argomenti. È possibile scegliere di presentarli utilizzando caselle di controllo per selezioni di più argomenti, numerando per indicare la struttura gerarchica o visualizzando il titolo dell&#39;argomento o il nome del file.

>[!NOTE]
>
> Queste impostazioni di visualizzazione si applicano solo in Gestione corsi e non hanno alcun impatto sull’output pubblicato.

![](assets/course-display-settings.png)

Per una panoramica video, visualizza [Mostra impostazioni](https://video.tv.adobe.com/v/3475210/learning-content-aem-guides) ![](assets/Smock_VideoCheckedOut_18_N.svg).

## Crea attività di revisione

In qualità di Autore di un corso di apprendimento o di Amministratore, puoi creare un’attività di revisione per il corso e assegnarla a un Revisore per un feedback. Inizia aprendo il tuo corso nel pannello **Gestione corsi**, quindi seleziona **Crea attività di revisione** dal menu **Opzioni** come mostrato di seguito:

![](assets/create-review-task-lc.png)

Viene visualizzata la pagina **Crea attività di revisione**, in cui è necessario aggiungere dettagli sull&#39;attività, ad esempio il titolo dell&#39;attività di revisione, specificare il progetto DITA di cui fa parte, definire le sequenze temporali dell&#39;attività, assegnare revisori e altro ancora. Al termine, i revisori riceveranno una notifica per questa attività. Gli argomenti del corso selezionati vengono visualizzati nell’interfaccia utente Revisione, dove i revisori possono aggiungere commenti e inviare nuovamente gli argomenti per gli aggiornamenti.

Per comprendere il flusso di lavoro di revisione in Experience Manager Guides, visualizza, [Invia argomenti per la revisione](../user-guide/review-send-topics-for-review.md).


