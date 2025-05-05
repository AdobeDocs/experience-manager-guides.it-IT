---
title: Crea argomenti
description: Scopri come creare tipi di argomenti DITA utilizzando modelli personalizzati nell’editor web di AEM Guides.
feature: Authoring
role: User
hide: true
exl-id: 70ab9226-82d4-4e6a-aa0b-0e298f266c2a
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Crea argomenti {#id2056AL00O5Z}

AEM Guides consente di creare argomenti DITA di tipo topic, task, concept, reference, glossary, DITAVAL e altro ancora. Oltre a creare argomenti basati su modelli predefiniti, puoi anche definire modelli personalizzati. Questi modelli devono essere aggiunti al profilo della cartella per essere visualizzati nella blueprint di selezione dei modelli e nell’editor web.

La configurazione Global e Folder Profile (Profilo cartella) è disponibile solo per gli utenti amministratori a livello di cartella. Per informazioni dettagliate sulla configurazione dei profili globali e a livello di cartella, consulta *Configurare i modelli di authoring* in Installare e configurare Adobe Experience Manager Guides per la configurazione.

Per creare un argomento, effettua le seguenti operazioni:

1. Nell’interfaccia utente di Assets, individua il percorso in cui desideri creare l’argomento.

1. Per creare un nuovo argomento, fare clic su **Crea** \> **Argomento DITA**.

1. Nella pagina Blueprint selezionare il tipo di documento DITA che si desidera creare e fare clic su **Avanti**.

   ![](images/create_dita_topic.png){width="800" align="left"}

   Per impostazione predefinita, AEM Guides fornisce i modelli di argomenti DITA più utilizzati. Puoi configurare altri modelli di argomento in base ai requisiti organizzativi. Consulta *Configurare i modelli di authoring* in Installare e configurare Adobe Experience Manager Guides per la tua configurazione.

   >[!NOTE]
   >
   > Nella vista a elenco dell&#39;interfaccia utente di Assets, il tipo di argomento DITA viene visualizzato nella colonna Tipo come Argomento, Attività, Concetto, Riferimento, Glossentry o DITAVAL. La mappa DITA viene visualizzata come Mappa.

1. Nella pagina Proprietà specificare il documento **Titolo**.

1. \(Facoltativo\) Specificare il file **Name**.

   Se l’amministratore ha configurato il nome file automatico in base all’impostazione UUID, l’opzione per specificare il nome file non sarà visibile. Al file viene automaticamente assegnato un nome di file basato su UUID.

   Se l&#39;opzione di denominazione file è disponibile, anche il nome viene suggerito automaticamente in base al **Titolo** del documento. Se si desidera specificare manualmente il nome del documento, verificare che il **Nome** non contenga spazi, apostrofi o parentesi graffe e termini con .xml o .dita. Per impostazione predefinita, AEM Guides sostituisce tutti i caratteri speciali con trattini. Per informazioni sulle procedure consigliate per la denominazione dei file DITA, vedere la sezione Nomi di file nella guida alle best practice.

1. Fai clic su **Crea**. Viene visualizzato il messaggio Topic Created (Creazione argomento).

   È possibile scegliere di aprire l&#39;argomento per la modifica nell&#39;editor Web o salvare il file dell&#39;argomento nel repository di AEM.

   A ogni nuovo argomento creato dall&#39;interfaccia utente di Assets **Crea** \> **Argomento DITA** o dall&#39;editor Web viene assegnato un ID argomento univoco. Il valore di questo ID è il nome del file stesso. Inoltre, un nuovo documento viene salvato come ultima copia di lavoro dell’argomento in DAM. Fino a quando non si salva una revisione di un argomento appena creato, nella Cronologia versioni non verrà visualizzato alcun numero di versione. Se si apre l&#39;argomento per la modifica, le informazioni sulla versione vengono visualizzate nell&#39;angolo superiore destro della scheda del file di argomento:

   ![](images/topic-version-none_cs.png){width="550" align="left"}

   Le informazioni sulla versione per un argomento appena creato vengono visualizzate come *none*. Quando salvi una nuova versione, ad essa viene assegnato il numero di versione 1.0. Per ulteriori informazioni sul salvataggio di una nuova versione, vedere [Salva come nuova versione](web-editor-features.md#save-as-new-version-id209ME400GXA).


>[!NOTE]
>
> Se l&#39;amministratore ha configurato l&#39;editor Web per estrarre i file prima della modifica, non sarà possibile modificare un file finché non lo si estrae. Analogamente, se configurata, verrà richiesto di archiviare tutti i file estratti prima di chiuderli.

>[!IMPORTANT]
>
> Dopo aver creato l&#39;argomento DITA, salvare le modifiche apportate alla copia di lavoro e creare una nuova versione una volta completati gli aggiornamenti all&#39;argomento.

**Argomento padre:**&#x200B;[ Crea e visualizza in anteprima argomenti](create-preview-topics.md)
