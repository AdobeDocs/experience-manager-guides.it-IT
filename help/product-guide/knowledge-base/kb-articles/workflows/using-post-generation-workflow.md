---
title: Flusso di lavoro di post-generazione
description: Panoramica del flusso di lavoro di post-generazione con un esempio
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Pubblicazione di guide AEM - Flusso di lavoro di post-generazione

Le guide AEM offrono la flessibilità di specificare un flusso di lavoro per la generazione post-output. Puoi eseguire alcune attività di post-elaborazione sull’output generato utilizzando le guide AEM.
Ad esempio, potrebbe essere utile impostare alcune proprietà nell’output di PDF oppure inviare un messaggio e-mail a un set di utenti una volta generato l’output.


## Quali sono i passaggi necessari per utilizzare i flussi di lavoro di post-generazione

### Creare un processo di workflow

Creare un processo di flusso di lavoro basato su Java o ECMA che esegue l&#39;operazione sull&#39;output generato. Ad esempio, copiando alcuni metadati dall’origine al contenuto generato o manipolando i metadati dell’output generato.

- Prendiamo ad esempio la creazione di tale processo utilizzando lo script ECMA (puoi fare riferimento al pacchetto allegato)
- Per il processo del flusso di lavoro basato su Java, consulta la sezione &quot;*Personalizzare il flusso di lavoro di generazione post-output*&quot; di [Guida all’installazione e alla configurazione](/help/product-guide/install-guide/customize-workflows.md#id17A6GI004Y4)


### Creare un modello di flusso di lavoro

Con il processo di flusso di lavoro personalizzato creato nel passaggio precedente, crea un modello di flusso di lavoro e aggiungi a esso il passaggio del processo.

- È inoltre necessario aggiungere un passaggio di processo obbligatorio &quot;*Finalizza post-generazione*&quot; come ultimo passaggio del flusso di lavoro.

Fai riferimento al modello di flusso di lavoro di esempio mostrato di seguito:

![Modello di flusso di lavoro di post-generazione](../assets/workflows/pgwf-workflow-model.png)


### Utilizza questo flusso di lavoro di post-generazione su una mappa

Il flusso di lavoro di post-generazione è una proprietà che può essere configurata su qualsiasi predefinito di output nel meccanismo di pubblicazione delle guide AEM. Esempio:

![Flusso di lavoro di post-generazione nel predefinito di output](../assets/workflows/pgwf-preset-settings.png)


Supponendo che il modello selezionato sia già stato creato.


### Test

Ora puoi eseguire la pubblicazione utilizzando questo predefinito e convalidare l’output del passaggio del processo


## Esempio

Per riferimento, puoi utilizzare il pacchetto seguente e installarlo tramite Gestione pacchetti per testare il flusso di lavoro di esempio di post-generazione (*come indicato nelle schermate precedenti*)

[Esempio di modello di flusso di lavoro di post-generazione basato su ECMA](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
