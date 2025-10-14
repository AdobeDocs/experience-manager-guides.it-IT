---
title: Utilizza l’Assistente AI per creare i documenti in modo intelligente "
description: Scopri come utilizzare l’Assistente IA per l’authoring di documenti con efficienza intelligente nell’editor web.
hide: true
exl-id: c7d37da8-e838-47a2-b469-287bcd841933
source-git-commit: 8659035c57ce2b6f760b342fa9d88d656fcabf23
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 0%

---

# Assistente AI per l’authoring di documenti con efficienza intelligente

Experience Manager Guides fornisce uno strumento di assistenza per l’intelligenza artificiale che consente di rendere l’authoring più intelligente e veloce. La gestione dei documenti è semplificata grazie a suggerimenti intelligenti e all’ottimizzazione. Utilizzando questo strumento, puoi visualizzare i suggerimenti avanzati per riutilizzare il contenuto dell’archivio dei contenuti esistente. Utilizza la funzione di prompt di testo per inviare un prompt e modificare il contenuto o generare un output in base alle tue esigenze. Utilizza l’Assistente AI per convertire in modo intelligente un paragrafo in un elenco. È possibile creare una breve descrizione dell&#39;argomento corrente. Questa funzione consente inoltre di migliorare e tradurre facilmente il contenuto selezionato.


>[!NOTE]
>
> Per aggiungere la funzionalità Assistente AI nel pannello di destra, l&#39;amministratore di sistema deve selezionare l&#39;opzione **Assistente AI** nella scheda **Pannelli** delle **impostazioni Workspace** ![icona impostazioni Workspace](./images/editor_settings_icon.svg).
> &#x200B;> È inoltre necessario estrarre il documento per visualizzare l&#39;icona Assistente AI.

Questa funzione è disponibile solo per gli argomenti DITA. Dopo aver selezionato il testo in un argomento, puoi scegliere di eseguire una delle azioni dell’Assistente AI:

![assistente ai](./images/ai-assistant-panel.png)



## Suggerisci contenuti riutilizzabili


