---
title: Flusso di lavoro di generazione Post
description: Panoramica del flusso di lavoro di post-generazione con un esempio
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
feature: Workflow Configuration
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Pubblicazione AEM Guides - Flusso di lavoro di generazione Post

AEM Guides offre la flessibilità di specificare un flusso di lavoro per la generazione post-output. Puoi eseguire alcune attività di post-elaborazione sull’output generato tramite AEM Guides.
Ad esempio, potrebbe essere utile impostare alcune proprietà nell’output di PDF oppure inviare un messaggio e-mail a un set di utenti una volta generato l’output.


## Quali sono i passaggi necessari per utilizzare i flussi di lavoro di generazione Post

### Creare un processo di workflow

Creare un processo di flusso di lavoro basato su Java o ECMA che esegue l&#39;operazione sull&#39;output generato. Ad esempio, copiando alcuni metadati dall’origine al contenuto generato o manipolando i metadati dell’output generato.
- Prendiamo ad esempio la creazione di tale processo utilizzando lo script ECMA (puoi fare riferimento al pacchetto allegato)
- Per il processo del flusso di lavoro basato su Java, fare riferimento alla sezione &quot;*Personalizzare il flusso di lavoro di generazione post-output*&quot; della [Guida all&#39;installazione e alla configurazione](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Creare un modello di flusso di lavoro

Con il processo di flusso di lavoro personalizzato creato nel passaggio precedente, crea un modello di flusso di lavoro e aggiungi a esso il passaggio del processo.
- È inoltre necessario aggiungere un passaggio di processo obbligatorio &quot;*Finalize Post Generation*&quot; come ultimo passaggio del flusso di lavoro.

Fai riferimento al modello di flusso di lavoro di esempio mostrato di seguito:

![Modello flusso di lavoro generazione Post](../assets/workflows/pgwf-workflow-model.png)


### Utilizza questo flusso di lavoro di post-generazione su una mappa

Il flusso di lavoro di generazione Post è una proprietà che può essere configurata su qualsiasi predefinito di output nel meccanismo di pubblicazione di AEM Guides. Esempio:

![Flusso di lavoro di generazione Post nel predefinito di output](../assets/workflows/pgwf-preset-settings.png)


Supponendo che il modello selezionato sia già stato creato.


### Test

Ora puoi eseguire la pubblicazione utilizzando questo predefinito e convalidare l’output del passaggio del processo


## Esempio

Per riferimento, puoi utilizzare il pacchetto seguente e installarlo tramite Gestione pacchetti per testare il flusso di lavoro di post-generazione di esempio (*come indicato nelle schermate precedenti*)

[Esempio di modello di flusso di lavoro di post-generazione basato su ECMA](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
