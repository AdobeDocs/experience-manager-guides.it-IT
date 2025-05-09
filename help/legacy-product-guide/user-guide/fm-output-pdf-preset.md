---
title: PDF
description: Genera e configura l’output di PDF per i documenti FrameMaker in AEM Guides.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: 3a8cb163-94ac-48b1-ae6b-1309179f462a
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

Per l&#39;output PDF sono disponibili le seguenti opzioni:

>[!NOTE]
>
> Per aprire i predefiniti di output per PDF, fare clic su un file FrameMaker \(`.fm` o `.book`\), quindi su Predefiniti di output e infine sull&#39;opzione Output di PDF.

| Opzioni PDF | Descrizione |
|-----------|-----------|
| Tipo di output | Tipo di output che si desidera generare. Per generare l&#39;output di PDF, scegliere l&#39;opzione PDF. |
| Nome impostazione | Assegna un nome descrittivo alle impostazioni di output di PDF che stai creando. Ad esempio, puoi specificare *Output clienti interni* o *Output utenti finali*. |
| **Impostazioni processo** |
| Opzioni | Scegli il predefinito PDF da utilizzare per generare l’output PDF. |
| Genera PDF con tag | Selezionare questa opzione per generare PDF con tag che conterranno informazioni sul contenuto e sulla struttura del documento. Queste informazioni vengono utilizzate dai lettori su schermo. |
| Genera PDF per ogni file della libreria | Se si sta generando l&#39;output per un file registro, selezionare questa opzione per generare un PDF separato per ciascun file del registro. |
| Genera PDF solo per revisione | Seleziona questa opzione per generare PDF con la funzione di commento abilitata. |
| Creare una destinazione denominata per tutti gli elementi e i paragrafi | Seleziona questa opzione per creare destinazioni denominate in base a elementi e paragrafi. |
| **Impostazioni visualizzazione** |
| Apri documento sulla pagina | Specifica il numero di pagina da visualizzare all’apertura del PDF. |
| Livello di zoom iniziale | Scegliere il livello di zoom del documento. |
| Contrassegno di registrazione | Per stampare un documento con indicatori di ritaglio e indicatori di registrazione, scegliere un&#39;opzione dall&#39;elenco a discesa Indicatori di registrazione. |
| Larghezza e altezza pagina | Specifica la larghezza e l&#39;altezza della pagina. |
| Serie di pagine | Scegliere se pubblicare tutte le pagine del libro o un intervallo di pagine. Se si sceglie Intervallo, è necessario specificare l&#39;intervallo di pagine Da e A. |
| Converti CYMK in RGB | Selezionate questa opzione per convertire i colori CYMK in RGB nel PDF generato. |
| Genera segnalibri PDF | Creare un PDF accessibile contenente segnalibri. |
| Percorso di destinazione | Il percorso all’interno dell’archivio AEM in cui è memorizzato l’output PDF. |
| Esegui flusso di lavoro di post-generazione | Quando scegli questa opzione, viene visualizzato un nuovo elenco a discesa Flusso di lavoro di post-generazione contenente tutti i flussi di lavoro configurati in AEM. È necessario selezionare un flusso di lavoro da eseguire dopo il completamento del flusso di lavoro di generazione dell&#39;output. |

**Argomento padre:**&#x200B;[ Genera output di documenti FrameMaker](fm-output-generatation.md)
