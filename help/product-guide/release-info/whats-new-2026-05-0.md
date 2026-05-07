---
title: Note sulla versione | Novità della versione 2026.05.0 di Adobe Experience Manager Guides
description: Scopri le funzioni nuove e migliorate della versione 2026.05.0 di Adobe Experience Manager Guides
role: Leader
source-git-commit: 2c9e91a85bb9cfbfec05dbe5c2e9eae9e240d571
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 0%

---

# Novità della versione 2026.05.0 (maggio 2026)

Questo articolo descrive le funzioni nuove e migliorate introdotte con la versione 2026.05.0 di Adobe Experience Manager Guides as a Cloud Service.

Per l&#39;elenco dei problemi risolti in questa versione, visualizzare [Problemi risolti nella versione 2026.05.0](fixed-issues-2026-05-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2026.05.0](../release-info/upgrade-instructions-2026-05-0.md).

## Introduzione a Editor 2.0

L’editor 2.0 (noto anche come nuovo editor) offre funzioni di authoring semplificate, che consentono di creare contenuti in modo più efficiente sia nelle modalità tag che in quelle diverse da tag, grazie a un’esperienza più intuitiva. Questa versione offre prestazioni migliorate, velocizza il caricamento delle pagine e semplifica le operazioni di modifica, anche per argomenti complessi e di grandi dimensioni. Offre inoltre una maggiore stabilità, colmando le principali lacune nell’authoring, in particolare per quanto riguarda la navigazione e il comportamento dei cursori. Inoltre, un’interfaccia moderna offre un’interfaccia utente aggiornata e intuitiva che bilancia le funzionalità con la facilità d’uso. Per ulteriori dettagli, visualizzare [Introduzione all&#39;editor](../user-guide/web-editor.md).

Ecco una panoramica video che evidenzia le funzionalità di Editor 2.0.

>[!VIDEO](https://video.tv.adobe.com/v/3484007)


>[!NOTE]
>
> Contatta il team Customer Success di AEM Guides per far sì che l’editor 2.0 sia abilitato nel tuo ambiente.

Di seguito sono riportati i miglioramenti che rendono l’authoring più semplice ed efficiente.

### Interfaccia utente ed esperienza riprogettate

Un’interfaccia aggiornata migliora l’usabilità complessiva, rendendo la navigazione e l’authoring dei contenuti più intuitivi e coerenti.

- **CSS più ricco per gli elementi in modalità Creazione e Anteprima**: i CSS predefiniti migliorati per gli elementi consentono una migliore formattazione e una migliore coerenza visiva sia nelle modalità di creazione che in quelle di anteprima.

  ![](assets/rich-css.png){width="650"}

- **Supporto per tema scuro**: il supporto per un tema scuro nell&#39;area di modifica dei contenuti migliora l&#39;esperienza di authoring per gli utenti che preferiscono lavorare con un&#39;interfaccia scura.

  ![](assets/dark-theme.png){width="650"}

- **Impostazioni dell&#39;editor a livello utente consolidate**: nuovo pannello delle impostazioni centralizzato che offre agli autori un migliore controllo sul comportamento dell&#39;editor, consentendo agli utenti di gestire le preferenze più facilmente da un&#39;unica posizione. Le opzioni di configurazione includono, possibilità di abilitare/disabilitare:

   - Spazi unificatori in modalità Creazione
   - Impostazioni di visibilità dei tag con attributi o senza attributi
   - Commenti XML in modalità Creazione
   - Menu di inserimento rapido per l&#39;inserimento di elementi nell&#39;editor

  ![](assets/editor-settings-dialog.png){width="350"}


  Per ulteriori informazioni su come configurare le impostazioni dell&#39;editor, visualizzare [Impostazioni editor](../user-guide/config-editor-settings.md).

- **Migliore rappresentazione del contenuto condizionale in modalità Creazione**: il contenuto condizionale viene visualizzato più chiaramente in modalità Creazione, consentendo agli autori di identificare e gestire le varianti in modo più efficace. Per informazioni dettagliate, visualizza [Condizioni](../user-guide/web-editor-left-panel.md#conditions) nel pannello sinistro dell&#39;editor.

  ![](assets/multiple-conditions-applied_cs-editor-2-0.png){width="650"}

### Funzionalità di authoring migliorate

Offre strumenti migliorati e flessibilità per semplificare la creazione e la modifica dei contenuti nei flussi di lavoro.

- **Visualizza gli attributi insieme agli elementi in modalità tag**: gli autori possono ora visualizzare gli attributi degli elementi in modalità tag, offrendo maggiore visibilità e controllo sui contenuti strutturati. Per configurare questa funzionalità, visualizzare [Impostazioni editor](../user-guide/config-editor-settings.md).

  ![](assets/config-tags-attributes.png){width="650"}

- **Menu inserimento rapido**: consente di aggiungere elementi direttamente durante la modifica in modalità Creazione in corrispondenza del cursore senza passare alla barra degli strumenti. Gli elementi utilizzati di frequente possono anche essere configurati nella sezione Preferiti tramite le impostazioni dell’editor per un accesso più rapido. Per ulteriori dettagli, visualizzare [Modifica argomenti](../user-guide/web-editor-edit-topics.md).

  ![](assets/quick-insert-menu.png){width="650"}

- **Possibilità di visualizzare, modificare e inserire commenti XML in modalità Autore**: consente agli autori di visualizzare, modificare e inserire commenti XML direttamente in modalità Autore per una migliore visibilità all&#39;interno del contenuto. Per configurare questa funzionalità, visualizzare [Impostazioni editor](../user-guide/config-editor-settings.md).

  ![](assets/config-xml-comments.png){width="650"}

- **Modalità affiancata**: consente la visualizzazione simultanea delle modalità Autore e Source, con entrambe le visualizzazioni che rimangono sincronizzate per facilitare il confronto, la modifica e la convalida delle modifiche al contenuto. Per ulteriori dettagli, visualizzare [Visualizzazioni editor](../user-guide/web-editor-views.md).

  ![](assets/side-by-side-editor-2-0.png){width="650"}

- **Miglioramento dell&#39;authoring delle tabelle**: migliora l&#39;esperienza complessiva di authoring delle tabelle con interazioni più intuitive ed efficienti per la creazione e la gestione delle tabelle.

   - Interazioni fluide e intuitive: inserimento semplificato di righe e colonne, con supporto della funzione di trascinamento della selezione per riordinare righe e colonne.
   - Barra degli strumenti contestuale: consente di accedere ad azioni specifiche della tabella, ad esempio formattazione, allineamento, unione e altre azioni aggiuntive direttamente all’interno della tabella.
   - Configurazione delle tabelle: puoi aggiungere più righe o colonne in un’unica azione, riducendo i passaggi ripetitivi e migliorando l’efficienza.

  ![](assets/config-table.png){width="650"}

  Per ulteriori dettagli, visualizzare [Operazioni con le tabelle](../user-guide/web-editor-other-features.md#work-with-tables-in-the-new-editor).

### Prestazioni migliorate per argomenti di grandi dimensioni

Il nuovo editor offre un’esperienza di lavoro migliore con argomenti complessi e di grandi dimensioni, velocizzando il rendering dei contenuti, rendendo più affidabili le funzionalità di annullamento e ripristino e aggiungendo un marcatore sporco per indicare chiaramente le modifiche non salvate.

## Accedere al percorso e all’UUID dei riferimenti nei file dal pannello Proprietà contenuto

Ora puoi utilizzare **Percorso collegamento** per visualizzare il percorso relativo del riferimento selezionato e **Collega UUID** per visualizzarne l&#39;identificatore univoco dal pannello delle proprietà del contenuto. Puoi anche copiare il percorso assoluto completo e l’UUID associato direttamente dall’interfaccia utilizzando le icone accanto a Percorso collegamento e UUID collegamento, per tracciare e riutilizzare più facilmente le risorse collegate.

Per ulteriori dettagli, visualizzare [Proprietà contenuto](../user-guide/web-editor-right-panel.md#content-properties).

## Miglioramenti della revisione

I seguenti miglioramenti alla funzione Revisione sono stati apportati come parte di questa versione:

- È ora possibile abilitare **Promemoria automatici** per pianificare le notifiche di AEM e i promemoria e-mail per i revisori, sia prima della scadenza di un&#39;attività di revisione che dopo la scadenza. È possibile configurare più promemoria in ogni caso, con promemoria scaduti inviati in una sequenza definita e promemoria scaduti attivati dopo che l&#39;attività è stata contrassegnata come scaduta, in base alla pianificazione del promemoria configurata. Per ulteriori dettagli, visualizzare [Invia argomenti per la revisione](../user-guide/review-send-topics-for-review.md).

- I revisori possono ora accedere alla cronologia delle versioni per gli argomenti in revisione, consentendo loro di visualizzare e confrontare le versioni precedentemente esaminate e aggiornate dello stesso argomento nelle attività di revisione precedenti. In questo modo i revisori possono convalidare le modifiche apportate dai cicli di revisione precedenti e mantenere la continuità esaminando commenti, etichette e altri dettagli correlati all&#39;interno del contesto di revisione corrente. Per ulteriori dettagli, visualizzare la cronologia delle versioni [per il revisore](../user-guide/review-topics.md#version-history-for-the-reviewer).

## Nuova esperienza linea di base introdotta in Experience Manager Guides

>[!NOTE]
>
> Contatta il team Customer Success di AEM Guides per far sì che nel tuo ambiente sia abilitata la nuova linea di base.

La gestione di baseline grandi e complesse è ora più veloce, più stabile e più semplice da scalare con la **nuova esperienza di base**, basata su un&#39;architettura di base riprogettata. Questo aggiornamento affronta le problematiche di prestazioni e affidabilità che si pongono da tempo, preservando al contempo i flussi di lavoro esistenti.

Disponibile come miglioramento della versione beta, questo aggiornamento fornisce una soluzione ai punti critici più comuni, quali il caricamento lento, gli stati di base incoerenti e la gestibilità limitata, offrendo un’esperienza di base più rapida, stabile e prevedibile, con un ulteriore supporto per l’automazione e le operazioni di base su larga scala. I principali miglioramenti sono i seguenti:

- Prestazioni e scalabilità migliorate
- Maggiore coerenza nell’interfaccia utente e nel back-end
- Filtro, navigazione e visibilità delle dipendenze espansi

Per informazioni dettagliate, visualizzare [Nuova esperienza linea di base (Beta) in Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).






