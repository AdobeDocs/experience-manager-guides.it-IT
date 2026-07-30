---
title: Configurare i criteri sulla sicurezza dei contenuti per l’anteprima SCORM
description: Scopri come configurare i criteri sulla sicurezza dei contenuti per l’anteprima SCORM utilizzando una variabile di ambiente in Cloud Manager
feature: Authoring
role: User
source-git-commit: 730fe6021aa20aa2b57801807da0f471f84a7718
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 3%

---


# Configurare i criteri sulla sicurezza dei contenuti (CSP) per l’anteprima SCORM

L’anteprima SCORM di Experience Manager Guides viene gestita tramite una variabile di ambiente dedicata che governa i criteri di sicurezza del contenuto (CSP) applicati all’esperienza di anteprima. Dopo aver abilitato l&#39;impostazione, gli amministratori possono estenderla aggiungendo altre fonti attendibili. Queste origini possono includere script, stili, font, immagini, file multimediali, frame e altri elementi necessari affinché i pacchetti SCORM possano essere caricati e riprodotti correttamente nelle anteprime in Experience Manager Guides.

Questo articolo spiega come aggiungere e configurare la variabile di ambiente in Cloud Manager, suddivide ciò che fa ogni campo nel valore JSON e mostra come aggiornare il valore in un secondo momento, in caso di modifiche alle tue esigenze.

## Campi di configurazione

La variabile `GUIDES_SCORM_PREVIEW_CONFIG` accetta come valore l&#39;oggetto JSON. Ogni valore controlla un aspetto specifico della CSP applicata durante l’anteprima SCORM:

| Campi | Tipo | Descrizione |
|---|---|---|
| `CSP_ENABLED` | Booleano | Attiva (`true`) o disattiva (`false`) l&#39;applicazione CSP per l&#39;anteprima SCORM. |
| `ALLOW_UNSAFE_EVAL` | Booleano | Consente l&#39;utilizzo di `eval()` e di metodi di valutazione JavaScript non sicuri se impostati su `true`. |
| `ADDITIONAL_SCRIPT_SRC` | Array | Altre origini attendibili consentite per JavaScript. |
| `ADDITIONAL_STYLE_SRC` | Array | Ulteriori origini attendibili consentite per la gestione dei fogli di stile. |
| `ADDITIONAL_FONT_SRC` | Array | Altre origini attendibili consentite per la gestione dei caratteri. |
| `ADDITIONAL_FRAME_SRC` | Array | Altre origini attendibili possono essere caricate all&#39;interno di `<iframe>` elementi. |
| `ADDITIONAL_IMG_SRC` | Array | Altre fonti attendibili consentite per distribuire le immagini. |
| `ADDITIONAL_MEDIA_SRC` | Array | Altre fonti attendibili consentite per la trasmissione di contenuti audio/video. |
| `ADDITIONAL_WORKER_SRC` | Array | Ulteriori origini attendibili consentite per i Web worker. |
| `ADDITIONAL_CONNECT_SRC` | Array | Altre origini attendibili a cui è consentita la connessione dell’anteprima (ad esempio, chiamate XHR/fetch). |
| `ADDITIONAL_MANIFEST_SRC` | Array | Sono consentite altre origini attendibili per distribuire i manifesti dell’app Web. |
| `ADDITIONAL_OBJECT_SRC` | Array | Altre origini attendibili possono essere caricate tramite `<object>`, `<embed>` o `<applet>`. |


## Valori predefiniti per i campi di configurazione

```json
{
  "CSP_ENABLED": true,
  "ALLOW_UNSAFE_EVAL": false,
  "ADDITIONAL_STYLE_SRC": ["https://fonts.googleapis.com"],
  "ADDITIONAL_FONT_SRC": ["https://fonts.gstatic.com"],
  "ADDITIONAL_FRAME_SRC": ["https://www.youtube-nocookie.com", "https://www.youtube.com"],
  "ADDITIONAL_SCRIPT_SRC": [],
  "ADDITIONAL_WORKER_SRC": [],
  "ADDITIONAL_IMG_SRC": [],
  "ADDITIONAL_MEDIA_SRC": [],
  "ADDITIONAL_CONNECT_SRC": [],
  "ADDITIONAL_MANIFEST_SRC": [],
  "ADDITIONAL_OBJECT_SRC": []
}
```

A seconda delle tue esigenze, non è necessario compilare ogni valore; lascia qualsiasi tipo di origine come un array vuoto se non devi consentire origini aggiuntive.

>[!NOTE]
>
> Se vuoi disabilitare l&#39;imposizione CSP per l&#39;anteprima SCORM, imposta `"CSP_ENABLED": false` nel valore JSON.

## Aggiungere la variabile in Cloud Manager

1. Accedi a Cloud Manager e seleziona l’ambiente in cui desideri applicare la configurazione.
2. Passa alla scheda **Configurazione** dell&#39;ambiente.
3. Seleziona **Aggiungi/Aggiorna** per aggiungere una variabile di ambiente.

   ![Aggiunta di una nuova variabile al cloud manager ](assets/add-new-variable.png){width="650"}

4. Immettere il nome della variabile (`GUIDES_SCORM_PREVIEW_CONFIG`) nel campo **Name**.

   ![Aggiunta del nome della variabile nel campo del nome](assets/variable-name.png){width="650"}

5. Immetti la configurazione JSON completa, inclusi gli elenchi di corsi consentiti di origine necessari, nel campo **Valore**.
6. Seleziona il **Servizio applicato** per scegliere se la variabile deve essere applicata a **Autore**, **Pubblica** o a entrambi. Per l&#39;authoring di Experience Manager Guides, selezionare **Autore**.
7. Seleziona **Variabile** nel campo **Tipo**.
8. Seleziona **Aggiungi**.
9. Seleziona **Salva**.

   ![Salvataggio della variabile per l&#39;applicazione all&#39;ambiente](assets/save.png){width="650"}

Dopo il salvataggio, Cloud Manager applica la configurazione all’ambiente selezionato. La propagazione di questa operazione richiede in genere 10-12 minuti, quindi attendi il completamento dell’aggiornamento. Al termine, la nuova configurazione sarà attiva per l’anteprima SCORM in tale ambiente.

## Aggiornare i valori delle variabili

Se i requisiti cambiano, è possibile rivedere la variabile `GUIDES_SCORM_PREVIEW_CONFIG` in qualsiasi momento dalla stessa scheda Configurazione in Cloud Manager. Individua la variabile esistente e seleziona la relativa opzione **Aggiungi/aggiorna** per aprirla per la modifica, quindi rivedi il valore come necessario.