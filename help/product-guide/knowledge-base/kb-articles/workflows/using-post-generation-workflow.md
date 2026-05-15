---
title: Flusso di lavoro di post-generazione
description: Panoramica del flusso di lavoro di post-generazione con un esempio
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
feature: Workflow Configuration
role: User, Admin
TQID: https://experienceleague.adobe.com/GmpUvIwR5aDOIQ4RNUXoeOeQB3MrueRuxpvYBwYev4I
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b455a250-64c4-4598-b015-7b6b6dc528b1id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 0%

---

# Pubblicazione AEM Guides - Flusso di lavoro di post-generazione

AEM Guides offre la flessibilità di specificare un flusso di lavoro per la generazione post-output. Puoi eseguire alcune attività di post-elaborazione sull’output generato tramite AEM Guides.
Ad esempio, potrebbe essere utile impostare determinate proprietà nell’output di PDF oppure inviare un messaggio e-mail a un set di utenti una volta generato l’output.


## Quali sono i passaggi necessari per utilizzare i flussi di lavoro di post-generazione

### Creare un processo di workflow

Creare un processo di flusso di lavoro basato su Java o ECMA che esegue l&#39;operazione sull&#39;output generato. Ad esempio, copiando alcuni metadati dall’origine al contenuto generato o manipolando i metadati dell’output generato.
- Prendiamo ad esempio la creazione di tale processo utilizzando lo script ECMA (puoi fare riferimento al pacchetto allegato)
- Per il processo del flusso di lavoro basato su Java, fare riferimento alla sezione &quot;*Personalizzare il flusso di lavoro di generazione post-output*&quot; della [Guida all&#39;installazione e alla configurazione](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Creare un modello di flusso di lavoro

Con il processo di flusso di lavoro personalizzato creato nel passaggio precedente, crea un modello di flusso di lavoro e aggiungi a esso il passaggio del processo.
- È inoltre necessario aggiungere un passaggio di processo obbligatorio &quot;*Finalize Post Generation*&quot; come ultimo passaggio del flusso di lavoro.

Fai riferimento al modello di flusso di lavoro di esempio mostrato di seguito:

![Modello flusso di lavoro di post-generazione](../assets/workflows/pgwf-workflow-model.png)


### Utilizza questo flusso di lavoro di post-generazione su una mappa

Il flusso di lavoro di post-generazione è una proprietà che può essere configurata su qualsiasi predefinito di output nel meccanismo di pubblicazione di AEM Guides. Esempio:

![Flusso di lavoro di post-generazione nel predefinito di output](../assets/workflows/pgwf-preset-settings.png)


Supponendo che il modello selezionato sia già stato creato.


### Test

Ora puoi eseguire la pubblicazione utilizzando questo predefinito e convalidare l’output del passaggio del processo


## Esempio

Per riferimento, puoi utilizzare il pacchetto seguente e installarlo tramite Gestione pacchetti per testare il flusso di lavoro di post-generazione di esempio (*come indicato nelle schermate precedenti*)

[Esempio di modello di flusso di lavoro di post-generazione basato su ECMA](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