Utilizza la funzionalità **Suggerisci contenuto riutilizzabile** ![ai suggerisci contenuto riutilizzabile &#x200B;](./images/ai-suggest-reusable-content-icon.svg) per creare contenuti in modo coerente e preciso. È possibile selezionare il contenuto e Experience Manager Guides fornisce suggerimenti su come riutilizzare il contenuto esistente nell’archivio.
Ulteriori informazioni sull&#39;utilizzo di [suggerimenti avanzati basati sull&#39;intelligenza artificiale per l&#39;authoring dei contenuti](authoring-ai-based-smart-suggestions.md).





## Usa prompt di testo


Un prompt di testo è un’istruzione, una domanda o un’istruzione che guida l’Assistente AI nella generazione di una risposta o di un output specifico.

Puoi utilizzare un prompt di testo per modificare il contenuto e generare un output.  Ad esempio, puoi generare un riepilogo delle funzioni di un prodotto e utilizzarlo nel rapporto per mostrare il prodotto. Puoi utilizzare questa funzione anche per confrontare due prodotti. Ad esempio, puoi anche creare una tabella di confronto per le funzioni di due prodotti.


1. Selezionare il testo per il quale si desidera utilizzare il prompt di testo.
1. Selezionare **Usa prompt di testo** ![ai icona Usa prompt di testo](./images/ai-use-text-prompt.svg)dal pannello **Assistente AI**.
1. Chiedi conferma in uno dei modi seguenti:

   - Scegliete un prompt dai prompt suggeriti.
   - Modifica o modifica un prompt suggerito per creare un prompt personalizzato in base alle tue esigenze.

     >[!NOTE]
     >
     > I prompt suggeriti sono configurati in `ui_config.json` dall&#39;amministratore.

   - Immettere il prompt nella casella di testo.


1. Seleziona **Rigenera** ![Icona Rigenera](./images/refresh-icon.svg) per un&#39;altra risposta o output in base al prompt, come gli strumenti di intelligenza artificiale.

1. (Facoltativo) Seleziona **Espandi** ![espandi](./images/expand-icon.svg) per aprire l&#39;editor **Utilizza prompt di testo**. Vengono visualizzati il contenuto corrente e quello generato. Puoi modificare il contenuto del layout sorgente e controllare l’anteprima.


   >[!NOTE]
   >
   > Le risposte vengono generate in base al contenuto selezionato.



1. Puoi anche modificare il prompt nell’editor e rigenerare la risposta. Ad esempio, è possibile modificare il prompt per rendere il testo più conciso, impostandolo su circa 40 parole.

   ![editor prompt di testo assistente ai](./images/ai-assisstant-text-prompt.png)

1. Puoi verificare l’origine del contenuto generato e modificarla, se necessario.

1. Seleziona **Accetta** per sostituire il contenuto selezionato nell&#39;argomento con il contenuto generato.
1. **Annulla**: annulla l&#39;azione del prompt di testo. Torna allo stato iniziale del pannello.

   >[!NOTE]
   >
   > Se si seleziona l&#39;icona **Annulla** nel pannello delle funzioni, viene ripristinato anche lo stato iniziale.

## Migliorare i contenuti


Migliora il contenuto selezionato. Controlla l’ortografia, la lingua e la struttura grammaticale e suggerisci una versione migliore del contenuto. Migliora anche la qualità delle frasi.

1. Seleziona il contenuto.
1. Seleziona **Migliora contenuto** ![icona di miglioramento contenuto](./images/ai-improve-icon.svg) per trovare i suggerimenti per il contenuto migliorato.
1. Seleziona **Rigenera** per un altro suggerimento di contenuto migliorato.

1. (Facoltativo) Seleziona **Espandi** per aprire l&#39;editor di contenuti migliorato. Vengono visualizzati il contenuto corrente e quello generato. Puoi modificare il contenuto nel layout sorgente e anche controllare l’anteprima.



![assistente ai migliora editor contenuti](./images/ai-assisstant-improve-content.png)

Accetta il suggerimento o rigenera per una risposta diversa, oppure annulla l’azione per tornare allo stato precedente.





## Creare collegamenti

Crea una breve descrizione dell&#39;argomento in base al contenuto selezionato in circa 30-50 parole. La breve descrizione consente agli utenti di cercare e trovare contenuti rilevanti.
Ad esempio, puoi elencare i requisiti di sistema e generare una breve descrizione di conseguenza.



1. Seleziona il contenuto.
1. Selezionare **Crea collegamento** ![ai icona Crea descrizione breve](./images/ai-create-shortdesc-icon.svg) per creare una breve descrizione per l&#39;argomento corrente.
1. Selezionare **Accetta** per creare una nuova breve descrizione se questa non è già presente. Se è presente una breve descrizione, è necessario confermarla prima di sostituirla con la nuova breve descrizione.

È inoltre possibile eseguire le azioni seguenti:

- Seleziona **Rigenera** per generare un&#39;altra breve descrizione per il tuo argomento, come gli strumenti di intelligenza artificiale.
- Seleziona **Espandi** per aprire l&#39;editor **Crea collegamento**.

![assistente ai crea editor di descrizioni brevi](./images/ai-assistant-create-short-desc.png)




## Dettagli contenuto

Questa funzione converte in modo intelligente un paragrafo selezionato in un elenco.  Analizza il contenuto e crea un elenco logico di elementi. Non è necessario creare manualmente gli elementi. Ad esempio, se disponi di un paragrafo che descrive i passaggi necessari per creare un account utente, lo strumento può trasformarlo in un elenco dettagliato, eliminando la necessità di creare manualmente gli elementi uno alla volta.

![icona del contenuto dell&#39;Assistente ai](./images/ai-assisstant-itemise-content.png)



1. Seleziona il contenuto.
1. Selezionare **Icona Dettaglio contenuto** ![icona Dettaglio contenuto](./images/ai-itemize-icon.svg) per convertire il contenuto selezionato in un elenco.
Lo strumento AI Assistant converte il contenuto in modo intelligente in un elenco di elementi.
1. (Facoltativo) Seleziona **Espandi** per aprire l&#39;editor di **Dettagli contenuto**.
1. Quando l’elenco è pronto, accetta le modifiche nel contenuto generato. Il contenuto generato sostituisce quindi il contenuto selezionato.



## Tradurre il contenuto

Utilizza questa funzione intelligente per tradurre il contenuto selezionato nella lingua di destinazione. Ad esempio, puoi aggiungere contenuti in inglese e tradurli rapidamente in tedesco.
Per tradurre il contenuto, effettua le seguenti operazioni:

1. Seleziona il contenuto da tradurre.
1. Selezionare **Traduci contenuto** ![ai icona Traduci contenuto](./images/ai-translate-content-icon.svg) dal pannello dell&#39;Assistente AI.
1. Seleziona la lingua di destinazione dal menu a discesa. Il contenuto tradotto viene visualizzato nel pannello Assistente AI.

1. (Facoltativo) Seleziona **Espandi** per aprire l&#39;editor **Traduci contenuto**.
1. Puoi anche selezionare un’altra lingua dal menu a discesa e rigenerare il contenuto nella lingua scelta. Se ad esempio si seleziona Francese e quindi si seleziona **Rigenera**, il contenuto verrà tradotto in francese.

![assistente ai traduci contenuto](./images/ai-assisstant-translate-content.png)
