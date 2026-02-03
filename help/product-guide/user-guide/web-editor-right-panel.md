---
title: Pannello a destra nell’editor
description: Scopri il pannello A destra nell’editor. Scopri l’interfaccia e le funzioni dell’editor in Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
exl-id: 6a0f4ed2-6eca-4b3c-bd3a-3f72f6919b36
source-git-commit: 05a44af6982a9a23e6bbddeaac52b0700e2e2170
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 0%

---

# Pannello a destra nell’editor

Il pannello di destra contiene informazioni sul documento attualmente selezionato.

>[!NOTE]
>
> Il pannello a destra è ridimensionabile. Per ridimensionare il pannello, posiziona il cursore sul bordo del pannello. Il cursore si trasforma in una freccia a due punte, seleziona e trascina per ridimensionare la larghezza del pannello.

Il pannello a destra consente di accedere alle seguenti funzioni:

- [Proprietà contenuto](#content-properties)
- [Proprietà file](#file-properties)
- [Rivedere](#review)
- [Rileva modifiche](#track-changes)
- [Schematron](#schematron)

## Proprietà contenuto

Puoi accedere alla funzione **Proprietà contenuto** selezionando l&#39;icona **Proprietà contenuto** nel pannello di destra. Il pannello **Proprietà contenuto** contiene informazioni sul tipo di elemento attualmente selezionato nel documento e sui relativi attributi.

**Tipo**: è possibile visualizzare e selezionare i tag della gerarchia completa per il tag corrente dal menu a discesa.

**Attributi**: il pannello a discesa **Attributi** è disponibile nelle visualizzazioni Layout, Autore e Source. Puoi aggiungere, modificare o eliminare facilmente gli attributi.

<details>
    <summary> Passaggi per aggiungere attributi </summary>


1. Seleziona **Aggiungi**.

   ![attributi nelle proprietà del contenuto](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. Nel pannello a discesa **Attributo**, seleziona l&#39;attributo dall&#39;elenco a discesa e specifica il valore di un attributo.  Quindi seleziona **Aggiungi**.

   ![pannello attributi con più attributi &#x200B;](images/attributes-multiple-properties.png){width="300" align="left"}

1. Per modificare l&#39;attributo, passa il puntatore su di esso e seleziona **Modifica** ![icona-modifica](images/edit_pencil_icon.svg).

1. Per eliminare l&#39;attributo, posizionare il puntatore del mouse su di esso e selezionare **Elimina** ![elimina-icona](images/Delete_icon.svg).

</details>


>[!NOTE]
>
> Anche se l&#39;argomento contiene contenuto di riferimento, è possibile aggiungervi attributi utilizzando il pannello delle proprietà.

Se l’amministratore ha creato un profilo per gli attributi, questi vengono ottenuti insieme ai relativi valori configurati. Utilizzando il pannello delle proprietà del contenuto, potete scegliere questi attributi e assegnarli al contenuto pertinente nell&#39;argomento. In questo modo puoi anche creare contenuto condizionale, che può quindi essere utilizzato per creare l’output condizionale. Per ulteriori informazioni sulla generazione dell&#39;output utilizzando i predefiniti condizionali, visualizzare [Usa predefiniti condizione](generate-output-use-condition-presets.md#).



## Proprietà file

Visualizzare le proprietà del file selezionato selezionando l&#39;icona Proprietà file nel pannello di destra. La funzione Proprietà file è disponibile in tutte e quattro le modalità o visualizzazioni: Layout, Autore, Source e Anteprima.

Le proprietà File sono suddivise nelle due sezioni seguenti:

**Generale**

La sezione Generale consente di accedere alle seguenti funzioni:

![proprietà-file](images/file-properties-general.png){width="300" align="left"}

- **Nome file**: visualizza il nome del file dell&#39;argomento selezionato. Il nome del file viene collegato alla pagina delle proprietà del file selezionato.
- **ID**: visualizza l&#39;ID dell&#39;argomento selezionato.
- **Conteggio parole**: visualizza il numero totale di parole nell&#39;argomento DITA corrispondente. Le parole separate da spazi sono considerate singole parole. Il conteggio viene aggiornato ogni volta che si salvano le modifiche apportate all&#39;argomento. Per i riferimenti incrociati, nel conteggio viene incluso solo il testo visualizzato, mentre le chiavi sono escluse.

  >[!NOTE]
  >
  > La funzione **Conteggio parole** è stata introdotta nella versione 2026.01.0 di Experience Manager Guides as a Cloud Service. Tutti i nuovi argomenti DITA creati dopo l&#39;aggiornamento a questa versione avranno automaticamente il conteggio delle parole calcolato nel pannello di destra. Per gli argomenti esistenti, è richiesta la [rielaborazione delle risorse](./asset-processor.md).

- **Tag**: questi sono i tag di metadati dell&#39;argomento. Vengono impostati dal campo tag della pagina delle proprietà. Puoi digitarli o selezionarli dal menu a discesa.  I tag vengono visualizzati sotto il menu a discesa. Per eliminare un tag, seleziona l’icona a forma di croce accanto al tag.
- **Modifica altre proprietà**: è possibile modificare altre proprietà ( per i file che non sono in modalità **Sola lettura**) dalla pagina Proprietà file.

  >[!NOTE]
  >
  > Qualsiasi aggiunta, eliminazione o modifica delle proprietà dei metadati (predefinite o personalizzate) attiverà l&#39;[indicatore della copia di lavoro](./web-editor-edit-topics.md#working-copy-indicator) nella versione del documento.


- **Lingua**: mostra la lingua dell&#39;argomento. Viene impostato dal campo della lingua nella pagina delle proprietà.
- **Data creazione**: visualizza la data e l&#39;ora di creazione dell&#39;argomento.
- **Modificato il**: visualizza la data e l&#39;ora di modifica dell&#39;argomento.
- **Bloccato da**: mostra l&#39;utente che ha bloccato l&#39;argomento.
- **Stato documento**: è possibile selezionare e aggiornare lo stato del documento dell&#39;argomento attualmente aperto. Per ulteriori dettagli, visualizzare [Stato documento](web-editor-document-states.md#).

>[!NOTE]
>
> È possibile copiare negli Appunti i valori degli attributi dei vari campi delle proprietà File.

**Riferimenti**

La sezione Riferimenti (References) consente di accedere alle seguenti funzioni:

![](images/file-properties-references.png){width="300" align="left"}

- **Usato in**: Usato nei riferimenti elenca i documenti in cui viene fatto riferimento o utilizzato il file corrente.
- **Collegamenti in uscita:** I collegamenti in uscita elencano i documenti a cui si fa riferimento nel documento corrente.

Per impostazione predefinita, è possibile visualizzare i file in base ai titoli. Passando il puntatore del mouse su un file, potete visualizzare il titolo e il percorso del file come descrizione comando.

>[!NOTE]
>
> In qualità di amministratore, puoi anche scegliere di visualizzare l’elenco dei file in base ai nomi dei file nell’Editor. Selezionare l&#39;opzione **Nome file** della sezione **Configurazione di visualizzazione dei file dell&#39;editor** in **Preferenze utente**.

>[!NOTE]
>
> Tutti i riferimenti utilizzati in e in uscita sono collegati ai documenti. È possibile aprire e modificare facilmente i documenti collegati.

Oltre ad aprire i file, è possibile eseguire molte azioni utilizzando il menu **Opzioni** nella sezione Riferimenti. Alcune delle azioni che puoi eseguire includono Modifica, Anteprima, Copia UUID, Copia percorso, Aggiungi a raccolte, Proprietà.

## Rivedere

Se si seleziona l&#39;icona Revisione, viene aperto il pannello Revisione in cui è possibile selezionare un task di revisione per il documento aperto e visualizzare i commenti.

![](images/review-panel-before-opening.png){width="300" align="left"}

Se hai creato più progetti di revisione, puoi selezionarne uno dal menu a discesa e accedere ai relativi commenti.

Il pannello Revisione consente di visualizzare e pubblicare le risposte ai commenti sull&#39;argomento. È possibile accettare o rifiutare i commenti singolarmente.

>[!NOTE]
>
> La casella dei commenti e la casella delle risposte supportano le voci su più righe e consentono agli utenti di espanderle in base alle esigenze per fornire commenti completi e risposte dettagliate ai commenti. È possibile utilizzare **Maiusc** + **Invio** per passare alla riga successiva durante la scrittura dei commenti o delle risposte.

Per ulteriori informazioni, visualizzare [Commenti sulla revisione degli indirizzi](review-address-review-comments.md#).

## Rileva modifiche

Utilizzando la funzione Tracked changes (Modifiche tracciate) del pannello di destra, potete visualizzare le informazioni di tutti gli aggiornamenti apportati in un documento. È inoltre possibile cercare qualsiasi aggiornamento specifico apportato al documento.

>[!NOTE]
>
> La funzionalità delle modifiche rilevate mostra tutti gli aggiornamenti rilevati tramite la funzionalità Attiva/Disattiva rilevamento modifiche della [barra delle schede](./web-editor-tab-bar.md).

## Schematron

&quot;Schematron&quot; si riferisce a un linguaggio di convalida basato su regole utilizzato per definire test per un file XML. L&#39;editor supporta i file Schematron. Potete importare i file Schematron e modificarli nell&#39;Editor. Utilizzando un file Schematron è possibile definire determinate regole e quindi convalidarle per un argomento o una mappa DITA.

Scopri come utilizzare i file Schematron in Experience Manager Guides. Fai riferimento a [Supporto per i file Schematron](./support-schematron-file.md).



**Argomento padre:**&#x200B;[&#x200B; Introduzione all&#39;editor](web-editor.md)
